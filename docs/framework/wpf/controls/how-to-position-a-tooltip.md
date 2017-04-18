---
title: "방법: 도구 설명 배치 | Microsoft Docs"
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
  - "ToolTip 컨트롤 위치 지정"
  - "ToolTip 컨트롤, 위치 지정"
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 도구 설명 배치
이 예제에서는 화면에서 도구 설명 위치를 지정하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ToolTipService> 클래스 모두에서 정의되는 다섯 개의 속성 집합을 사용하여 도구 설명을 배치할 수 있습니다.  다음 표에서는 이러한 다섯 가지 속성 집합 두 개를 보여 주고 클래스에 대한 참고 문서 링크를 제공합니다.  
  
### 클래스에 따른 해당 도구 설명 속성  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=fullName> 클래스 속성|<xref:System.Windows.Controls.ToolTipService?displayProperty=fullName> 클래스 속성|  
|----------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=fullName>|  
  
 <xref:System.Windows.Controls.ToolTip> 개체를 사용하여 도구 설명의 내용을 정의하는 경우 두 클래스 중 하나의 속성을 사용할 수 있지만 <xref:System.Windows.Controls.ToolTipService> 속성의 우선 순위가 더 높습니다.  <xref:System.Windows.Controls.ToolTip> 개체로 정의되지 않은 도구 설명에는 <xref:System.Windows.Controls.ToolTipService> 속성을 사용합니다.  
  
 다음 그림에서는 이들 속성을 사용하여 도구 설명을 배치하는 방법을 보여 줍니다.  이 그림의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제는 <xref:System.Windows.Controls.ToolTip> 클래스로 정의된 속성을 설정하는 방법을 보여 주긴 하지만, <xref:System.Windows.Controls.ToolTipService> 클래스의 해당 속성에도 같은 레이아웃 규칙이 적용됩니다.  Placement 속성에 사용할 수 있는 값에 대한 자세한 내용은 [Popup 배치 동작](../../../../docs/framework/wpf/controls/popup-placement-behavior.md)을 참조하십시오.  
  
 ![ToolTip 배치](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
Placement 속성을 사용한 도구 설명 배치  
  
 ![배치 사각형을 사용하여 ToolTip 배치](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
Placement 및 PlacementRectangle 속성을 사용한 도구 설명 배치  
  
 ![ToolTip 배치 다이어그램](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
Placement, PlacementRectangle 및 Offset 속성을 사용한 도구 설명 배치  
  
 다음 예제에서는 <xref:System.Windows.Controls.ToolTip> 속성을 사용하여 내용이 <xref:System.Windows.Controls.ToolTip> 개체인 도구 설명의 위치를 지정하는 방법을 보여 줍니다.  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.ToolTipService> 속성을 사용하여 내용이 <xref:System.Windows.Controls.ToolTip> 개체가 아닌 도구 설명의 위치를 지정하는 방법을 설명합니다.  
  
 [!code-xml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [방법 항목](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)   
 [도구 설명 개요](../../../../docs/framework/wpf/controls/tooltip-overview.md)   
 [Use the ContextMenuService and ToolTipService](http://msdn.microsoft.com/ko-kr/809b0e9c-d612-4cda-b8af-1a698c68f4d1)