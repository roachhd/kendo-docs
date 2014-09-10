---
title: Circle
page_title: API reference for methods and fields of Kendo UI DataViz Geometry Circle
---

# kendo.dataviz.geometry.Circle

A circle with set center and radius.

## Example - Creating a circle
        <script>
            var geo = kendo.dataviz.geometry;
            var center = new geo.Point(10, 10);
            var rect = new geo.Circle(center, 20);
        </script>

## Example - Creating a circle (short syntax)
        <script>
            var geo = kendo.dataviz.geometry;
            var rect = new geo.Circle([10, 10], 20);
        </script>

## Fields

### center `kendo.dataviz.geometry.Point`

The location of the circle center.


### radius `Number`

The radius of the circle.


## Methods

### bbox

Returns the bounding box of this circle after applying the
specified transformation matrix.

#### Parameters

##### matrix `kendo.dataviz.geometry.Matrix`

Transformation matrix to apply.

#### Returns

`kendo.dataviz.geometry.Rect` The bounding box after applying the transformation matrix.


### clone

Creates a new instance with the same center and radius.

#### Returns

`kendo.dataviz.geometry.Circle` A new Circle instance with the same center and radius.


### equals

Compares this circle with another instance.

#### Parameters

##### other `kendo.dataviz.geometry.Circle`

The circle to compare with.

#### Returns

`Boolean` true if the point coordinates match; false otherwise.


### getCenter

Gets the circle center location.

#### Returns

`kendo.dataviz.geometry.Point` The location of the circle center.


### getRadius

Gets the circle radius.

#### Returns

`Number` The radius of the circle.


### pointAt

Gets the location of a point on the circle's circumference at a given angle.

#### Parameters

##### angle `Number`

Angle in decimal degrees. Measured in clockwise direction with 0 pointing "right".
Negative values or values greater than 360 will be normalized.

#### Returns

`kendo.dataviz.geometry.Point` The point on the circle's circumference.


### setCenter

Sets the location of the circle center.

#### Parameters

##### value `kendo.dataviz.geometry.Point|Array`

The new center Point or equivalent [x, y] array.

#### Returns

`kendo.dataviz.geometry.Point` The location of the circle center.


### setRadius

Sets the circle radius.

#### Parameters

##### value `Number`

The new circle radius.

#### Returns

`kendo.dataviz.geometry.Circle` The current circle instance.

