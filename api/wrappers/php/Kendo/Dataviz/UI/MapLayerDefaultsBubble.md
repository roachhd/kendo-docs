---
title: MapLayerDefaultsBubble
---

# \Kendo\Dataviz\UI\MapLayerDefaultsBubble

A PHP class representing the bubble setting of MapLayerDefaults.


## Methods

### attribution
The attribution for all bubble layers.

#### Returns
`\Kendo\Dataviz\UI\MapLayerDefaultsBubble`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $bubble = new \Kendo\Dataviz\UI\MapLayerDefaultsBubble();
    $bubble->attribution('value');
    ?>

### maxSize
The maximum symbol size for bubble layer symbols.

#### Returns
`\Kendo\Dataviz\UI\MapLayerDefaultsBubble`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $bubble = new \Kendo\Dataviz\UI\MapLayerDefaultsBubble();
    $bubble->maxSize(1);
    ?>

### minSize
The minimum symbol size for bubble layer symbols.

#### Returns
`\Kendo\Dataviz\UI\MapLayerDefaultsBubble`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $bubble = new \Kendo\Dataviz\UI\MapLayerDefaultsBubble();
    $bubble->minSize(1);
    ?>

### opacity
The the opacity of all bubble layers.

#### Returns
`\Kendo\Dataviz\UI\MapLayerDefaultsBubble`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $bubble = new \Kendo\Dataviz\UI\MapLayerDefaultsBubble();
    $bubble->opacity(1);
    ?>

### style

The default style for bubble layer symbols.

#### Returns
`\Kendo\Dataviz\UI\MapLayerDefaultsBubble`

#### Parameters

##### $value `\Kendo\Dataviz\UI\MapLayerDefaultsBubbleStyle|array`


#### Example - using [\Kendo\Dataviz\UI\MapLayerDefaultsBubbleStyle](/api/wrappers/php/Kendo/Dataviz/UI/MapLayerDefaultsBubbleStyle)
    <?php
    $bubble = new \Kendo\Dataviz\UI\MapLayerDefaultsBubble();
    $style = new \Kendo\Dataviz\UI\MapLayerDefaultsBubbleStyle();
    $fill = new \Kendo\Dataviz\UI\MapLayerDefaultsBubbleStyleFill();
    $style->fill($fill);
    $bubble->style($style);
    ?>

#### Example - using array

    <?php
    $bubble = new \Kendo\Dataviz\UI\MapLayerDefaultsBubble();
    $fill = new \Kendo\Dataviz\UI\MapLayerDefaultsBubbleStyleFill();
    $bubble->style(array('fill' => $fill));
    ?>

### symbol
The default symbol for bubble layers. Possible values:The function must accept an object with the following fields:
* center - The symbol center on the current layer.
* size - The symbol size.
* style - The symbol style.
* dataItem - The dataItem used to create the symbol.
* location - The location of the data point.The function return value must be a kendo.dataviz.drawing.Shape.

#### Returns
`\Kendo\Dataviz\UI\MapLayerDefaultsBubble`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`



#### Example  - using string
    <?php
    $bubble = new \Kendo\Dataviz\UI\MapLayerDefaultsBubble();
    $bubble->symbol('value');
    ?>

#### Example  - using \Kendo\JavaScriptFunction
    <?php
    $bubble = new \Kendo\Dataviz\UI\MapLayerDefaultsBubble();
    $bubble->symbol(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

