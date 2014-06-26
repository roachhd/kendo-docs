---
title: map-layerDefaults-bubble
---

# \<kendo:map-layerDefaults-bubble\>

The default configuration for bubble layers.

#### Example
    <kendo:map-layerDefaults>
        <kendo:map-layerDefaults-bubble></kendo:map-layerDefaults-bubble>
    </kendo:map-layerDefaults>

## Configuration Attributes

### attribution `java.lang.String`

The attribution for all bubble layers.

#### Example
    <kendo:map-layerDefaults-bubble attribution="attribution">
    </kendo:map-layerDefaults-bubble>

### maxSize `float`

The maximum symbol size for bubble layer symbols.

#### Example
    <kendo:map-layerDefaults-bubble maxSize="maxSize">
    </kendo:map-layerDefaults-bubble>

### minSize `float`

The minimum symbol size for bubble layer symbols.

#### Example
    <kendo:map-layerDefaults-bubble minSize="minSize">
    </kendo:map-layerDefaults-bubble>

### opacity `float`

The the opacity of all bubble layers.

#### Example
    <kendo:map-layerDefaults-bubble opacity="opacity">
    </kendo:map-layerDefaults-bubble>

### symbol `java.lang.String`

The default symbol for bubble layers. Possible values:The function must accept an object with the following fields:
* center - The symbol center on the current layer.
* size - The symbol size.
* style - The symbol style.
* dataItem - The dataItem used to create the symbol.
* location - The location of the data point.The function return value must be a kendo.dataviz.drawing.Shape.

#### Example
    <kendo:map-layerDefaults-bubble symbol="symbol">
    </kendo:map-layerDefaults-bubble>


##  Configuration JSP Tags

### kendo:map-layerDefaults-bubble-style

The default style for bubble layer symbols.

More documentation is available at [kendo:map-layerDefaults-bubble-style](/api/wrappers/jsp/map/layerdefaults-bubble-style).

#### Example

    <kendo:map-layerDefaults-bubble>
        <kendo:map-layerDefaults-bubble-style></kendo:map-layerDefaults-bubble-style>
    </kendo:map-layerDefaults-bubble>


## Event Attributes

### symbol `String`

The default symbol for bubble layers. Possible values:The function must accept an object with the following fields:
* center - The symbol center on the current layer.
* size - The symbol size.
* style - The symbol style.
* dataItem - The dataItem used to create the symbol.
* location - The location of the data point.The function return value must be a kendo.dataviz.drawing.Shape.


#### Example
    <kendo:map-layerDefaults-bubble symbol="handle_symbol">
    </kendo:map-layerDefaults-bubble>
    <script>
        function handle_symbol(e) {
            // Code to handle the symbol event.
        }
    </script>

## Event Tags

### kendo:map-layerDefaults-bubble-symbol

The default symbol for bubble layers. Possible values:The function must accept an object with the following fields:
* center - The symbol center on the current layer.
* size - The symbol size.
* style - The symbol style.
* dataItem - The dataItem used to create the symbol.
* location - The location of the data point.The function return value must be a kendo.dataviz.drawing.Shape.


#### Example
    <kendo:map-layerDefaults-bubble>
        <kendo:map-layerDefaults-bubble-symbol>
            <script>
                function(e) {
                    // Code to handle the symbol event.
                }
            </script>
        </kendo:map-layerDefaults-bubble-symbol>
    </kendo:map-layerDefaults-bubble>

