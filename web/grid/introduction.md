---
title: Introduction
page_title: Overview of Grid UI widget | Kendo UI Documentation
description: Quick steps to help you create Kendo UI Grid
position: 1
---

# Grid Introduction

The Grid is a powerful widget for displaying tabular data. It provides a lot of options that define how the data is presented and manipulated,
including paging, sorting, filtering, grouping and editing. The Grid can be bound to local or remote data using the Kendo DataSource component.

## Getting Started

There are two primary ways to create a Kendo UI Grid:

* From an empty `div` element. In this case all the Grid settings are provided in the initialization script statement.
* From an existing HTML `table` element. In this case some of the Grid settings can be inferred from the table structure and elements' HTML attributes.

### Create a Grid from an empty div

    <!-- Define the HTML div that will hold the Grid -->
    <div id="grid"></div>

    <!-- Initialize the Grid -->
    <script>

        $(document).ready(function(){
            $("#grid").kendoGrid({
                columns: [{
                    field: "FirstName",
                    title: "First Name"
                },
                {
                    field: "LastName",
                    title: "Last Name"
                }],
                dataSource: {
                    data: [{
                        FirstName: "Joe",
                        LastName: "Smith"
                    },
                    {
                        FirstName: "Jane",
                        LastName: "Smith"
                    }]
                }
            });
        });

    </script>

### Create a Grid from an existing HTML table

When creating the Grid from a table, it is usually already populated with data. This improves the accessibility and search engine optimization,
and ensures that the user will see data even if Javascript is disabled or there is a Javascript error on the page.

    <!-- Define the HTML table, with rows, columns, and data -->
    <table id="grid">
        <thead>
            <tr>
                <th data-field="title">Title</th>
                <th data-field="year">Year</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Star Wars: A New Hope</td>
                <td>1977</td>
            </tr>
            <tr>
                <td>Star Wars: The Empire Strikes Back</td>
                <td>1980</td>
            </tr>
        </tbody>
    </table>

    <!-- Initialize the Grid -->
    <script>

        $(document).ready(function(){
          $("#grid").kendoGrid();
        });

    </script>

It is important to know that the Grid uses a Kendo UI DataSource instance even when it is created from a table. The cell content is extracted and thus the DataSource is populated.
The data field names in the DataSource are either created from the header cell content or the `data-field` attributes of the header cells.
The data field names should be valid Javascript identifiers, that's why it is recommended to use `data-field` attributes, otherwise the header cell content must obey several limitations:

* no spaces
* no special characters
* the first character should be a letter

As seen from the above code snippets, in one case the Grid client object is attached to a `div`, while in the other case, the object is attached to a `table`.
However, the generated resulting HTML output of the Grid depends entirely on the widget settings and it will always be the same, no matter how the widget is initialized.
