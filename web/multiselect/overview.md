---
title: Overview
page_title: Overview of jQuery UI multiselect | Kendo UI Documentation
description: Create MultiSelect UI widget, use Kendo UI templates, instructions how to use MultiSelect.
---

# MultiSelect Overview

The **MultiSelect** displays a list of values and allows the selection of multiple values from this
list.

The **MultiSelect** represents a richer version of a `<select>` element, providing support for
local and remote data binding, item and tag templates, and configurable options for controlling the list behavior.


## Getting Started

There are two ways to create a **MultiSelect** from a `<select>` element:

1.  Using its `<option>` list as a list of items
2.  With databinding to define the list items


A **MultiSelect** will look and operate consistently regardless of the way in which it was created.

### Creating a MultiSelect from an existing &lt;select&gt; element with defined data items

    <select id="multiselect"></select>

Initialization of a **MultiSelect** should occur after the DOM is fully loaded. It is recommended
that initialization the **MultiSelect** occur within a handler is provided to
$(document).ready().

> Widget copies any styles and CSS classes from the input element to the wrapper element and visible input.

### Initialize a MultiSelect using a selector within $(document).ready()

    $(document).ready(function(){
        $("#multiselect").kendoMultiSelect({
            dataTextField: "text",
            dataValueField: "value",
            dataSource: [
                { text: "Item1", value: "1" },
                { text: "Item2", value: "2" }
            ]
        });
    });

### Creating a MultiSelect from existing `<select>` element with a pre-defined structure

    <select id="multiselect" multiple>
        <option>Item 1</option>
        <option>Item 2</option>
        <option>Item 3</option>
    </select>

    <script>
        $(document).ready(function(){
            $("#multiselect").kendoMultiSelect();
        });
    </script>

## Binding to Local or Remote Data

The **MultiSelect** can be bound to both local arrays and remote data via the
**DataSource** component; an abstraction for local and
remote data. Local arrays are appropriate for limited value options, while remote data binding is better for
larger data sets. With remote data-binding, items will be loaded on-demand; when they are displayed.
The **DataSource**
component can be used to serve data from a variety of data services,
such as
[XML](http://en.wikipedia.org/wiki/XML),
[JSON](http://en.wikipedia.org/wiki/JSON), and
[JSONP](http://en.wikipedia.org/wiki/JSONP).

### Binding to a remote service

    <select id="multiselect" multiple></select>

    <script>
    $(document).ready(function() {
        $("#multiselect").kendoMultiSelect({
            dataTextField: "ProductName",
            dataValueField: "ProductID",
            dataSource: {
                transport: {
                    read: {
                        dataType: "jsonp",
                        url: "http://demos.telerik.com/kendo-ui/service/Products"
                    }
                }
            }
        });
    });
    </script>

## Customizing Templates

The **MultiSelect** uses Kendo UI templates to enable you to control how item, tag or header is rendered. For a
detailed description of the capabilities and syntax of the Kendo UI templates, please refer to the
[documentation](/framework/templates/overview).

### Item template customization

The **MultiSelect** uses Kendo UI templates to control how *drop-down items* are rendered.

#### Example - define an item template

    <select id="multiselect" multiple></select>
    <!-- Item Template -->
    <script id="itemTemplate" type="text/x-kendo-template">
        ContactName: #:data.ContactName#, CustomerID: #:data.CustomerID#
    </script>

    <!-- MultiSelect initialization -->
    <script>
        $(document).ready(function() {
            $("#multiselect").kendoMultiSelect({
                itemTemplate: $("#itemTemplate").html(),
                dataTextField: "ContactName",
                dataValueField: "CustomerID",
                dataSource: {
                    transport: {
                        read: {
                            dataType: "jsonp",
                            url: "http://demos.telerik.com/kendo-ui/service/Customers"
                        }
                    }
                }
            });
        });
    </script>

### Tag template customization

The **MultiSelect** uses Kendo UI templates to control how selected tag is rendered.

#### Example - define a tag template

    <select id="multiselect" multiple></select>
    <!-- Item Template -->
    <script id="tagTemplate" type="text/x-kendo-template">
        ContactName: #:data.ContactName#
    </script>

    <!-- MultiSelect initialization -->
    <script>
        $(document).ready(function() {
            $("#multiselect").kendoMultiSelect({
                tagTemplate: $("#tagTemplate").html(),
                dataTextField: "ContactName",
                dataValueField: "CustomerID",
                dataSource: {
                    transport: {
                        read: {
                            dataType: "jsonp",
                            url: "http://demos.telerik.com/kendo-ui/service/Customers"
                        }
                    }
                }
            });
        });
    </script>

### Header template customization

The **MultiSelect** gives the ability to render a popup header.

#### Example - define a header template

    <input id="multiselect" />
    <!-- Template -->
    <script id="headerTemplate" type="text/x-kendo-template">
        <strong>Header</strong>
    </script>

    <!-- MultiSelect initialization -->
    <script>
        $(document).ready(function() {
            $("#multiselect").kendoMultiSelect({
                headerTemplate: $("#headerTemplate").html(),
                dataTextField: "ContactName",
                dataValueField: "CustomerID",
                dataSource: {
                    transport: {
                        read: {
                            dataType: "jsonp",
                            url: "http://demos.telerik.com/kendo-ui/service/Customers"
                        }
                    }
                }
            });
        });
    </script>

## Customizing the width of the drop-down list

Width of MultiSelect' drop-down list can be changed via jQuery width method.

### Example

    var multiselect = $("#multiselect").data("kendoMultiSelect");

    // set width of the drop-down list
    multiselect.list.width(400);

## Pre-select values on initial loading

When deffered binding (autoBind: false) is used you will need to specify a list of data items instead of just list of strings.
This functionality is supported in Q1 SP1 2013 release and later versions of Kendo UI.

    <!-- MultiSelect initialization -->
    <script>
        $(document).ready(function() {
            $("#multiselect").kendoMultiSelect({
                autoBind: false,
                dataTextField: "Name",
                dataValueField: "Id",
                dataSource: {
                    type: "odata",
                    serverFiltering: true,
                    transport: {
                        read: {
                            url: "http://demos.telerik.com/kendo-ui/service/Northwind.svc/Products",
                        }
                    }
                },
                value: [
                    { ProductName: "Chang", ProductID: 2 },
                    { ProductName: "Uncle Bob's Organic Dried Pears", ProductID: 7 }
                ]
            });
        });
    </script>

## Make the MultiSelect scrollable

By design, the MultiSelect expands vertically when adding more items that do not fit in the existing free space. Limited expansion and scrolling can be achieved with some CSS and Javascript code.

Add a custom CSS class to the MultiSelect wrapper element after initialization.

    $(document).ready(function() {
        $("#multiselect").kendoMultiSelect({
            select: onSelect
        });

        $("#multiselect").data("kendoMultiSelect").wrapper.addClass("myClass");
    });

Use the following CSS rule to limit the MultiSelect expansion (with a `min-height` style) or set a fixed height (with a `height` style).

    .myClass .k-multiselect-wrap
    {
        overflow: auto;

        max-height: 100px;
        /* or */
        /* height: 100px; */
    }

You may want to scroll the widget automatically to the bottom when new items are added, so that they are visible to the user. Use the `select` event handler.

    function onSelect(e) {
        setTimeout(function() {
            var container = e.sender.wrapper.children(".k-multiselect-wrap");
            container.scrollTop(container[0].scrollHeight);
        });
    }

## Support for label element

Because of the complex rendering of the widget, focusing of the widget using label element will require additional implementation.
Check [this jsFiddle demo](http://jsfiddle.net/krustev/6mHKF/), which shows how to achieve this.

## Accessing an Existing MultiSelect

You can reference an existing **MultiSelect** instance via
[jQuery.data()](http://api.jquery.com/jQuery.data/). Objectnce a reference has been established, you
can use the API to control its behavior.

### Accessing an existing MultiSelect instance

    var multiselect = $("#multiselect").data("kendoMultiSelect");
