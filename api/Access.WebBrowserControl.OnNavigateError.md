---
title: WebBrowserControl.OnNavigateError property (Access)
keywords: vbaac10.chm14415,vbaac10.chm5906
f1_keywords:
- vbaac10.chm14415,vbaac10.chm5906
ms.prod: access
api_name:
- Access.WebBrowserControl.OnNavigateError
ms.assetid: aeb415fb-3dcf-f656-db0d-71db2a72433c
ms.date: 03/26/2019
ms.localizationpriority: medium
---


# WebBrowserControl.OnNavigateError property (Access)

Gets or sets the value of the **On Navigate Error** box in the property sheet of a web browser control. Read/write **String**.


## Syntax

_expression_.**OnNavigateError**

_expression_ A variable that represents a **[WebBrowserControl](Access.WebBrowserControl.md)** object.


## Remarks

This property is helpful for programmatically changing the action that Microsoft Access takes when an event is triggered. For example, between event calls you may want to change an expression's parameters, or switch from an event procedure to an expression or macro, depending on the circumstances under which the event was triggered.


[!include[Support and feedback](~/includes/feedback-boilerplate.md)]