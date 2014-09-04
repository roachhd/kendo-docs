---
title: Printing and Exporting
page_title: Printing and Exporting the Kendo UI Grid widget
description: This documentation page will explain how to print and export the Kendo UI Grid widget
---

# Printing and Exporting the Grid

## Printing

In most cases the Grid is not the only content on the page, however, there are cases when one would like to print the Grid only. There are two ways to achieve that.

1. Print the existing web page, but use a print stylesheet to hide parts of the page, which are not needed.  
2. Retrieve the Grid HTML, inject it in a new browser window, and trigger printing of the new page.

The example below shows how to implement the second option. There are some other important things to keep in mind, which are also addressed by the provided example.

* If the Grid is scrollable, some rows or columns may not be visible on the printed paper. You need to ensure that the Grid has no height during printing, and the scrollability of the data area is disabled.
* Browsers repeat table headers on each printed page automatically. However, when the Grid is scrollable, it renders a separate table for the header area.
Since the browser cannot understand the relationship between the two Grid tables, it will not repeat the header row. This problem is resolved by cloning the header row inside the data table.

### Example

**HTML**

    <div id="grid"></div>

    <script type="text/x-kendo-template" id="toolbar-template">
        <button type="button" class="k-button" id="printGrid">Print Grid</button>
    </script>

**Javascript**

	function printGrid() {
		var gridElement = $('#grid'),
			printableContent = '',
			win = window.open('', '', 'width=800, height=500'),
			doc = win.document.open();

		var htmlStart =
				'<!DOCTYPE html>' +
				'<html>' +
				'<head>' +
				'<meta charset="utf-8" />' +
				'<title>Kendo UI Grid</title>' +
				'<link href="http://cdn.kendostatic.com/' + kendo.version + '/styles/kendo.common.min.css" rel="stylesheet" /> ' +
				'<style>' +
				'html { font: 11pt sans-serif; }' +
				'.k-grid { border-top-width: 0; }' +
				'.k-grid, .k-grid-content { height: auto !important; }' +
				'.k-grid-content { overflow: visible !important; }' +
				'.k-grid .k-grid-header th { border-top: 1px solid; }' +
				'.k-grid-toolbar, .k-grid-pager > .k-link { display: none; }' +
				'</style>' +
				'</head>' +
				'<body>';

		var htmlEnd =
				'</body>' +
				'</html>';

		var gridHeader = gridElement.children('.k-grid-header');
		if (gridHeader[0]) {
			var thead = gridHeader.find('thead').clone().addClass('k-grid-header');
			printableContent = gridElement
				.clone()
					.children('.k-grid-header').remove()
				.end()
					.children('.k-grid-content')
						.find('table')
							.first()
								.children('tbody').before(thead)
							.end()
						.end()
					.end()
				.end()[0].outerHTML;
		} else {
			printableContent = gridElement.clone()[0].outerHTML;
		}

		doc.write(htmlStart + printableContent + htmlEnd);
		doc.close();
		win.print();
	}

	$(function () {
		var grid = $('#grid').kendoGrid({
			dataSource: {
				type: 'odata',
				transport: {
					read: "http://demos.telerik.com/kendo-ui/service/Northwind.svc/Products"
				},
				pageSize: 20,
				serverPaging: true,
				serverSorting: true,
				serverFiltering: true
			},
			toolbar: kendo.template($('#toolbar-template').html()),
			height: 400,
			pageable: true,
			columns: [
				{ field: 'ProductID', title: 'Product ID', width: 100 },
				{ field: 'ProductName', title: 'Product Name' },
				{ field: 'UnitPrice', title: 'Unit Price', width: 100 },
				{ field: 'QuantityPerUnit', title: 'Quantity Per Unit' }
			]
		});

		$('#printGrid').click(function () {
			printGrid();
		});

	});

## Exporting

There are two ways to export the Grid:

* Use a server-side implementation to directly export the data that is otherwise displayed by the Grid.
* Use a client-side implementation to export the Grid table's HTML markup or the Grid dataSource items.

The Kendo UI Code Library provides several examples of exporting the Grid to CSV, Excel and PDF formats.

* [Export Kendo UI Grid to Excel](http://www.telerik.com/support/code-library/export-grid-to-excel-8d91dd145501)
* [Export MVC Grid to Excel](http://www.telerik.com/support/code-library/export-grid-to-excel)
* [Export MVC Grid to PDF](http://www.telerik.com/support/code-library/export-grid-to-pdf)
* [Export MVC Grid to CSV](http://www.telerik.com/support/code-library/export-grid-to-csv)

A thing to keep in mind during client-side export is that the Grid and its dataSource contain only the data items from the current page.
As a result, exporting should be made in chunks, or paging should be disabled.