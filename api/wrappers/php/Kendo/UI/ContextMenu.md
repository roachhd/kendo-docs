---
title: ContextMenu
---

# \Kendo\UI\ContextMenu

A PHP wrapper for Kendo UI [ContextMenu](/api/web/contextmenu).

Inherits from [\Kendo\UI\Widget](/api/wrappers/php/Kendo/UI/Widget).

## Usage

To use ContextMenu in a PHP page instantiate a new instance, configure it via the available
configuration [methods](#methods) and output it by `echo`-ing the result of the [render](/api/wrappers/php/Kendo/UI/Widget#render) method.

### Using Kendo ContextMenu

    <?php
    // Create a new instance of ContextMenu and specify its id
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');

    // Configure it
    $contextMenu->alignToAnchor(true)

    // Output it

    echo $contextMenu->render();
    ?>


## Methods

### activate
Fires when a sub menu or the ContextMenu gets opened and its animation finished.
For additional information check the [activate](/api/web/contextmenu#events-activate) event documentation.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->activate('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onActivate(e) {
            // handle the activate event.
        }
    </script>
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->activate('onActivate');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->activate(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### alignToAnchor
Specifies that ContextMenu should be shown aligned to the target or the filter element if specified.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->alignToAnchor(true);
    ?>

### animation

A collection of Animation objects, used to change default animations. A value of false will disable all animations in the widget.Available animations for the ContextMenu are listed below.  Each animation has a reverse options which is used for the close effect by default, but can be over-ridden
by setting the close animation. Each animation also has a direction which can be set off the animation (i.e. slideIn:Down).

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `\Kendo\UI\ContextMenuAnimation|array`


#### Example - using [\Kendo\UI\ContextMenuAnimation](/api/wrappers/php/Kendo/UI/ContextMenuAnimation)
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $animation = new \Kendo\UI\ContextMenuAnimation();
    $close = new \Kendo\UI\ContextMenuAnimationClose();
    $animation->close($close);
    $contextMenu->animation($animation);
    ?>

#### Example - using array

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $close = new \Kendo\UI\ContextMenuAnimationClose();
    $contextMenu->animation(array('close' => $close));
    ?>

### close
Fires before a sub menu or the ContextMenu gets closed. You can cancel this event to prevent closure.
For additional information check the [close](/api/web/contextmenu#events-close) event documentation.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->close('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onClose(e) {
            // handle the close event.
        }
    </script>
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->close('onClose');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->close(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### closeOnClick
Specifies that sub menus should close after item selection (provided they won't navigate).

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->closeOnClick(true);
    ?>

### dataSource

Sets the data source of the dataSource.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `\Kendo\Data\DataSource|array`

#### Example - using [\Kendo\Data\DataSource](/api/wrappers/php/kendo/data/datasource)

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $dataSource = new \Kendo\Data\DataSource();
    $contextMenu->dataSource($dataSource);
    ?>

#### Example - using array

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $schema = new \Kendo\Data\DataSourceSchema();
    $contextMenu->dataSource(array('schema' => $schema));
    ?>

### deactivate
Fires when a sub menu or the ContextMenu gets closed and its animation finished.
For additional information check the [deactivate](/api/web/contextmenu#events-deactivate) event documentation.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->deactivate('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onDeactivate(e) {
            // handle the deactivate event.
        }
    </script>
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->deactivate('onDeactivate');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->deactivate(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### direction
Specifies ContextMenu sub menu opening direction. Can be "top", "bottom", "left", "right".
The example below will initialize the sub menus to open to the left.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->direction('value');
    ?>

### filter
Specifies ContextMenu filter selector - the ContextMenu will only be shown on items that satisfy the provided selector.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->filter('value');
    ?>

### hoverDelay
Specifies the delay in ms before the sub menus are opened/closed - used to avoid accidental closure on leaving.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `float`



#### Example 
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->hoverDelay(1);
    ?>

### open
Fires before a sub menu or the ContextMenu gets opened. You can cancel this event to prevent opening the sub menu.
For additional information check the [open](/api/web/contextmenu#events-open) event documentation.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->open('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onOpen(e) {
            // handle the open event.
        }
    </script>
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->open('onOpen');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->open(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### orientation
Root menu orientation. Could be horizontal or vertical.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->orientation('value');
    ?>

### popupCollision
Specifies how ContextMenu should adjust to screen boundaries. By default the strategy is "fit" for a sub menu with a horizontal parent or the root menu,
meaning it will move to fit in screen boundaries in all directions, and "fit flip" for a sub menu with vertical parent, meaning it will fit vertically and flip over
its parent horizontally. You can also switch off the screen boundary detection completely if you set the popupCollision to false.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->popupCollision('value');
    ?>

### select
Fires when a menu item gets selected.
For additional information check the [select](/api/web/contextmenu#events-select) event documentation.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`

#### Example - using string which defines a JavaScript function

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->select('function(e) { }');
    ?>

#### Example - using string which defines a JavaScript name
    <script>
        function onSelect(e) {
            // handle the select event.
        }
    </script>
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->select('onSelect');
    ?>

#### Example - using [\Kendo\JavaScriptFunction](/api/wrappers/php/kendo/javascriptfunction)

    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->select(new \Kendo\JavaScriptFunction('function(e) { }'));
    ?>

### showOn
Specifies the event or events on which ContextMenu should open. By default ContextMenu will show on contextmenu event on desktop and hold event on touch devices.
Could be any pointer/mouse/touch event, also several, separated by spaces.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->showOn('value');
    ?>

### target
Specifies the element on which ContextMenu should open. The default element is the document body.

#### Returns
`\Kendo\UI\ContextMenu`

#### Parameters

##### $value `string|`



#### Example  - using string
    <?php
    $contextMenu = new \Kendo\UI\ContextMenu('ContextMenu');
    $contextMenu->target('value');
    ?>

