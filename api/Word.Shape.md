---
title: Shape object (Word)
keywords: vbawd10.chm2464
f1_keywords:
- vbawd10.chm2464
ms.prod: word
api_name:
- Word.Shape
ms.assetid: 604029ce-9b2f-9748-5d4e-b458796fa2f0
ms.date: 04/25/2019
ms.localizationpriority: medium
---


# Shape object (Word)

Represents an object in the drawing layer, such as an AutoShape, freeform, OLE object, ActiveX control, or picture. The **Shape** object is a member of the **[Shapes](Word.shapes.md)** collection, which includes all the shapes in the main story of a document or in all the headers and footers of a document.


## Remarks

A shape is always attached to an anchoring range. You can position the shape anywhere on the page that contains the anchor. 

There are three objects that represent shapes: the **Shapes** collection, which represents all the shapes on a document; the **[ShapeRange](Word.shaperange.md)** object, which represents a specified subset of the shapes on a document (for example, a **ShapeRange** object could represent shapes one and four on the document, or it could represent all the selected shapes on the document); and the **Shape** object, which represents a single shape on a document. If you want to work with several shapes at the same time or with shapes within the selection, use a **ShapeRange** collection.

Use **Shapes** (_index_), where _index_ is the name or the index number, to return a single **Shape** object. The following example horizontally flips shape one on the active document.

```vb
ActiveDocument.Shapes(1).Flip msoFlipHorizontal
```

<br/>

The following example horizontally flips the shape named Rectangle 1 on the active document.

```vb
ActiveDocument.Shapes("Rectangle 1").Flip msoFlipHorizontal
```

<br/>

Each shape is assigned a default name when it is created. For example, if you add three different shapes to a document, they might be named Rectangle 2, TextBox 3, and Oval 4. To give a shape a more meaningful name, set the **Name** property.

Use **ShapeRange** (_index_), where _index_ is the name or the index number, to return a **Shape** object that represents a shape within a selection. The following example sets the fill for the first shape in the selection, assuming that the selection contains at least one shape.

```vb
Selection.ShapeRange(1).Fill.ForeColor.RGB = RGB(255, 0, 0)
```

<br/>

The following example sets the fill for all the shapes in the selection, assuming that the selection contains at least one shape.

```vb
Selection.ShapeRange.Fill.ForeColor.RGB = RGB(255, 0, 0)
```

<br/>

To add a **Shape** object to the collection of shapes for the specified document and return a **Shape** object that represents the newly created shape, use one of the following methods of the **Shapes** collection: **AddCallout**, **AddCurve**, **AddLabel**, **AddLine**, **AddOleControl**, **AddOleObject**, **AddPolyline**, **AddShape**, **AddTextbox**, **AddTextEffect**, or **BuildFreeForm**. The following example adds a rectangle to the active document.

```vb
ActiveDocument.Shapes.AddShape msoShapeRectangle, 50, 50, 100, 200
```

<br/>

Use **GroupItems** (_index_), where _index_ is the shape name or the index number within the group, to return a **Shape** object that represents a single shape in a grouped shape.

Use the **Group** or **Regroup** method to group a range of shapes and return a single **Shape** object that represents the newly formed group. After a group has been formed, you can work with the group the same way you work with any other shape.

Every **Shape** object is anchored to a range of text. A shape is anchored to the beginning of the first paragraph that contains the anchoring range. The shape will always remain on the same page as its anchor.

You can view the anchor itself by setting the **ShowObjectAnchors** property to **True**. The shape's **Top** and **Left** properties determine its vertical and horizontal positions. The shape's **RelativeHorizontalPosition** and **RelativeVerticalPosition** properties determine whether the position is measured from the anchoring paragraph, the column that contains the anchoring paragraph, the margin, or the edge of the page.

If the **LockAnchor** property for the shape is set to **True**, you cannot drag the anchor from its position on the page.

Use the **Fill** property to return the **FillFormat** object, which contains all the properties and methods for formatting the fill of a closed shape. 

The **Shadow** property returns the **ShadowFormat** object, which you use to format a shadow. 

Use the **Line** property to return the **LineFormat** object, which contains properties and methods for formatting lines and arrows. 

The **TextEffect** property returns the **TextEffectFormat** object, which you use to format WordArt. 

The **Callout** property returns the **CalloutFormat** object, which you use to format line callouts. 

The **WrapFormat** property returns the **WrapFormat** object, which you use to define how text wraps around shapes. 

The **ThreeD** property returns the **ThreeDFormat** object, which you use to create 3D shapes. 

Use the **PickUp** and **Apply** methods to transfer formatting from one shape to another.

Use the **SetShapesDefaultProperties** method for a **Shape** object to set the formatting for the default shape for the document. New shapes inherit many of their attributes from the default shape.

Use the **Type** property to specify the type of shape: freeform, AutoShape, OLE object, callout, or linked picture, for example. Use the **AutoShapeType** property to specify the type of AutoShape: oval, rectangle, or balloon, for example.

Use the **Width** and **Height** properties to specify the size of the shape.

The **TextFrame** property returns the **TextFrame** object, which contains all the properties and methods for attaching text to shapes and linking the text between text frames.

**Shape** objects are anchored to a range of text but are free-floating and can be positioned anywhere on the page. **InlineShape** objects are treated like characters and are positioned as characters within a line of text. Use the **ConvertToInlineShape** method and the **ConvertToShape** method to convert shapes from one type to the other. You can convert only pictures, OLE objects, and ActiveX controls to inline shapes.

## Methods

- [Apply](Word.Shape.Apply.md)
- [CanvasCropBottom](Word.Shape.CanvasCropBottom.md)
- [CanvasCropLeft](Word.Shape.CanvasCropLeft.md)
- [CanvasCropRight](Word.Shape.CanvasCropRight.md)
- [CanvasCropTop](Word.Shape.CanvasCropTop.md)
- [ConvertToInlineShape](Word.Shape.ConvertToInlineShape.md)
- [Delete](Word.Shape.Delete.md)
- [Duplicate](Word.Shape.Duplicate.md)
- [Flip](Word.Shape.Flip.md)
- [IncrementLeft](Word.Shape.IncrementLeft.md)
- [IncrementRotation](Word.Shape.IncrementRotation.md)
- [IncrementTop](Word.Shape.IncrementTop.md)
- [PickUp](Word.Shape.PickUp.md)
- [ScaleHeight](Word.Shape.ScaleHeight.md)
- [ScaleWidth](Word.Shape.ScaleWidth.md)
- [Select](Word.Shape.Select.md)
- [SetShapesDefaultProperties](Word.Shape.SetShapesDefaultProperties.md)
- [Ungroup](Word.Shape.Ungroup.md)
- [ZOrder](Word.Shape.ZOrder.md)

## Properties

- [Adjustments](Word.Shape.Adjustments.md)
- [AlternativeText](Word.Shape.AlternativeText.md)
- [Anchor](Word.Shape.Anchor.md)
- [Application](Word.Shape.Application.md)
- [AutoShapeType](Word.Shape.AutoShapeType.md)
- [BackgroundStyle](Word.Shape.BackgroundStyle.md)
- [Callout](Word.Shape.Callout.md)
- [CanvasItems](Word.Shape.CanvasItems.md)
- [Chart](Word.Shape.Chart.md)
- [Child](Word.Shape.Child.md)
- [Creator](Word.Shape.Creator.md)
- [Decorative](Word.Shape.Decorative.md)
- [Fill](Word.Shape.Fill.md)
- [Glow](Word.Shape.Glow.md)
- [GraphicStyle](Word.Shape.GraphicStyle.md)
- [GroupItems](Word.Shape.GroupItems.md)
- [HasChart](Word.Shape.HasChart.md)
- [HasSmartArt](Word.Shape.HasSmartArt.md)
- [Height](Word.Shape.Height.md)
- [HeightRelative](Word.Shape.HeightRelative.md)
- [HorizontalFlip](Word.Shape.HorizontalFlip.md)
- [Hyperlink](Word.Shape.Hyperlink.md)
- [ID](Word.Shape.ID.md)
- [LayoutInCell](Word.Shape.LayoutInCell.md)
- [Left](Word.Shape.Left.md)
- [LeftRelative](Word.Shape.LeftRelative.md)
- [Line](Word.Shape.Line.md)
- [LinkFormat](Word.Shape.LinkFormat.md)
- [LockAnchor](Word.Shape.LockAnchor.md)
- [LockAspectRatio](Word.Shape.LockAspectRatio.md)
- [Model3D](Word.Shape.Model3D.md)
- [Name](Word.Shape.Name.md)
- [Nodes](Word.Shape.Nodes.md)
- [OLEFormat](Word.Shape.OLEFormat.md)
- [Parent](Word.Shape.Parent.md)
- [ParentGroup](Word.Shape.ParentGroup.md)
- [PictureFormat](Word.Shape.PictureFormat.md)
- [Reflection](Word.Shape.Reflection.md)
- [RelativeHorizontalPosition](Word.Shape.RelativeHorizontalPosition.md)
- [RelativeHorizontalSize](Word.Shape.RelativeHorizontalSize.md)
- [RelativeVerticalPosition](Word.Shape.RelativeVerticalPosition.md)
- [RelativeVerticalSize](Word.Shape.RelativeVerticalSize.md)
- [Rotation](Word.Shape.Rotation.md)
- [Script](Word.Shape.Script.md)
- [Shadow](Word.Shape.Shadow.md)
- [ShapeStyle](Word.Shape.ShapeStyle.md)
- [SmartArt](Word.Shape.SmartArt.md)
- [SoftEdge](Word.Shape.SoftEdge.md)
- [TextEffect](Word.Shape.TextEffect.md)
- [TextFrame](Word.Shape.TextFrame.md)
- [TextFrame2](Word.Shape.TextFrame2.md)
- [ThreeD](Word.Shape.ThreeD.md)
- [Title](Word.Shape.Title.md)
- [Top](Word.Shape.Top.md)
- [TopRelative](Word.Shape.TopRelative.md)
- [Type](Word.Shape.Type.md)
- [VerticalFlip](Word.Shape.VerticalFlip.md)
- [Vertices](Word.Shape.Vertices.md)
- [Visible](Word.Shape.Visible.md)
- [Width](Word.Shape.Width.md)
- [WidthRelative](Word.Shape.WidthRelative.md)
- [WrapFormat](Word.Shape.WrapFormat.md)
- [ZOrderPosition](Word.Shape.ZOrderPosition.md)

## See also

- [Word Object Model Reference](overview/Word/object-model.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]
