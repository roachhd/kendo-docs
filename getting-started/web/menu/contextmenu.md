---
title: Context Menu
page_title: Overview of Kendo UI ContextMenu widget
description: Steps that help you initialize the ContextMenu widget using JSON data object.
---

# ContextMenu Overview

The **ContextMenu** displays hierarchical data as a multi-level menu in a popup. It provides rich styling for unordered lists
of items, and can be used for both navigation and executing JavaScript commands. Items can be defined and
initialized from HTML, or the API can be used to add and remove items. Also a ContextMenu target can be specified, a filter
for multiple targets and an event to which the ContextMenu will listen in order to pop up.

## Getting Started

### Create a HTML hierarchical list of items

    <ul id="context-menu">
        <li>Normal Item
            <ul>
                <li><span class="k-sprite icon-class"></span>Item with a Sprite</li>
                <li><img src="Icons/contacts.gif" />Item with an Icon</li>
            </ul>
        </li>
        <li><a href="http://www.google.com">Navigation Item</a></li>
        <li class="k-state-active">Active Item</li>
        <li>Template Item
            <div class="k-group k-content">
                Test button - <a class="k-button">Button</a>
            </div>
        </li>
    </ul>

Initialization of a **ContextMenu** should occur after the DOM is fully loaded. It is recommended that
initialization the **ContextMenu** occur within a handler provided to $(document).ready().

### Initialize a ContextMenu using a selector within $(document).ready()

    <ul id="context-menu">
        <li>Item 1</li>
        <li>Item 2</li>
    </ul>
    <script>
        $(document).ready(function() {
            $("#context-menu").kendoContextMenu();
        });
    </script>

### Initialize the ContextMenu using JSON data object

    <ul id="context-menu"></ul>
    <script>
        $(document).ready(function() {
            $("#context-menu").kendoContextMenu({
                dataSource:
                    [{
                        text: "Item 1",
                        cssClass: "myClass",                         // Add custom CSS class to the item, optional, added 2012 Q3 SP1.
                        url: "http://www.telerik.com"                // Link URL if navigation is needed, optional.
                    },
                    {
                        text: "<b>Item 2</b>",
                        encoded: false,                              // Allows use of HTML for item text
                        content: "text"                              // content within an item
                    },
                    {
                        text: "Item 3",
                        imageUrl: "http://www.telerik.com/test.jpg", // Item image URL, optional.
                        items: [{                                    // Sub item collection
                             text: "Sub Item 1"
                        },
                        {
                             text: "Sub Item 2"
                        }]
                    },
                    {
                        text: "Item 4",
                        spriteCssClass: "imageClass3"                // Item image sprite CSS class, optional.
                    }]
            })
        });
    </script>

## Customizing ContextMenu Animations

By default, the **ContextMenu** uses a slide animation to expand and reveal sub-items as the mouse hovers. Animations can be easily
customized using configuration properties, changing the animation style and delay. ContextMenu can be also configured to use a different
open event than the default "contextmenu" (right click).

### Changing ContextMenu animation and open event

    <ul id="context-menu">
        <li>Item 1</li>
        <li>Item 2</li>
    </ul>
    <script>
        $("#context-menu").kendoContextMenu({
            animation: {
                open: { effects: "fadeIn" },
                duration: 500
            },
            showOn: "click"
        });
    </script>

## Dynamically configuring ContextMenu items

The **ContextMenu** API provides several methods for dynamically adding
or removing Items. To add items, provide the new item as a JSON
object along with a reference item that will be used to determine the
placement in the hierarchy.

A reference item is simply a target ContextMenu Item HTML element that
already exists in the ContextMenu. Any valid jQuery selector can be used to
obtain a reference to the target item. Removing an item only requires a reference to the target element that
should be removed.

### Dynamically add a new root ContextMenu item

    <ul id="context-menu">
        <li>Item 1</li>
        <li>Item 2</li>
    </ul>
    <script>
        var contextMenu = $("#context-menu").kendoContextMenu().data("kendoContextMenu");
        contextMenu.insertAfter(
            { text: "New ContextMenu Item" },
            contextMenu.element.children("li:last")
        );
    </script>

## Accessing an Existing ContextMenu

You can reference an existing **ContextMenu** instance via
[jQuery.data()](http://api.jquery.com/jQuery.data/).
Once a reference has been established, you can use the API to control
its behavior.

### Accessing an existing ContextMenu instance

    <ul id="context-menu" data-role="contextmenu" data-target="body">
        <li>Item 1</li>
        <li>Item 2</li>
    </ul>
    <script>
        kendo.bind(document.body);
    </script>

    ...

    <script>
        var contextMenu = $("#context-menu").data("kendoContextMenu");
    </script>

