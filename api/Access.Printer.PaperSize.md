---
title: Printer.PaperSize property (Access)
keywords: vbaac10.chm12864
f1_keywords:
- vbaac10.chm12864
ms.prod: access
api_name:
- Access.Printer.PaperSize
ms.assetid: f2bafab2-f5bd-21be-fc5e-b428c31c9e4b
ms.date: 03/23/2019
ms.localizationpriority: medium
---


# Printer.PaperSize property (Access)

Returns or sets an **[AcPrintPaperSize](Access.AcPrintPaperSize.md)** constant indicating the paper size to use when printing. Read/write.


## Syntax

_expression_.**PaperSize**

_expression_ A variable that represents a **[Printer](Access.Printer.md)** object.


## Example

The following example sets a variety of printer settings for the form specified in the _strFormname_ argument of the procedure.

```vb
Sub SetPrinter(strFormname As String) 
 
 DoCmd.OpenForm FormName:=strFormname, view:=acDesign, _ 
 datamode:=acFormEdit, windowmode:=acHidden 
 
 With Forms(form1).Printer 
 
 .TopMargin = 1440 
 .BottomMargin = 1440 
 .LeftMargin = 1440 
 .RightMargin = 1440 
 
 .ColumnSpacing = 360 
 .RowSpacing = 360 
 
 .ColorMode = acPRCMColor 
 .DataOnly = False 
 .DefaultSize = False 
 .ItemSizeHeight = 2880 
 .ItemSizeWidth = 2880 
 .ItemLayout = acPRVerticalColumnLayout 
 .ItemsAcross = 6 
 
 .Copies = 1 
 .Orientation = acPRORLandscape 
 .Duplex = acPRDPVertical 
 .PaperBin = acPRBNAuto 
  .PaperSize = acPRPSLetter 
 .PrintQuality = acPRPQMedium 
 
 End With 
 
 DoCmd.Close objecttype:=acForm, objectname:=strFormname, _ 
 Save:=acSaveYes 
 
 
End Sub
```


[!include[Support and feedback](~/includes/feedback-boilerplate.md)]