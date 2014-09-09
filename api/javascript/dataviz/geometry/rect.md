---
title: Rect
page_title: API reference for methods and fields of Kendo UI DataViz Geometry Rectangle
---

# kendo.dataviz.geometry.Rect

A rectangle with set origin (top-left corner) and size.

## Example - Creating a rectangle
        <script>
            var geo = kendo.dataviz.geometry;
            var origin = new geo.Point(10, 10);
            var size = new geo.Size(20, 20);
            var rect = new geo.Rect(origin, size);
        </script>

## Example - Creating a rectangle (short syntax)
        <script>
            var geo = kendo.dataviz.geometry;
            var rect = new geo.Rect([10, 10], [20, 20]);
        </script>

## Fields

### origin `kendo.dataviz.geometry.Point`

The origin (top-left corner) of the rectangle.


### size `kendo.dataviz.geometry.Size`

The size of the rectangle.


## Class methods

### fromPoints

Creates a Rect instance that contains the points given as arguments.

#### Parameters

##### pointA `kendo.dataviz.geometry.Point`

The first point.

##### pointB `kendo.dataviz.geometry.Point`

The second point.

Multiple arguments are accepted.

#### Returns

`kendo.dataviz.geometry.Rect` The new Rect instance.


### union

Creates a new Rect instance that encloses the two rectangles given as arguments.

#### Parameters

##### rectA `kendo.dataviz.geometry.Rect`

The first rectangle.

##### rectB `kendo.dataviz.geometry.Rect`

The second rectangle.

#### Returns

`kendo.dataviz.geometry.Rect` The new Rect instance.


## Methods

### bbox

Returns the bounding box of this rectangle after applying the
specified transformation matrix.

#### Parameters

##### matrix `kendo.dataviz.geometry.Matrix`

Transformation matrix to apply.

#### Returns

`kendo.dataviz.geometry.Rect` The bounding box after applying the transformation matrix.


### bottomLeft

Gets the position of the bottom-left corner of the rectangle.
This is also the rectangle origin

#### Returns

`kendo.dataviz.geometry.Point` The position of the bottom-left corner.


### bottomRight

Gets the position of the bottom-right corner of the rectangle.

#### Returns

`kendo.dataviz.geometry.Point` The position of the bottom-right corner.


### center

Gets the position of the center of the rectangle.

#### Returns

`kendo.dataviz.geometry.Point` The position of the center.


### clone

Creates a new instance with the same origin and size.

#### Returns

`kendo.dataviz.geometry.Rect` A new Rect instance with the same origin and size.


### equals

Compares this rectangle with another instance.

#### Parameters

##### other `kendo.dataviz.geometry.Rect`

The rectangle to compare with.

#### Returns

`Boolean` true if the origin and size is the same for both rectangles; false otherwise.


### getOrigin

Gets the origin (top-left point) of the rectangle.

#### Returns

`kendo.dataviz.geometry.Point` The origin (top-left point).


### getSize

Gets the rectangle size.

#### Returns

`kendo.dataviz.geometry.Size` The current rectangle Size.


### height

Gets the rectangle height.

#### Returns

`Number` The rectangle height.


### setOrigin

Sets the origin (top-left point) of the rectangle.

#### Parameters

##### value `kendo.dataviz.geometry.Point|Array`

The new origin Point or equivalent [x, y] array.

#### Returns

`kendo.dataviz.geometry.Rect` The current rectangle instance.


### setSize

Sets the rectangle size.

#### Parameters

##### value `kendo.dataviz.geometry.Size|Array`

The new rectangle Size or equivalent [width, height] array.

#### Returns

`kendo.dataviz.geometry.Rect` The current rectangle instance.


### topLeft

Gets the position of the top-left corner of the rectangle.
This is also the rectangle origin

#### Returns

`kendo.dataviz.geometry.Point` The position of the top-left corner.


### topRight

Gets the position of the top-right corner of the rectangle.

#### Returns

`kendo.dataviz.geometry.Point` The position of the top-right corner.


### width

Gets the rectangle width.

#### Returns

`Number` The rectangle width.

