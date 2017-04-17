---
title: "방법: Drawing에 GuidelineSet 적용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "그래픽[WPF], GuidelineSet 속성"
  - "GuidelineSet 속성, 그리기에 적용"
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: Drawing에 GuidelineSet 적용
이 예제에서는 <xref:System.Windows.Media.DrawingGroup>에 <xref:System.Windows.Media.GuidelineSet>을 적용하는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Media.DrawingGroup> 클래스는 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> 속성이 있는 유일한 형식의 <xref:System.Windows.Media.Drawing>입니다.  다른 형식의 <xref:System.Windows.Media.Drawing>에 <xref:System.Windows.Media.GuidelineSet>을 적용하려면 <xref:System.Windows.Media.DrawingGroup>에 추가한 다음 해당 <xref:System.Windows.Media.DrawingGroup>에 <xref:System.Windows.Media.GuidelineSet>을 적용합니다.  
  
## 예제  
 다음 예제에서는 거의 동일한 두 개의 <xref:System.Windows.Media.DrawingGroup> 개체를 만듭니다. 두 번째 <xref:System.Windows.Media.DrawingGroup>에는 <xref:System.Windows.Media.GuidelineSet>이 있고 첫 번째 개체에는 이 속성이 없다는 점만 다릅니다.  
  
 다음 그림에서는 이 예제를 실행한 결과를 보여 줍니다.  두 <xref:System.Windows.Media.DrawingGroup> 개체의 렌더링된 모양에 별다른 차이가 없어 보이므로 그리기의 일부를 확대해서 보여 줍니다.  
  
 ![GuidelineSet이 있는 DrawingGroup과 없는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm\_drawinggroup\_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## 참고 항목  
 <xref:System.Windows.Media.DrawingGroup>   
 <xref:System.Windows.Media.GuidelineSet>   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)