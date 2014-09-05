---
title: Using Kendo with AngularJS
previous_url: /using-kendo-with-angularjs
position: 1
---

{% raw %}

# Using Kendo with AngularJS

Kendo UI can be used seamlessly with AngularJS.  The two frameworks have some overlapping features though; if you are using AngularJS then you probably want to use Angular's own routing mechanism and data binding.  Do not mix that with Kendo MVVM.

## Using Angular-Kendo bindings

The Angular bindings are now integrated into Kendo UI.  If you're using one of the bundles (such as `kendo.all.min.js`) then the required code is already there.  If you load individual Kendo UI files, you need to also load `kendo.angular.js` (or `kendo.angular.min.js`).  It must be loaded after `kendo.core`.

In order for the Angular bindings to be activated, you must load `angular.js` _before_ Kendo.

Therefore, load the scripts in this order:

    <script src="jquery.js"></script>
    <script src="angular.js"></script>
    <script src="kendo.all.js"></script>

Don't forget to load the Kendo UI stylesheets too.

Next, when creating your AngularJS application you must declare dependency on "kendo.directives":

    var app = angular.module("your-angular-app", [ "kendo.directives" ]);

### Creating widgets the Angular way

The directives kick in on attributes like `kendo-widget-name`.  For example to get a `DatePicker` widget, you'd write the following:

    <label>Birthday: <input kendo-date-picker /></label>

When AngularJS compiles the HTML, the Kendo UI directive will turn the `<input>` field into a nice date picker widget.

As a shortcut, you can discard the dashes after `kendo-`:

    <input kendo-numerictextbox />

### Widget options in HTML

You can specify any options supported by Kendo UI widgets in element attributes, by converting the option name from camelCase to dash-separated-words, and prefixing it with `k-`.  For example:

    <input kendo-numerictextbox
           k-min="1" k-max="10"
           k-up-arrow-text="'Increment'"
           k-down-arrow-text="'Decrement'" />

Notice an important detail in the example above: the strings `'Increment'` and `'Decrement'` are quoted inside the attribute values.  Without the single inside they will be interpreted as variable names and Angular-Kendo will look for `$scope.Increment` and `$scope.Decrement` variables.  Because omitting the quotes is a common error, Angular-Kendo will emit a warning in the JS console when such variables are not found.

For instance, to declare the texts in the controller you could say:

    <input kendo-numerictextbox
           k-up-arrow-text="textUp"
           k-down-arrow-text="textDown" />

and have the following in your controller:

    $scope.textUp = "Increment";
    $scope.textDown = "Decrement";

You can use declarative attributes for array and object configuration options, too.

    <textarea kendo-editor
              k-tools="[
                  'bold',
                  'italic',
                  'undeline',
                  {
                    name: 'foreColor',
                    palette: [ '#f00', '#0f0', '#00f' ]
                  }
              ]"></textarea>

### Widget configuration in controller

If you'd like to store all widget configuration in the controller, you can use the special `k-options` attribute:

    // in controller:
    $scope.monthPickerConfig = {
      start  : "year",
      depth  : "year",
      format : "MMMM yyyy"
    };

    <!-- in HTML: -->
    <input kendo-date-picker k-options="monthPickerConfig" />

### Scope bindings (`ng-model`)

For all widgets which provide a `value()` method you can use the standard `ng-model` directive to bind their value into the AngularJS scope.  Example:

    <label>Birthday: <input kendo-date-picker ng-model="birthday" /></label>
    <p>
      Your selection: {{ birthday }}
    </p>

The input field is now bound to the scope variable.  When you select a date, the `birthday` variable will be set to the input field's value (as a string).

### Scope bindings (`k-ng-model`)

If your element is a form field like `<input>` or `<textarea>` (which has a text value), the `ng-model` will bind the field contents, which is what most AngularJS users would expect.  So for the DatePicker example above, you would get a string date, instead of a JavaScript Date object, in the scope.

If you need to get the actual `widget.value()` you can use `k-ng-model`:

    <input kendo-date-picker k-ng-model="birthday" />

The directive will update the `birthday` variable with the selected `Date` object whenever the `change` event occurs on the widget.

### Event handlers

If you store the whole configuration in the controller, then adding an event handler is done the same you would do with plain Kendo:

    // in controller:
    $scope.monthPickerConfig = {
      start  : "year",
      depth  : "year",
      format : "MMMM yyyy",
      change : function(e) { // handler for "change" event
        var datePicker = e.sender;
        console.log(datePicker.value());
        $scope.selected = true;
        $scope.$digest();
      }
    };

    <!-- in HTML: -->
    <input kendo-date-picker k-options="monthPickerConfig" />
    <p ng-show="selected">A month was picked</p>

The sample above includes a paragraph that's using Angular's `ng-show` directive and will be displayed only after a month was picked.  Notice in the event handler that we had to call `$scope.$digest()` in order for this trick to work.

It is possible to specify event handlers using attributes as well. They require the `k-on-` prefix:

    // in controller:
    $scope.onDateSelected = function(e) {
      var datePicker = e.sender;
      console.log(datePicker.value());
      $scope.selected = true;
    };

    <!-- in HTML: -->
    <input kendo-date-picker k-on-change="onDateSelected(kendoEvent)" />
    <p ng-show="selected">A month was picked</p>

Notice that the `kendoEvent` variable will be defined in scope and we must pass it to the event handler.  If we are using the `k-on-` attributes, there is no need to call `$digest()` on the scope (it's taken care of by our bindings).

#### Special `"change"` event on certain widgets

The Grid, TreeView and ListView widgets will evaluate handlers defined with `k-on-change` in a scope containing additional information about the selected item(s), as local variables.  The following locals are defined:

- `selected` (jQuery object) -- the selected elements

- `data` (array or data item) -- the selected data model(s).  It will be an array when multiple selection is enabled, or a single item otherwise.

- `dataItem` -- when multiple selection is not enabled, this is provided for consistency and will be the same item as `data`.

- `columns` -- for the Grid, when cell selection is enabled, it will be an array with zero-based column indexes for the selected columns. Also in this case the `selected` object will contain the respective `<td>` elements, instead of `<tr>`-s.

The `kendoEvent` is available as well.

### Updating widgets when options change

You can use the special `k-rebind` attribute to create a widget which automatically updates when some scope variable changes:

    // in controller:
    $scope.orientation = "horizontal";

    <!-- in HTML: -->
    <ul kendo-menu k-orientation="orientation" k-rebind="orientation">
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ul>

    <select kendo-drop-down-list k-ng-model="orientation">
      <option>horizontal</option>
      <option>vertical</option>
    </select>

To watch multiple options for change, just use `k-options` and pass the same variable to `k-rebind`:

    <ul kendo-menu k-options="menuOptions" k-rebind="menuOptions"> ... </ul>

### Delaying widget initialization

It's sometimes useful to postpone creating a widget until after some asynchronously-loaded data is available.  For example you would need this to initialize a Grid widget when you load the column definitions from server (as the Grid does not support re-defining the columns after the widget is instantiated).

You can use the special `k-ng-delay` attribute for this.  Example:

    // in controller
    $http({ method: "GET", url: "customers.json" })
      .success(function(result){
        var dataSource = new kendo.data.DataSource({
          data: result.data
        });
        $scope.gridOptions = {
          dataSource: data,
          columns: result.columns,
          ...
        };
      });

    <!-- in HTML: -->
    <div kendo-grid k-options="gridOptions" k-ng-delay="gridOptions"></div>

The grid will be created only when the `gridOptions` variable becomes available.

### Getting widget references

Sometimes you might need a reference to the widgets in order to call methods on it from your controller.  To get one, just assign a name to the `kendo-widget-name` attribute, for example:

    // in controller:
    $scope.onChange = function() {
      // $scope.datePicker will be initialized by the directive
      alert($scope.datePicker.value());
    };

    <!-- in HTML: -->
    <input kendo-date-picker="datePicker" k-on-change="onChange()" />

### Global Angular events emitted by the Kendo bindings

#### `kendoWidgetCreated`

This event is emitted when a Kendo widget has been created.  You can hook on it from your Angular controller like this:

    // in controller
    $scope.$on("kendoWidgetCreated", function(ev, widget){
      // in widget you have a reference to the event
      if (widget === $scope.myGrid) {
        // the Grid defined below has just been created
      }
    });

    <!-- in HTML: -->
    <div kendo-grid="myGrid" ...></div>

#### `kendoRendered`

This event is emitted when all Kendo widgets defined in the page have been created.  It's sometimes useful to be able to intercept this event, since widgets are created asynchronously.  For example you can initially display a "Loading..." overlay in the page, and hide it from a handler on this event.

{% endraw %}
