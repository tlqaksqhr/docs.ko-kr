---
title: "방법: 도구 설명 배치"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc81fa247f21448a4ccbd62baccb72c0ec14bb31
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-position-a-tooltip"></a>방법: 도구 설명 배치
이 예제에서는 화면에 도구 설명의 위치를 지정 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
 도구 설명 모두에서 정의 하는 5 개의 속성 집합이 사용 하 여 배치할 수 있습니다는 <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ToolTipService> 클래스입니다. 다음 표에서 이러한 두 속성 집합의 5 개 보여주며, 클래스에 따라 참조 설명서의 링크를 제공 합니다.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>클래스에 따라 해당 하는 도구 설명 속성  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>클래스 속성|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>클래스 속성|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 사용 하 여 도구 설명의 내용을 정의 하는 경우는 <xref:System.Windows.Controls.ToolTip> 개체 클래스의 속성을 사용할 수 있지만 <xref:System.Windows.Controls.ToolTipService> 속성 보다 우선 적용 합니다. 사용 하 여는 <xref:System.Windows.Controls.ToolTipService> 로 정의 되어 있지 않은 도구 설명에 대 한 속성 <xref:System.Windows.Controls.ToolTip> 개체입니다.  
  
 다음 그림은 이러한 속성을 사용 하 여 도구 설명을 배치 하는 방법을 보여 줍니다. 하지만, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 이러한 그림의 예제에서 정의한 속성을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ToolTip> 클래스의 해당 속성은 <xref:System.Windows.Controls.ToolTipService> 클래스 같은 레이아웃 규칙을 따릅니다. 배치 속성에 대 한 가능한 값에 대 한 자세한 내용은 참조 [팝업 배치 동작](../../../../docs/framework/wpf/controls/popup-placement-behavior.md)합니다.  
  
 ![ToolTip 배치](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
배치 속성을 사용 하 여 ToolTip 배치  
  
 ![배치 사각형을 사용 하 여 ToolTip 배치](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
배치 및 PlacementRectangle 속성을 사용 하 여 ToolTip 배치  
  
 ![ToolTip 배치 다이어그램](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
Placement, PlacementRectangle, 및 오프셋 속성을 사용 하 여 ToolTip 배치  
  
 사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.ToolTip> 내용이 도구 설명의 위치를 지정 하는 속성을 <xref:System.Windows.Controls.ToolTip> 개체입니다.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.ToolTipService> 내용이 없는 도구 설명의 위치를 지정 하는 속성은 <xref:System.Windows.Controls.ToolTip> 개체입니다.  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [방법 항목](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [도구 설명 개요](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [ContextMenuService 및 ToolTipService 사용](http://msdn.microsoft.com/library/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
