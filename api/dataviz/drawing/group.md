---
title: Group
page_title: API reference for Kendo UI Drawing API Group
---

# kendo.dataviz.drawing.Group : kendo.dataviz.drawing.Element
Represents a set of drawing elements, possibly including other groups.

#### Example - creating a group
    <div id="surface"></div>
    <script>
        var d = kendo.dataviz.drawing;
        var group = new d.Group();

        var pathA = new d.Path().moveTo(0, 0).lineTo(100, 100);
        var pathB = new d.Path().moveTo(0, 100).lineTo(100, 0);

        group.append(pathA, pathB);

        var surface = d.Surface.create($("#surface"));
        surface.draw(group);
    </script>

## Constructor Parameters

### options `Object`
The configuration of this Group.

## Fields

### children `Array`
The children of this group.

## Methods

### append
Appends the specified element as a last child of the group.

#### Parameters

##### element `kendo.dataviz.drawing.Element`
The element to append. Multiple parameters are accepted.


### clear
Removes all child elements from the group.


### remove
Removes the specified element from the group.

#### Parameters

##### element `kendo.dataviz.drawing.Element`
The element to remove.


### removeAt
Removes the child element at the specified position.

#### Parameters

##### index `Number`
The index at which the element currently resides.


### visible
Gets or sets the visibility of the element.

#### Parameters

##### visible `Boolean`
A flag indicating if the element should be visible.

#### Returns
`Boolean` true if the element is visible; false otherwise.

