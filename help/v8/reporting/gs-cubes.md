---
title: Get started with Adobe Campaign analytics reports
description: Learn how to create cubes
feature: Reporting
role: Data Engineer
level: Beginner
---
# Get started with marketing analytics {#gs-cube}

Adobe Campaign comes with an intuitive data exploration tool to create dynamic reports.

Use marketing analytics capatilities to analyze and measure data, calculate statistics, simplify and optimize report creation and calculation. You can create reports and build target populations and store them into lists which can be used in Adobe Campaign for targeting or segmentation tasks.
    
You can extend the database exploration and analysis capacities while making it easier for final users to configure reports and tables: all they need to do is select an existing (fully configured) cube when creating their report or table to process calculations, measures and statistics.

Once they have been created and configured, cubes are used in report query boxes and Web applications. They can be used and manipulated within pivot tables.

Use the Campaign Marketing Analytics module to:

1. Create cubes and indicators

    * aggregate and store data in a work table to pre-calculate indicators based on user needs,
    * reduce the volume of data involved in the various calculations used for reports and queries, thus significantly optimizing indicator calculation times,
    * simplify access to data, enable users to manipulate data (whether it is pre-aggregated or not) depending on various dimensions.

   For more on this, refer to [Create indicators](cube-indicators.md).

1. Create pivot tables and explore data

    * explore calculated data, configured measures,
    * select the data to display as well as its display mode,
    * personalize the measures and indicators used,
    * offer interactive analysis tools to users with a non-technical background.

   For more on this, refer to [Use cubes to explore data](cube-tables.md).

1. Build a query using data calculated and aggregated in a Cube.
1. Identify populations and reference them in lists.

## Terminology {#terminology}

Specific terms when working with cubes are listed below.

* **Cube** - A cube is a representation of multidimensional information: it provides end users with structures designed for interactive data analysis.

* **Fact table/schema** - The fact table (or fact schema) contains the raw or elementary data on which analyses will be based. These are mainly large volume tables (possibly with linked tables) with potentially long calculations. For example, a fact table can be: the broadlog table, the purchase table, etc.

* **Dimension** - Dimensions let you segment data into groups: once they have been created, the dimensions serve as analysis axes. In most cases, for a given dimension, several levels will be defined. For example, for a temporal dimension, the levels will be months, days, hours, minutes, etc. This set of levels represents the dimension hierarchy and enables various levels of data analysis.

* **Binning** - For some fields, you can define binning to group values and make it easier to read information. Binning is applied to levels. We recommend that you define binning when there is a possibility of many different values.

* **Measure** - The most frequent measures are sum, average, maximum, minimum, standard deviation etc. Measures can be calculated: for instance, the acceptance rate of an offer is the ratio of the number of times it was presented compared to the number of times it was accepted.
