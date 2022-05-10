---
title: Get started with Campaign FDA-Snowflake deployment
description: Get started with Campaign FDA-Snowflake deployment
feature: Overview
role: Data Engineer
level: Beginner
---
# [!DNL Campaign] FDA [!DNL Snowflake] deployment{#gs-fda-snowflake}

In a [!DNL Snowflake] FDA (default) deployment, [!DNL Adobe Campaign] v8 is connected to [!DNL Snowflake] to access data through [Federated Data Access](../connect/fda.md) capability: you can access and process external data and information stored in your [!DNL Snowflake] database without changing the structure of Adobe Campaign data. 

With this deployment model, Adobe Campaign users can extend their data into [!DNL Snowflake] and leverage the benefits of a single, integrated data platform for powerful marketing campaign data insights in real-time. It provides users with the ability to unlock deep value from their data by offering a single, unified, and easy-to-use platform for data analysis. The cloud data platform requires no management as it infinitely scales to support any volume of marketing data from Adobe Campaign.

General communication between servers and processes is carried out according to the following schema:

![](assets/fda-architecture.png) 

PostgreSQL is the primary database, and Snowflake is the secondary database. You can extend your data model and store your data on Snowflake. Subsequently, you can run ETL, segmentation and reports on a large data set with outstanding performances.

