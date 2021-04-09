---
solution: Campaign Classic
product: campaign
title: Uninstalling Campaign
description: Learn how to uninstall Campaign
audience: installation
content-type: reference
topic-tags: appendices
exl-id: 71c06216-040c-445b-bb72-dc44e47c1407,e2b026ba-aaf3-443d-8c36-c908288a14fd
---
# Uninstalling Campaign{#uninstalling-campaign}

>[!CAUTION]
>
>These procedures will uninstall permanently Adobe Campaign. All data will be lost.

**RHEL:**

```
rpm -e nlserver6-v7
userdel -r neolane
groupdel neolane
rm -rf /user/local/neolane
```

**Debian:**

```
apt purge nlserver6-v7
userdel -r neolane
groupdel neolane
rm -rf /user/local/neolane
```

**Windows:**

Refer to this [page](../../migration/using/migrating-in-windows-for-adobe-campaign-7.md#deleting-and-cleansing-adobe-campaign-previous-version). Don't forget to remove the Campaign installation folder.
