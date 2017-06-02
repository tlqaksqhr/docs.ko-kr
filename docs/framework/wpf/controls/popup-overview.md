---
title: "Popup 개요 | Microsoft Docs"
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
  - "컨트롤, Popup"
  - "Popup 컨트롤[WPF], Popup 컨트롤 정보"
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Popup 개요
<xref:System.Windows.Controls.Primitives.Popup> 컨트롤은 지정된 요소나 화면 좌표를 기준으로 현재 응용 프로그램 창 위에 있는 별도의 창에 콘텐츠를 표시할 수 있는 방법을 제공합니다.  이 항목에서는 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤을 소개하고 기본적인 사용 방법에 대한 정보를 제공합니다.  
  
   
  
<a name="What_Is_a_Popup_"></a>   
## Popup 정의  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤은 요소나 화면의 지점을 기준으로 별도의 창에 콘텐츠를 표시합니다.  <xref:System.Windows.Controls.Primitives.Popup>이 표시되면 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 속성은 `true`로 설정됩니다.  
  
> [!NOTE]
>  마우스 포인터를 해당 부모 개체 위로 이동할 때 <xref:System.Windows.Controls.Primitives.Popup>이 자동으로 열리지는 않습니다.  <xref:System.Windows.Controls.Primitives.Popup>이 자동으로 열리게 하려면 <xref:System.Windows.Controls.ToolTip> 또는 <xref:System.Windows.Controls.ToolTipService> 클래스를 사용합니다.  자세한 내용은 [도구 설명 개요](../../../../docs/framework/wpf/controls/tooltip-overview.md)를 참조하십시오.  
  
<a name="APopupExample"></a>   
## Popup 만들기  
 다음 예제에서는 <xref:System.Windows.Controls.Button> 컨트롤의 자식 요소인 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤을 정의하는 방법을 보여 줍니다.  <xref:System.Windows.Controls.Button>에는 자식 요소가 하나만 있을 수 있으므로 이 예제에서는 <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤의 텍스트를 <xref:System.Windows.Controls.StackPanel>에 배치합니다.  <xref:System.Windows.Controls.Primitives.Popup>의 콘텐츠는 <xref:System.Windows.Controls.TextBlock> 컨트롤에 표시됩니다. 이 컨트롤은 관련 <xref:System.Windows.Controls.Button> 컨트롤 근처의 응용 프로그램 창 위에 있는 별도의 창에 텍스트를 표시합니다.  
  
 [!code-xml[PopupSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xml[PopupSimple#CreatePopupCodeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## Popup을 구현하는 컨트롤  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤을 다른 컨트롤로 빌드할 수 있습니다.  다음 컨트롤은 특정한 용도의 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤을 구현합니다.  
  
-   <xref:System.Windows.Controls.ToolTip>.  요소에 대한 도구 설명을 만들려면 <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ToolTipService> 클래스를 사용합니다.  자세한 내용은 [도구 설명 개요](../../../../docs/framework/wpf/controls/tooltip-overview.md)를 참조하십시오.  
  
-   <xref:System.Windows.Controls.ContextMenu>.  요소의 상황에 맞는 메뉴를 만들려면 <xref:System.Windows.Controls.ContextMenu> 컨트롤을 사용합니다.  자세한 내용은 [ContextMenu 개요](../../../../docs/framework/wpf/controls/contextmenu-overview.md)를 참조하십시오.  
  
-   <xref:System.Windows.Controls.ComboBox>.  표시하거나 숨길 수 있는 드롭다운 목록을 포함하는 선택 컨트롤을 만들려면 <xref:System.Windows.Controls.ComboBox> 컨트롤을 사용합니다.  
  
-   <xref:System.Windows.Controls.Expander>.  콘텐츠를 표시하는 축소 가능한 영역과 함께 헤더를 표시하는 컨트롤을 만들려면 <xref:System.Windows.Controls.Expander> 컨트롤을 사용합니다.  자세한 내용은 [Expander 개요](../../../../docs/framework/wpf/controls/expander-overview.md)를 참조하십시오.  
  
<a name="PopupBehaviorandAppearance"></a>   
## Popup 동작 및 모양  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에서는 컨트롤의 동작과 모양을 사용자 지정할 수 있는 기능을 제공합니다.  예를 들어 열기 및 닫기 동작, 애니메이션, 불투명 및 비트맵 효과, <xref:System.Windows.Controls.Primitives.Popup> 크기 및 위치 등을 설정할 수 있습니다.  
  
<a name="OpenandCloseBehavior"></a>   
### 열기 및 닫기 동작  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에서는 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 속성이 `true`로 설정되어 있는 경우에 해당 콘텐츠를 표시합니다.  기본적으로 <xref:System.Windows.Controls.Primitives.Popup>은 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 속성이 `false`로 설정될 때까지 계속 열려 있습니다.  그러나 <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> 속성을 `false`로 설정하여 기본 동작을 변경할 수 있습니다.  이 속성을 `false`로 설정하면 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠 창이 마우스 캡처를 얻습니다.  <xref:System.Windows.Controls.Primitives.Popup> 창 외부에서 마우스 이벤트가 발생하면 <xref:System.Windows.Controls.Primitives.Popup>이 마우스 캡처를 잃고 창이 닫힙니다.  
  
 <xref:System.Windows.Controls.Primitives.Popup.Opened> 및 <xref:System.Windows.Controls.Primitives.Popup.Closed> 이벤트는 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠 창이 열리거나 닫힐 때 발생합니다.  
  
<a name="Animation"></a>   
### 애니메이션  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에서는 일반적으로 페이드 인 및 슬라이드 인과 같은 동작에 연결되는 애니메이션을 기본적으로 지원합니다.  <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> 속성을 <xref:System.Windows.Controls.Primitives.PopupAnimation> 열거형 값으로 설정하여 이러한 애니메이션을 설정할 수 있습니다.  <xref:System.Windows.Controls.Primitives.Popup> 애니메이션이 제대로 작동하려면 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 속성을 `true`로 설정해야 합니다.  
  
 또한 <xref:System.Windows.Media.Animation.Storyboard>와 같은 애니메이션을 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에 적용할 수도 있습니다.  
  
<a name="OpacityandBitmapEffects"></a>   
### 불투명 및 비트맵 효과  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤의 <xref:System.Windows.UIElement.Opacity%2A> 속성을 설정해도 해당 콘텐츠에는 영향이 없습니다.  기본적으로 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠 창은 불투명합니다.  투명한 <xref:System.Windows.Controls.Primitives.Popup>을 만들려면 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 속성을 `true`로 설정합니다.  
  
 <xref:System.Windows.Controls.Primitives.Popup>의 콘텐츠는 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤이나 부모 창의 다른 요소에서 직접 설정하는 <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>와 같은 비트맵 효과를 상속하지 않습니다.  <xref:System.Windows.Controls.Primitives.Popup>의 콘텐츠에서 비트맵 효과를 표시하려면 해당 콘텐츠에서 직접 비트맵 효과를 설정해야 합니다.  예를 들어 <xref:System.Windows.Controls.Primitives.Popup>의 자식이 <xref:System.Windows.Controls.StackPanel>인 경우 <xref:System.Windows.Controls.StackPanel>에서 비트맵 효과를 설정합니다.  
  
<a name="PopupSize"></a>   
### Popup 크기  
 기본적으로 <xref:System.Windows.Controls.Primitives.Popup>은 해당 콘텐츠에 맞게 크기가 조정됩니다.  자동 크기 조정이 발생할 때 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠에 대해 정의한 화면 영역의 기본 크기가 비트맵 효과를 표시할 충분한 공간을 제공하지 않기 때문에 일부 비트맵 효과가 숨겨질 수 있습니다.  
  
 또한 콘텐츠에서 <xref:System.Windows.UIElement.RenderTransform%2A>을 설정하는 경우에도 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠가 가려질 수 있습니다.  이 경우 변환된 <xref:System.Windows.Controls.Primitives.Popup>의 콘텐츠가 원래 <xref:System.Windows.Controls.Primitives.Popup>의 영역을 넘어 확장되어 일부 콘텐츠가 숨겨질 수 있습니다.  비트맵 효과나 변환에 추가 공간이 필요한 경우 컨트롤에 더 많은 영역을 제공하기 위해 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠 주위에 여백을 정의할 수 있습니다.  
  
<a name="DefiningPopupPosition"></a>   
## Popup 위치 정의  
 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> 속성을 설정하여 팝업을 배치할 수 있습니다.  자세한 내용은 [Popup 배치 동작](../../../../docs/framework/wpf/controls/popup-placement-behavior.md)을 참조하십시오.  화면에 표시된 <xref:System.Windows.Controls.Primitives.Popup>은 해당 부모 항목의 위치가 변경되더라도 이전 위치를 유지합니다.  
  
<a name="CustomizingPopupPlacement"></a>   
### 팝업 배치 사용자 지정  
 <xref:System.Windows.Controls.Primitives.Popup>을 표시할 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>을 기준으로 하는 좌표 집합을 지정하여 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤의 배치를 사용자 지정할 수 있습니다.  
  
 배치를 사용자 지정하려면 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 <xref:System.Windows.Controls.Primitives.PlacementMode>으로 설정합니다.  그런 다음 <xref:System.Windows.Controls.Primitives.Popup>에 대해 사용 가능한 배치 지점과 기본 축 집합을 기본 설정의 순서에 따라 반환하는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 대리자를 정의합니다.  <xref:System.Windows.Controls.Primitives.Popup>의 가장 큰 부분을 표시하는 지점이 자동으로 선택됩니다.  예제를 보려면 [사용자 지정 팝업 위치 지정](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md)을 참조하십시오.  
  
<a name="PopupandtheVisualTree"></a>   
## Popup 및 시각적 트리  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에는 자체의 [시각적 트리](GTMT)가 없습니다. 대신 <xref:System.Windows.Controls.Primitives.Popup>의 <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> 메서드를 호출하면 이 컨트롤은 크기 0을 반환합니다.  그러나 <xref:System.Windows.Controls.Primitives.Popup>의 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 속성을 `true`로 설정하면 자체의 시각적 트리가 있는 새 창이 만들어집니다.  새 창에는 <xref:System.Windows.Controls.Primitives.Popup>의 <xref:System.Windows.Controls.Primitives.Popup.Child%2A> 콘텐츠가 포함됩니다.  새 창의 너비와 높이는 화면의 너비 또는 높이의 75%보다 클 수 없습니다.  
  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에서는 <xref:System.Windows.Controls.Primitives.Popup.Child%2A> 콘텐츠에 대한 참조를 논리적 자식으로 유지합니다.  새 창이 생성되면 <xref:System.Windows.Controls.Primitives.Popup>의 콘텐츠가 창의 시각적 자식이 되고 <xref:System.Windows.Controls.Primitives.Popup>의 논리적 자식으로 유지됩니다.  반대로 <xref:System.Windows.Controls.Primitives.Popup>은 <xref:System.Windows.Controls.Primitives.Popup.Child%2A> 콘텐츠의 논리적 부모로 유지됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Controls.Primitives.Popup>   
 <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>   
 <xref:System.Windows.Controls.Primitives.PlacementMode>   
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>   
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>   
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [방법 항목](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)