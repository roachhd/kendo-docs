---
title: Technical Requirements
page_title: Technical Requirements for using Kendo UI JavaScript framework
description: Check browser and platform support and prerequisites for best performance when working with Kendo UI.
position: 3
---

# Technical Requirements for using Kendo UI

Below are the system requirements for the Kendo UI Framework.

### Supported Desktop Browsers

|                   | Kendo UI Core                                 | Kendo UI Professional
| ---               | ---                                           | ---
| Internet Explorer | 7+<br/>10+ (for mobile widgets)               | 7+<br/>10+ (for mobile widgets)
| Firefox           | ESR +<br/>\*not supported by mobile widgets   | ESR +<br/>\*not supported by mobile widgets
| Chrome            | Yes                                           | Yes
| Opera             | 15.0 +                                        | 15.0 +
| Safari 5+ (OS X)  | Yes                                           | Yes

**NOTES:**

* Browsers in beta stage are not supported.
* [Quirks mode](http://www.quirksmode.org/css/quirksmode.html) is not supported. Always specify a [DOCTYPE](http://reference.sitepoint.com/html/doctypes)! Supported DOCTYPES include `HTML5`, `XHTML 1.1`, `XHTML 1.0` (`Transitional` or `Strict`) and `HTML4 Strict`.
Note that `HTML4 Transitional` triggers quirks mode.
* Internet Explorer compatibility modes are not supported. These modes can exhibit different behavior and rendering bugs, compared to the browser versions they emulate.
It is highly recommended to use IE's [Edge mode](http://blogs.msdn.com/b/ie/archive/2010/06/16/ie-s-compatibility-features-for-site-developers.aspx) via META tag or HTTP header.

        <meta http-equiv="X-UA-Compatible" content="IE=edge" />

* Kendo UI uses progressive enhancement for its CSS styling. As a result, old and obsolete browsers may ignore CSS3 styles, such as rounded corners and linear gradients.

### Kendo UI Platform support

| Platform           | Version
| ---                | ---
| Windows            | XP +, Server 2003 +
| Mac OS             | OS X +
| Android            | 2.3 +
| iOS                | 6.0 +
| BlackBerry         | 10.0+
| Windows Phone      | 8.0+
| Chrome for Android | Any

**NOTES:**

* In Android 2.3 dataviz widgets support only Canvas rendering mode.
* Hybrid mouse and touch devices are supported (for instance IE10, Chrome and Firefox on Windows 8).


## Prerequisites:

* JavaScript must be enabled on all browsers

For best performance:

* 'Disable script debugging' in the browser's config options must be checked
* Caching on Internet Explorer must be activated
