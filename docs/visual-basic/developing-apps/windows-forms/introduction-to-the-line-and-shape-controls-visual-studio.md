---
title: "Introduction to the Line and Shape Controls (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Line control, overview"
  - "Shape control, overview"
  - "lines, drawing"
  - "shapes, drawing"
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Introduction to the Line and Shape Controls (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Visual Basic Power Packs의 Line 및 Shape 컨트롤은 폼 및 컨테이너에 선 및 도형을 그릴 수 있는 세 그래픽 컨트롤의 집합입니다.  <xref:Microsoft.VisualBasic.PowerPacks.LineShape> 컨트롤을 사용하여 가로선, 세로선 및 대각선을 그립니다.  <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 컨트롤을 사용하여 원 및 타원을 그리고, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 컨트롤을 사용하여 사각형을 그립니다.  
  
## Line 및 Shape 컨트롤  
 Line 및 Shape 컨트롤은 <xref:System.Drawing> 네임스페이스에 포함된 많은 그래픽 메서드를 캡슐화합니다.  이를 통해 그래픽 개체, 펜 및 브러시를 만들지 않고도 한 번에 선 및 도형을 그릴 수 있습니다.  일부 속성을 설정하기만 하여 그라데이션 채우기와 같은 복잡한 그래픽 기술을 수행할 수 있습니다.  
  
 그래픽 메서드를 사용하여 선과 도형을 그릴 수도 있지만 Line 및 Shape 컨트롤을 사용하는 경우 여러 이점이 있습니다.  
  
-   그래픽 메서드는 런타임에만 호출할 수 있지만  Line 및 Shape 컨트롤은 디자인 타임에 폼에 추가할 수 있습니다.  따라서 이러한 컨트롤의 모양을 확인하고 컨트롤을 정확하게 배치할 수 있습니다. 또한 이러한 컨트롤을 런타임에 추가할 수도 있습니다.  
  
-   런타임에 Line 및 Shape 컨트롤을 선택할 수 있으며 이러한 컨트롤에서 <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> 및 <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>과 같은 이벤트를 제공합니다.  그래픽 메서드의 출력은 선택할 수 없으며 이벤트를 제공하지도 않습니다.  
  
-   Line 및 Shape 컨트롤은 <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> 및 <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> 메서드를 제공합니다. 따라서 사용자는 디자인 타임과 런타임에 Z 순서를 제어할 수 있습니다.  그래픽 메서드의 Z 순서는 런타임에 실행 순서를 변경해야만 제어할 수 있습니다.  
  
-   Line 및 Shape 컨트롤은 창 없는 컨트롤입니다. 이러한 컨트롤에 창 핸들이 없으므로 시스템 리소스가 덜 사용됩니다.  
  
### 개체 모델  
 Line 및 Shape 컨트롤은 공유 속성, 메서드 및 이벤트를 정의하는 기본 <xref:Microsoft.VisualBasic.PowerPacks.Shape> 클래스에서 파생됩니다.  
  
 다음 그림에서는 Line 및 Shape 개체 계층 구조를 보여 줍니다.  
  
 ![선 및 도형 개체의 계층 구조를 보여 주는 다이어그램](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Line 및 Shape 개체 계층 구조  
  
 파생 <xref:Microsoft.VisualBasic.PowerPacks.LineShape> 클래스에는 선에 고유한 속성, 메서드 및 이벤트가 포함됩니다.  파생 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> 클래스는 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 및 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>의 기본 클래스입니다. 이 클래스에는 모든 도형에 공통적인 속성, 메서드 및 이벤트가 포함됩니다.  또한 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape>에서 파생하여 사용자 고유의 `Shape` 컨트롤을 만들 수 있습니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 및 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 클래스를 사용하여 원, 타원, 사각형 및 모퉁이가 둥근 사각형을 그릴 수 있습니다.  
  
 Line 또는 Shape 컨트롤이 폼 또는 컨테이너에 추가되면 보이지 않는 <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> 개체가 만들어집니다.  <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>는 각 컨테이너 컨트롤 내에서 도형에 대한 캔버스로 작동합니다. 각 <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>에는 해당되는 <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection>이 있어 사용자가 Line 및 Shape 컨트롤을 반복할 수 있습니다.  잘라내어 붙여넣기를 사용하거나 끌어서 놓아 한 컨테이너에서 다른 컨테이너로 도형을 이동할 수 있습니다.  컨테이너에서 마지막 도형이 제거되면 <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>도 제거됩니다.  
  
> [!NOTE]
>  일부 컨테이너에서는 Line 및 Shape 컨트롤을 지원하지 않습니다.  <xref:System.Windows.Forms.TableLayoutPanel> 또는 <xref:System.Windows.Forms.FlowLayoutPanel>에서 Line 또는 Shape 컨트롤을 호스팅할 수 없습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks>   
 [How to: Draw Lines with the LineShape Control](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)   
 [How to: Draw Shapes with the OvalShape and RectangleShape Controls](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)   
 [How to: Enable Tabbing Between Shapes](../Topic/How%20to:%20Enable%20Tabbing%20Between%20Shapes%20\(Visual%20Studio\).md)