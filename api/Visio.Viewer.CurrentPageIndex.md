---
title: Viewer.CurrentPageIndex property (Visio Viewer)
ms.prod: visio
api_name:
- Visio.Viewer.CurrentPageIndex
ms.assetid: 2a7950cf-c079-da63-676d-cf6a7e8a3600
ms.date: 06/21/2019
ms.localizationpriority: medium
---


# Viewer.CurrentPageIndex property (Visio Viewer)

Gets or sets the index of the page displayed when a drawing opens in Microsoft Visio Viewer. Read/write.


## Syntax

_expression_.**CurrentPageIndex**

_expression_ An expression that returns a **[Viewer](Visio.Viewer.md)** object.


## Return value

**Long**


## Remarks

Set the **CurrentPageIndex** value to the index of the page in the Visio drawing that you want to display. For example, to display Page-1, set the value to 1. If you don't specify a page index or if you set the value to 0, Visio Viewer displays the same page that was displayed the last time you saved the drawing.

If no drawing is loaded in Visio Viewer, the **CurrentPageIndex** value is 0.

If the **DocumentLoaded** property value is **True**, the **CurrentPageIndex** value must be between 1 and the value of the **PageCount** property; if you set the property to a value that represents a nonexistent page, Visio Viewer ignores the setting.


## Example

The following code gets the index of the page displayed in Visio Viewer when a drawing opens.

```vb
 Debug.Print vsoViewer.CurrentPageIndex
```

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]