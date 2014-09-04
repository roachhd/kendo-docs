---
title: Supported Browsers
page_title: Supported browsers for Kendo UI Drawing API
position: 100
---

# Supported Browsers

The Drawing API adapts to the browser capabilities by using dedicated
[Surface](/api/dataviz/drawing/surface) implementations.

The [Surface.create](/api/dataviz/drawing/surface#create) method
uses feature detection to determine the default surface type.

## Supported surfaces by browser

Surfaces are listed in order of preference.

The user can request a specific [type](/api/dataviz/drawing/surface#configuration-type),
e.g. "canvas", if desired. The preference will be ignored if no support is provided by the browser.

| Surface | IE   | Chrome| Firefox | Safari | iOS | Android
| ---     | ---  | ---   | ---     | ---    | --- | ---
| SVG     | 9+   | ✓     | ✓       | ✓      | ✓   | 4+
| Canvas  | 10+  | ✓     | ✓       | ✓      | ✓   | ✓
| VML     | 7+   | ✕     | ✕       | ✕      | ✕   | ✕

## Known limitations

- The Canvas surface doesn't fire [events](/api/dataviz/drawing/surface#events)

