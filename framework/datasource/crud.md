---
title: CRUD Operations
page_title: Kendo UI DataSource CRUD Operations
description: How to use the Kendo UI DataSource component for CRUD operations (create, read, update, delete), i.e. editing
---

# Kendo UI DataSource CRUD Operations

The Kendo UI DataSource fully supports CRUD (Create, Read, Update, Destroy) data operations.
Surely, it must be combined with some user interface or another Kendo UI widget (Grid, ListView, etc).
The examples below will use a Grid, but the same considerations apply in any other scenario.

The DataSource can work with local data or remote data. In both cases the CRUD operations are managed by the so-called Kendo UI Transport.
This is a Javascript object that can be configured to execute predefined functions or make requests to predefined URLs on certain events.

## CRUD Operations with Local Data

### Read

When a Kendo UI DataSource instance must be bound to local data without the need to support editing, it is sufficient to use the `data` option like this:

    var dataSource = new kendo.data.DataSource({
        data: sampleData
    }

However, when editing will be used, then a `transport` configuration is required. The `data` option is no longer needed.
The `read` method of the `transport` should pass a local variable. It can even make a custom Ajax request and then pass the response.

    var dataSource = new kendo.data.DataSource({
        transport: {
            read: function (e) {
                // on success
                e.success(sampleData);
                // on failure
                //e.error("XHR response", "status code", "error message");
            }
        },
        error: function (e) {
            alert("Status: " + e.status + "; Error message: " + e.errorThrown);
        }
    }

Executing the `success` method of the `read` function argument will populate the DataSource instance and fire its `change` event.
Executing the `error` method will fire the `error` event of the DataSource, which can be handled.

### Update

The `update` configuration setting of the DataSource should define a function that handles the updated data item(s), received as a function argument.
When `batch` is disabled (default) and only one data item can be updated at a time, the updated data item is received as an object in `e.data`. If `batch` is enabled and multiple data items can be
updated, they are received as an array of objects in `e.data.models`. Again, the `success` or `error` method of the function argument must be executed at the end.

    var dataSource = new kendo.data.DataSource({
        transport: {
            update: function (e) {
                // batch is enabled
                //var updateItems = e.data.models;
                // batch is disabled
                var updatedItem = e.data;
                
                // save the updated item to the original datasource
                // ...
                
                // on success
                e.success();
                // on failure
                //e.error("XHR response", "status code", "error message");
            }
        },
        error: function (e) {
            alert("Status: " + e.status + "; Error message: " + e.errorThrown);
        }
    });

### Create

The `create` function should perform a similar routine as `update`, with a couple of notable differences:

* The newly created data item(s) has no ID, so it must be added by the function script or returned by the remote service.
* The newly created data item(s) must be returned in the `success` method **with their IDs assigned**.
Otherwise the DataSource instance will operate with incorrect data and subsequent data operations can fail.

<!-- exit list -->
    
    var dataSource = new kendo.data.DataSource({
        transport: {
            update: function (e) {
                // batch is disabled
                // generate appropriate data item ID and save the new items to the original datasource
                e.data.my_ID_field_name = 123;
                // ...
                
                // on success return the new data items with IDs
                e.success(e.data);
                // on failure
                //e.error("XHR response", "status code", "error message");
            }
        },
        error: function (e) {
            // handle error
            alert("Status: " + e.status + "; Error message: " + e.errorThrown);
        }
    });

### Destroy

The `destroy` function receives the item(s) to be deleted in `e.data`, similar to `create` and `update`.
The function should remove the provided items from the original datasource and return `success` or `error`.

    var dataSource = new kendo.data.DataSource({
        transport: {
            destroy: function (e) {
                // remove items from the original datasource by using e.data
                
                // on success
                e.success();
                // on failure
                //e.error("XHR response", "status code", "error message");
            }
        },
        error: function (e) {
            // handle error
            alert("Status: " + e.status + "; Error message: " + e.errorThrown);
        }
    });

### Complete example: Local CRUD Operations with the Kendo UI Grid

The following example uses the information above to demonstrate CRUD operations with simple Products data.
"original datasource" signifies the sampleData variable, which is used to populate the Grid initially.
All data operations are persisted in this variable, so that it can be used or submitted somewhere else.

    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="utf-8" />
    <title>Kendo UI Grid - CRUD operations with local data</title>

    <style>html { font-size: 12px; font-family: Arial, Helvetica, sans-serif; }</style>
    <link href="http://cdn.kendostatic.com/2014.2.903/styles/kendo.common.min.css" rel="stylesheet" />
    <link href="http://cdn.kendostatic.com/2014.2.903/styles/kendo.default.min.css" rel="stylesheet" />

    <script src="http://cdn.kendostatic.com/2014.2.903/js/jquery.min.js"></script>
    <script src="http://cdn.kendostatic.com/2014.2.903/js/kendo.web.min.js"></script>
    </head>
    <body>

    <div id="grid"></div>

    <script>
        var sampleData = [
            {ProductID: 1, ProductName: "Apple iPhone 5s", Introduced: new Date(2013, 8, 10), UnitPrice: 525, Discontinued: false, UnitsInStock: 10},
            {ProductID: 2, ProductName: "HTC One M8", Introduced: new Date(2014, 2, 25), UnitPrice: 425, Discontinued: false, UnitsInStock: 3},
            {ProductID: 3, ProductName: "Nokia 5880", Introduced: new Date(2008, 10, 2), UnitPrice: 275, Discontinued: true, UnitsInStock: 0}
        ];

        // custom logic start    
        
        var sampleDataNextID = sampleData.length + 1;
        
        function getIndexById(id) {
            var idx,
                l = sampleData.length;
            
            for (var j; j < l; j++) {
                if (sampleData[j].ProductID == id) {
                    return j;
                }
            }
            return null;
        }
        
        // custom logic end

        $(document).ready(function () {
            var dataSource = new kendo.data.DataSource({
                transport: {
                    read: function (e) {
                        // on success
                        e.success(sampleData);
                        // on failure
                        //e.error("XHR response", "status code", "error message");
                    },
                    create: function (e) {
                        // assign an ID to the new item
                        e.data.ProductID = sampleDataNextID++;
                        // save data item to the original datasource
                        sampleData.push(e.data);
                        // on success
                        e.success(e.data);
                        // on failure
                        //e.error("XHR response", "status code", "error message");
                    },
                    update: function (e) {
                        // locate item in original datasource and update it
                        sampleData[getIndexById(e.data.ProductID)] = e.data;
                        // on success
                        e.success();
                        // on failure
                        //e.error("XHR response", "status code", "error message");
                    },
                    destroy: function (e) {
                        // locate item in original datasource and remove it
                        sampleData.splice(getIndexById(e.data.ProductID), 1);
                        // on success
                        e.success();
                        // on failure
                        //e.error("XHR response", "status code", "error message");
                    }
                },
                error: function (e) {
                    // handle data operation error
                    alert("Status: " + e.status + "; Error message: " + e.errorThrown);
                },
                pageSize: 10,
                batch: false,
                schema: {
                    model: {
                        id: "ProductID",
                        fields: {
                            ProductID: { editable: false, nullable: true },
                            ProductName: { validation: { required: true } },
                            Introduced: { type: "date" },
                            UnitPrice: { type: "number", validation: { required: true, min: 1} },
                            Discontinued: { type: "boolean" },
                            UnitsInStock: { type: "number", validation: { min: 0, required: true } }
                        }
                    }
                }
            });

            $("#grid").kendoGrid({
                dataSource: dataSource,
                pageable: true,
                toolbar: ["create"],
                columns: [
                    { field: "ProductName", title: "Mobile Phone" },
                    { field: "Introduced", title: "Introduced", format: "{0:yyyy/MM/dd}", width: "200px" },
                    { field: "UnitPrice", title: "Price", format: "{0:c}", width: "120px" },
                    { field: "UnitsInStock", title:"Units In Stock", width: "120px" },
                    { field: "Discontinued", width: "120px" },
                    { command: ["edit", "destroy"], title: "&nbsp;", width: "200px" }
                ],
                editable: "inline"
            });
        });
    </script>

    </body>
    </html>

## CRUD Operations with Remote Data

Coming soon. Please refer to the [DataSource API](/api/javascript/data/datasource).