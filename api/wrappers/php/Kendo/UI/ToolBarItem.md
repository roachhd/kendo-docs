---
title: ToolBarItem
---

# \Kendo\UI\ToolBarItem

A PHP class representing the item setting of ToolBarItems.


## Methods

### addButton

Adds one or more ToolBarItemButton to the ToolBarItem.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value[, $value2, ...] `\Kendo\UI\ToolBarItemButton|array`

#### Example - using \Kendo\UI\ToolBarItemButton

    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $button = new \Kendo\UI\ToolBarItemButton();
    $enable = true;
    $button->enable($enable);
    $item->addButton($button);
    ?>

#### Example - using array

    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $enable = true;
    $item->addButton(array('enable' => $enable));
    ?>

#### Example - adding more than one ToolBarItemButton

    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $first  = new \Kendo\UI\ToolBarItemButton();
    $second = new \Kendo\UI\ToolBarItemButton();
    $item->addButton($first, $second);
    ?>

### click
Specifies the click event handler of the button. Applicable only for commands of type button and splitButton.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `\Kendo\JavaScriptFunction`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->click(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

### enable
Specifies whether the control is initially enabled or disabled. Default value is "true".

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->enable(true);
    ?>

### group
Assigns the button to a group. Applicable only for buttons with togglable: true.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->group('value');
    ?>

### icon
Sets icon for the item. The icon should be one of the existing in the Kendo UI theme sprite.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->icon('value');
    ?>

### id
Specifies the ID of the button.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->id('value');
    ?>

### imageUrl
If set, the ToolBar will render an image with the specified URL in the button.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->imageUrl('value');
    ?>

### addMenuButton

Adds one or more ToolBarItemMenuButton to the ToolBarItem.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value[, $value2, ...] `\Kendo\UI\ToolBarItemMenuButton|array`

#### Example - using \Kendo\UI\ToolBarItemMenuButton

    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $menuButton = new \Kendo\UI\ToolBarItemMenuButton();
    $enable = true;
    $menuButton->enable($enable);
    $item->addMenuButton($menuButton);
    ?>

#### Example - using array

    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $enable = true;
    $item->addMenuButton(array('enable' => $enable));
    ?>

#### Example - adding more than one ToolBarItemMenuButton

    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $first  = new \Kendo\UI\ToolBarItemMenuButton();
    $second = new \Kendo\UI\ToolBarItemMenuButton();
    $item->addMenuButton($first, $second);
    ?>

### overflow
Specifies how the button behaves when the ToolBar is resized. Possible values are: "always", "never" or "auto" (default).

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->overflow('value');
    ?>

### overflowTemplate
Specifies what element will be added in the command overflow popup. Applicable only for items that have a template.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`



#### Example  - using string
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->overflowTemplate('value');
    ?>

#### Example  - using \Kendo\JavaScriptFunction
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->overflowTemplate(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

### primary
Specifies whether the button is primary. Primary buttons receive different styling.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->primary(true);
    ?>

### selectable
Specifies if the toggle button is initially selected. Applicable only for buttons with togglable: true.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->selectable(true);
    ?>

### showIcon
Specifies where the button icon will be displayed. Possible values are: "toolbar", "overflow" or "both" (default).

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->showIcon('value');
    ?>

### showText
Specifies where the text will be displayed. Possible values are: "toolbar", "overflow" or "both" (default).

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->showText('value');
    ?>

### spriteCssClass
Defines a CSS class (or multiple classes separated by spaces) which will be used for button icon.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->spriteCssClass('value');
    ?>

### template
Specifies what element will be added in the ToolBar wrapper. Items with template does not have a type.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`



#### Example  - using string
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->template('value');
    ?>

#### Example  - using \Kendo\JavaScriptFunction
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->template(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

### text
Sets the text of the button.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->text('value');
    ?>

### togglable
Specifies if the button is togglable, e.g. has a selected and unselected state.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->togglable(true);
    ?>

### toggle
Specifies the toggle event handler of the button. Applicable only for commands of type button and togglable: true.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `\Kendo\JavaScriptFunction`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->toggle(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

### type
Specifies the command type. Supported types are "button", "splitButton", "buttonGroup", "separator".

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->type('value');
    ?>

### url
Specifies the url to navigate to.

#### Returns
`\Kendo\UI\ToolBarItem`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $item = new \Kendo\UI\ToolBarItem();
    $item->url('value');
    ?>

