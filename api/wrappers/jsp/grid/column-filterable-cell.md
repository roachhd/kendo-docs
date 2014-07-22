---
title: grid-column-filterable-cell
---

# \<kendo:grid-column-filterable-cell\>

Specifies options for the filter cell when enabled.Can be set to a JavaScript object which represents the filter cell configuration.

#### Example
    <kendo:grid-column-filterable>
        <kendo:grid-column-filterable-cell></kendo:grid-column-filterable-cell>
    </kendo:grid-column-filterable>

## Configuration Attributes

### dataTextField `java.lang.String`

Specifies the name of the field which will provide the text representation for the AutoComplete suggestion (when using String type column) when CustomDataSource is provided. By default the name of the field bound to the column will be used.

#### Example
    <kendo:grid-column-filterable-cell dataTextField="dataTextField">
    </kendo:grid-column-filterable-cell>

### delay `float`

Specifies the delay of the AutoComplete widget which will provide the suggest functionality (when using String type column).

#### Example
    <kendo:grid-column-filterable-cell delay="delay">
    </kendo:grid-column-filterable-cell>

### enabled `boolean`

When set to false the Grid will not render the cell filtering widget for that specific column.

#### Example
    <kendo:grid-column-filterable-cell enabled="enabled">
    </kendo:grid-column-filterable-cell>

### inputWidth `float`

Specifies the width of the input before it is initialized or turned into a widget. Provides convenient way to set the width according to the column width.

#### Example
    <kendo:grid-column-filterable-cell inputWidth="inputWidth">
    </kendo:grid-column-filterable-cell>

### minLength `float`

Specifies the minLength option of the AutoComplete widget when column is of type string.

#### Example
    <kendo:grid-column-filterable-cell minLength="minLength">
    </kendo:grid-column-filterable-cell>

### operator `java.lang.String`

Specifies the default operator that will be used for the cell filtering.

#### Example
    <kendo:grid-column-filterable-cell operator="operator">
    </kendo:grid-column-filterable-cell>

### showOperators `boolean`

Specifies whether to show or hide the DropDownList with the operators.

#### Example
    <kendo:grid-column-filterable-cell showOperators="showOperators">
    </kendo:grid-column-filterable-cell>

### suggestionOperator `java.lang.String`

Specifies the AutoComplete filter option. Possible values are same as the one for the AutoComplete filter option- "startswidht", "endswith", "contains". Notice this operator is completely separate from the operator used for filtering on this column.

#### Example
    <kendo:grid-column-filterable-cell suggestionOperator="suggestionOperator">
    </kendo:grid-column-filterable-cell>

### template `java.lang.String`

JavaScript function which will customize how the input for the filter value is customized.

#### Example
    <kendo:grid-column-filterable-cell template="template">
    </kendo:grid-column-filterable-cell>


## Event Attributes

### template `String`

JavaScript function which will customize how the input for the filter value is customized.


#### Example
    <kendo:grid-column-filterable-cell template="handle_template">
    </kendo:grid-column-filterable-cell>
    <script>
        function handle_template(e) {
            // Code to handle the template event.
        }
    </script>

## Event Tags

### kendo:grid-column-filterable-cell-template

JavaScript function which will customize how the input for the filter value is customized.


#### Example
    <kendo:grid-column-filterable-cell>
        <kendo:grid-column-filterable-cell-template>
            <script>
                function(e) {
                    // Code to handle the template event.
                }
            </script>
        </kendo:grid-column-filterable-cell-template>
    </kendo:grid-column-filterable-cell>

