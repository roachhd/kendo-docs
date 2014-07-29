---
title: Troubleshooting
page_title: Troubleshooting of Kendo UI Editor widget
description: How to deal with the troubleshooting of Editor UI widget.
position: 6
---

# Editor troubleshooting

## Pasting content in the editor when using IE does not display anything

Pasting in the editor requires permission to access clipboard data. This may require users with strict security settings to add the site in the trusted sites zone, or to adjust their Internet options so that the "Allow Programmatic clipboard access" setting is set to either "Allowed" or "Prompt".

## Editor inside a popup is readonly in Firefox

Firefox cannot handle iframes properly when they are moved in the DOM. When an Editor will be used inside a popup, which moves elements in the DOM, the popup (e.g. Kendo UI Window, jQuery dialog, etc) should be initialized first.

## Editor inside iPad expands instead of being scrollable

Iframes cannot be scrollable in iOS and always expand to display all their content. A possible solution is to use the Editor's inline editing mode, which does not include an iframe.
In this mode the Editor's value should be posted manually (see below).

## Inline editor value is not posted to the server

Since the inline editor is initialized from a non-form element, it is not posted to the server by design. If you need to submit the editor value along with the form, use the following approach:

    <form>
      <div id="comment" contentEditable></div>

      <button class="k-button">Submit</button>
    </form>

    <script>
      $("form").on("submit", function() {
        var form = $(this);

        // for each editor in the form
        form.find("[data-role=editor]").each(function() {
          var editor = $(this).data("kendoEditor");

          // ... append a hidden input that holds the editor value
          $("<input type='hidden' />")
            .attr("name", editor.element.attr("id"))
            .val(editor.value())
            .appendTo(form);
        });
      });
    </script>

## Images inside the Editor are not resizable in some scenarios

To begin with, image resizing inside contenteditable elements depends on the browser and is not an Editor feature. In addition, there is a browser issue, which is exhibited in the following way -
if a "classic" Editor (which uses an `iframe`) is created while hidden, or is hidden after initialization and then displayed back, then images become non-resizable. This problem is not related to Kendo UI.
It can be resolved by calling the Editor's [`refresh`](/api/web/editor#methods-refresh) method after the Editor becomes visible. Refreshing the widget will recreate the iframe.
Another possible approach is to use the Editor's "inline" mode, i.e. create the Editor from a `div`.

## Editor displays raw HTML content when using the browser's Back and Forward buttons

The Editor stores its value encoded by default. When the page is retrieved from the *bfcache* (back-forward cache), the textarea value is persisted encoded and the Editor encodes it again. This process can be easily observed if one navigates several times back and forth - on each navigation, the Editor value will be encoded once more.

To resolve the problem, set the [`encoded`](/api/web/editor#configuration-encoded) property to `false`, and expect the editor value to be posted unencoded to the server. If you are using ASP.NET, be sure to either disable the ASP.NET security validation or set the `AllowHtml` attribute on the model field that will receive the HTML string. Here is some more [information about request validation in ASP.NET](http://blogs.learnnowonline.com/blog/bid/199703/ASP-NET-MVC-Request-Validation-Protection-AllowHtml-Attribute).

Another option is to enable the [inline Editor mode](/getting-started/web/editor/overview#classic-mode-vs-inline-mode), which does not use an `iframe` and a `textarea`. In this case, however, the Editor's value should be [submitted manually](/getting-started/web/editor/troubleshooting#inline-editor-value-is-not-posted-to-the-server).