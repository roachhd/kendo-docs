---
title: TreeMap
---

# \Kendo\Dataviz\UI\TreeMap

A PHP wrapper for Kendo UI [TreeMap](/api/dataviz/treemap).

Inherits from [\Kendo\UI\Widget](/api/wrappers/php/Kendo/UI/Widget).

## Usage

To use TreeMap in a PHP page instantiate a new instance, configure it via the available
configuration [methods](#methods) and output it by `echo`-ing the result of the [render](/api/wrappers/php/Kendo/UI/Widget#render) method.

### Using Kendo TreeMap

    <?php
    // Create a new instance of TreeMap and specify its id
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');

    // Configure it
    $treeMap->autoBind(true)

    // Output it

    echo $treeMap->render();
    ?>


## Methods

### autoBind
If set to false the widget will not bind to the data source during initialization. In this case data binding will occur when the change event of the
data source is fired. By default the widget will bind to the data source specified in the configuration.

#### Returns
`\Kendo\Dataviz\UI\TreeMap`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->autoBind(true);
    ?>

### colorField
The data item field which contains the tile color.

#### Returns
`\Kendo\Dataviz\UI\TreeMap`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->colorField('value');
    ?>

### colors
The default colors for the treemap tiles. When all colors are used, new colors are pulled from the start again.

#### Returns
`\Kendo\Dataviz\UI\TreeMap`

#### Parameters

##### $value `array`



#### Example 
    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->colors(new array());
    ?>

### dataBound
Fired when the widget is bound to data from its dataSource.
For additional information check the [dataBound](/api/dataviz/treemap#events-dataBound) event documentation.

#### Returns
`\Kendo\Dataviz\UI\TreeMap`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->dataBound('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onDataBound(e) {
            // handle the dataBound event.
        }
    </script>
    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->dataBound('onDataBound');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->dataBound(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### dataSource

Sets the data source of the dataSource.

#### Returns
`\Kendo\Dataviz\UI\TreeMap`

#### Parameters

##### $value `\Kendo\Data\DataSource|array`

#### Example - using [\Kendo\Data\DataSource](/api/wrappers/php/kendo/data/datasource)

    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $dataSource = new \Kendo\Data\DataSource();
    $treeMap->dataSource($dataSource);
    ?>

#### Example - using array

    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $schema = new \Kendo\Data\DataSourceSchema();
    $treeMap->dataSource(array('schema' => $schema));
    ?>

### itemCreated
Fired when a tile has been created.
For additional information check the [itemCreated](/api/dataviz/treemap#events-itemCreated) event documentation.

#### Returns
`\Kendo\Dataviz\UI\TreeMap`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->itemCreated('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onItemCreated(e) {
            // handle the itemCreated event.
        }
    </script>
    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->itemCreated('onItemCreated');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->itemCreated(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### template
The template which renders the treeMap tile content.The fields which can be used in the template are:

#### Returns
`\Kendo\Dataviz\UI\TreeMap`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`



#### Example  - using string
    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->template('value');
    ?>

#### Example  - using \Kendo\JavaScriptFunction
    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->template(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

### textField
The data item field which contains the tile title.

#### Returns
`\Kendo\Dataviz\UI\TreeMap`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->textField('value');
    ?>

### type
The layout type for the Treemap.The Supported values are:

#### Returns
`\Kendo\Dataviz\UI\TreeMap`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->type('value');
    ?>

### valueField
The data item field which contains the tile value.

#### Returns
`\Kendo\Dataviz\UI\TreeMap`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $treeMap = new \Kendo\Dataviz\UI\TreeMap('TreeMap');
    $treeMap->valueField('value');
    ?>

