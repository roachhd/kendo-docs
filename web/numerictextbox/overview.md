---
title: Overview
page_title: NumericTextBox UI widget - documentation overview
description: How to create NumericTextBox widget and deal with proper configuration of its behaviors.
---

# NumericTextBox Overview

The NumericTextBox widget can convert an INPUT element into a numeric, percentage or currency textbox.
The type is defined depending on the specified format. The widget renders spin buttons and with their help you can
increment/decrement the value with a predefined step. The NumericTextBox widget accepts only numeric entries.
The widget uses _kendo.culture.current_ culture in order to determine number precision and other culture
specific properties.


## Getting Started

### Creating a NumericTextBox from existing INPUT element

    <input id="textBox" />

### NumericTextBox initialization

    $(document).ready(function(){
        $("#textBox").kendoNumericTextBox();
    });

When a **NumericTextBox** is initialized, it will automatically
wraps the input element with span element and will render spin
buttons.

> When working the input being used for your NumericTextBox, always select by id instead of class. Behind the scenes, the NumericTextBox creates a secondary element to represent the visual look of the widget, and copies over all non-id attributes, including the class. As such, selecting this widget by class can cause unexpected results.

## Configuring NumericTextBox behaviors


The **NumericTextBox** provides configuration options that can be
easily set during initialization. Among the properties that can be
controlled:


*   Value of the **NumericTextBox**
*   Minimum and/or maximum values
*   Increment step
*   Precision of the number
*   Number format (any valid number format is allowed)

For a complete overview of the NumericTextBox's methods and configuration options, [review the NumericTextBox API Reference](/api/web/numerictextbox).

### Customizing NumericTextBox defaults

     $("#textbox").kendoNumericTextBox({
         value: 10,
         min: -10,
         max: 100,
         step: 0.75,
         format: "n",
         decimals: 3
     });



### Create Currency NumericTextBox widget

     $("#textbox").kendoNumericTextBox({
         format: "c2" //Define currency type and 2 digits precision
     });



### Create Percentage NumericTextBox widget

     $("#textbox").kendoNumericTextBox({
         format: "p",
         value: 0.15 // 15 %
     });

## Support for label element

Because of the complex rendering of the widget, focusing of the widget using label element will require additional implementation.
Check [this jsFiddle demo](http://jsfiddle.net/krustev/6mHKF/), which shows how to achieve this.

## Accessing an Existing NumericTextBox


You can reference an existing **NumericTextBox** instance via
[jQuery.data()](http://api.jquery.com/jQuery.data/).
Once a reference has been established, you can use the API to control
its behavior.

### Accessing an existing NumericTextBox instance

    var numericTextBox = $("#numericTextBox").data("kendoNumericTextBox");

## Known limitations

Kendo NumericTextBox widget uses JavaScript [Number](http://ecma262-5.com/ELS5_HTML.htm#Section_8.5) object to keep its value, which has a certain precision limitation.
In general, Number object can persists its precision up to 16 digits. Numbers longer than that length will be converted to
exponential numbers and hence will lose their precision. As the widget relies on a Number object, it gets the same precision limitation.

#### Workaround
Unfortunately, there is no feasible workaround for this limitation as it comes from the JavaScript itself. What we suggest is to use
simple INPUT element with server validation, because the used server language should be able to parse long numbers.
