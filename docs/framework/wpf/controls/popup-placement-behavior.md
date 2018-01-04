---
title: "Popup 배치 동작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d991895b7c10ee5c210b252855e5affcfcb22a9c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="popup-placement-behavior"></a>Popup 배치 동작
A <xref:System.Windows.Controls.Primitives.Popup> 컨트롤은 응용 프로그램 위에 배치 되는 별도 창에서 콘텐츠를 표시 합니다. 위치를 지정할 수는 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤, 마우스, 또는 사용 하 여 화면을 기준으로 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성입니다.  이러한 속성의 위치를 지정 하는 유연성을 제공 하기 위해 함께 작동는 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ContextMenu> 클래스도 이러한 5 가지 속성을 정의 하 고 유사 하 게 동작 합니다.  
  

  
<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Popup 위치 지정  
 배치는 <xref:System.Windows.Controls.Primitives.Popup> 기준으로 지정할 수는 <xref:System.Windows.UIElement> 또는 전체 화면입니다.  다음 예제에서는 4 개의 <xref:System.Windows.Controls.Primitives.Popup> 기준으로 하는 컨트롤을 <xref:System.Windows.UIElement>-이 경우 이미지에 합니다. 모든는 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성이로 설정 `image1`, 되지만 각 <xref:System.Windows.Controls.Primitives.Popup> 배치 속성에 대 한 다른 값이 있습니다.  
  
 [!code-xaml[PopupPositionSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 다음 그림과 이미지 및 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤  
  
 ![네 개의 팝업 컨트롤이 있는 이미지](../../../../docs/framework/wpf/controls/media/popupplacementintro.png "PopupPlacementIntro")  
네 개의 Popup이 있는 이미지  
  
 설정 하는 방법을 보여 주는 간단한 예제는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 사용 하 여는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성을 where 더욱 제어할 수 있습니다는 <xref:System.Windows.Controls.Primitives.Popup> 배치 됩니다.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>용어 정의: Popup 분석  
 다음 용어는 이해에 유용한 방법을 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성 간에 서로 관계 된 및 <xref:System.Windows.Controls.Primitives.Popup>:  
  
-   대상 개체  
  
-   대상 영역  
  
-   대상 원점  
  
-   Popup 맞춤 지점  
  
 본이 계약의 다양 한 측면을 참조 하는 편리한 방법을 제공는 <xref:System.Windows.Controls.Primitives.Popup> 와 연결 된 컨트롤입니다.  
  
### <a name="target-object"></a>대상 개체  
 *대상 개체* 는 요소는는 <xref:System.Windows.Controls.Primitives.Popup> 연결 된입니다. 경우는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성이 설정 되어 있으면 대상 개체를 지정 합니다.  경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 을 설정 하지 않으면 및 <xref:System.Windows.Controls.Primitives.Popup> 는 부모가 부모는 대상 개체입니다.  없는 경우 없는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 값과 부모가 없는 대상 개체가 없는 및 <xref:System.Windows.Controls.Primitives.Popup> 화면을 기준으로 배치 됩니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Controls.Primitives.Popup> 의 자식인은 <xref:System.Windows.Controls.Canvas>합니다.  이 예제에서는 설정 되지 않습니다는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성에는 <xref:System.Windows.Controls.Primitives.Popup>합니다. 에 대 한 기본값 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>이므로 <xref:System.Windows.Controls.Primitives.Popup> 아래에 표시 됩니다는 <xref:System.Windows.Controls.Canvas>합니다.  
  
 [!code-xaml[PopupPositionSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup> 기준으로 배치 된 <xref:System.Windows.Controls.Canvas>합니다.  
  
 ![Placementtarget이 없는 팝업 컨트롤](../../../../docs/framework/wpf/controls/media/popupplacementnoplacementtarget.PNG "PopupPlacementNoPlacementTarget")  
PlacementTarget이 없는 Popup 컨트롤  
  
 다음 예제에서는 한 <xref:System.Windows.Controls.Primitives.Popup> 의 자식인은 <xref:System.Windows.Controls.Canvas>, 하지만이 이번은 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 로 설정 된 `ellipse1`이므로 아래 팝업이 표시 되는 <xref:System.Windows.Shapes.Ellipse>합니다.  
  
 [!code-xaml[PopupPositionSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup> 기준으로 배치 된 <xref:System.Windows.Shapes.Ellipse>합니다.  
  
 ![타원에 상대적으로 배치 되는 팝업](../../../../docs/framework/wpf/controls/media/popupplacementwithplacementtarget.PNG "PopupPlacementWithPlacementTarget")  
PlacementTarget이 있는 Popup 컨트롤  
  
> [!NOTE]
>  에 대 한 <xref:System.Windows.Controls.ToolTip>, 기본값인 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>합니다.  에 대 한 <xref:System.Windows.Controls.ContextMenu>, 기본값인 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>합니다. 이러한 값은 나중에 "속성을 함께 사용하는 방법"에서 설명합니다.  
  
### <a name="target-area"></a>대상 영역  
 *영역 대상* 화면에 있는 영역 하는 <xref:System.Windows.Controls.Primitives.Popup> 기준으로 합니다. 앞의 예에서 <xref:System.Windows.Controls.Primitives.Popup> 대상 개체의 하지만 경우에 따라 경계에 맞춰집니다는 <xref:System.Windows.Controls.Primitives.Popup> 다른 범위에 정렬 경우에는 <xref:System.Windows.Controls.Primitives.Popup> 에 대상 개체가 합니다.  경우는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 속성이 설정 되어 있으면 대상 영역은 대상 개체의 범위와 다릅니다.  
  
 다음 예제에서는 두 개의 <xref:System.Windows.Controls.Canvas> 개의 개체는 <xref:System.Windows.Shapes.Rectangle> 및 <xref:System.Windows.Controls.Primitives.Popup>합니다.  두 경우 모두 대상 개체에 대 한는 <xref:System.Windows.Controls.Primitives.Popup> 는 <xref:System.Windows.Controls.Canvas>합니다. <xref:System.Windows.Controls.Primitives.Popup> 첫 번째 범위에서 <xref:System.Windows.Controls.Canvas> 에 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 해당 <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A>, 및 <xref:System.Windows.Rect.Height%2A> 속성이 각각 50, 50, 50, 100으로 설정 합니다. <xref:System.Windows.Controls.Primitives.Popup> 두 번째에서 <xref:System.Windows.Controls.Canvas> 없는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 합니다.  결과적으로, 첫 번째 <xref:System.Windows.Controls.Primitives.Popup> 아래에 배치 되는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 및 두 번째 <xref:System.Windows.Controls.Primitives.Popup> 아래에 배치 됩니다는 <xref:System.Windows.Controls.Canvas>합니다. 각 <xref:System.Windows.Controls.Canvas> 도 포함 되어는 <xref:System.Windows.Shapes.Rectangle> 동일한 범위의 올려진는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 첫 번째 <xref:System.Windows.Controls.Primitives.Popup>합니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 응용 프로그램에 표시 되는 요소를 만들지 않습니다이 예에서는 만듭니다는 <xref:System.Windows.Shapes.Rectangle> 나타내기 위해는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>합니다.  
  
 [!code-xaml[PopupPositionSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 다음 그림에서는 이전 예제의 결과를 보여 줍니다.  
  
 ![팝업 및 placementrectangle](../../../../docs/framework/wpf/controls/media/popupplacementplacementrectangle.PNG "PopupPlacementPlacementRectangle")  
PlacementRectangle이 있을 때와 없을 때의 팝업  
  
### <a name="target-origin-and-popup-alignment-point"></a>대상 원점 및 Popup 맞춤 지점  
 *대상 원점* 및 *Popup 맞춤 지점*은 각각 대상 영역 및 Popup에서 위치 지정에 사용되는 참조 지점입니다. 사용할 수는 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 대상 영역에서 팝업을 오프셋 하는 속성입니다.  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 대상 원점 및 팝업 맞춤 지점 기준으로 합니다. 값은 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성 대상 원점 및 팝업 맞춤 지점 하는 위치를 결정 합니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Controls.Primitives.Popup> 설정 하 고는 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성을 20입니다.  <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (기본값) 이면 되므로 대상 원점 대상 영역의 왼쪽 아래 모서리 이며 팝업 맞춤 지점의 왼쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
 [!code-xaml[PopupPositionSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 다음 그림에서는 이전 예제의 결과를 보여 줍니다.  
  
 ![대상 원점 맞춤 지점 사용한 팝업 배치](../../../../docs/framework/wpf/controls/media/popupplacementtargetoriginalignmentpoint.PNG "PopupPlacementTargetOriginAlignmentPoint")  
HorizontalOffset 및 VerticalOffset을 사용한 Popup  
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>속성을 함께 사용하는 방법  
 값 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, 및 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 올바른 대상 영역, 대상 원점 및 팝업 맞춤 지점을 함께 고려해 야 합니다.  예를 들어 경우의 값 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, 대상 개체가 없는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 무시 되 대상 영역에 마우스 포인터의 범위 이며 합니다. 반면에 경우 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 대상 개체를 결정 하는 부모 또는 및 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 영역을 결정 합니다.  
  
 다음 표에서 대상 개체, 대상 영역, 대상 원점 및 팝업 맞춤 지점 설명 하 고 나타냅니다 여부 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 각각에 대해 사용 <xref:System.Windows.Controls.Primitives.PlacementMode> 열거형 값입니다.  
  
|PlacementMode|대상 개체|대상 영역|대상 원점|Popup 맞춤 지점|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>무시 됩니다.|화면 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 화면에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>무시 됩니다.|화면 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 화면에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 왼쪽 아래 모퉁이.|왼쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 가운데.|중심은 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|으로 정의 되는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>합니다.|으로 정의 되는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|오른쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>무시 됩니다.|마우스 포인터의 경계. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>무시 됩니다.|대상 영역의 왼쪽 아래 모퉁이.|왼쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>무시 됩니다.|마우스 포인터의 경계. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>무시 됩니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 오른쪽 위 모퉁이.|왼쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 아래 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
  
 다음 그림에 나온은 <xref:System.Windows.Controls.Primitives.Popup>, 각각에 대해 대상 영역, 대상 원점 및 팝업 맞춤 지점 <xref:System.Windows.Controls.Primitives.PlacementMode> 값입니다. 각 도형에 있는 대상 영역은 노란색, 및 <xref:System.Windows.Controls.Primitives.Popup> 는 파란색입니다.  
  
 ![Absolute 또는 AbsolutePoint 배치의 팝업](../../../../docs/framework/wpf/controls/media/popupplacementabsolute.png "PopupPlacementAbsolute")  
Placement가 Absolute 또는 AbsolutePoint임  
  
 ![Bottom 배치의 팝업](../../../../docs/framework/wpf/controls/media/popupplacementbottom.png "PopupPlacementBottom")  
Placement가 Bottom임  
  
 ![Center 배치의 팝업](../../../../docs/framework/wpf/controls/media/popupplacementcenter.png "PopupPlacementCenter")  
Placement가 Center임  
  
 ![Left 배치의 팝업](../../../../docs/framework/wpf/controls/media/popupplacementleft.png "PopupPlacementLeft")  
Placement가 Left임  
  
 ![Mouse 배치의 팝업](../../../../docs/framework/wpf/controls/media/popupplacementmouse.png "PopupPlacementMouse")  
Placement가 Mouse임  
  
 ![MousePoint 배치의 팝업](../../../../docs/framework/wpf/controls/media/popupplacementmousepoint.png "PopupPlacementMousePoint")  
Placement가 MousePoint임  
  
 ![Relative 또는 RelativePoint 배치의 팝업](../../../../docs/framework/wpf/controls/media/popupplacementrelative.png "PopupPlacementRelative")  
Placement가 Relative 또는 RelativePoint임  
  
 ![Right 배치의 팝업](../../../../docs/framework/wpf/controls/media/popupplacementright.png "PopupPlacementRight")  
Placement가 Right임  
  
 ![Top 배치의 팝업](../../../../docs/framework/wpf/controls/media/popupplacementtop.png "PopupPlacementTop")  
Placement가 Top임  
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Popup이 화면 가장자리와 만나는 경우  
 보안상의 이유로 한 <xref:System.Windows.Controls.Primitives.Popup> 화면 가장자리로으로 숨길 수 없습니다. 다음 세 가지 중 하나에 때는 <xref:System.Windows.Controls.Primitives.Popup> 화면 가장자리에서 발생 합니다.  
  
-   팝업은 자체를 모호 하 게 하는 화면 가장자리를 따라 이동는 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
-   Popup에 다른 Popup 맞춤 지점이 사용됩니다.  
  
-   Popup에 다른 대상 원점 및 Popup 맞춤 지점이 사용됩니다.  
  
 이러한 옵션은 이 섹션의 뒷부분에서 설명합니다.  
  
 동작은 <xref:System.Windows.Controls.Primitives.Popup> 화면 가장자리의 값에 따라 발견 한 경우는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성 및 화면 팝업에서 가장자리입니다. 다음 표에서 동작을 요약 때는 <xref:System.Windows.Controls.Primitives.Popup> 각 화면 가장자리를 만나는 <xref:System.Windows.Controls.Primitives.PlacementMode> 값입니다.  
  
|PlacementMode|위쪽 가장자리|아래쪽 가장자리|왼쪽 가장자리|오른쪽 가장자리|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|위쪽 가장자리에 맞춥니다.|팝업 맞춤 지점 왼쪽 아래 모퉁이로 변경의 <xref:System.Windows.Controls.Primitives.Popup>합니다.|왼쪽 가장자리에 맞춥니다.|팝업 맞춤 지점의 오른쪽 위 모퉁이에 변경 된 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|위쪽 가장자리에 맞춥니다.|대상 원점 대상 영역의 왼쪽 위 모퉁이 바뀌고 팝업 맞춤 지점 왼쪽 아래 모퉁이로 변경의 <xref:System.Windows.Controls.Primitives.Popup>합니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|대상 영역의 오른쪽 위 모퉁이에 대상 원점이 변경, 팝업 맞춤 지점 왼쪽 위 모퉁이의 코드 변경 내용에서 <xref:System.Windows.Controls.Primitives.Popup>합니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|위쪽 가장자리에 맞춥니다.|대상 원점 대상 영역 (마우스 포인터의 범위)의 왼쪽 위 모서리 바뀌고 팝업 맞춤 지점 왼쪽 아래 모퉁이로 변경의 <xref:System.Windows.Controls.Primitives.Popup>합니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|위쪽 가장자리에 맞춥니다.|팝업 맞춤 지점 왼쪽 아래 모퉁이로 변경의 <xref:System.Windows.Controls.Primitives.Popup>합니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 Popup의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|위쪽 가장자리에 맞춥니다.|팝업 맞춤 지점 왼쪽 아래 모퉁이로 변경의 <xref:System.Windows.Controls.Primitives.Popup>합니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 Popup의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|대상 영역의 왼쪽 위 모퉁이에 대상 원점이 변경, 팝업 맞춤 지점 오른쪽 위 모퉁이의 코드 변경 내용에서 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|대상 원점 대상 영역의 왼쪽 아래 모퉁이로 변경 되 고 팝업 맞춤 지점의 왼쪽 위 모퉁이로 변경는 <xref:System.Windows.Controls.Primitives.Popup>합니다. 실제로이 경우와 동일는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>합니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
  
### <a name="aligning-to-the-screen-edge"></a>화면 가장자리에 맞춤  
 A <xref:System.Windows.Controls.Primitives.Popup> 맞출 수 화면의 가장자리를 따라서 자체의 위치를 변경 하 여 전체 <xref:System.Windows.Controls.Primitives.Popup> 화면에 표시 됩니다.  대상 원점 및 팝업 맞춤 지점 사이의 거리의 값에서 다를 수 있습니다 이러한 경우 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>합니다. 때 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center>, 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, <xref:System.Windows.Controls.Primitives.Popup> 모든 화면 가장자리에 맞춰 정렬 합니다.  예를 들어 한 <xref:System.Windows.Controls.Primitives.Popup> 가 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 로 설정 <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 100으로 설정 합니다.  전체 또는 일부의 아래쪽 가장자리의 화면을 표시 하지는 <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.Primitives.Popup> 자체적 맞춤 지점이 100 미만으로 화면과 대상 원점 및 팝업 사이의 세로 거리의 아래쪽 가장자리를 따라 합니다. 다음 그림에서 이 경우를 보여 줍니다.  
  
 ![화면 가장자리에 맞춰진 팝업](../../../../docs/framework/wpf/controls/media/popupplacementrelativescreenedge.png "PopupPlacementRelativeScreenEdge")  
화면 가장자리에 맞춰진 Popup  
  
### <a name="changing-the-popup-alignment-point"></a>Popup 맞춤 지점 변경  
 경우 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>, 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, 팝업 맞춤 지점 아래쪽 또는 오른쪽 화면 가장자리로 팝업에서 발생 하는 경우 변경 합니다.  
  
 다음 그림을 보여 줍니다는 아래쪽 화면 가장자리로 전체 또는 일부의 경우는 <xref:System.Windows.Controls.Primitives.Popup>, 팝업 맞춤 지점은 왼쪽 아래 모퉁이의 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
 ![아래쪽 화면 가장자리로 인 한 새로운 맞춤 지점](../../../../docs/framework/wpf/controls/media/popupplacementrelativepointscreenedge.png "PopupPlacementRelativePointScreenEdge")  
Popup이 화면의 아래쪽 가장자리와 만나고 Popup 맞춤 지점을 변경함  
  
 다음 그림에서는 해당는 <xref:System.Windows.Controls.Primitives.Popup> 숨겨져 팝업 맞춤 지점은 오른쪽 위 모퉁이의 오른쪽 화면 가장자리로으로 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
 ![화면 가장자리로 인 한 새로운 팝업 맞춤 지점](../../../../docs/framework/wpf/controls/media/popupplacementrelativepointrightscreenedge.png "PopupPlacementRelativePointRightScreenEdge")  
Popup이 화면의 오른쪽 가장자리와 만나고 Popup 맞춤 지점을 변경함  
  
 경우는 <xref:System.Windows.Controls.Primitives.Popup> 아래쪽 및 오른쪽 화면 가장자리 발생 하면 팝업 맞춤 지점은의 오른쪽 아래 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>대상 원점 및 Popup 맞춤 지점 변경  
 때 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right>, 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, 특정 화면 가장자리 발견 되 면 대상 원점 및 팝업 맞춤 지점이 변경 합니다.  위치 변경을 발생 하는 화면 가장자리에 따라 달라 집니다는 <xref:System.Windows.Controls.Primitives.PlacementMode> 값입니다.  
  
 다음 그림에서는 해당 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> 및 <xref:System.Windows.Controls.Primitives.Popup> 아래쪽 화면 가장자리로 발견 대상 원점 대상 영역의 왼쪽 위 모퉁이 이며 팝업 맞춤 지점의 왼쪽 아래 모퉁이 <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![아래쪽 화면 가장자리로 인 한 새로운 맞춤 지점](../../../../docs/framework/wpf/controls/media/popupplacementbottomscreenedge.png "PopupPlacementBottomScreenEdge")  
Placement가 Bottom이고 Popup이 화면의 아래쪽 가장자리와 만남  
  
 다음 그림에서는 해당 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Left> 및 <xref:System.Windows.Controls.Primitives.Popup> 화면 왼쪽된 가장자리와 만나는 대상 원점 대상 영역의 오른쪽 위 모퉁이 이며 팝업 맞춤 지점에서 의왼쪽위모서리<xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![왼쪽된 화면 가장자리로 인 한 새로운 맞춤 지점](../../../../docs/framework/wpf/controls/media/popupplacementleftscreenedge.png "PopupPlacementLeftScreenEdge")  
Placement가 Left이고 Popup이 화면의 왼쪽 가장자리와 만남  
  
 다음 그림에서는 해당 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Right> 및 <xref:System.Windows.Controls.Primitives.Popup> 오른쪽 화면 가장자리 대상 원점 대상 영역의 왼쪽 위 모퉁이 이며 팝업 맞춤 지점의 오른쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![오른쪽 화면 가장자리로 인 한 새로운 맞춤 지점](../../../../docs/framework/wpf/controls/media/popupplacementrightscreenedge.png "PopupPlacementRightScreenEdge")  
Placement가 Right이고 Popup이 화면의 오른쪽 가장자리와 만남  
  
 다음 그림에서는 해당 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Top> 및 <xref:System.Windows.Controls.Primitives.Popup> 화면 위쪽 가장자리와 만나는 대상 원점 대상 영역의 왼쪽 아래 모서리 이며 팝업 맞춤 지점의 왼쪽 위 모서리는 <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![위쪽 화면 가장자리로 인 한 새로운 맞춤 지점](../../../../docs/framework/wpf/controls/media/popupplacementtopscreenedge.png "PopupPlacementTopScreenEdge")  
Placement가 Top이고 Popup이 화면의 위쪽 가장자리와 만남  
  
 다음 그림에서는 해당 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> 및 <xref:System.Windows.Controls.Primitives.Popup> 아래쪽 화면 가장자리로 발견 대상 원점은 왼쪽 위 모퉁이 대상 영역 (마우스 포인터의 범위)와 팝업 맞춤 포인터가의 왼쪽 아래 모서리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
 ![화면 가장자리 근처의 마우스로 인 한 새로운 맞춤 지점](../../../../docs/framework/wpf/controls/media/popupplacementmousescreenedge.png "PopupPlacementMouseScreenEdge")  
Placement가 Mouse이고 Popup이 화면의 아래쪽 가장자리와 만남  
  
### <a name="customizing-popup-placement"></a>Popup 배치 사용자 지정  
 대상 원점 및 팝업 맞춤 지점 설정 하 여 사용자 지정할 수 있습니다는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>합니다. 그런 다음 정의 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 대리자에 대 한 가능한 배치 지점 및 기본 축 (기본 설정의 순서로)의 집합을 반환 하는 <xref:System.Windows.Controls.Primitives.Popup>합니다. 가장 큰 부분을 표시 하는 지점이 고 <xref:System.Windows.Controls.Primitives.Popup> 을 선택 합니다.  위치는 <xref:System.Windows.Controls.Primitives.Popup> 경우 자동으로 조정 됩니다는 <xref:System.Windows.Controls.Primitives.Popup> 화면의 가장자리에 의해 숨겨져 있습니다. 예제를 보려면 [사용자 지정 팝업 위치 지정](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Popup Placement Sample](http://go.microsoft.com/fwlink/?LinkID=160032)(Popup 배치 샘플)
