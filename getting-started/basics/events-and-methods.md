---
title: Call Widget Methods and Bind to Widget Events
page_title: Call widget methods and bind to widget events
description: Learn how to obtain a reference to an initialized Kendo UI widget instance and call its methods and events
position: 3
---

In addition to the initialization configuration options, each Kendo UI widget instance features **methods** and **events**, which may be used to query or modify its state during run time. In order to use them, you should obtain a reference to the widget instance first.

## Obtain a Reference to the Kendo UI widget Instance Using jQuery

To get a reference to a widget instance, use the [jQuery data](http://api.jquery.com/data/) method and pass the plugin name as a *string*.


### Obtain a Reference to the Kendo UI AutoComplete Widget Instance

        <p>Animal: <input id="animal" /></p>

        <script>
            $(function() {
              $("#animal").kendoAutoComplete({ dataSource: [ "Ant", "Antilope", "Badger", "Beaver", "Bird" ] });

              var autoComplete = $("#animal").data("kendoAutoComplete");
              console.log(autoComplete);
            });
        </script>

> The jQuery convention of returning the selected DOM element applies the widget initialization plugin methods too. This means that the plugin method returns **not the widget instance** but **the jQuery selector it was used on**.

Once the widget instance is available, you may call its methods using the standard JavaScript method syntax:

        <p>Animal: <input id="animal" /></p>

        <script>
            $(function() {
              $("#animal").kendoAutoComplete({ dataSource: [ "Ant", "Antilope", "Badger", "Beaver", "Bird" ] });

              var autoComplete = $("#animal").data("kendoAutoComplete");

              // Focus the widget
              autoComplete.focus();
            });
        </script>

> A complete list and examples of the widget methods and method parameters is available in the [API reference](/api/introduction) section.

## Bind to The Widget Events

Each widget exposes different events, depending on its features - for example, the `AutoComplete` widget triggers `change`, `close`, `dataBound`.
You may pass event handlers when you instantiate the widget, or after that, using the widget `bind` method.

    <p>Animal: <input id="animal" /></p>

    <script>
        $(function() {
          $("#animal").kendoAutoComplete({
              dataSource: [ "Ant", "Antilope", "Badger", "Beaver", "Bird" ],
              change: function(e) { console.log("event handler in constructor")
          });

          var autoComplete = $("#animal").data("kendoAutoComplete");

          // Bind to the widget change event
          autoComplete.bind('change', function(e) {
             console.log(e);
          });
        });
    </script>

The widget passes one argument to the event handler, the so called **event object**. Usually, it has one or more fields with information specific to
the event.  All event objects have the `sender` field, a reference to the widget instance which triggered it.

> A full list and examples of the widget events and the fields available in the event objects is available in the [API reference](/api/introduction)
> section.

In addition to the `bind` method, the widget instance also features `one` method. It works in the same way, but the passed event handler gets executed
**only once**.

### Prevent the Effect of Certain Events

Certain widget events may be prevented by calling the `preventDefault` method of the **event object**.
The effect of the event prevention is specific for each event and is documented in the [API reference](/api/introduction).

    <p>Animal: <input id="animal" /></p>

    <script>
        $(function() {
          $("#animal").kendoAutoComplete({
              dataSource: [ "Ant", "Antilope", "Badger", "Beaver", "Bird" ]
          });

          var autoComplete = $("#animal").data("kendoAutoComplete");

          // prevent the autocomplete from opening the suggestions list
          autoComplete.bind('open', function(e) {
            e.preventDefault();
          });
        });
    </script>

### Unbind from a Widget Event

To unbind from a given event, you should keep a reference to the event handler function and invoke the `unbind` method with it.

    <p>Animal: <input id="animal" /></p>

    <button>Unbind event</button>

    <script>
        $(function() {
          var handler = function(e) { console.log(e); };
          $("#animal").kendoAutoComplete({ dataSource: [ "Ant", "Antilope", "Badger", "Beaver", "Bird" ] });

          var autoComplete = $("#animal").data("kendoAutoComplete");

          autoComplete.bind("open", handler);

          $("button").on("click", function() {
              autoComplete.unbind("open", handler);
          });
        });
    </script>

> Calling the `unbind` method without a second argument **unbinds all event handlers** from the event.
