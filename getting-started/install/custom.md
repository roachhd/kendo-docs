---
title: Include Only What You Need
page_title: Build a Custom Kendo UI Dstribution
previous_url: /getting-started/javascript-dependencies
description: "How to include only the parts of Kendo UI which your project uses"
position: 4
---

## Pick the Right Combined Script Based on Your Project Type

The following combined scripts are available in the bundles or at the CDN in order to facilitate common project types:

*  **kendo.ui.core.min.js** - contains all widgets available in the [Kendo UI Core project](https://github.com/telerik/kendo-ui-core). The script is available in the Kendo UI Core distribution.
*  **kendo.all.min.js** - contains a minified version of all features provided by Kendo UI.

> **Important**: kendo.all.min.js is available in the Kendo UI Professional, Telerik UI for ASP.NET MVC**, **Telerik UI for JSP** and **Telerik UI for PHP distributions. The contents of
**kendo.aspnetmvc.min.js** are **not** included in kendo.all.min.js - you need to include **kendo.aspnetmvc.min.js** in addition to kendo.all.min.js or use the
[custom download builder tool](http://www.telerik.com/download/custom-download).

* **kendo.web.min.js** Available in Kendo UI Professional, JSP, PHP and MVC. Includes the core framework and all desktop browser widgets (previously distributed as Kendo UI Web).
* **kendo.dataviz.min.js** Available in Kendo UI Professional, JSP, PHP and MVC. Includes the core framework and all data visualization widgets (previously distributed as Kendo UI DataViz).
* **kendo.mobile.min.js** Available in Kendo UI Professional, JSP, PHP and MVC. Includes the core framework and all mobile device specific widgets (previously distributed as Kendo UI Mobile).

> **Important:** Only one of the combined JavaScript files can be included at a time, because they include the Kendo UI framework. If widgets from
different Kendo UI suites will be used simultaneously, you should use **kendo.all.min.js** or build a custom script.

In addition, each of the combined script files should not be registered together with an **individual widget script** from the same suite. For example, `kendo.grid.js` should not be registered together with
`kendo.web.js` or `kendo.all.js`, because they already include the Grid scripts.

> Registering duplicate scripts may cause Javascript errors and unexpected behavior.

## Build a Custom Combined Script With the Kendo UI Download Builder

Users with a commercial license may use the [custom download builder tool](http://www.telerik.com/download/custom-download) to create a single JavaScript file which contains only the required widgets and features.

## Use Grunt to Build a Custom Script

If you use **Kendo UI Core**, you may build a custom distribution using the `grunt` build tool by following the [instructions in the README](https://github.com/telerik/kendo-ui-core#building-only-what-you-need).

## Include Individual Widget Scripts

The following script files, either minified or not, can be included on a per-widget basis:

## Framework

Shared components providing behaviors, data access and other services

### MVVM
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.binder.js

### Core
1. jquery.js
1. kendo.core.js

### Data source
1. jquery.js
1. kendo.core.js
1. kendo.data.odata.js (OData feature)
1. kendo.data.xml.js (XML feature)
1. kendo.data.js

### Drag & drop
1. jquery.js
1. kendo.core.js
1. kendo.userevents.js
1. kendo.draganddrop.js

### Effects
1. jquery.js
1. kendo.core.js
1. kendo.fx.js

### Router
1. jquery.js
1. kendo.core.js
1. kendo.router.js

### Sortable
1. jquery.js
1. kendo.core.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.sortable.js

### View
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.fx.js
1. kendo.view.js


## Web

Desktop UI Widgets for mobile-ready Web Sites and Applications
### AutoComplete
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.popup.js
1. kendo.list.js
1. kendo.fx.js (Mobile scroller feature)
1. kendo.userevents.js (Mobile scroller feature)
1. kendo.draganddrop.js (Mobile scroller feature)
1. kendo.mobile.scroller.js (Mobile scroller feature)
1. kendo.autocomplete.js

### Button
1. jquery.js
1. kendo.core.js
1. kendo.button.js

### Calendar
1. jquery.js
1. kendo.core.js
1. kendo.calendar.js

### Color tools
1. jquery.js
1. kendo.core.js
1. kendo.popup.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.slider.js
1. kendo.colorpicker.js

### ComboBox
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.popup.js
1. kendo.list.js
1. kendo.fx.js (Mobile scroller feature)
1. kendo.userevents.js (Mobile scroller feature)
1. kendo.draganddrop.js (Mobile scroller feature)
1. kendo.mobile.scroller.js (Mobile scroller feature)
1. kendo.combobox.js

### DatePicker
1. jquery.js
1. kendo.core.js
1. kendo.calendar.js
1. kendo.popup.js
1. kendo.datepicker.js

### DateTimePicker
1. jquery.js
1. kendo.core.js
1. kendo.calendar.js
1. kendo.popup.js
1. kendo.datepicker.js
1. kendo.timepicker.js
1. kendo.datetimepicker.js

### DropDownList
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.popup.js
1. kendo.list.js
1. kendo.fx.js (Mobile scroller feature)
1. kendo.userevents.js (Mobile scroller feature)
1. kendo.draganddrop.js (Mobile scroller feature)
1. kendo.mobile.scroller.js (Mobile scroller feature)
1. kendo.dropdownlist.js

### Editor
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.popup.js
1. kendo.list.js
1. kendo.combobox.js
1. kendo.dropdownlist.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.window.js
1. kendo.slider.js
1. kendo.colorpicker.js
1. kendo.listview.js (Image Browser feature)
1. kendo.upload.js (Image Browser feature)
1. kendo.filebrowser.js (Image Browser feature)
1. kendo.imagebrowser.js (Image Browser feature)
1. kendo.editor.js

### Gantt
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.popup.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.resizable.js
1. kendo.dom.js
1. kendo.touch.js
1. kendo.columnsorter.js
1. kendo.calendar.js
1. kendo.datepicker.js
1. kendo.timepicker.js
1. kendo.datetimepicker.js
1. kendo.numerictextbox.js
1. kendo.validator.js
1. kendo.binder.js
1. kendo.editable.js
1. kendo.gantt.list.js
1. kendo.gantt.timeline.js
1. kendo.gantt.js

### Grid
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.columnsorter.js
1. kendo.calendar.js (Editing feature)
1. kendo.popup.js (Editing feature)
1. kendo.datepicker.js (Editing feature)
1. kendo.userevents.js (Editing feature)
1. kendo.numerictextbox.js (Editing feature)
1. kendo.validator.js (Editing feature)
1. kendo.binder.js (Editing feature)
1. kendo.editable.js (Editing feature)
1. kendo.draganddrop.js (Editing feature)
1. kendo.window.js (Editing feature)
1. kendo.calendar.js (Filtering feature)
1. kendo.popup.js (Filtering feature)
1. kendo.datepicker.js (Filtering feature)
1. kendo.userevents.js (Filtering feature)
1. kendo.numerictextbox.js (Filtering feature)
1. kendo.list.js (Filtering feature)
1. kendo.dropdownlist.js (Filtering feature)
1. kendo.filtermenu.js (Filtering feature)
1. kendo.popup.js (Column menu feature)
1. kendo.calendar.js (Column menu feature)
1. kendo.datepicker.js (Column menu feature)
1. kendo.userevents.js (Column menu feature)
1. kendo.numerictextbox.js (Column menu feature)
1. kendo.list.js (Column menu feature)
1. kendo.dropdownlist.js (Column menu feature)
1. kendo.filtermenu.js (Column menu feature)
1. kendo.menu.js (Column menu feature)
1. kendo.columnmenu.js (Column menu feature)
1. kendo.userevents.js (Grouping feature)
1. kendo.draganddrop.js (Grouping feature)
1. kendo.groupable.js (Grouping feature)
1. kendo.popup.js (Row filter feature)
1. kendo.list.js (Row filter feature)
1. kendo.autocomplete.js (Row filter feature)
1. kendo.filtercell.js (Row filter feature)
1. kendo.pager.js (Paging feature)
1. kendo.userevents.js (Selection feature)
1. kendo.selectable.js (Selection feature)
1. kendo.userevents.js (Column reordering feature)
1. kendo.draganddrop.js (Column reordering feature)
1. kendo.reorderable.js (Column reordering feature)
1. kendo.userevents.js (Column resizing feature)
1. kendo.draganddrop.js (Column resizing feature)
1. kendo.resizable.js (Column resizing feature)
1. kendo.popup.js (Grid adaptive rendering feature)
1. kendo.fx.js (Grid adaptive rendering feature)
1. kendo.userevents.js (Grid adaptive rendering feature)
1. kendo.draganddrop.js (Grid adaptive rendering feature)
1. kendo.mobile.scroller.js (Grid adaptive rendering feature)
1. kendo.binder.js (Grid adaptive rendering feature)
1. kendo.view.js (Grid adaptive rendering feature)
1. kendo.mobile.view.js (Grid adaptive rendering feature)
1. kendo.mobile.loader.js (Grid adaptive rendering feature)
1. kendo.mobile.pane.js (Grid adaptive rendering feature)
1. kendo.router.js (Grid adaptive rendering feature)
1. kendo.mobile.application.js (Grid adaptive rendering feature)
1. kendo.mobile.popover.js (Grid adaptive rendering feature)
1. kendo.mobile.shim.js (Grid adaptive rendering feature)
1. kendo.mobile.actionsheet.js (Grid adaptive rendering feature)
1. kendo.grid.js

### ListView
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.calendar.js (Editing feature)
1. kendo.popup.js (Editing feature)
1. kendo.datepicker.js (Editing feature)
1. kendo.userevents.js (Editing feature)
1. kendo.numerictextbox.js (Editing feature)
1. kendo.validator.js (Editing feature)
1. kendo.binder.js (Editing feature)
1. kendo.editable.js (Editing feature)
1. kendo.userevents.js (Selection feature)
1. kendo.selectable.js (Selection feature)
1. kendo.listview.js

### MaskedTextBox
1. jquery.js
1. kendo.core.js
1. kendo.maskedtextbox.js

### Menu
1. jquery.js
1. kendo.core.js
1. kendo.popup.js
1. kendo.menu.js

### MultiSelect
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.popup.js
1. kendo.list.js
1. kendo.fx.js (Mobile scroller feature)
1. kendo.userevents.js (Mobile scroller feature)
1. kendo.draganddrop.js (Mobile scroller feature)
1. kendo.mobile.scroller.js (Mobile scroller feature)
1. kendo.multiselect.js

### Notification
1. jquery.js
1. kendo.core.js
1. kendo.popup.js
1. kendo.notification.js

### NumericTextBox
1. jquery.js
1. kendo.core.js
1. kendo.userevents.js
1. kendo.numerictextbox.js

### PanelBar
1. jquery.js
1. kendo.core.js
1. kendo.panelbar.js

### PivotConfigurator
1. jquery.js
1. kendo.core.js
1. kendo.dom.js
1. kendo.data.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.sortable.js
1. kendo.pivotgrid.js
1. kendo.popup.js
1. kendo.list.js
1. kendo.dropdownlist.js
1. kendo.treeview.js
1. kendo.pivotgrid.configurator.js

### PivotGrid
1. jquery.js
1. kendo.core.js
1. kendo.dom.js
1. kendo.data.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.sortable.js
1. kendo.pivotgrid.js

### ProgressBar
1. jquery.js
1. kendo.core.js
1. kendo.progressbar.js

### Scheduler
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.popup.js
1. kendo.list.js
1. kendo.dropdownlist.js
1. kendo.calendar.js
1. kendo.datepicker.js
1. kendo.userevents.js
1. kendo.numerictextbox.js
1. kendo.validator.js
1. kendo.binder.js
1. kendo.editable.js
1. kendo.multiselect.js
1. kendo.draganddrop.js
1. kendo.window.js
1. kendo.scheduler.recurrence.js
1. kendo.scheduler.view.js
1. kendo.scheduler.dayview.js (Scheduler Day View feature)
1. kendo.scheduler.agendaview.js (Scheduler Agenda View feature)
1. kendo.scheduler.monthview.js (Scheduler Month View feature)
1. kendo.fx.js (Scheduler adaptive rendering feature)
1. kendo.mobile.scroller.js (Scheduler adaptive rendering feature)
1. kendo.view.js (Scheduler adaptive rendering feature)
1. kendo.mobile.view.js (Scheduler adaptive rendering feature)
1. kendo.mobile.loader.js (Scheduler adaptive rendering feature)
1. kendo.mobile.pane.js (Scheduler adaptive rendering feature)
1. kendo.router.js (Scheduler adaptive rendering feature)
1. kendo.mobile.application.js (Scheduler adaptive rendering feature)
1. kendo.mobile.popover.js (Scheduler adaptive rendering feature)
1. kendo.mobile.shim.js (Scheduler adaptive rendering feature)
1. kendo.mobile.actionsheet.js (Scheduler adaptive rendering feature)
1. kendo.scheduler.js

### Slider
1. jquery.js
1. kendo.core.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.slider.js

### Splitter
1. jquery.js
1. kendo.core.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.resizable.js
1. kendo.splitter.js

### TabStrip
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.tabstrip.js

### TimePicker
1. jquery.js
1. kendo.core.js
1. kendo.popup.js
1. kendo.timepicker.js

### ToolBar
1. jquery.js
1. kendo.core.js
1. kendo.toolbar.js

### Tooltip
1. jquery.js
1. kendo.core.js
1. kendo.popup.js
1. kendo.tooltip.js

### TreeView
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.treeview.js

### Upload
1. jquery.js
1. kendo.core.js
1. kendo.upload.js

### Validator
1. jquery.js
1. kendo.core.js
1. kendo.validator.js

### Window
1. jquery.js
1. kendo.core.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.window.js


## DataViz

Data Visualization Widgets for Desktop and Mobile web apps
### Barcode
1. jquery.js
1. kendo.core.js
1. kendo.dataviz.core.js
1. kendo.dataviz.svg.js
1. kendo.dataviz.canvas.js
1. kendo.dataviz.barcode.js

### Output: Canvas
1. jquery.js
1. kendo.core.js
1. kendo.dataviz.core.js
1. kendo.dataviz.canvas.js

### Chart
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.userevents.js
1. kendo.dataviz.core.js
1. kendo.dataviz.svg.js
1. kendo.dataviz.themes.js
1. kendo.dataviz.chart.js (Polar & Radar feature)
1. kendo.dataviz.chart.polar.js (Polar & Radar feature)
1. kendo.dataviz.chart.js (Funnel chart feature)
1. kendo.dataviz.chart.funnel.js (Funnel chart feature)
1. kendo.dataviz.chart.js

### Diagram
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.userevents.js
1. kendo.fx.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.dataviz.core.js
1. kendo.dataviz.diagram.js

### Drawing API
1. jquery.js
1. kendo.core.js
1. kendo.dataviz.core.js
1. kendo.dataviz.drawing.js

### Gauge
1. jquery.js
1. kendo.core.js
1. kendo.dataviz.core.js
1. kendo.dataviz.svg.js
1. kendo.dataviz.themes.js
1. kendo.dataviz.gauge.js

### Map
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.userevents.js
1. kendo.popup.js
1. kendo.tooltip.js
1. kendo.dataviz.core.js
1. kendo.dataviz.drawing.js
1. kendo.fx.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.dataviz.map.js

### QRCode
1. jquery.js
1. kendo.core.js
1. kendo.dataviz.core.js
1. kendo.dataviz.svg.js
1. kendo.dataviz.canvas.js
1. kendo.dataviz.qrcode.js

### Sparkline
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.userevents.js
1. kendo.dataviz.core.js
1. kendo.dataviz.svg.js
1. kendo.dataviz.themes.js
1. kendo.dataviz.chart.js
1. kendo.dataviz.sparkline.js

### StockChart
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.userevents.js
1. kendo.dataviz.core.js
1. kendo.dataviz.svg.js
1. kendo.dataviz.themes.js
1. kendo.dataviz.chart.js
1. kendo.dataviz.stockchart.js

### Output: SVG
1. jquery.js
1. kendo.core.js
1. kendo.dataviz.core.js
1. kendo.dataviz.svg.js

### TreeMap
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.userevents.js
1. kendo.dataviz.core.js
1. kendo.dataviz.treeMap.js

### Output: VML
1. jquery.js
1. kendo.core.js
1. kendo.dataviz.core.js
1. kendo.dataviz.vml.js


## Mobile

Framework and Widgets for Mobile Applications
### ActionSheet
1. jquery.js
1. kendo.core.js
1. kendo.popup.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js
1. kendo.mobile.popover.js
1. kendo.mobile.shim.js
1. kendo.mobile.actionsheet.js

### Application
1. jquery.js
1. kendo.core.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js

### Button
1. jquery.js
1. kendo.core.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js
1. kendo.mobile.button.js

### ButtonGroup
1. jquery.js
1. kendo.core.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js
1. kendo.mobile.buttongroup.js

### Drawer
1. jquery.js
1. kendo.core.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.drawer.js

### ListView
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js
1. kendo.mobile.listview.js

### ModalView
1. jquery.js
1. kendo.core.js
1. kendo.popup.js
1. kendo.mobile.shim.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js
1. kendo.mobile.modalview.js

### NavBar
1. jquery.js
1. kendo.core.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js
1. kendo.mobile.navbar.js

### PopOver
1. jquery.js
1. kendo.core.js
1. kendo.popup.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js
1. kendo.mobile.popover.js

### Scroller
1. jquery.js
1. kendo.core.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js

### ScrollView
1. jquery.js
1. kendo.core.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js
1. kendo.mobile.scrollview.js

### SplitView
1. jquery.js
1. kendo.core.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js
1. kendo.mobile.splitview.js

### Switch
1. jquery.js
1. kendo.core.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js
1. kendo.mobile.switch.js

### TabStrip
1. jquery.js
1. kendo.core.js
1. kendo.fx.js
1. kendo.userevents.js
1. kendo.draganddrop.js
1. kendo.mobile.scroller.js
1. kendo.data.js
1. kendo.binder.js
1. kendo.view.js
1. kendo.mobile.view.js
1. kendo.mobile.loader.js
1. kendo.mobile.pane.js
1. kendo.router.js
1. kendo.mobile.application.js
1. kendo.mobile.tabstrip.js

### Touch
1. jquery.js
1. kendo.core.js
1. kendo.userevents.js
1. kendo.touch.js


## Server Wrappers

Supplementary scripts for integration with server-side technologies

### ASP.NET MVC
1. jquery.js
1. kendo.core.js
1. kendo.data.js
1. kendo.popup.js
1. kendo.list.js
1. kendo.combobox.js
1. kendo.multiselect.js
1. kendo.validator.js
1. kendo.aspnetmvc.js
