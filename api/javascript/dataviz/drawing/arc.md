---
title: Arc
page_title: API reference for Kendo UI Drawing API Arc
---

# kendo.dataviz.drawing.Arc : kendo.dataviz.drawing.Element
Draws an arc with set geometry, fill and stroke.

#### Example - creating an arc
    <div id="surface"></div>
    <script>
        var d = kendo.dataviz.drawing;
        var geo = kendo.dataviz.geometry;

        var arcGeometry = new geo.Arc([100, 100], {
            radiusX: 10,
            radiusY: 10,
            startAngle: 45,
            endAngle: 135
        });
        var arc = new d.Arc(arcGeometry).stroke("red", 1);

        var surface = d.Surface.create($("#surface"));
        surface.draw(arc);
    </script>

## Constructor Parameters

### geometry `kendo.dataviz.geometry.Arc`
The geometric object that defines the arc parameters.

### options `Object`
The configuration options.

## Configuration

### fill `kendo.dataviz.drawing.FillOptions`
The fill options of the shape.

### stroke `kendo.dataviz.drawing.StrokeOptions`
The stroke options of the shape.

### transform `kendo.dataviz.geometry.Transformation`
The transformation to apply to this element.
Inherited from [Element.transform](element#configuration-transform)

### visible `Boolean`
A flag, indicating if the element is visible.
Inherited from [Element.visible](element#configuration-visible)

## Methods

### bbox
Returns the bounding box of the element with transformations applied.
Inherited from [Element.bbox](element#methods-bbox)

#### Returns
`kendo.dataviz.geometry.Rect` The bounding box of the element with transformations applied.


### geometry
Gets or sets the arc geometry.

#### Parameters

##### value `kendo.dataviz.geometry.Arc`
The new geometry to use.

#### Returns
`kendo.dataviz.geometry.Arc` The current arc geometry.


### fill
Sets the shape [fill](#configuration-fill).

#### Parameters

##### color `String`
The [fill color](fill-options#fields-color) to set.

##### opacity `Number` *optional*
The [fill opacity](fill-options#fields-opacity) to set.

#### Returns
`kendo.dataviz.drawing.Arc` The current instance to allow chaining.


### stroke
Sets the shape [stroke](#configuration-stroke).

#### Parameters

##### color `String`
The [stroke color](stroke-options#fields-color) to set.

##### width `Number` *optional*
The [stroke width](stroke-options#fields-width) to set.

##### opacity `Number` *optional*
The [stroke opacity](stroke-options#fields-opacity) to set.

#### Returns
`kendo.dataviz.drawing.Arc` The current instance to allow chaining.


### transform
Gets or sets the transformation of the element.
Inherited from [Element.transform](element#methods-transform)

#### Parameters

##### transform `kendo.dataviz.geometry.Transformation`
The transformation to apply to the element.

#### Returns
`kendo.dataviz.geometry.Transformation` The current transformation on the element.


### visible
Gets or sets the visibility of the element.
Inherited from [Element.visible](element#methods-visible)

#### Parameters

##### visible `Boolean`
A flag indicating if the element should be visible.

#### Returns
`Boolean` true if the element is visible; false otherwise.
