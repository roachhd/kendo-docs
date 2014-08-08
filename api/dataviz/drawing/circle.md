---
title: Circle
page_title: API reference for Kendo UI Drawing API Circle
---

# kendo.dataviz.drawing.Circle : kendo.dataviz.drawing.Element
Draws a circle with set geometry, fill and stroke.

#### Example - creating a circle
    <div id="surface"></div>
    <script>
        var d = kendo.dataviz.drawing;
        var geo = kendo.dataviz.geometry;

        var circleGeometry = new geo.Circle([100, 100], 20);
        var circle = new d.Circle(circleGeometry).stroke("red", 1);

        var surface = d.Surface.create($("#surface"));
        surface.draw(circle);
    </script>

## Constructor Parameters

### geometry `kendo.dataviz.geometry.Circle`
The geometric object that defines the circle center and radius.

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
Gets or sets the circle geometry.

#### Parameters

##### value `kendo.dataviz.geometry.Circle`
The new geometry to use.

#### Returns
`kendo.dataviz.geometry.Circle` The current circle geometry.


### fill
Sets the shape [fill](#configuration-fill).

#### Parameters

##### color `String`
The [fill color](fill-options#fields-color) to set.

##### opacity `Number` *optional*
The [fill opacity](fill-options#fields-opacity) to set.

#### Returns
`kendo.dataviz.drawing.Circle` The current instance to allow chaining.


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
`kendo.dataviz.drawing.Circle` The current instance to allow chaining.


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
