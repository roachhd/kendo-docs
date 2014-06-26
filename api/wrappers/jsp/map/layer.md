---
title: map-layer
---

# \<kendo:map-layer\>

The configuration of the map layers.
The layer type is determined by the value of the type field.

#### Example
    <kendo:map-layers>
        <kendo:map-layer></kendo:map-layer>
    </kendo:map-layers>

## Configuration Attributes

### attribution `java.lang.String`

The attribution for the layer. Accepts valid HTML.

#### Example
    <kendo:map-layer attribution="attribution">
    </kendo:map-layer>

### autoBind `boolean`

If set to false the layer will not bind to the data source during initialization. In this case data binding will occur when the change event of the
data source is fired. By default the widget will bind to the data source specified in the configuration.

#### Example
    <kendo:map-layer autoBind="autoBind">
    </kendo:map-layer>

### extent `java.lang.Object`

Specifies the extent of the region covered by this layer.
The layer will be hidden when the specified area is out of view.Accepts a four-element array that specifies the extent covered by this layer:
North-West lat, longitude, South-East latitude, longitude.If not specified, the layer is always visible.

#### Example
    <kendo:map-layer extent="extent">
    </kendo:map-layer>

### imagerySet `java.lang.String`

The bing map tile types. Possible options.

#### Example
    <kendo:map-layer imagerySet="imagerySet">
    </kendo:map-layer>

### key `java.lang.String`

The API key for the layer. Currently supported only for Bing (tm) tile layers.

#### Example
    <kendo:map-layer key="key">
    </kendo:map-layer>

### locationField `java.lang.String`

The data item field which contains the marker (symbol) location.
The field should be an array with two numbers - latitude and longitude in decimal degrees.Requires the dataSource option to be set.Only applicable to "marker" and "bubble" layers.

#### Example
    <kendo:map-layer locationField="locationField">
    </kendo:map-layer>

### maxSize `float`

The maximum symbol size for bubble layer symbols.

#### Example
    <kendo:map-layer maxSize="maxSize">
    </kendo:map-layer>

### minSize `float`

The minimum symbol size for bubble layer symbols.

#### Example
    <kendo:map-layer minSize="minSize">
    </kendo:map-layer>

### opacity `float`

The the opacity for the layer.

#### Example
    <kendo:map-layer opacity="opacity">
    </kendo:map-layer>

### shape `java.lang.String`

The marker shape. Supported shapes are "pin" and "pinTarget".

#### Example
    <kendo:map-layer shape="shape">
    </kendo:map-layer>

### subdomains `java.lang.Object`

A list of subdomains to use for loading tiles.
Alternating between different subdomains allows more requests to be executed in parallel.

#### Example
    <kendo:map-layer subdomains="subdomains">
    </kendo:map-layer>

### symbol `java.lang.String`

The symbol to use for bubble layers. Possible values:The function must accept an object with the following fields:
* center - The symbol center on the current layer.
* size - The symbol size.
* style - The symbol style.
* dataItem - The dataItem used to create the symbol.
* location - The location of the data point.The function return value must be a kendo.dataviz.drawing.Shape.

#### Example
    <kendo:map-layer symbol="symbol">
    </kendo:map-layer>

### titleField `java.lang.String`

The data item field which contains the marker title.
Requires the dataSource option to be set.

#### Example
    <kendo:map-layer titleField="titleField">
    </kendo:map-layer>

### type `java.lang.String`

The layer type. Supported types are "tile" and "shape".

#### Example
    <kendo:map-layer type="type">
    </kendo:map-layer>

### urlTemplate `java.lang.String`

The URL template for tile layers. Template variables:

#### Example
    <kendo:map-layer urlTemplate="urlTemplate">
    </kendo:map-layer>

### valueField `java.lang.String`

The value field for bubble layer symbols.
The data item field should be a number.

#### Example
    <kendo:map-layer valueField="valueField">
    </kendo:map-layer>


##  Configuration JSP Tags

### kendo:map-layer-style

The default style for shapes.

More documentation is available at [kendo:map-layer-style](/api/wrappers/jsp/map/layer-style).

#### Example

    <kendo:map-layer>
        <kendo:map-layer-style></kendo:map-layer-style>
    </kendo:map-layer>

### kendo:map-layer-tooltip

The default Kendo UI Tooltip options for data-bound markers.

More documentation is available at [kendo:map-layer-tooltip](/api/wrappers/jsp/map/layer-tooltip).

#### Example

    <kendo:map-layer>
        <kendo:map-layer-tooltip></kendo:map-layer-tooltip>
    </kendo:map-layer>


## Event Attributes

### symbol `String`

The symbol to use for bubble layers. Possible values:The function must accept an object with the following fields:
* center - The symbol center on the current layer.
* size - The symbol size.
* style - The symbol style.
* dataItem - The dataItem used to create the symbol.
* location - The location of the data point.The function return value must be a kendo.dataviz.drawing.Shape.


#### Example
    <kendo:map-layer symbol="handle_symbol">
    </kendo:map-layer>
    <script>
        function handle_symbol(e) {
            // Code to handle the symbol event.
        }
    </script>

## Event Tags

### kendo:map-layer-symbol

The symbol to use for bubble layers. Possible values:The function must accept an object with the following fields:
* center - The symbol center on the current layer.
* size - The symbol size.
* style - The symbol style.
* dataItem - The dataItem used to create the symbol.
* location - The location of the data point.The function return value must be a kendo.dataviz.drawing.Shape.


#### Example
    <kendo:map-layer>
        <kendo:map-layer-symbol>
            <script>
                function(e) {
                    // Code to handle the symbol event.
                }
            </script>
        </kendo:map-layer-symbol>
    </kendo:map-layer>

