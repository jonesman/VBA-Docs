---
title: Application.SetCustomMenus method (Visio)
keywords: vis_sdr.chm10016560
f1_keywords:
- vis_sdr.chm10016560
ms.prod: visio
api_name:
- Visio.Application.SetCustomMenus
ms.assetid: 90aa627c-ba51-87a7-4347-6a806998e1a4
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# Application.SetCustomMenus method (Visio)

Replaces the current built-in or custom menus of an application or document.

> [!NOTE] 
> Starting with Visio 2010, the Microsoft Office Fluent user interface (UI) replaced the previous system of layered menus, toolbars, and task panes. VBA objects and members that you used to customize the user interface in previous versions of Visio are still available in Visio, but they function differently.

## Syntax

_expression_.**SetCustomMenus** (_MenusObject_)

_expression_ A variable that represents an **[Application](Visio.Application.md)** object.


## Parameters



|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _MenusObject_|Required| **[IVUIOBJECT]**|An expression that returns a **UIObject** object that represents the new custom menus.|

## Return value

Nothing


## Remarks



If the **UIObject** object was created in a separate process by using the CreateObject procedure instead of getting the appropriate property of an **Application** or **Document** object, the **SetCustomMenus** method returns an error.


## Example

This Microsoft Visual Basic for Applications (VBA) macro shows how to add a menu and menu item to the user interface, and then replace the built-in menu set with the custom set.

To restore the Microsoft Visio built-in user interface after you run this macro, call the **ThisDocument.ClearCustomMenus** method.




```vb
 
Public Sub SetCustomMenus_Example() 
 
 Dim vsoUIObject As Visio.UIObject 
 Dim vsoMenuSets As Visio.MenuSets 
 Dim vsoMenuSet As Visio.MenuSet 
 Dim vsoMenus As Visio.Menus 
 Dim vsoMenu As Visio.Menu 
 Dim vsoMenuItems As Visio.MenuItems 
 Dim vsoMenuItem As Visio.MenuItem 
 
 'Get a UI object that represents the Microsoft Visio built-in menus. 
 Set vsoUIObject = Visio.Application.BuiltInMenus 
 
 'Get the MenuSets collection. 
 Set vsoMenuSets = vsoUIObject.MenuSets 
 
 'Get the drawing window menu set. 
 Set vsoMenuSet = vsoMenuSets.ItemAtID(visUIObjSetDrawing) 
 
 'Get the Menus collection. 
 Set vsoMenus = vsoMenuSet.Menus 
 
 'Add a Demo menu. 
 Set vsoMenu = vsoMenus.AddAt(1) 
 vsoMenu.Caption = "Demo" 
 
 'Get the MenuItems collection. 
 Set vsoMenuItems = vsoMenu.MenuItems 
 
 'Add a menu item to the new Demo menu. 
 Set vsoMenuItem = vsoMenuItems.Add 
 
 'Set the properties for the new menu item. 
 vsoMenuItem.Caption = "&Hello" 
 vsoMenuItem.AddOnName = "MsgBox ""Hello""" 
 
 'Tell Visio to use the new UI when the document is active. 
 ThisDocument.SetCustomMenus vsoUIObject 
 
End Sub
```

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]