---
title: Selection.Flags property (Word)
keywords: vbawd10.chm158663058
f1_keywords:
- vbawd10.chm158663058
ms.prod: word
api_name:
- Word.Selection.Flags
ms.assetid: bca92e77-077c-57d0-3012-8c064e93f112
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# Selection.Flags property (Word)

Returns or sets properties of the selection. Read/write **[WdSelectionFlags](Word.WdSelectionFlags.md)**.


## Syntax

_expression_.**Flags**

_expression_ Required. An expression that returns a **[Selection](Word.Selection.md)** object.

## Remark

Once set this value, it will be stored with MS Word itself, which means when you next time start MS Word, the Selection objects' behavior will be the previous setting. So if you set this value to 8 or 9, the next time you will not be able to replace the selected range when you add or type the new one. That is, for example, when "hello" is selected and type "world" on the selected range, It will be inserted before the "hello" and not replace "hello" with "world". You have to reset this value to 24 or 25 to restore the default behavior about Selection objects. The value of this property 24 should be the sum of the [wdSelActive and wdSelReplace](Word.WdSelectionFlags.md) and 25 = 24 + 1 should be plus the [wdSelStartActive](Word.WdSelectionFlags.md) after. And 8 or 9 is without the value wdSelReplace, so when without wdSelReplace setting in this, it will not allow to replace the selected range.

## Example

This example selects the first word in the active document. The first message box displays "False" because the end of the selection is active. The **Flags** property makes the beginning of the selection active, and the second message box displays "True."


```vb
ActiveDocument.Words(1).Select 
MsgBox Selection.StartIsActive 
Selection.Flags = wdSelStartActive 
MsgBox Selection.StartIsActive
```

This example turns on overtype mode for the selection.




```vb
Selection.Flags = wdSelOvertype
```


## See also


[Selection Object](Word.Selection.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]
