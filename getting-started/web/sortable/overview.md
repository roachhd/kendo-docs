---
title: Overview
page_title: Sortable widget - getting started help topic
description: How to use the Sortable widget
position: 0
---

# Sortable Overview

The Sortable widget makes a group of DOM elements sortable by dragging and dropping with a mouse or a finger.

## Initialization and basic usage

The Sortable widget is initialized for an existing HTML mark-up and provides ability for reordering the sortable HTML items in the DOM tree.

### Initialize a Sortable widget using jQuery plug-in syntax

    <ul id="sortable">
        <li>Item1</li>
        <li>Item2</li>
        <li>Item3</li>
    </ul>

    <script>
        $("#sortable").kendoSortable();
    </script>

You may reference an existing Sortable widget instance via [jQuery.data()](http://api.jquery.com/jQuery.data/).

### Accessing an existing Sortable widget instance

    var sortable = $("#sortable").data("kendoSortable");

## Key features

### Placeholder

The Placeholder is the element which indicates where the dragged item will be placed after drop action. By default the placeholder is a clone of the dragged element with removed `id` attribute and visibility set to hidden. Developer may change the default placeholder though the `placeholder` configuration option.

> **Important** Placeholder element is appended to the Sortable container DOM element. This is why jQuery's `index` method may return unexpected results. When the developer wants to find the index of a given item inside the Sortable collection it is recommended to use widget's [`indexOf`](../../../api/web/sortable#methods-indexof) method.

#### Set the placeholder to a function

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>

    <script>
        $("#sortable").kendoSortable({
            placeholder: function(element) {
                return element.clone().css({
                    "opacity": 0.3,
                    "border": "1px dashed #000000"
                });
            }
        });
    </script>

#### Set the placeholder to a string

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>

    <script>
        $("#sortable").kendoSortable({ 
            placeholder: "<li>Drop Here!</li>"
        });
    </script>

### Hint

The Hint is the element which represents the dragged item. By default the hint is a clone of the dragged item. Developer may change the default hint though the `hint` configuration option.

> **Important** Hint element is appended to the `<body>` tag. This might cause styling issues if the CSS rules are applied only to the Sortable's container.

#### Set the hint to a function

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>

    <script>
        $("#sortable").kendoSortable({ 
            hint: function(element) {
                return $("<span></span>")
                        .text(element.text())
                        .css("color", "#FF0000");
            }
        });
    </script>

#### Set the hint to a string

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>

    <script>
        $("#sortable").kendoSortable({ 
            hint: "<span>hint!</span>"
        });
    </script>

#### Disabling the hint

The Sortable widget can operate without hint. To disable the hint you may set it to an empty function ([jQuery.noop](http://api.jquery.com/jQuery.noop/)).

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>

    <script>
        $("#sortable").kendoSortable({ 
            hint: $.noop
        });
    </script>

### Filter/Disable items

The **filter** option specifies which items inside the Sortable's container will be sortable. Items that does not match the filter selector will not be draggable nor reordered when the user drags a sortable item over them.

The **disabled** option specifies which items inside the Sortable's container cannot be dragged. Items that match the disabled selector cannot be dragged but will reorder when the user drags a sortable item over them.

#### Disable all items at runtime

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>

    <button id="btnDisable">Disable</button>

    <script>
        $("#sortable").kendoSortable({ 
            disabled: ".disabled"
        });

        $("#btnDisable").click(function() {
            $("#sortable").children().addClass("disabled");
        });
    </script>

### Ignore elements

A common problem that developers encounter is that input elements inside the Sortable container cannot be focused with the mouse. The solution is to use the `ignore` option.

> **Important** The `ignore` option is available in Q1 2014 SP1 (2014.1.416)! This feature is **not** included in Q1 2014 (v2014.1.318).

#### Example - Sortable widget with focus-able input elements

    <ul id="sortable">
        <li>ItemA1 <input type="text" /></li>
        <li>ItemA2 <input type="text" /></li>
        <li>ItemA3 <input type="text" /></li>
    </ul>

    <script>
        $("#sortable").kendoSortable({ 
            ignore: "input"
        });
    </script>

### Cursor

The `cursor` configuration options is used to specify what cursor will be shown while the user drags a sortable item. There are a variety of cursor types you can choose from that are built into the browser or operating system of the user's computer (you can see a list of them at [quirksmode.org](http://quirksmode.org/css/user-interface/cursor.html). Here's an example of how to change the cursor:

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>

    <script>
        $("#sortable").kendoSortable({
            cursor: "move"
        });
    </script>

> Cursor option changes the cursor style only while the item is being dragged. If the developer wants to change the on-hover cursor he/she should use CSS.

#### Example - grab/grabbing cursor

    <ul id="sortable">
        <li>ItemA1</li>
        <li>ItemA2</li>
        <li>ItemA3</li>
    </ul>

    <script>
        $("#sortable").kendoSortable({
            cursor: "url('http://demos.telerik.com/kendo-ui//content/web/sortable/grabbing.cur'), default"
        });
    </script>

    <style>
        #sortable li {
            cursor: url('http://demos.telerik.com/kendo-ui//content/web/sortable/grabbing.cur'), default;
        }
    </style>

### Movement by axis

By default the widget uses mouse cursor to determine the drop target before/after which sorted item should be placed. This means that if the mouse cursor is not over the target sortable element the placeholder will not be re-positioned.

If the `axis` is set to "x" or "y" however, the widget will start operating in movement by axis mode - the widget will use x/y position of the mouse cursor to determine the current target. To see this feature in action please check [constraints demo page](http://demos.telerik.com/kendo-ui/web/sortable/constraints.html).

## Common scenarios

### Persists the order

The Sortable widget does not offer functionality that will automatically save or send to the server the current items order.
You may use the `change` event to detect when changes in the order occur and save them either in the local storage of the browser or submit them to the server via [jQuery.ajax](http://api.jquery.com/jQuery.ajax/) request.

In order to restore the Sortable layout you should render the DOM elements in their last order. Check the example below:

#### Example - persist items order in the local storage

    <div id="sortable"></div>

    <button id="reset">Reset</button>

    <script id="tmp" type="text/x-kendo-template">
        <div class="sortable">Item #:data#</div>
    </script>

    <script>
        var initialData = [ 1, 2, 3, 4, 5, 6, 7 ], //initial items order (used if there is no saved data
            localStorageSupport = (('localStorage' in window && window['localStorage'] !== null)),
            data,
            html;

        if (localStorageSupport) {
            //retrieve local storage data if such is available, else use the default order
            data = JSON.parse(localStorage.getItem("sortableData")) || initialData;
        } else {
            alert("your browser does not support local storage");
            data = initialData;
        }

        html = kendo.render(kendo.template($("#tmp").html()), data); //render the HTML with the data
        $("#sortable").html(html); //append the HTML to the Sortable container

        $("#sortable").kendoSortable({ //initialize the sortable widget
            filter: ".sortable",
            change: function(e) {
                var item = data.splice(e.oldIndex, 1)[0]; //remove the item that has changed its order
                data.splice(e.newIndex, 0, item); //add the item back using the newIndex

                localStorage.setItem("sortableData", kendo.stringify(data)); //set the updated data in the local storage
            }
        });

        $("#reset").click(function() {
            localStorage.clear(); //clear the local storage
            alert("Local storage is cleared. Please reload the page!");
        });
    </script>

    <style>
        #sortable {
            -webkit-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            user-select: none;

            width: 300px;
        }

        .sortable {
            padding: 10px 0;
            margin: 1px 0;
            width: 358px;
            text-align: center;
            color: #ffffff;
            background-color: #51A0ED;
        }
    </style>

