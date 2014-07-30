---
title: Overview
page_title: Overview of DOM element Draggable functionality | Kendo UI Docs
description: Lear more for the draggable functionality on any DOM element and how to enable and initialize it. We guide you how to enable DOM to be a target for draggable elements.
---

# Drag'n'Drop Overview

There are two separate Kendo UI widgets that allows the developer to implement Drag'n'Drop scenarios - `kendoDraggable` and `kendoDropTarget`.
First one enables the draggable functionality, while the second one creates the drop-able zones.

## Draggable

Draggable widget allows any DOM elements to be moved using the mouse.

### Initialization

    <div id="draggable" style="width: 200px; height: 200px; background-color: #0ff;">drag me</div>
    <script>
        var draggable = $("#draggable").kendoDraggable({
          hint: function(element) {
            return element.clone();
          }
        });
    </script>

> If a `hint` is not specified the user will not have any visual indication that the item is being dragged.

### Creating a list/table with draggable items

Draggable widget itself does not support binding to DataSource which is why the developer should bind the DataSource to ListView or Grid and initialize Draggable for it. 
Usually the data is retrieved from the remote server **asynchronously** which means that at the time when Draggable is initialized the items that should be draggable are not yet rendered.
In order this to be resolved, the developer should initialize Draggable for the parent container and use `filter` option to specify which child items will be draggable.

    <div id="listA"></div>
    <script>
        //create dataSource
        var listA_DS= new kendo.data.DataSource({
            data: [
                { id: 1, item: "Item 1" },
                { id: 2, item: "Item 2" }
            ],
            schema: {
                model: {
                    id: "id",
                    fields: {
                        id: { type: "number" },
                        item: { type: "string" }
                    }
                }
            }
        });

        //display dataSource's data through ListView
        $("#listA").kendoListView({
            dataSource: listA_DS,
            template: "<div class='item'>ListA: #: item #</div>"
        });

        //create a draggable for the parent container
        $("#listA").kendoDraggable({
            filter: ".item", //specify which items will be draggable
            hint: function(element) { //create a UI hint
                return element.clone().css({
                    "opacity": 0.6,
                    "background-color": "#0cf"
                });
            }
        });
    </script>
    <style>
        #listA {
            width: 300px;
            border: 3px solid black;
            border-radius: 3px;
        }

        .item {
            margin: 5px;
            padding: 5px;
            text-align: center;
            border: 2px solid #ccc;
            border-radius: 5px;
        }
    </style>

## DropTarget

DropTarget widget creates from any DOM element a target for draggable elements.

### Initialization

    <div id="listB"></div>
    <script>
        $("#listB").kendoDropTarget();
    </script>
    <style>
        #listB {
            width: 300px;
            height: 280px;
            border: 3px solid black;
            border-radius: 3px;
        }
    </style>

> If the DropTarget element is initially empty, the developer should explicitly specify its `height` or `min-height`. The user will not be able to drag on target with zero height.

## Handling events

Draggable, DropTarget and DropTargetArea provide various [events](/api/framework/draggable#events) that the developer may use to implement specific business requirements.

### Getting the dataItem that corresponds to the dragged element

Data management widgets such as Grid or ListView automatically append a `uid` data attribute to their items. The developer may use the `uid` attribute to get reference to the dataItem from DataSource.

    <div id="listA"></div>
    <script>
        $("#listA").kendoListView({
            dataSource: listA_DS,
            template: "<div class='item'>ListA: #: item #</div>"
        });

        $("#listA").kendoDraggable({
            filter: ".item",
            dragstart: function(e) {
                var draggedElement = e.currentTarget, //get the DOM element that is being dragged
                    dataItem = listA_DS.getByUid(draggedElement.data("uid")); //get corresponding dataItem from the DataSource

                console.log(dataItem);
            },
            hint: function(element) {
                return element.clone().css({
                    "opacity": 0.6,
                    "background-color": "#0cf"
                });
            }
        });
    </script>

### Add visual indications

The developer may use DropTarget events such as `dragenter` and `dragleave` to visually indicate that the dragged item is over the DropTarget element.


    <div id="listA"></div>
    <div id="listB"></div>
    <script>
        var listA_DS= new kendo.data.DataSource({
            data: [
                { id: 1, item: "Item 1" },
                { id: 2, item: "Item 2" },
                { id: 3, item: "Item 3" }
            ],
            schema: {
                model: {
                    id: "id",
                    fields: {
                        id: { type: "number" },
                        item: { type: "string" }
                    }
                }
            }
        });

        var listB_DS= new kendo.data.DataSource({
            data: [ /* still no data */ ],
            schema: {
                model: {
                    id: "id",
                    fields: {
                        id: { type: "number" },
                        item: { type: "string" }
                    }
                }
            }
        });

        function addStyling(e) {
            this.element.css({
                "border-color": "#06c",
                "background-color": "#e0e0e0",
                "opacity": 0.6
            });
        }

        function resetStyling(e) {
            this.element.css({
                "border-color": "black",
                "background-color": "transparent",
                "opacity": 1
            });
        }

        $("#listA").kendoListView({
            dataSource: listA_DS,
            template: "<div class='item'>ListA: #: item #</div>"
        });

        //create draggable
        $("#listA").kendoDraggable({
            filter: ".item",
            dragstart: function(e) {
                var draggedElement = e.currentTarget,
                    dataItem = listA_DS.getByUid(draggedElement.data("uid"));

                console.log(dataItem);
            },
            hint: function(element) {
                return element.clone().css({
                    "opacity": 0.6,
                    "background-color": "#0cf"
                });
            }
        });

        $("#listB").kendoListView({
            dataSource: listB_DS,
            template: "<div class='item'>ListB: #: item #</div>"
        });

        //create dropTarget
        $("#listB").kendoDropTarget({
            dragenter: addStyling, //add visual indication
            dragleave: resetStyling, //remove the visual indication
        });
    </script>
    <style>
        #listA, #listB {
            width: 300px;
            height: 280px;
            float: left;
            margin-right: 30px;
            border: 3px solid black;
            border-radius: 3px;
        }

        .item {
            margin: 5px;
            padding: 5px;
            text-align: center;
            border: 2px solid #ccc;
            border-radius: 5px;
        }
    </style>

### Moving items from one list to another

The Drag'n'Drop components does not manage the list data. In order to move items from one list to another, developer may hook up to the `drop` event and use DataSource's `remove` and `add` methods to apply changes in the data.

    <div id="listA"></div>
    <div id="listB"></div>
    <script>
        var listA_DS= new kendo.data.DataSource({
            data: [
                { id: 1, item: "Item 1" },
                { id: 2, item: "Item 2" },
                { id: 3, item: "Item 3" }
            ],
            schema: {
                model: {
                    id: "id",
                    fields: {
                        id: { type: "number" },
                        item: { type: "string" }
                    }
                }
            }
        });

        var listB_DS= new kendo.data.DataSource({
            data: [ /* still no data */ ],
            schema: {
                model: {
                    id: "id",
                    fields: {
                        id: { type: "number" },
                        item: { type: "string" }
                    }
                }
            }
        });

        function addStyling(e) {
            this.element.css({
                "border-color": "#06c",
                "background-color": "#e0e0e0",
                "opacity": 0.6
            });
        }

        function resetStyling(e) {
            this.element.css({
                "border-color": "black",
                "background-color": "transparent",
                "opacity": 1
            });
        }

        $("#listA").kendoListView({
            dataSource: listA_DS,
            template: "<div class='item'>ListA: #: item #</div>"
        });

        $("#listA").kendoDraggable({
            filter: ".item",
            dragstart: function(e) {
                var draggedElement = e.currentTarget,
                    dataItem = listA_DS.getByUid(draggedElement.data("uid"));

                console.log(dataItem);
            },
            hint: function(element) {
                return element.clone().css({
                    "opacity": 0.6,
                    "background-color": "#0cf"
                });
            }
        });

        $("#listB").kendoListView({
            dataSource: listB_DS,
            template: "<div class='item'>ListB: #: item #</div>"
        });

        $("#listB").kendoDropTarget({
            dragenter: addStyling,
            dragleave: resetStyling,
            drop: function(e) { //apply changes in the data after item is dropped
                var draggableElement = e.draggable.currentTarget,
                dataItem = listA_DS.getByUid(draggableElement.data("uid")); //find the corresponding dataItem by uid

                listA_DS.remove(dataItem); //remove the item from ListA
                listB_DS.add(dataItem); //add the item to ListB

                resetStyling.call(this); //reset visual dropTarget indication that was added on dragenter
            }
        });
    </script>
    <style>
        #listA, #listB {
            width: 300px;
            height: 280px;
            float: left;
            margin-right: 30px;
            border: 3px solid black;
            border-radius: 3px;
        }

        .item {
            margin: 5px;
            padding: 5px;
            text-align: center;
            border: 2px solid #ccc;
            border-radius: 5px;
        }
    </style>

## DropTargetArea

DropTargetArea allows the developer to create multiple DropTarget elements located in the area container. This is useful when the DropTarget elements will be added dynamically.

> Specifying `filter` for the DropTargetArea is mandatory!

### Initialization

    <p>Area accepts only draggable elements from orange group</p>
    <div id="area">
      <div id="droptarget" class="orange"></div>
    </div>
    <div id="draggable" class="purple"></div>

    <script>
      $("#draggable").kendoDraggable({
        hint: function(element) {
          return element.clone();
        }
      });

      $("#area").kendoDropTargetArea({ 
          filter: "#droptarget",
          drop: onDrop
      });

      function onDrop(e) {
        e.dropTarget.toggleClass("orange").toggleClass("purple");
        e.draggable.element.toggleClass("orange").toggleClass("purple");
      }
    </script>
    <style>
      #draggable {
        width: 50px;
        height: 50px;
        border: 2px solid green;
        margin: 5px;
        display: inline-block;
      }
      .orange { background-color: orange; }
      .purple { background-color: purple; }
      #area {
          width: 300px;
          height: 300px;
          line-height: 300px;
          background-color: gray;
      }
      #droptarget {
        width: 100px;
        height: 100px;
        border: 2px solid green;
        margin: 0 96px;
        display: inline-block;
        vertical-align: middle;
      }
    </style>

### Next Steps

- [Online demos](http://demos.telerik.com/kendo-ui/dragdrop/index)
- [Draggable API reference](/api/framework/draggable)
- [DropTarget API reference](/api/framework/droptarget)
- [DropTargetArea API reference](/api/framework/droptargetarea)
