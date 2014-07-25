---
title: Map
---

# \Kendo\Dataviz\UI\Map

A PHP wrapper for Kendo UI [Map](/api/dataviz/map).

Inherits from [\Kendo\UI\Widget](/api/wrappers/php/Kendo/UI/Widget).

## Usage

To use Map in a PHP page instantiate a new instance, configure it via the available
configuration [methods](#methods) and output it by `echo`-ing the result of the [render](/api/wrappers/php/Kendo/UI/Widget#render) method.

### Using Kendo Map

    <?php
    // Create a new instance of Map and specify its id
    $map = new \Kendo\Dataviz\UI\Map('Map');

    // Configure it
    $map->maxZoom(1)

    // Output it

    echo $map->render();
    ?>


## Methods

### beforeReset
Fired immediately before the map is reset.
This event is typically used for cleanup by layer implementers.
For additional information check the [beforeReset](/api/dataviz/map#events-beforeReset) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->beforeReset('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onBeforeReset(e) {
            // handle the beforeReset event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->beforeReset('onBeforeReset');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->beforeReset(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### center
The map center. Coordinates are listed as [Latitude, Longitude].

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `array`



#### Example 
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->center(new array());
    ?>

### click
Fired when the user clicks on the map.
For additional information check the [click](/api/dataviz/map#events-click) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->click('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onClick(e) {
            // handle the click event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->click('onClick');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->click(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### controls

The configuration of built-in map controls.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `\Kendo\Dataviz\UI\MapControls|array`


#### Example - using [\Kendo\Dataviz\UI\MapControls](/api/wrappers/php/Kendo/Dataviz/UI/MapControls)
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $controls = new \Kendo\Dataviz\UI\MapControls();
    $attribution = true;
    $controls->attribution($attribution);
    $map->controls($controls);
    ?>

#### Example - using array

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $attribution = true;
    $map->controls(array('attribution' => $attribution));
    ?>

### layerDefaults

The default configuration for map layers by type.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `\Kendo\Dataviz\UI\MapLayerDefaults|array`


#### Example - using [\Kendo\Dataviz\UI\MapLayerDefaults](/api/wrappers/php/Kendo/Dataviz/UI/MapLayerDefaults)
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $layerDefaults = new \Kendo\Dataviz\UI\MapLayerDefaults();
    $marker = new \Kendo\Dataviz\UI\MapLayerDefaultsMarker();
    $layerDefaults->marker($marker);
    $map->layerDefaults($layerDefaults);
    ?>

#### Example - using array

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $marker = new \Kendo\Dataviz\UI\MapLayerDefaultsMarker();
    $map->layerDefaults(array('marker' => $marker));
    ?>

### addLayer

Adds one or more MapLayer to the Map.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value[, $value2, ...] `\Kendo\Dataviz\UI\MapLayer|array`

#### Example - using \Kendo\Dataviz\UI\MapLayer

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $layer = new \Kendo\Dataviz\UI\MapLayer();
    $attribution = 'value';
    $layer->attribution($attribution);
    $map->addLayer($layer);
    ?>

#### Example - using array

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $attribution = 'value';
    $map->addLayer(array('attribution' => $attribution));
    ?>

#### Example - adding more than one MapLayer

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $first  = new \Kendo\Dataviz\UI\MapLayer();
    $second = new \Kendo\Dataviz\UI\MapLayer();
    $map->addLayer($first, $second);
    ?>

### markerActivate
Fired when a marker has been displayed.
For additional information check the [markerActivate](/api/dataviz/map#events-markerActivate) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->markerActivate('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onMarkerActivate(e) {
            // handle the markerActivate event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->markerActivate('onMarkerActivate');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->markerActivate(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### markerClick
Fired when a marker has been clicked or tapped.
For additional information check the [markerClick](/api/dataviz/map#events-markerClick) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->markerClick('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onMarkerClick(e) {
            // handle the markerClick event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->markerClick('onMarkerClick');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->markerClick(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### markerCreated
Fired when a marker has been created and is about to be displayed.
Cancelling the event will prevent the marker from being shown.
For additional information check the [markerCreated](/api/dataviz/map#events-markerCreated) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->markerCreated('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onMarkerCreated(e) {
            // handle the markerCreated event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->markerCreated('onMarkerCreated');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->markerCreated(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### markerDefaults

The default options for all markers.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `\Kendo\Dataviz\UI\MapMarkerDefaults|array`


#### Example - using [\Kendo\Dataviz\UI\MapMarkerDefaults](/api/wrappers/php/Kendo/Dataviz/UI/MapMarkerDefaults)
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $markerDefaults = new \Kendo\Dataviz\UI\MapMarkerDefaults();
    $shape = 'value';
    $markerDefaults->shape($shape);
    $map->markerDefaults($markerDefaults);
    ?>

#### Example - using array

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $shape = 'value';
    $map->markerDefaults(array('shape' => $shape));
    ?>

### addMarker

Adds one or more MapMarker to the Map.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value[, $value2, ...] `\Kendo\Dataviz\UI\MapMarker|array`

#### Example - using \Kendo\Dataviz\UI\MapMarker

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $marker = new \Kendo\Dataviz\UI\MapMarker();
    $shape = 'value';
    $marker->shape($shape);
    $map->addMarker($marker);
    ?>

#### Example - using array

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $shape = 'value';
    $map->addMarker(array('shape' => $shape));
    ?>

#### Example - adding more than one MapMarker

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $first  = new \Kendo\Dataviz\UI\MapMarker();
    $second = new \Kendo\Dataviz\UI\MapMarker();
    $map->addMarker($first, $second);
    ?>

### maxZoom
The maximum zoom level.
Typical web maps use zoom levels from 0 (whole world) to 19 (sub-meter features).

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->maxZoom(1);
    ?>

### minSize
The size of the map in pixels at zoom level 0.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->minSize(1);
    ?>

### minZoom
The minimum zoom level.
Typical web maps use zoom levels from 0 (whole world) to 19 (sub-meter features).

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->minZoom(1);
    ?>

### pan
Fired while the map viewport is being moved.
For additional information check the [pan](/api/dataviz/map#events-pan) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->pan('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onPan(e) {
            // handle the pan event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->pan('onPan');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->pan(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### panEnd
Fires after the map viewport has been moved.
For additional information check the [panEnd](/api/dataviz/map#events-panEnd) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->panEnd('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onPanEnd(e) {
            // handle the panEnd event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->panEnd('onPanEnd');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->panEnd(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### pannable
Controls whether the user can pan the map.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->pannable(true);
    ?>

### reset
Fired when the map is reset.
This typically occurs on initial load and after a zoom/center change.
For additional information check the [reset](/api/dataviz/map#events-reset) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->reset('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onReset(e) {
            // handle the reset event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->reset('onReset');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->reset(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### shapeClick
Fired when a shape is clicked or tapped.
For additional information check the [shapeClick](/api/dataviz/map#events-shapeClick) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeClick('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onShapeClick(e) {
            // handle the shapeClick event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeClick('onShapeClick');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeClick(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### shapeCreated
Fired when a shape is created, but is not rendered yet.
For additional information check the [shapeCreated](/api/dataviz/map#events-shapeCreated) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeCreated('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onShapeCreated(e) {
            // handle the shapeCreated event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeCreated('onShapeCreated');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeCreated(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### shapeMouseEnter
Fired when the mouse enters a shape.
For additional information check the [shapeMouseEnter](/api/dataviz/map#events-shapeMouseEnter) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeMouseEnter('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onShapeMouseEnter(e) {
            // handle the shapeMouseEnter event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeMouseEnter('onShapeMouseEnter');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeMouseEnter(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### shapeMouseLeave
Fired when the mouse leaves a shape.
For additional information check the [shapeMouseLeave](/api/dataviz/map#events-shapeMouseLeave) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeMouseLeave('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onShapeMouseLeave(e) {
            // handle the shapeMouseLeave event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeMouseLeave('onShapeMouseLeave');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->shapeMouseLeave(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### wraparound
Specifies whether the map should wrap around the east-west edges.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->wraparound(true);
    ?>

### zoom
The initial zoom level.Typical web maps use zoom levels from 0 (whole world) to 19 (sub-meter features).The map size is derived from the zoom level and minScale options: size = (2 ^ zoom) * minSize

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->zoom(1);
    ?>

### zoomEnd
Fired when the map zoom level has changed.
For additional information check the [zoomEnd](/api/dataviz/map#events-zoomEnd) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->zoomEnd('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onZoomEnd(e) {
            // handle the zoomEnd event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->zoomEnd('onZoomEnd');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->zoomEnd(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### zoomStart
Fired when the map zoom level is about to change.
Cancelling the event will prevent the user action.
For additional information check the [zoomStart](/api/dataviz/map#events-zoomStart) event documentation.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->zoomStart('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onZoomStart(e) {
            // handle the zoomStart event.
        }
    </script>
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->zoomStart('onZoomStart');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->zoomStart(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### zoomable
Controls whether the map zoom level can be changed by the user.

#### Returns
`\Kendo\Dataviz\UI\Map`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $map = new \Kendo\Dataviz\UI\Map('Map');
    $map->zoomable(true);
    ?>

