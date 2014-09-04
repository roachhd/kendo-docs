---
title: Overview
page_title: Overview of DropDownList widget - primary uses
description: Quickly explore all features of Kendo UI DropDown control and how to use them.
position: 1
---

# DropDownList Overview

A **DropDownList** displays a list of values and allows the selection of a single value from the
list.Custom values may not be entered via keyboard input.If you wish permit keyboard input - that is, custom
values are allowed - use the **ComboBox**.


## Getting Started

There are two ways to create a **DropDownList**:

1.  From a &lt;select&gt; element with HTML to define the list items
2.  From an &lt;input&gt; element with databinding to define the listitems



A **DropDownList** will look and operate consistently regardless of the way in which it was
created.

### Creating a DropDownList from existing &lt;input&gt; element

    <input id="dropDownList" />

Initialization of a **DropDownList** should occur after the DOM is fully loaded. It is recommended
that initialization the **DropDownList** occur within a handler is provided to
$(document).ready().

> Widget copies any styles and CSS classes from the input element to the wrapper element.

### Initialize a DropDownList using a selector within $(document).ready()

    $(document).ready(function() {
        $("#dropDownList").kendoDropDownList({
            dataTextField: "text",
            dataValueField: "value",
            dataSource: [
                { text: "Item1", value: "1" },
                { text: "Item2", value: "2" }
            ]
        });
    });

### Create a DropDownList from existing &lt;select&gt; element with a pre-defined structure

    <select id="dropDownList">
        <option>Item 1</option>
        <option>Item 2</option>
        <option>Item 3</option>
    </select>

    <script>
        $(document).ready(function(){
            $("#dropDownList").kendoDropDownList();
        });
    </script>

## Binding to Local or Remote Data

The **DropDownList** can be bound to both local arrays and remote data via the
**DataSource** component; an abstraction for local and
remote data. Local arrays are appropriate for limited value options, while remote data binding is better for
larger data sets. With remote data-binding, items will be loaded on-demand; when they are displayed.
The **DataSource**
component can be used to serve data from a variety of data services,
such as
[XML](http://en.wikipedia.org/wiki/XML),
[JSON](http://en.wikipedia.org/wiki/JSON), and
[JSONP](http://en.wikipedia.org/wiki/JSONP).

### Binding to a remote OData service

    $(document).ready(function() {
        $("#titles").kendoDropDownList({
            index: 0,
            dataTextField: "ContactName",
            dataValueField: "CustomerID",
            dataSource: {
                type: "odata", // specifies data protocol
                transport: {
                    read: "http://demos.telerik.com/kendo-ui/service/Northwind.svc/Customers"
                }
            }
        });
    });

## Customizing Templates

The **DropDownList** uses Kendo UI templates to enable control over how item, popup header and selected value is rendered. For a
detailed description of the capabilities and syntax of the Kendo UI templates, please refer to the
[documentation](/framework/templates/overview).

### Item template customization

The **DropDownList** uses Kendo UI templates to control how *drop-down items* are rendered.

#### Example - define an item template

    <input id="dropdownlist" />
    <!-- Template -->
    <script id="scriptTemplate" type="text/x-kendo-template">
        ContactName: #:data.ContactName#, CustomerID: #:data.CustomerID#
    </script>

    <!-- DropDownList initialization -->
    <script>
        $(document).ready(function() {
            $("#dropdownlist").kendoDropDownList({
                template: $("#scriptTemplate").html(),
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

### Value template customization

The **DropDownList** uses Kendo UI templates to control how the selected value is rendered.

> Note that value template should be consisted only of **inline** HTML elements.

#### Example - define a value template

    <input id="dropdownlist" />
    <!-- Template -->
    <script id="valueTemplate" type="text/x-kendo-template">
        ContactName: #:data.ContactName#
    </script>

    <!-- DropDownList initialization -->
    <script>
        $(document).ready(function() {
            $("#dropdownlist").kendoDropDownList({
                valueTemplate: $("#valueTemplate").html(),
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

The **DropDownList** gives the ability to render a popup header.

#### Example - define a header template

    <input id="dropdownlist" />
    <!-- Template -->
    <script id="headerTemplate" type="text/x-kendo-template">
        <strong>Header</strong>
    </script>

    <!-- DropDownList initialization -->
    <script>
        $(document).ready(function() {
            $("#dropdownlist").kendoDropDownList({
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

Width of widget's drop-down list can be changed via jQuery width method.

### Example

    var dropdownlist = $("#dropdown").data("kendoDropDownList");

    // set width of the drop-down list
    dropdownlist.list.width(400);

## Accessing an Existing DropDownList


You can reference an existing **DropDownList** instance via
[jQuery.data()](http://api.jquery.com/jQuery.data/). Once a reference has been established, you can
use the API to control its behavior.

### Accessing an existing DropDownList instance

    var dropDownList = $("#dropDownList").data("kendoDropDownList");
