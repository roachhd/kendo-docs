---
title: map
---

# \<kendo:map\>
A JSP wrapper for Kendo UI [Map](/api/dataviz/map).

## Configuration Attributes

### center `java.lang.Object`

The map center. Coordinates are listed as [Latitude, Longitude].

#### Example
    <kendo:map center="center">
    </kendo:map>

### maxZoom `float`

The maximum zoom level.
Typical web maps use zoom levels from 0 (whole world) to 19 (sub-meter features).

#### Example
    <kendo:map maxZoom="maxZoom">
    </kendo:map>

### minSize `float`

The size of the map in pixels at zoom level 0.

#### Example
    <kendo:map minSize="minSize">
    </kendo:map>

### minZoom `float`

The minimum zoom level.
Typical web maps use zoom levels from 0 (whole world) to 19 (sub-meter features).

#### Example
    <kendo:map minZoom="minZoom">
    </kendo:map>

### pannable `boolean`

Controls whether the user can pan the map.

#### Example
    <kendo:map pannable="pannable">
    </kendo:map>

### wraparound `boolean`

Specifies whether the map should wrap around the east-west edges.

#### Example
    <kendo:map wraparound="wraparound">
    </kendo:map>

### zoom `float`

The initial zoom level.Typical web maps use zoom levels from 0 (whole world) to 19 (sub-meter features).The map size is derived from the zoom level and minScale options: size = (2 ^ zoom) * minSize

#### Example
    <kendo:map zoom="zoom">
    </kendo:map>

### zoomable `boolean`

Controls whether the map zoom level can be changed by the user.

#### Example
    <kendo:map zoomable="zoomable">
    </kendo:map>


##  Configuration JSP Tags

### kendo:map-controls

The configuration of built-in map controls.

More documentation is available at [kendo:map-controls](/api/wrappers/jsp/map/controls).

#### Example

    <kendo:map>
        <kendo:map-controls></kendo:map-controls>
    </kendo:map>

### kendo:map-layerDefaults

The default configuration for map layers by type.

More documentation is available at [kendo:map-layerDefaults](/api/wrappers/jsp/map/layerdefaults).

#### Example

    <kendo:map>
        <kendo:map-layerDefaults></kendo:map-layerDefaults>
    </kendo:map>

### kendo:map-layers

The configuration of the map layers.
The layer type is determined by the value of the type field.

More documentation is available at [kendo:map-layers](/api/wrappers/jsp/map/layers).

#### Example

    <kendo:map>
        <kendo:map-layers></kendo:map-layers>
    </kendo:map>

### kendo:map-markerDefaults

The default options for all markers.

More documentation is available at [kendo:map-markerDefaults](/api/wrappers/jsp/map/markerdefaults).

#### Example

    <kendo:map>
        <kendo:map-markerDefaults></kendo:map-markerDefaults>
    </kendo:map>

### kendo:map-markers

Static markers to display on the map.

More documentation is available at [kendo:map-markers](/api/wrappers/jsp/map/markers).

#### Example

    <kendo:map>
        <kendo:map-markers></kendo:map-markers>
    </kendo:map>


## Event Attributes

### beforeReset `String`

Fired immediately before the map is reset.
This event is typically used for cleanup by layer implementers.


For additional information check the [beforeReset](/api/dataviz/map#events-beforeReset) event documentation.

#### Example
    <kendo:map beforeReset="handle_beforeReset">
    </kendo:map>
    <script>
        function handle_beforeReset(e) {
            // Code to handle the beforeReset event.
        }
    </script>

### click `String`

Fired when the user clicks on the map.


For additional information check the [click](/api/dataviz/map#events-click) event documentation.

#### Example
    <kendo:map click="handle_click">
    </kendo:map>
    <script>
        function handle_click(e) {
            // Code to handle the click event.
        }
    </script>

### markerCreated `String`

Fired when a marker has been created and is about to be displayed.
Cancelling the event will prevent the marker from being shown.


For additional information check the [markerCreated](/api/dataviz/map#events-markerCreated) event documentation.

#### Example
    <kendo:map markerCreated="handle_markerCreated">
    </kendo:map>
    <script>
        function handle_markerCreated(e) {
            // Code to handle the markerCreated event.
        }
    </script>

### pan `String`

Fired while the map viewport is being moved.


For additional information check the [pan](/api/dataviz/map#events-pan) event documentation.

#### Example
    <kendo:map pan="handle_pan">
    </kendo:map>
    <script>
        function handle_pan(e) {
            // Code to handle the pan event.
        }
    </script>

### panEnd `String`

Fires after the map viewport has been moved.


For additional information check the [panEnd](/api/dataviz/map#events-panEnd) event documentation.

#### Example
    <kendo:map panEnd="handle_panEnd">
    </kendo:map>
    <script>
        function handle_panEnd(e) {
            // Code to handle the panEnd event.
        }
    </script>

### reset `String`

Fired when the map is reset.
This typically occurs on initial load and after a zoom/center change.


For additional information check the [reset](/api/dataviz/map#events-reset) event documentation.

#### Example
    <kendo:map reset="handle_reset">
    </kendo:map>
    <script>
        function handle_reset(e) {
            // Code to handle the reset event.
        }
    </script>

### shapeClick `String`

Fired when a shape is clicked or tapped.


For additional information check the [shapeClick](/api/dataviz/map#events-shapeClick) event documentation.

#### Example
    <kendo:map shapeClick="handle_shapeClick">
    </kendo:map>
    <script>
        function handle_shapeClick(e) {
            // Code to handle the shapeClick event.
        }
    </script>

### shapeCreated `String`

Fired when a shape is created, but is not rendered yet.


For additional information check the [shapeCreated](/api/dataviz/map#events-shapeCreated) event documentation.

#### Example
    <kendo:map shapeCreated="handle_shapeCreated">
    </kendo:map>
    <script>
        function handle_shapeCreated(e) {
            // Code to handle the shapeCreated event.
        }
    </script>

### shapeMouseEnter `String`

Fired when the mouse enters a shape.


For additional information check the [shapeMouseEnter](/api/dataviz/map#events-shapeMouseEnter) event documentation.

#### Example
    <kendo:map shapeMouseEnter="handle_shapeMouseEnter">
    </kendo:map>
    <script>
        function handle_shapeMouseEnter(e) {
            // Code to handle the shapeMouseEnter event.
        }
    </script>

### shapeMouseLeave `String`

Fired when the mouse leaves a shape.


For additional information check the [shapeMouseLeave](/api/dataviz/map#events-shapeMouseLeave) event documentation.

#### Example
    <kendo:map shapeMouseLeave="handle_shapeMouseLeave">
    </kendo:map>
    <script>
        function handle_shapeMouseLeave(e) {
            // Code to handle the shapeMouseLeave event.
        }
    </script>

### zoomStart `String`

Fired when the map zoom level is about to change.
Cancelling the event will prevent the user action.


For additional information check the [zoomStart](/api/dataviz/map#events-zoomStart) event documentation.

#### Example
    <kendo:map zoomStart="handle_zoomStart">
    </kendo:map>
    <script>
        function handle_zoomStart(e) {
            // Code to handle the zoomStart event.
        }
    </script>

### zoomEnd `String`

Fired when the map zoom level has changed.


For additional information check the [zoomEnd](/api/dataviz/map#events-zoomEnd) event documentation.

#### Example
    <kendo:map zoomEnd="handle_zoomEnd">
    </kendo:map>
    <script>
        function handle_zoomEnd(e) {
            // Code to handle the zoomEnd event.
        }
    </script>

## Event Tags

### kendo:map-beforeReset

Fired immediately before the map is reset.
This event is typically used for cleanup by layer implementers.


For additional information check the [beforeReset](/api/dataviz/map#events-beforeReset) event documentation.

#### Example
    <kendo:map>
        <kendo:map-beforeReset>
            <script>
                function(e) {
                    // Code to handle the beforeReset event.
                }
            </script>
        </kendo:map-beforeReset>
    </kendo:map>

### kendo:map-click

Fired when the user clicks on the map.


For additional information check the [click](/api/dataviz/map#events-click) event documentation.

#### Example
    <kendo:map>
        <kendo:map-click>
            <script>
                function(e) {
                    // Code to handle the click event.
                }
            </script>
        </kendo:map-click>
    </kendo:map>

### kendo:map-markerCreated

Fired when a marker has been created and is about to be displayed.
Cancelling the event will prevent the marker from being shown.


For additional information check the [markerCreated](/api/dataviz/map#events-markerCreated) event documentation.

#### Example
    <kendo:map>
        <kendo:map-markerCreated>
            <script>
                function(e) {
                    // Code to handle the markerCreated event.
                }
            </script>
        </kendo:map-markerCreated>
    </kendo:map>

### kendo:map-pan

Fired while the map viewport is being moved.


For additional information check the [pan](/api/dataviz/map#events-pan) event documentation.

#### Example
    <kendo:map>
        <kendo:map-pan>
            <script>
                function(e) {
                    // Code to handle the pan event.
                }
            </script>
        </kendo:map-pan>
    </kendo:map>

### kendo:map-panEnd

Fires after the map viewport has been moved.


For additional information check the [panEnd](/api/dataviz/map#events-panEnd) event documentation.

#### Example
    <kendo:map>
        <kendo:map-panEnd>
            <script>
                function(e) {
                    // Code to handle the panEnd event.
                }
            </script>
        </kendo:map-panEnd>
    </kendo:map>

### kendo:map-reset

Fired when the map is reset.
This typically occurs on initial load and after a zoom/center change.


For additional information check the [reset](/api/dataviz/map#events-reset) event documentation.

#### Example
    <kendo:map>
        <kendo:map-reset>
            <script>
                function(e) {
                    // Code to handle the reset event.
                }
            </script>
        </kendo:map-reset>
    </kendo:map>

### kendo:map-shapeClick

Fired when a shape is clicked or tapped.


For additional information check the [shapeClick](/api/dataviz/map#events-shapeClick) event documentation.

#### Example
    <kendo:map>
        <kendo:map-shapeClick>
            <script>
                function(e) {
                    // Code to handle the shapeClick event.
                }
            </script>
        </kendo:map-shapeClick>
    </kendo:map>

### kendo:map-shapeCreated

Fired when a shape is created, but is not rendered yet.


For additional information check the [shapeCreated](/api/dataviz/map#events-shapeCreated) event documentation.

#### Example
    <kendo:map>
        <kendo:map-shapeCreated>
            <script>
                function(e) {
                    // Code to handle the shapeCreated event.
                }
            </script>
        </kendo:map-shapeCreated>
    </kendo:map>

### kendo:map-shapeMouseEnter

Fired when the mouse enters a shape.


For additional information check the [shapeMouseEnter](/api/dataviz/map#events-shapeMouseEnter) event documentation.

#### Example
    <kendo:map>
        <kendo:map-shapeMouseEnter>
            <script>
                function(e) {
                    // Code to handle the shapeMouseEnter event.
                }
            </script>
        </kendo:map-shapeMouseEnter>
    </kendo:map>

### kendo:map-shapeMouseLeave

Fired when the mouse leaves a shape.


For additional information check the [shapeMouseLeave](/api/dataviz/map#events-shapeMouseLeave) event documentation.

#### Example
    <kendo:map>
        <kendo:map-shapeMouseLeave>
            <script>
                function(e) {
                    // Code to handle the shapeMouseLeave event.
                }
            </script>
        </kendo:map-shapeMouseLeave>
    </kendo:map>

### kendo:map-zoomStart

Fired when the map zoom level is about to change.
Cancelling the event will prevent the user action.


For additional information check the [zoomStart](/api/dataviz/map#events-zoomStart) event documentation.

#### Example
    <kendo:map>
        <kendo:map-zoomStart>
            <script>
                function(e) {
                    // Code to handle the zoomStart event.
                }
            </script>
        </kendo:map-zoomStart>
    </kendo:map>

### kendo:map-zoomEnd

Fired when the map zoom level has changed.


For additional information check the [zoomEnd](/api/dataviz/map#events-zoomEnd) event documentation.

#### Example
    <kendo:map>
        <kendo:map-zoomEnd>
            <script>
                function(e) {
                    // Code to handle the zoomEnd event.
                }
            </script>
        </kendo:map-zoomEnd>
    </kendo:map>

