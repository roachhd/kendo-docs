---
title: Element
page_title: API reference for Kendo UI Drawing API Element
---

# kendo.dataviz.drawing.Element : kendo.Class
An abstract base class representing common members of all drawing elements.

## Constructor Parameters

### options `Object`
The configuration of this Group.

## Configuration

### transform `kendo.dataviz.geometry.Transformation`
The transformation to apply to this element.

### visible `Boolean`
A flag, indicating if the element is visible.

## Fields

### options `kendo.dataviz.drawing.OptionsStore`
The configuration options of the drawing element.

## Methods

### bbox
Returns the bounding box of the element with transformations applied.

#### Returns
`kendo.dataviz.geometry.Rect` The bounding box of the element with transformations applied.


### transform
Gets or sets the transformation of the element.

#### Example - setting transformation on an element
    <div id="surface"></div>
    <script>
        var d = kendo.dataviz.drawing;
        var geo = kendo.dataviz.geometry;

        var path = new d.Path();
        path.moveTo(0, 0).lineTo(100, 100);

        path.transform(geo.transform().scale(2, 1));

        var surface = d.Surface.create($("#surface"));
        surface.draw(path);
    </script>

#### Parameters

##### transform `kendo.dataviz.geometry.Transformation`
The transformation to apply to the element.

#### Returns
`kendo.dataviz.geometry.Transformation` The current transformation on the element.


### visible
Gets or sets the visibility of the element.

#### Parameters

##### visible `Boolean`
A flag indicating if the element should be visible.

#### Returns
`Boolean` true if the element is visible; false otherwise.

