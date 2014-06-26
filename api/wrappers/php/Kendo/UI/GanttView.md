---
title: GanttView
---

# \Kendo\UI\GanttView

A PHP class representing the view setting of GanttViews.


## Methods

### dayHeaderTemplate
The [template](/api/framework/kendo#methods-template used to render the day slots in "day" and "week" views.

#### Returns
`\Kendo\UI\GanttView`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`



#### Example  - using string
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->dayHeaderTemplate('value');
    ?>

#### Example  - using \Kendo\JavaScriptFunction
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->dayHeaderTemplate(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

### monthHeaderTemplate
The [template](/api/framework/kendo#methods-template used to render the month slots in "month" views.

#### Returns
`\Kendo\UI\GanttView`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`



#### Example  - using string
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->monthHeaderTemplate('value');
    ?>

#### Example  - using \Kendo\JavaScriptFunction
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->monthHeaderTemplate(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

### selected
If set to true the view will be initially selected by the gantt widget. The default selected view is "day".

#### Returns
`\Kendo\UI\GanttView`

#### Parameters

##### $value `boolean`



#### Example 
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->selected(true);
    ?>

### slotSize
The size of the time slot headers. Values are treated as pixels.

#### Returns
`\Kendo\UI\GanttView`

#### Parameters

##### $value `float|string`



#### Example  - using float
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->slotSize(1);
    ?>

#### Example  - using string
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->slotSize('value');
    ?>

### timeHeaderTemplate
The [template](/api/framework/kendo#methods-template used to render the time slots in "day" view

#### Returns
`\Kendo\UI\GanttView`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`



#### Example  - using string
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->timeHeaderTemplate('value');
    ?>

#### Example  - using \Kendo\JavaScriptFunction
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->timeHeaderTemplate(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

### type
The type of the view. The built-in views are: "day", "week", and "month".

#### Returns
`\Kendo\UI\GanttView`

#### Parameters

##### $value `string`



#### Example 
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->type('value');
    ?>

### weekHeaderTemplate
The [template](/api/framework/kendo#methods-template used to render the week slots in "week" and "month" views.

#### Returns
`\Kendo\UI\GanttView`

#### Parameters

##### $value `string|\Kendo\JavaScriptFunction`



#### Example  - using string
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->weekHeaderTemplate('value');
    ?>

#### Example  - using \Kendo\JavaScriptFunction
    <?php
    $view = new \Kendo\UI\GanttView();
    $view->weekHeaderTemplate(new \Kendo\JavaScriptFunction('function() { }'));
    ?>

