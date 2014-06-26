---
title: contextMenu
---

# \<kendo:contextMenu\>
A JSP wrapper for Kendo UI [ContextMenu](/api/web/contextmenu).

## Configuration Attributes

### alignToAnchor `boolean`

Specifies that ContextMenu should be shown aligned to the target or the filter element if specified.

#### Example
    <kendo:contextMenu alignToAnchor="alignToAnchor">
    </kendo:contextMenu>

### closeOnClick `boolean`

Specifies that sub menus should close after item selection (provided they won't navigate).

#### Example
    <kendo:contextMenu closeOnClick="closeOnClick">
    </kendo:contextMenu>

### direction `java.lang.String`

Specifies ContextMenu sub menu opening direction. Can be "top", "bottom", "left", "right".
The example below will initialize the sub menus to open to the left.

#### Example
    <kendo:contextMenu direction="direction">
    </kendo:contextMenu>

### filter `java.lang.String`

Specifies ContextMenu filter selector - the ContextMenu will only be shown on items that satisfy the provided selector.

#### Example
    <kendo:contextMenu filter="filter">
    </kendo:contextMenu>

### hoverDelay `float`

Specifies the delay in ms before the sub menus are opened/closed - used to avoid accidental closure on leaving.

#### Example
    <kendo:contextMenu hoverDelay="hoverDelay">
    </kendo:contextMenu>

### orientation `java.lang.String`

Root menu orientation. Could be horizontal or vertical.

#### Example
    <kendo:contextMenu orientation="orientation">
    </kendo:contextMenu>

### popupCollision `java.lang.String`

Specifies how ContextMenu should adjust to screen boundaries. By default the strategy is "fit" for a sub menu with a horizontal parent or the root menu,
meaning it will move to fit in screen boundaries in all directions, and "fit flip" for a sub menu with vertical parent, meaning it will fit vertically and flip over
its parent horizontally. You can also switch off the screen boundary detection completely if you set the popupCollision to false.

#### Example
    <kendo:contextMenu popupCollision="popupCollision">
    </kendo:contextMenu>

### showOn `java.lang.String`

Specifies the event or events on which ContextMenu should open. By default ContextMenu will show on contextmenu event on desktop and hold event on touch devices.
Could be any pointer/mouse/touch event, also several, separated by spaces.

#### Example
    <kendo:contextMenu showOn="showOn">
    </kendo:contextMenu>

### target `java.lang.Object`

Specifies the element on which ContextMenu should open. The default element is the document body.

#### Example
    <kendo:contextMenu target="target">
    </kendo:contextMenu>


##  Configuration JSP Tags

### kendo:contextMenu-animation

A collection of Animation objects, used to change default animations. A value of false will disable all animations in the widget.Available animations for the ContextMenu are listed below.  Each animation has a reverse options which is used for the close effect by default, but can be over-ridden
by setting the close animation. Each animation also has a direction which can be set off the animation (i.e. slideIn:Down).

More documentation is available at [kendo:contextMenu-animation](/api/wrappers/jsp/contextmenu/animation).

#### Example

    <kendo:contextMenu>
        <kendo:contextMenu-animation></kendo:contextMenu-animation>
    </kendo:contextMenu>


## Event Attributes

### close `String`

Fires before a sub menu or the ContextMenu gets closed. You can cancel this event to prevent closure.


For additional information check the [close](/api/web/contextmenu#events-close) event documentation.

#### Example
    <kendo:contextMenu close="handle_close">
    </kendo:contextMenu>
    <script>
        function handle_close(e) {
            // Code to handle the close event.
        }
    </script>

### open `String`

Fires before a sub menu or the ContextMenu gets opened. You can cancel this event to prevent opening the sub menu.


For additional information check the [open](/api/web/contextmenu#events-open) event documentation.

#### Example
    <kendo:contextMenu open="handle_open">
    </kendo:contextMenu>
    <script>
        function handle_open(e) {
            // Code to handle the open event.
        }
    </script>

### activate `String`

Fires when a sub menu or the ContextMenu gets opened and its animation finished.


For additional information check the [activate](/api/web/contextmenu#events-activate) event documentation.

#### Example
    <kendo:contextMenu activate="handle_activate">
    </kendo:contextMenu>
    <script>
        function handle_activate(e) {
            // Code to handle the activate event.
        }
    </script>

### deactivate `String`

Fires when a sub menu or the ContextMenu gets closed and its animation finished.


For additional information check the [deactivate](/api/web/contextmenu#events-deactivate) event documentation.

#### Example
    <kendo:contextMenu deactivate="handle_deactivate">
    </kendo:contextMenu>
    <script>
        function handle_deactivate(e) {
            // Code to handle the deactivate event.
        }
    </script>

### select `String`

Fires when a menu item gets selected.


For additional information check the [select](/api/web/contextmenu#events-select) event documentation.

#### Example
    <kendo:contextMenu select="handle_select">
    </kendo:contextMenu>
    <script>
        function handle_select(e) {
            // Code to handle the select event.
        }
    </script>

## Event Tags

### kendo:contextMenu-close

Fires before a sub menu or the ContextMenu gets closed. You can cancel this event to prevent closure.


For additional information check the [close](/api/web/contextmenu#events-close) event documentation.

#### Example
    <kendo:contextMenu>
        <kendo:contextMenu-close>
            <script>
                function(e) {
                    // Code to handle the close event.
                }
            </script>
        </kendo:contextMenu-close>
    </kendo:contextMenu>

### kendo:contextMenu-open

Fires before a sub menu or the ContextMenu gets opened. You can cancel this event to prevent opening the sub menu.


For additional information check the [open](/api/web/contextmenu#events-open) event documentation.

#### Example
    <kendo:contextMenu>
        <kendo:contextMenu-open>
            <script>
                function(e) {
                    // Code to handle the open event.
                }
            </script>
        </kendo:contextMenu-open>
    </kendo:contextMenu>

### kendo:contextMenu-activate

Fires when a sub menu or the ContextMenu gets opened and its animation finished.


For additional information check the [activate](/api/web/contextmenu#events-activate) event documentation.

#### Example
    <kendo:contextMenu>
        <kendo:contextMenu-activate>
            <script>
                function(e) {
                    // Code to handle the activate event.
                }
            </script>
        </kendo:contextMenu-activate>
    </kendo:contextMenu>

### kendo:contextMenu-deactivate

Fires when a sub menu or the ContextMenu gets closed and its animation finished.


For additional information check the [deactivate](/api/web/contextmenu#events-deactivate) event documentation.

#### Example
    <kendo:contextMenu>
        <kendo:contextMenu-deactivate>
            <script>
                function(e) {
                    // Code to handle the deactivate event.
                }
            </script>
        </kendo:contextMenu-deactivate>
    </kendo:contextMenu>

### kendo:contextMenu-select

Fires when a menu item gets selected.


For additional information check the [select](/api/web/contextmenu#events-select) event documentation.

#### Example
    <kendo:contextMenu>
        <kendo:contextMenu-select>
            <script>
                function(e) {
                    // Code to handle the select event.
                }
            </script>
        </kendo:contextMenu-select>
    </kendo:contextMenu>

