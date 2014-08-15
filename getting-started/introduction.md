---
title: Introduction
page_title: HTML5, jQuery-based framework | Kendo UI
description: "Kendo UI framework overview: UI components, rich data vizualization framework, auto-adaptive mobile widgets and all tools for building rich web apps."
position: 1
---

# What is Kendo UI

Kendo UI is an HTML5, jQuery-based framework for building modern web apps. The framework features lots of UI widgets, a rich data vizualization framework,
an auto-adaptive Mobile framework, and all of the tools needed for HTML5 app development, such as Data Source, Templating, MVVM, Drag-and-Drop API, and more.

Kendo UI comes in different bundles:

* Kendo UI Core - free open source version of Kendo UI licensed under Apache 2.0, including web and mobile widgets and framework features.
* Kendo UI Professional - includes web, dataviz and mobile widgets and framework features.
* Telerik UI for ASP.NET MVC - Kendo UI Professional plus ASP.NET MVC wrappers for all available widgets.
* Telerik UI for JSP - Kendo UI Professional plus JSP wrappers for the available web and dataviz widgets.
* Telerik UI for PHP - Kendo UI Professional plus PHP wrappers for the available web and dataviz widgets.

*See comparison between Kendo UI Professional and Kendo UI Core here: http://www.telerik.com/kendo-ui/comparison

# Installing and Getting Started with Kendo UI

You can download all Kendo UI bundles from the [download page](http://www.telerik.com/download/kendo-ui-complete).

The distribution zip file contains the following:

* /examples - quick start demos.
* /js - minified JavaScript files.
* /src - complete source code. Not available in the trial distribution.
* /styles - minified CSS files and theme images.
* /wrappers - server-side wrappers. Available in Telerik UI for ASP.NET MVC, JSP or PHP.
* changelog.html - Kendo UI release notes.

## Using Kendo UI

To use Kendo UI in your HTML page you need to include the required JavaScript and CSS files.

### Kendo UI Web

1. Download Kendo UI Professional and extract the distribution zip file to a convenient location.
1. Copy the **/js** and **/styles** directories of the Kendo UI Professional distribution to your web application root directory.
1. Include the Kendo UI Web JavaScript and CSS files in the `head` tag of your HTML page. **Make sure the common CSS file is registered before the theme CSS file.
Also make sure only one combined script file is registered. For more information, please refer to the [Javascript Dependencies page](/getting-started/javascript-dependencies).**

        <!-- Common Kendo UI Web CSS -->
        <link href="styles/kendo.common.min.css" rel="stylesheet" />
        <!-- Default Kendo UI Web theme CSS -->
        <link href="styles/kendo.default.min.css" rel="stylesheet" />
        <!-- jQuery JavaScript -->
        <script src="js/jquery.min.js"></script>
        <!-- Kendo UI Web combined JavaScript -->
        <script src="js/kendo.web.min.js"></script>
1. Initialize a Kendo UI Web Widget (the Kendo DatePicker in this example):

        <!-- HTML element from which the Kendo DatePicker would be initialized -->
        <input id="datepicker" />
        <script>
        $(function() {
            // Initialize the Kendo DatePicker by calling the kendoDatePicker jQuery plugin
            $("#datepicker").kendoDatePicker();
        });
        </script>

Here is the complete example:

    <!doctype html>
    <html>
        <head>
            <title>Kendo UI Web</title>
            <link href="styles/kendo.common.min.css" rel="stylesheet" />
            <link href="styles/kendo.default.min.css" rel="stylesheet" />
            <script src="js/jquery.min.js"></script>
            <script src="js/kendo.web.min.js"></script>
        </head>
        <body>
            <input id="datepicker" />
            <script>
                $(function() {
                    $("#datepicker").kendoDatePicker();
                });
            </script>
        </body>
    </html>

### Kendo UI DataViz

1. Download Kendo UI Professional and extract the distribution zip file to a convenient location.
1. Copy the **/js** and **/styles** directories of the Kendo UI Professional distribution to your web application root directory.
1. Include the Kendo UI DataViz JavaScript and CSS files in the `head` tag of your HTML page:

        <!-- Kendo UI DataViz CSS -->
        <link href="styles/kendo.dataviz.min.css" rel="stylesheet" />
        <!-- jQuery JavaScript -->
        <script src="js/jquery.min.js"></script>
        <!-- Kendo UI DataViz combined JavaScript -->
        <script src="js/kendo.dataviz.min.js"></script>
1. Initialize a Kendo UI DataViz Widget (the Kendo Radial Gauge in this example):

        <!-- HTML element from which the Kendo Radial Gauge would be initialized -->
        <div id="gauge"></div>
        <script>
        $(function() {
            $("#gauge").kendoRadialGauge();
        });
        </script>

Here is the complete example:

    <!doctype html>
    <html>
        <head>
            <title>Kendo UI DataViz</title>
            <link href="styles/kendo.dataviz.min.css" rel="stylesheet" />
            <script src="js/jquery.min.js"></script>
            <script src="js/kendo.dataviz.min.js"></script>
        </head>
        <body>
            <div id="gauge"></div>
            <script>
            $(function() {
                $("#gauge").kendoRadialGauge();
            });
            </script>
        </body>
    </html>

### Kendo UI Mobile

1. Download Kendo UI Professional and extract the distribution zip file to a convenient location.
1. Copy the **/js** and **/styles** directories of the Kendo UI Professional distribution to your web application root directory.
1. Include the Kendo UI Mobile JavaScript and CSS files in the `head` tag of your HTML page:

        <!-- Kendo UI Mobile CSS -->
        <link href="styles/kendo.mobile.all.min.css" rel="stylesheet" />
        <!-- jQuery JavaScript -->
        <script src="js/jquery.min.js"></script>
        <!-- Kendo UI Mobile combined JavaScript -->
        <script src="js/kendo.mobile.min.js"></script>
1. Initialize a Kendo Mobile Application

        <!-- Kendo Mobile View -->
        <div data-role="view" data-title="View" id="index">
            <!--Kendo Mobile Header -->
            <header data-role="header">
                <!--Kendo Mobile NavBar widget -->
                <div data-role="navbar">
                    <span data-role="view-title"></span>
                </div>
            </header>
            <!--Kendo Mobile ListView widget -->
            <ul data-role="listview">
              <li>Item 1</li>
              <li>Item 2</li>
            </ul>
            <!--Kendo Mobile Footer -->
            <footer data-role="footer">
                <!-- Kendo Mobile TabStrip widget -->
                <div data-role="tabstrip">
                    <a data-icon="home" href="#index">Home</a>
                    <a data-icon="settings" href="#settings">Settings</a>
                </div>
            </footer>
        </div>
        <script>
        // Initialize a new Kendo Mobile Application
        var app = new kendo.mobile.Application();
        </script>

Here is the complete example:

    <!doctype html>
    <html>
        <head>
            <title>Kendo UI Mobile</title>
            <link href="styles/kendo.mobile.all.min.css" rel="stylesheet" />
            <script src="js/jquery.min.js"></script>
            <script src="js/kendo.mobile.min.js"></script>
        </head>
        <body>
            <div data-role="view" data-title="View" id="index">
                <header data-role="header">
                    <div data-role="navbar">
                        <span data-role="view-title"></span>
                    </div>
                </header>
                <ul data-role="listview">
                  <li>Item 1</li>
                  <li>Item 2</li>
                </ul>
                <footer data-role="footer">
                    <div data-role="tabstrip">
                        <a data-icon="home" href="#index">Home</a>
                        <a data-icon="settings" href="#settings">Settings</a>
                    </div>
                </footer>
            </div>
            <script>
            var app = new kendo.mobile.Application();
            </script>
        </body>
    </html>

## Server-side wrappers

Kendo UI provides server-side wrappers for ASP.NET, PHP and JSP. Those are classes (ASP.NET and PHP) or XML tags (JSP)
which allow configuring the Kendo UI widgets with server-side code.

You can find more info about the server-side wrappers here:

- [Get Started with Telerik UI for ASP.NET MVC](/getting-started/using-kendo-with/aspnet-mvc/introduction)
- [Get Started with Telerik UI for JSP](/getting-started/using-kendo-with/jsp/introduction)
- [Get Started with Telerik UI for PHP](/getting-started/using-kendo-with/php/introduction)

## Next Steps

### Kendo UI videos

You can watch the videos in the [Kendo UI YouTube channel](http://www.youtube.com/kendouitv).

### Kendo UI Dojo

A lot of interactive tutorials are available in the [Kendo UI Dojo](http://trykendoui.telerik.com).

### Further reading

1. [Kendo UI Widgets](/getting-started/widgets)
1. [Data Attribute Initialization](/getting-started/data-attribute-initialization)
1. [Requirements](/getting-started/technical-requirements)

### Examples

1. [Online demos](http://demos.telerik.com/kendo-ui)
1. [Code library projects](http://www.telerik.com/support/code-library)
1. Examples available on github
-   [ASP.NET MVC examples](https://github.com/telerik/kendo-examples-asp-net-mvc/)
-   [ASP.NET MVC Kendo UI Music Store](https://github.com/telerik/kendo-music-store)
-   [ASP.NET WebForms examples](https://github.com/telerik/kendo-examples-asp-net)
-   [JSP examples](https://github.com/telerik/kendo-examples-java)
-   [Kendo Mobile Sushi](https://github.com/telerik/kendo-mobile-sushi)
-   [PHP examples](https://github.com/telerik/kendo-examples-php)
-   [Ruby on Rails examples](https://github.com/telerik/kendo-examples-rails)

## Help Us Improve Kendo UI Documentation, Samples, Tutorials and Demos

The Kendo UI team would LOVE your help to improve our documentation. We encourage you to contribute in the way that you choose:

### Submit a New Issue at GitHub

[Open](https://github.com/telerik/kendo-docs/issues?state=open) a new issue on the topic if it does not exist already.

When creating an issue, please provide a descriptive title, be as specific as possible and link to the document in question.
If you can provide a link to the closest anchor to the issue, that is even better.

### Update the Documentation at GitHub

This is the most direct method. Follow [the contribution instructions](https://github.com/telerik/kendo-docs/blob/master/readme.md). The basic steps are that you fork our documentation and submit a pull request. That way you can contribute to exactly where you found the error and our technical writing team just needs to approve your change request. Please use only standard Markdown and follow the directions at the link. If you find an issue in the docs, or even feel like creating new content, we are happy to have your contributions!

### Forums

You can also go to the [Kendo UI Forums](http://www.telerik.com/forums) and leave feedback.
This method will take a bit longer to reach our documentation team, but if you like the accountability of forums and you want a fast reply from our amazing support team, leaving feedback in the Kendo UI forums guarantees that your suggestion has a support number and that weâ€™ll follow up on it.

Thank you for contributing to the Kendo UI community!
