---
title: treeMap
---

# \<kendo:treeMap\>
A JSP wrapper for Kendo UI [TreeMap](/api/dataviz/treemap).

## Configuration Attributes

### autoBind `boolean`

If set to false the widget will not bind to the data source during initialization. In this case data binding will occur when the change event of the
data source is fired. By default the widget will bind to the data source specified in the configuration.

#### Example
    <kendo:treeMap autoBind="autoBind">
    </kendo:treeMap>

### colorField `java.lang.String`

The data item field which contains the tile color.

#### Example
    <kendo:treeMap colorField="colorField">
    </kendo:treeMap>

### colors `java.lang.Object`

The default colors for the treemap tiles. When all colors are used, new colors are pulled from the start again.

#### Example
    <kendo:treeMap colors="colors">
    </kendo:treeMap>

### template `java.lang.String`

The template which renders the treeMap tile content.The fields which can be used in the template are:

#### Example
    <kendo:treeMap template="template">
    </kendo:treeMap>

### textField `java.lang.String`

The data item field which contains the tile title.

#### Example
    <kendo:treeMap textField="textField">
    </kendo:treeMap>

### type `java.lang.String`

The layout type for the Treemap.The Supported values are:

#### Example
    <kendo:treeMap type="type">
    </kendo:treeMap>

### valueField `java.lang.String`

The data item field which contains the tile value.

#### Example
    <kendo:treeMap valueField="valueField">
    </kendo:treeMap>


## Event Attributes

### itemCreated `String`

Fired when a tile has been created.


For additional information check the [itemCreated](/api/dataviz/treemap#events-itemCreated) event documentation.

#### Example
    <kendo:treeMap itemCreated="handle_itemCreated">
    </kendo:treeMap>
    <script>
        function handle_itemCreated(e) {
            // Code to handle the itemCreated event.
        }
    </script>

### dataBound `String`

Fired when the widget is bound to data from its dataSource.


For additional information check the [dataBound](/api/dataviz/treemap#events-dataBound) event documentation.

#### Example
    <kendo:treeMap dataBound="handle_dataBound">
    </kendo:treeMap>
    <script>
        function handle_dataBound(e) {
            // Code to handle the dataBound event.
        }
    </script>

## Event Tags

### kendo:treeMap-itemCreated

Fired when a tile has been created.


For additional information check the [itemCreated](/api/dataviz/treemap#events-itemCreated) event documentation.

#### Example
    <kendo:treeMap>
        <kendo:treeMap-itemCreated>
            <script>
                function(e) {
                    // Code to handle the itemCreated event.
                }
            </script>
        </kendo:treeMap-itemCreated>
    </kendo:treeMap>

### kendo:treeMap-dataBound

Fired when the widget is bound to data from its dataSource.


For additional information check the [dataBound](/api/dataviz/treemap#events-dataBound) event documentation.

#### Example
    <kendo:treeMap>
        <kendo:treeMap-dataBound>
            <script>
                function(e) {
                    // Code to handle the dataBound event.
                }
            </script>
        </kendo:treeMap-dataBound>
    </kendo:treeMap>

