---
title: QRCode
page_title: Configuration, methods and events of Kendo UI DataViz QRCode
description: Learn the configuration options for QRCode widget, set its options, use methods properly.
---

# kendo.dataviz.ui.QRCode

Represents the Kendo UI QRCode widget. Inherits from [Widget](/api/framework/widget).

## Configuration

### Example - Render as SVG, if supported

    <div id="qrCode"></div>
    <script>
    $("#qrCode").kendoQRCode({
      value: "http://demos.telerik.com/kendo-ui/dataviz/overview/index.html",
      renderAs: "svg"
    });
    </script>

### background `String` *(default: "#fff")*

The background color of the QR code. Accepts a valid CSS color string, including hex and rgb.

#### Example

    <div id="qrCode"></div>
    <script>
    $("#qrCode").kendoQRCode({
      value: "http://demos.telerik.com/kendo-ui/dataviz/overview/index.html",
      background: "red"
    });
    </script>

### border `Object`

The border of the QR code.

### border.color `String`

The color of the border. Accepts a valid CSS color string, including hex and rgb.

#### Example

    <div id="qrCode"></div>
    <script>
    $("#qrCode").kendoQRCode({
      value: "http://demos.telerik.com/kendo-ui/dataviz/overview/index.html",
      border: {
        color: "#FF321C",
        width: 2
      }
    });
    </script>

### border.width `Number`

The width of the border in pixels. By default the border width is set to zero which means that the border will not appear.

#### Example

    <div id="qrCode"></div>
    <script>
    $("#qrCode").kendoQRCode({
      value: "http://demos.telerik.com/kendo-ui/dataviz/overview/index.html",
      border: {
        width: 5,
        color: "#FF7D05"
      }
    });
    </script>

### color `String` *(default: "#000")*

The color of the QR code. Accepts a valid CSS color string, including hex and rgb.

#### Example

    <div id="qrCode"></div>
    <script>
    $("#qrCode").kendoQRCode({
      value: "http://demos.telerik.com/kendo-ui/dataviz/overview/index.html",
      color: "#aa00bb"
    });
    </script>

### encoding `String` *(default: "ISO_8859_1")*

The encoding mode used to encode the value.

The possible values are:

* "ISO\_8859\_1" - supports all characters from the [ISO/IEC 8859-1](http://en.wikipedia.org/wiki/ISO/IEC_8859-1) character set.
* "UTF_8" - supports all [Unicode](http://en.wikipedia.org/wiki/List_of_Unicode_characters) characters.

> *Important:* The UTF-8 encoding is not included in the specifications and is not supported by all readers.

#### Example

    <div id="qrCode"></div>
    <script>
    $("#qrCode").kendoQRCode({
      value: "丠",
      encoding: "UTF_8"
    });
    </script>

### errorCorrection `String` *(default: "L")*

The error correction level used to encode the value.

The possible values are:

* "L" - approximately 7% of the codewords can be restored.
* "M" - approximately 15% of the codewords can be restored.
* "Q" - approximately 25% of the codewords can be restored.
* "H" - approximately 30% of the codewords can be restored.

#### Example

    <div id="qrCode"></div>
    <script>
    $("#qrCode").kendoQRCode({
      value: "http://demos.telerik.com/kendo-ui/dataviz/overview/index.html",
      errorCorrection: "H"
    });
    </script>

### padding `Number` *(default: 0)*

Sets the minimum distance in pixels that should be left between the border and the QR modules.

#### Example

    <div id="qrCode"></div>
    <script>
    $("#qrCode").kendoQRCode({
      value: "http://demos.telerik.com/kendo-ui/dataviz/overview/index.html",
      size: 240,
      padding: 10
    });
    </script>

### renderAs `String` *(default: "svg")*

Sets the preferred rendering engine.
If it is not supported by the browser, the QRCode will switch to the first available mode.

The supported values are:

* "canvas" - renders the widget as a Canvas element, if available.
* "svg" - renders the widget as inline SVG document, if available
* "vml" - renders the widget as VML, if available

### size `Number|String`

Specifies the size of a QR code in pixels (i.e. "200px"). Numeric values are treated as pixels.
If no size is specified, it will be determined from the element width and height.
In case the element has width or height of zero, a default value of 200 pixels will be used.

#### Example

    <div id="qrCode"></div>
    <script>
    $("#qrCode").kendoQRCode({
      value: "http://demos.telerik.com/kendo-ui/dataviz/overview/index.html",
      size: 300
    });
    </script>

#### Example

    <div id="qrCode"></div>
    <script>
    $("#qrCode").kendoQRCode({
      value: "http://demos.telerik.com/kendo-ui/dataviz/overview/index.html",
      size: "300px"
    });
    </script>

### value `Number|String`

The value of the QRCode.

#### Example

    <div id="qrCode"></div>
    <script>
    $("#qrCode").kendoQRCode({
      value: "http://demos.telerik.com/kendo-ui/dataviz/overview/index.html"
    });
    </script>

## Methods

### destroy

Prepares the QRCode for safe removal from the DOM.

Removes data entries in order to avoid memory leaks.

#### Example

    var qrCode = $("#qrCode").data("kendoQRCode");
    qrCode.destroy();

### imageDataURL

Returns a PNG image of the qrcode encoded as a [Data URL](https://developer.mozilla.org/en-US/docs/data_URIs).

#### Returns

`String` A data URL with `image/png` MIME type. Will be `null` if the browser does not support the `canvas` element.

#### Example - show a snapshot of the QRCode

    <div id="qrcode"></div>
    <a download="export.png" id="export" class="k-button">Export PNG</a>
    <script>
    $("#qrcode").kendoQRCode({
      value: "Some text"
    });

    $("#export").on("click", function() {
      var qrcode = $("#qrcode").data("kendoQRCode");
      var imageDataURL = qrcode.imageDataURL();

      if (navigator.msSaveBlob) {
        var blob = toBlob(imageDataURL, "image/png");
        navigator.msSaveBlob(blob, this.getAttribute("download"));
      } else {
        this.href = imageDataURL;
      }
    });

    // See: http://goo.gl/qlg5dd
    function toBlob(base64, type) {
      var rawData = base64.substring(base64.indexOf("base64,") + 7);
      var data = atob(rawData);
      var arr = new Uint8Array(data.length);

      for (var i = 0; i < data.length; ++i) {
        arr[i] = data.charCodeAt(i);
      }

      return new Blob([ arr.buffer ], { type: type });
    }
    </script>

### redraw

Redraws the QR code using the current value and options.

#### Example

    var qrCode = $("#qrCode").data("kendoQRCode");
    qrCode.redraw();

### resize

Adjusts the widget layout to match the size of the container.

#### Example

    <div id="qrcode" style="width: 150px; height: 150px;"></div>
    <script>
        $("#qrcode").kendoQRCode({
          value: "FOO"
        });

        $("#qrcode")
           .css({ width: "600px", height: "300px" })
           .data("kendoQRCode").resize();
    </script>

#### Parameters

##### force `Boolean` *optional*

Defines whether the widget should proceed with resizing even if the element dimensions have not changed.

### setOptions

Sets new options to the QRCode and redraws it.

#### Parameters

##### options `Object`

An object with the new options. All [configuration](qrcode#configuration) options can be set.

#### Example

    var qrCode = $("#qrCode").data("kendoQRCode");

    qrCode.setOptions({
      errorCorrection: "H",
      size: 300,
      background: "#FFB821",
      border: {
        width: 5,
        color: "#FF7D05"
      }
    });

### svg

Returns the [SVG](http://www.w3.org/Graphics/SVG/) representation of the qrcode. The returned string is a self-contained SVG document that can be used as is or converted to other formats using tools like [Inkscape](http://inkscape.org/) and
[ImageMagick](http://www.imagemagick.org/). Both programs provide command-line interface suitable for server-side processing.

#### Returns

`String` the SVG representation of the qrcode.

#### Example - get the SVG representation of the qrcode

    <div id="qrcode"></div>
    <script>
    $("#qrcode").kendoQRCode({
      value:"Some value"
    });
    var qrcode = $("#qrcode").data("kendoQRCode");
    var svg = qrcode.svg();
    console.log(svg); // displays the SVG string
    </script>

### value

Change the value of the QR code.

#### Parameters

##### options `String|Number`

The new value to be set.

#### Example

    var qrCode = $("#qrCode").data("kendoQRCode");
    qrCode.value("Hello");

