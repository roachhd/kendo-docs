---
title: Integration with TabStrip
page_title: Sortable widget - integration with TabStrip
description: How to reorder Kendo UI TabStrip tabs with the Sortable widget
position: 2
---

# Integration with Kendo UI TabStrip

**Sortable widget** gives the ability to the user to sort the TabStrip's tab via drag and drop with the mouse.

Sortable widget should be initialized for TabStrip's `ul.k-tabstrip-items` element. In the general case filter property of the widget should select all `li.k-item` elements. If required the hint movement can be restricted within the `ul.k-tabstrip-items` element.

    $("#tabstrip ul.k-tabstrip-items").kendoSortable({
        filter: "li.k-item",
        axis: "x",
        container: "ul.k-tabstrip-items",
        hint: function(element) {
            return $("<div id='hint' class='k-widget k-header k-tabstrip'><ul class='k-tabstrip-items k-reset'><li class='k-item k-state-active k-tab-on-top'>" + element.html() + "</li></ul></div>");
        },
        start: function(e) {
            $("#tabstrip").data("kendoTabStrip").activateTab(e.item);
        },
        change: function(e) {
            var tabstrip = $("#tabstrip").data("kendoTabStrip"),
                reference = tabstrip.tabGroup.children().eq(e.newIndex);

            if(e.oldIndex < e.newIndex) {
                tabstrip.insertAfter(e.item, reference);
            } else {
                tabstrip.insertBefore(e.item, reference);
            }
        }
    });

In order to avoid visual glitches it is recommended to activate the current tab in the `start` event handler of the Sortable widget.

    start: function(e) {
        $("#tabstrip").data("kendoTabStrip").activateTab(e.item);
    }

After tab is sorted the developer should update its position in the TabStrip widget.

    change: function(e) {
        var tabstrip = $("#tabstrip").data("kendoTabStrip"),
            reference = tabstrip.tabGroup.children().eq(e.newIndex);

        if(e.oldIndex < e.newIndex) {
            tabstrip.insertAfter(e.item, reference);
        } else {
            tabstrip.insertBefore(e.item, reference);
        }
    }

For more information check [Sortable's events](../../../api/web/sortable#events) and TabStrip integration [demo page](http://demos.telerik.com/kendo-ui/web/sortable/integration-tabstrip.html).

