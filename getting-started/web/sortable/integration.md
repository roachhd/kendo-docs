---
title: Integration with Grid/ListView
page_title: Sortable widget - integration with Grid/ListView
description: How to reorder Kendo UI Grid/ListView items with the Sortable widget
position: 1
---

# Integration with Kendo UI Grid/ListView

The Sortable widget may be used for reordering Kendo UI Grid/ListView items via drag and drop.

>**Important:** The Sortable widget reorders the HTML DOM elements. It will not update automatically the position of the items in the DataSource. It is responsibility of the developer to update the DataSource.

## Prerequisites

The following help articles assumes that you are already familiar with:

- [Kendo UI Sortable](../../../getting-started/web/sortable/overview)
- [Kendo UI Grid](../../../getting-started/web/grid/overview)
- [Kendo UI DataSource API](../../../api/framework/datasource#methods)

## Reorder Kendo UI Grid table rows via drag and drop using the Sortable widget

The Sortable widget should be initialized for Grid's [`table element`](../../../api/web/grid#fields-table).
In the general case filter property of the widget should select all `tr` elements that are direct children of the table's `tbody` element. For example: `filter: ">tbody >tr"`.

**If the Grid's editing is enabled**, you should use a more specific filter selector that excludes the item that is currently in edit mode.
For example `.filter(">tbody >tr:not(.k-grid-edit-row)"`. In this way the Sortable functionality will not interfere with Grid's editing feature.

**If the Grid is configured to display details**, you should use a selector that matches only the master Grid rows. For example: `filter: ">tbody >tr.k-master-row"`.
In this way the detail rows will not be draggable.

For more information check [Sortable's events](../../../api/web/sortable#events) and Grid integration [demo page](http://demos.telerik.com/kendo-ui/web/sortable/integration-grid.html).

## Reorder the items in the DataSource

The `change` event of the Sortable widget will fire after row position is changed. You may use the `change` event data to update position of the items in the DataSource.

### Example - shifting the position of the items on the client

    function onChange(e) {
        var grid = e.sender.element.data("kendoGrid"),
            oldIndex = e.oldIndex , //the old position
            newIndex = e.newIndex , //the new position
            view = grid.dataSource.view(),
            dataItem = grid.dataSource.getByUid(e.item.data("uid")); //retrieved moved dataItem

        dataItem.Order = newIndex; //update the order
        dataItem.dirty = true;

        //shift the order of the records
        if (oldIndex < newIndex) {
            for (var i = oldIndex + 1; i <= newIndex; i++) {
                view[i].Order--;
                view[i].dirty = true;
            }
        } else {
            for (var i = oldIndex - 1; i >= newIndex; i--) {
                view[i].Order++;
                view[i].dirty = true;
            }
        }

        grid.dataSource.sync(); //submit the changes through the update transport and refresh the Grid
    }

### Example - sending the newIndex and oldIndex to the server

    function onChange(e) {
        var grid = e.sender.element.data("kendoGrid"),
            oldIndex = e.oldIndex , //the old position
            newIndex = e.newIndex , //the new position
            dataItem = grid.dataSource.getByUid(e.item.data("uid")); //retrieve moved dataItem

        $.ajax({
            url: "yourUrl",
            dataType: "json",
            data: { //send the data and update the order of items on the server
                oldIndex: oldIndex,
                newIndex: newIndex,
                dataItem: dataItem
            },
            success: function (response) {
                grid.dataSource.read(); //refresh the Grid
            }
        });
    }

## Customizing the hint

The hint element is appended to the `<body>` element and as a result its width will be different from the Grid's one.
The following example demonstrates how to style the hint element so it will look exactly like the row element that is currently dragged.

### Example - customizing the hint

    <div id="grid"></div>
    <script>

      $("#grid").kendoGrid({
        dataSource: {
          data: [{name: "John", age: 25}, {name: "Jane", age: 25}]
        }
      });

      $("#grid").data("kendoGrid").table.kendoSortable({
        filter: ">tbody >tr", //set the filter
        hint: function(element) { //customize the hint
          var grid = $("#grid").data("kendoGrid"),
              table = grid.table.clone(), //clone Grid's table
              wrapperWidth = grid.wrapper.width(), //get Grid's width
              wrapper = $("<div class='k-grid k-widget'></div>").width(wrapperWidth),
              hint;

          table.find("thead").remove(); //remove Grid's header from the hint
          table.find("tbody").empty(); //remove the existing rows from the hint
          table.wrap(wrapper); //wrap the table
          table.append(element.clone()); //append the dragged element

          hint = table.parent(); //get the wrapper

          return hint; //return the hint element
        },
        placeholder: function(element) { //customize the placeholder
          return element.clone().addClass("k-state-hover").css("opacity", 0.65);
        },
        change: function(e) {
          //handle the change event
          //update the underlying data according to the DOM position change
        }
      });
    </script>

## Known limitations

- The Sortable widget does not work well with Grid that has paging/virtual scrolling.

The Sortable widget operates with the existing DOM. It is not aware of the Grid nor its DataSource.
If paging or virtual scrolling are turned on, the Grid widget will render in the DOM only the elements that belong to the current page. As a result the sorting will be limited to the current page only.

- The Sortable widget does not work well with Grid that is grouped.

The Sortable widget uses the index of the DOM elements.
When the Grid displays grouped data, the index of the DOM element does not match the index of the corresponding data item in the DataSource. This makes updating the order in the DataSource impossible.

## Reorder Kendo UI ListView Items via drag and drop using the Sortable widget

>**Important:** Sortable widget reorders HTML DOM elements. It will not update automatically the position of the item in the DataSource. It is responsibility of the developer to update the data.

Sortable widget should be initialized for ListView's element. In the general case filter property of the widget should select all elements that are direct children of the ListView's element. For example: `.filter(">div")`.

If the ListView's editing is enabled the developer should use a more specific filter selector that excludes the item which is currently in edit mode.
For example `.filter(">div:not(.k-edit-item)"`. In this way the Sortable functionality will not interfere with ListView's editing feature.

For more information check [Sortable's events](../../../api/web/sortable#events) and ListView integration [demo page](http://demos.telerik.com/kendo-ui/web/sortable/integration-listview.html).
