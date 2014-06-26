---
title: gantt-view
---

# \<kendo:gantt-view\>

The views displayed by the gantt and their configuration. The array items can be either objects specifying the view configuration or strings representing the view types (assuming default configuration).
By default the Kendo UI Gantt widget displays all three ("day", "week", and "month") views.

#### Example
    <kendo:gantt-views>
        <kendo:gantt-view></kendo:gantt-view>
    </kendo:gantt-views>

## Configuration Attributes

### dayHeaderTemplate `java.lang.String`

The [template](/api/framework/kendo#methods-template used to render the day slots in "day" and "week" views.

#### Example
    <kendo:gantt-view dayHeaderTemplate="dayHeaderTemplate">
    </kendo:gantt-view>

### monthHeaderTemplate `java.lang.String`

The [template](/api/framework/kendo#methods-template used to render the month slots in "month" views.

#### Example
    <kendo:gantt-view monthHeaderTemplate="monthHeaderTemplate">
    </kendo:gantt-view>

### selected `boolean`

If set to true the view will be initially selected by the gantt widget. The default selected view is "day".

#### Example
    <kendo:gantt-view selected="selected">
    </kendo:gantt-view>

### slotSize `java.lang.Object`

The size of the time slot headers. Values are treated as pixels.

#### Example
    <kendo:gantt-view slotSize="slotSize">
    </kendo:gantt-view>

### timeHeaderTemplate `java.lang.String`

The [template](/api/framework/kendo#methods-template used to render the time slots in "day" view

#### Example
    <kendo:gantt-view timeHeaderTemplate="timeHeaderTemplate">
    </kendo:gantt-view>

### type `java.lang.String`

The type of the view. The built-in views are: "day", "week", and "month".

#### Example
    <kendo:gantt-view type="type">
    </kendo:gantt-view>

### weekHeaderTemplate `java.lang.String`

The [template](/api/framework/kendo#methods-template used to render the week slots in "week" and "month" views.

#### Example
    <kendo:gantt-view weekHeaderTemplate="weekHeaderTemplate">
    </kendo:gantt-view>


## Event Attributes

### timeHeaderTemplate `String`

The [template](/api/framework/kendo#methods-template used to render the time slots in "day" view


#### Example
    <kendo:gantt-view timeHeaderTemplate="handle_timeHeaderTemplate">
    </kendo:gantt-view>
    <script>
        function handle_timeHeaderTemplate(e) {
            // Code to handle the timeHeaderTemplate event.
        }
    </script>

### dayHeaderTemplate `String`

The [template](/api/framework/kendo#methods-template used to render the day slots in "day" and "week" views.


#### Example
    <kendo:gantt-view dayHeaderTemplate="handle_dayHeaderTemplate">
    </kendo:gantt-view>
    <script>
        function handle_dayHeaderTemplate(e) {
            // Code to handle the dayHeaderTemplate event.
        }
    </script>

### weekHeaderTemplate `String`

The [template](/api/framework/kendo#methods-template used to render the week slots in "week" and "month" views.


#### Example
    <kendo:gantt-view weekHeaderTemplate="handle_weekHeaderTemplate">
    </kendo:gantt-view>
    <script>
        function handle_weekHeaderTemplate(e) {
            // Code to handle the weekHeaderTemplate event.
        }
    </script>

### monthHeaderTemplate `String`

The [template](/api/framework/kendo#methods-template used to render the month slots in "month" views.


#### Example
    <kendo:gantt-view monthHeaderTemplate="handle_monthHeaderTemplate">
    </kendo:gantt-view>
    <script>
        function handle_monthHeaderTemplate(e) {
            // Code to handle the monthHeaderTemplate event.
        }
    </script>

## Event Tags

### kendo:gantt-view-timeHeaderTemplate

The [template](/api/framework/kendo#methods-template used to render the time slots in "day" view


#### Example
    <kendo:gantt-view>
        <kendo:gantt-view-timeHeaderTemplate>
            <script>
                function(e) {
                    // Code to handle the timeHeaderTemplate event.
                }
            </script>
        </kendo:gantt-view-timeHeaderTemplate>
    </kendo:gantt-view>

### kendo:gantt-view-dayHeaderTemplate

The [template](/api/framework/kendo#methods-template used to render the day slots in "day" and "week" views.


#### Example
    <kendo:gantt-view>
        <kendo:gantt-view-dayHeaderTemplate>
            <script>
                function(e) {
                    // Code to handle the dayHeaderTemplate event.
                }
            </script>
        </kendo:gantt-view-dayHeaderTemplate>
    </kendo:gantt-view>

### kendo:gantt-view-weekHeaderTemplate

The [template](/api/framework/kendo#methods-template used to render the week slots in "week" and "month" views.


#### Example
    <kendo:gantt-view>
        <kendo:gantt-view-weekHeaderTemplate>
            <script>
                function(e) {
                    // Code to handle the weekHeaderTemplate event.
                }
            </script>
        </kendo:gantt-view-weekHeaderTemplate>
    </kendo:gantt-view>

### kendo:gantt-view-monthHeaderTemplate

The [template](/api/framework/kendo#methods-template used to render the month slots in "month" views.


#### Example
    <kendo:gantt-view>
        <kendo:gantt-view-monthHeaderTemplate>
            <script>
                function(e) {
                    // Code to handle the monthHeaderTemplate event.
                }
            </script>
        </kendo:gantt-view-monthHeaderTemplate>
    </kendo:gantt-view>

