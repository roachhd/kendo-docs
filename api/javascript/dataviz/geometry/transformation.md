---
title: Transformation
page_title: API reference for methods and fields of Kendo UI DataViz Geometry Transformation
---

# kendo.dataviz.geometry.Transformation

An utility class for building transformation matrices.

## Example - Creating a transformation
        <script>
            var geo = kendo.dataviz.geometry;
            var tr = new geo.Transformation();
            tr.translate(10, 20);
            tr.scale(1, 1.5);
        </script>

## Example - Creating a transformation (short syntax)
        <script>
            var geo = kendo.dataviz.geometry;
            var tr = geo.transform().translate(10, 20).scale(1, 1.5);
        </script>

## Methods

### clone

Creates a new instance with the same transformation matrix.

#### Returns

`kendo.dataviz.geometry.Transformation` A new Transformation instance with the same matrix.


### equals

Compares this transformation with another instance.

#### Parameters

##### other `kendo.dataviz.geometry.Transformation`

The transformation to compare with.

#### Returns

`Boolean` true if the transformation matrix is the same; false otherwise.


### matrix

Gets the current transformation matrix for this transformation.

#### Returns

`kendo.dataviz.geometry.Matrix` The current transformation matrix.


### multiply

Multiplies the transformation with another.
The underlying transformation matrix is updated in-place.

#### Parameters

##### transformation `kendo.dataviz.geometry.Transformation`

The transformation to multiply by.

#### Returns

`kendo.dataviz.geometry.Transformation` The current transformation instance.


### rotate

Sets rotation with the specified parameters.

#### Parameters

##### angle `Number`

The angle of rotation in decimal degrees.
Measured in clockwise direction with 0 pointing "right".
Negative values or values greater than 360 will be normalized.

##### x `Number`

The center of rotation on the X axis.

##### y `Number`

The center of rotation on the Y axis.

#### Returns

`kendo.dataviz.geometry.Transformation` The current transformation instance.


### scale

Sets scale with the specified parameters.

#### Parameters

##### scaleX `Number`

The scale factor on the X axis.

##### scaleY `Number`

The scale factor on the Y axis.

#### Returns

`kendo.dataviz.geometry.Transformation` The current transformation instance.


### translate

Sets translation with the specified parameters.

#### Parameters

##### x `Number`

The distance to translate along the X axis.

##### y `Number`

The distance to translate along the Y axis.

#### Returns

`kendo.dataviz.geometry.Transformation` The current transformation instance.


