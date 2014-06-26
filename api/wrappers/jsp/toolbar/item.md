---
title: toolBar-item
---

# \<kendo:toolBar-item\>

A JavaScript array that contains the ToolBar's commands configuration.

#### Example
    <kendo:toolBar-items>
        <kendo:toolBar-item></kendo:toolBar-item>
    </kendo:toolBar-items>

## Configuration Attributes

### click `java.lang.String`

Specifies the click event handler of the button. Applicable only for commands of type button and splitButton.

#### Example
    <kendo:toolBar-item click="click">
    </kendo:toolBar-item>

### enable `boolean`

Specifies whether the control is initially enabled or disabled. Default value is "true".

#### Example
    <kendo:toolBar-item enable="enable">
    </kendo:toolBar-item>

### group `java.lang.String`

Assigns the button to a group. Applicable only for buttons with togglable: true.

#### Example
    <kendo:toolBar-item group="group">
    </kendo:toolBar-item>

### icon `java.lang.String`

Sets icon for the item. The icon should be one of the existing in the Kendo UI theme sprite.

#### Example
    <kendo:toolBar-item icon="icon">
    </kendo:toolBar-item>

### id `java.lang.String`

Specifies the ID of the button.

#### Example
    <kendo:toolBar-item id="id">
    </kendo:toolBar-item>

### imageUrl `java.lang.String`

If set, the ToolBar will render an image with the specified URL in the button.

#### Example
    <kendo:toolBar-item imageUrl="imageUrl">
    </kendo:toolBar-item>

### overflow `java.lang.String`

Specifies how the button behaves when the ToolBar is resized. Possible values are: "always", "never" or "auto" (default).

#### Example
    <kendo:toolBar-item overflow="overflow">
    </kendo:toolBar-item>

### overflowTemplate `java.lang.String`

Specifies what element will be added in the command overflow popup. Applicable only for items that have a template.

#### Example
    <kendo:toolBar-item overflowTemplate="overflowTemplate">
    </kendo:toolBar-item>

### primary `boolean`

Specifies whether the button is primary. Primary buttons receive different styling.

#### Example
    <kendo:toolBar-item primary="primary">
    </kendo:toolBar-item>

### selected `boolean`

Specifies if the toggle button is initially selected. Applicable only for buttons with togglable: true.

#### Example
    <kendo:toolBar-item selected="selected">
    </kendo:toolBar-item>

### showIcon `java.lang.String`

Specifies where the button icon will be displayed. Possible values are: "toolbar", "overflow" or "both" (default).

#### Example
    <kendo:toolBar-item showIcon="showIcon">
    </kendo:toolBar-item>

### showText `java.lang.String`

Specifies where the text will be displayed. Possible values are: "toolbar", "overflow" or "both" (default).

#### Example
    <kendo:toolBar-item showText="showText">
    </kendo:toolBar-item>

### spriteCssClass `java.lang.String`

Defines a CSS class (or multiple classes separated by spaces) which will be used for button icon.

#### Example
    <kendo:toolBar-item spriteCssClass="spriteCssClass">
    </kendo:toolBar-item>

### template `java.lang.String`

Specifies what element will be added in the ToolBar wrapper. Items with template does not have a type.

#### Example
    <kendo:toolBar-item template="template">
    </kendo:toolBar-item>

### text `java.lang.String`

Sets the text of the button.

#### Example
    <kendo:toolBar-item text="text">
    </kendo:toolBar-item>

### togglable `boolean`

Specifies if the button is togglable, e.g. has a selected and unselected state.

#### Example
    <kendo:toolBar-item togglable="togglable">
    </kendo:toolBar-item>

### toggle `java.lang.String`

Specifies the toggle event handler of the button. Applicable only for commands of type button and togglable: true.

#### Example
    <kendo:toolBar-item toggle="toggle">
    </kendo:toolBar-item>

### type `java.lang.String`

Specifies the command type. Supported types are "button", "splitButton", "buttonGroup", "separator".

#### Example
    <kendo:toolBar-item type="type">
    </kendo:toolBar-item>

### url `java.lang.String`

Specifies the url to navigate to.

#### Example
    <kendo:toolBar-item url="url">
    </kendo:toolBar-item>


##  Configuration JSP Tags

### kendo:toolBar-item-buttons

Specifies the buttons of ButtonGroup.

More documentation is available at [kendo:toolBar-item-buttons](/api/wrappers/jsp/toolbar/item-buttons).

#### Example

    <kendo:toolBar-item>
        <kendo:toolBar-item-buttons></kendo:toolBar-item-buttons>
    </kendo:toolBar-item>

### kendo:toolBar-item-menuButtons

Specifies the menu buttons of a SplitButton.

More documentation is available at [kendo:toolBar-item-menuButtons](/api/wrappers/jsp/toolbar/item-menubuttons).

#### Example

    <kendo:toolBar-item>
        <kendo:toolBar-item-menuButtons></kendo:toolBar-item-menuButtons>
    </kendo:toolBar-item>


## Event Attributes

### click `String`

Specifies the click event handler of the button. Applicable only for commands of type button and splitButton.


#### Example
    <kendo:toolBar-item click="handle_click">
    </kendo:toolBar-item>
    <script>
        function handle_click(e) {
            // Code to handle the click event.
        }
    </script>

### overflowTemplate `String`

Specifies what element will be added in the command overflow popup. Applicable only for items that have a template.


#### Example
    <kendo:toolBar-item overflowTemplate="handle_overflowTemplate">
    </kendo:toolBar-item>
    <script>
        function handle_overflowTemplate(e) {
            // Code to handle the overflowTemplate event.
        }
    </script>

### template `String`

Specifies what element will be added in the ToolBar wrapper. Items with template does not have a type.


#### Example
    <kendo:toolBar-item template="handle_template">
    </kendo:toolBar-item>
    <script>
        function handle_template(e) {
            // Code to handle the template event.
        }
    </script>

### toggle `String`

Specifies the toggle event handler of the button. Applicable only for commands of type button and togglable: true.


#### Example
    <kendo:toolBar-item toggle="handle_toggle">
    </kendo:toolBar-item>
    <script>
        function handle_toggle(e) {
            // Code to handle the toggle event.
        }
    </script>

## Event Tags

### kendo:toolBar-item-click

Specifies the click event handler of the button. Applicable only for commands of type button and splitButton.


#### Example
    <kendo:toolBar-item>
        <kendo:toolBar-item-click>
            <script>
                function(e) {
                    // Code to handle the click event.
                }
            </script>
        </kendo:toolBar-item-click>
    </kendo:toolBar-item>

### kendo:toolBar-item-overflowTemplate

Specifies what element will be added in the command overflow popup. Applicable only for items that have a template.


#### Example
    <kendo:toolBar-item>
        <kendo:toolBar-item-overflowTemplate>
            <script>
                function(e) {
                    // Code to handle the overflowTemplate event.
                }
            </script>
        </kendo:toolBar-item-overflowTemplate>
    </kendo:toolBar-item>

### kendo:toolBar-item-template

Specifies what element will be added in the ToolBar wrapper. Items with template does not have a type.


#### Example
    <kendo:toolBar-item>
        <kendo:toolBar-item-template>
            <script>
                function(e) {
                    // Code to handle the template event.
                }
            </script>
        </kendo:toolBar-item-template>
    </kendo:toolBar-item>

### kendo:toolBar-item-toggle

Specifies the toggle event handler of the button. Applicable only for commands of type button and togglable: true.


#### Example
    <kendo:toolBar-item>
        <kendo:toolBar-item-toggle>
            <script>
                function(e) {
                    // Code to handle the toggle event.
                }
            </script>
        </kendo:toolBar-item-toggle>
    </kendo:toolBar-item>

