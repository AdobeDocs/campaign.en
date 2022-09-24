---
title: Predictive user engagement capabilities
description: Learn how to use predictive send time and engagement scoring
feature: Send Time Optimization
role: User
level: Beginner
---
# Send-time optimization and predictive engagement scoring{#optimize-message-delivery}

Powered by AI and machine learning, Adobe Campaign’s Send-Time Optimization and Predictive Engagement Scoring can analyze and predict open rates, optimal send times, and probable churn based on historical engagement metrics.

Adobe Campaign offers two new Machine Learning models: [Predictive Send Time Optimization](#predictive-send) and [Predictive Engagement Scoring](#predictive-scoring). These two models are machine-learning models that are specific to designing and delivering better customer journeys.

>[!CAUTION]
>
>This capability is not available out of the box as part of the product. It is only available for Adobe Campaign Managed Cloud Services customers running Adobe Campaign Classic v7 or Adobe Campaign v8.
>
>The implementation requires Adobe Consulting to be engaged. To find out more, reach out to your Adobe representative.
>


## Predictive send time optimization{#predictive-send}

Predictive Send-Time Optimization predicts which is the best send time for each recipient profile for email opens or clicks and for push-message opens. For each recipient profile, the scores indicate the best send time for each weekday and which weekday is the best to send for best results. 

Within the Predictive Send-Time Optimization model, there are two sub-models:

* Predictive send time for open is the best time a communication must be sent to the customer to maximize opens

* Predictive send time for click is the best time a communication must be sent to the customer to maximize clicks


**Model Input**: Delivery logs, tracking logs and profile attributes (non-PII)

**Model Output**: Best time to send a message (for opens and clicks)

Output details:

* Compute the best time of day to send an email for in the 7 days of the week with 1 hour intervals (e.g.: 9:00 am, 10:00 am, 11:00 am)
* The model will indicate the best day in the week and the best hour in that day
* Each optimal time is computed twice: once to maximize open rate and once to maximize click rate
* 16 fields are given (14 for days of the week and 2 for the whole week):
    * best time to send an email to optimize clicks for Monday - values between 0 and 23
    * best time to send an email to optimize opens for Monday - values between 0 and 23
    * ...
    * best time to send an email to optimize clicks for Sunday - values between 0 and 23
    * best time to send an email to optimize opens for Sunday - values between 0 and 23
    * ...
    * best day to send an email to optimize opens for the whole week - Monday to Sunday
    * best time to send an email to optimize opens for the whole week - values between 0 and 23


Predictive Send Time Optimization is stored at profile level:

![](assets/sto-schema.png)


>[!NOTE]
>
>The model needs at least one month of data to produce significant results. These predictive capabilities apply only to email and push channels.
>


## Predictive engagement scoring {#predictive-scoring}

Predictive Engagement Scoring predicts the probability of a recipient engaging with a message as well as the probability of opting out (unsubscribing) within the next 7 days after the next email send. The probabilities are further divided into buckets according to the predicted level of engagement with your content: high, medium, or low. These models also provide the unsubscribe-risk percentile rank for the customers to understand where the rank of a certain customer is in relation to others.

The predictive engagement scoring lets you:

* **Select an audience**: by using the query activity, you can select the audience to engage with a specific message
* **Exclude an audience**: by using the query activity, you can remove the audience to unsubscribe
* **Personalize**: personalize message based on level of engagement (highly engaged users will get a different message than un-engaged ones)

This model uses multiple scores to indicate:

* **Open Engagement Score / Click Engagement Score**: this value matches the probability that a subscriber will engage with a specific message (open or click). Values range from 0.0 to 1.0.
* **Unsubscription probability**: this value matches the probability for recipient to unsubscribe from email channel given one email opened. Values range from 0.0 to 1.0.
* **Retention level**:  this value ranks users into three levels: low, medium and high. High being most likely to stay with the brand and low value likely to unsubscribe.
* **Percentile rank of retention**: profile rank in terms of unsubscription probability. Values range from 0.0 to 1.0. For example, if the retention percent rank is 0.953, this recipient is more likely to stay with brand and less likely to unsubscribe than 95.3% of all recipients.

>[!NOTE]
>
>These predictive capabilities only apply to email deliveries.
>
>The model needs at least one month of data to produce significant results.

**Model Input**: Delivery logs, tracking logs and specific profile attributes

**Model Output**: A profile attribute that describes the profile’s score and category
