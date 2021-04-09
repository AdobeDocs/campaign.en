---
solution: Campaign Classic
product: campaign
title: JSP behavior
description: JSP behavior
audience: production
content-type: reference
topic-tags: troubleshooting
exl-id: 858d00d0-7c65-43be-8bae-f0f945f71f1a,9424858f-e7bb-4af7-a6a2-ee2e47d5f3d4
---
# JSP behavior{#jsp-behavior}

If certain **jsp** jobs are not successfully executed, you must force them to recompile.

For this, enter the following commands:

```
nlserver stop web
cd nl6/tomcat-8
rm -r work/
nlserver start web
```

The **jsp** jobs are regenerated the next time you connect.
