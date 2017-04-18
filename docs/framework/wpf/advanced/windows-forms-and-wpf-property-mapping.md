---
title: "Windows Forms 및 WPF 속성 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "상호 운용성[WPF], Windows Forms"
  - "속성 매핑[WPF 상호 운용성]"
  - "Windows Forms[WPF], 상호 운용성"
  - "Windows Forms, WPF 상호 운용"
  - "WindowsFormsHost 요소 속성 매핑"
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Windows Forms 및 WPF 속성 매핑
[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기술에는 서로 비슷하지만 다른 두 개의 속성 모델이 있습니다.  *속성 매핑*은 두 아키텍처 간의 상호 운용을 지원하며 다음 기능을 제공합니다.  
  
-   호스트 환경에서의 관련 속성 변경 사항을 호스팅된 컨트롤 또는 요소에 보다 쉽게 매핑할 수 있습니다.  
  
-   가장 자주 사용되는 속성을 매핑하기 위한 기본 처리를 제공합니다.  
  
-   기본 속성을 쉽게 제거, 재정의 또는 확장할 수 있도록 합니다.  
  
-   호스트에서의 속성 값 변경 사항이 자동으로 검색되어 호스팅된 컨트롤 또는 요소로 변환되도록 합니다.  
  
> [!NOTE]
>  속성 변경 이벤트는 호스팅 컨트롤 또는 요소 계층 구조에서 위로 전파되지 않습니다.  직접 설정, 스타일, 상속, 데이터 바인딩 또는 속성 값을 변경하는 기타 메커니즘으로 인해 속성의 로컬 값이 변경되지 않으면 속성 변환이 수행되지 않습니다.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 속성과 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 속성을 사용하여 속성 매핑에 액세스합니다.  
  
## WindowsFormsHost 요소로 속성 매핑  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 다음 변환 표를 사용하여 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성을 이에 상응하는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]로 변환합니다.  
  
|Windows Presentation Foundation 호스팅|Windows Forms|상호 운용 동작|  
|-----------------------------------------|-------------------|--------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|<xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성과 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성을 설정합니다.  매핑은 다음 규칙을 사용하여 수행됩니다.<br /><br /> -   <xref:System.Windows.Controls.Control.Background%2A>가 단색일 경우에는 변환되어 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 설정하는 데 사용됩니다.  호스팅된 컨트롤이 <xref:System.Windows.Forms.Control.BackColor%2A> 속성의 값을 상속할 수 있으므로 <xref:System.Windows.Forms.Control.BackColor%2A> 속성은 호스팅된 컨트롤에 설정되지 않습니다. **Note:**  호스팅된 컨트롤은 투명도를 지원하지 않습니다.  <xref:System.Windows.Forms.Control.BackColor%2A>에 할당된 모든 색상은 알파 값 0xFF로 완전히 불투명해야 합니다. <br /><br /> -   <xref:System.Windows.Controls.Control.Background%2A>가 단색이 아닌 경우에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤이 <xref:System.Windows.Controls.Control.Background%2A> 속성에서 비트맵을 만듭니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤이 이 비트맵을 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성에 할당합니다.  이렇게 함으로써 투명도와 비슷한 효과가 제공됩니다. **Note:**  이 동작을 재정의하거나 <xref:System.Windows.Controls.Control.Background%2A> 속성 매핑을 제거할 수 있습니다.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|기본 매핑이 다시 할당되지 않으면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성이 설정된 상위 항목을 찾을 때까지 상위 계층 구조를 순회합니다.  이 값은 가장 유사한 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 커서로 변환됩니다.<br /><br /> <xref:System.Windows.FrameworkElement.ForceCursor%2A> 속성의 기본 매핑이 다시 할당되지 않으면 <xref:System.Windows.FrameworkElement.ForceCursor%2A>가 `true`로 설정된 첫 번째 상위 항목에서 순회가 중지됩니다.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> \(<xref:System.Windows.FlowDirection?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> \(<xref:System.Windows.Forms.RightToLeft?displayProperty=fullName>\)|<xref:System.Windows.FlowDirection>는 <xref:System.Windows.Forms.RightToLeft>에 매핑됩니다.<br /><br /> <xref:System.Windows.FlowDirection>는 <xref:System.Windows.Forms.RightToLeft>에 매핑됩니다.<br /><br /> <xref:System.Windows.Forms.RightToLeft>는 매핑되지 않습니다.<br /><br /> <xref:System.Windows.FlowDirection?displayProperty=fullName>는 <xref:System.Windows.Forms.RightToLeft?displayProperty=fullName>에 매핑됩니다.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|호스팅된 컨트롤의 <xref:System.Drawing.Font?displayProperty=fullName>에 있는 <xref:System.Drawing.Font.Style%2A>|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성의 집합은 해당 <xref:System.Drawing.Font>로 변환됩니다.  이러한 속성 중 하나가 변경될 때 새 <xref:System.Drawing.Font>가 만들어집니다.  <xref:System.Windows.FontStyles.Normal%2A>의 경우 <xref:System.Drawing.FontStyle>을 사용할 수 없습니다.  <xref:System.Windows.FontStyles.Italic%2A> 또는 <xref:System.Windows.FontStyles.Oblique%2A>의 경우 <xref:System.Drawing.FontStyle>을 사용할 수 있습니다.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|호스팅된 컨트롤의 <xref:System.Drawing.Font?displayProperty=fullName>에 있는 <xref:System.Drawing.Font.Style%2A>|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성의 집합은 해당 <xref:System.Drawing.Font>로 변환됩니다.  이러한 속성 중 하나가 변경될 때 새 <xref:System.Drawing.Font>가 만들어집니다.  <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A> 또는 <xref:System.Windows.FontWeights.UltraBold%2A>의 경우 <xref:System.Drawing.FontStyle>를 사용할 수 있습니다.  <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A> 또는 <xref:System.Windows.FontWeights.UltraLight%2A>의 경우 <xref:System.Drawing.FontStyle>를 사용할 수 없습니다.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> \(<xref:System.Drawing.Font?displayProperty=fullName>\)|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성의 집합은 해당 <xref:System.Drawing.Font>로 변환됩니다.  이러한 속성 중 하나가 변경될 때 새 <xref:System.Drawing.Font>가 만들어집니다.  호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 글꼴 크기를 기준으로 크기가 조정됩니다.<br /><br /> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 글꼴 크기는 1\/96인치로 표현되며 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에서는 1\/72인치로 표현됩니다.  해당 변환은 다음과 같습니다.<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 글꼴 크기 \= [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 글꼴 크기 \* 72.0 \/ 96.0|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.Foreground%2A> 속성 매핑은 다음 규칙을 사용하여 수행됩니다.<br /><br /> -   <xref:System.Windows.Controls.Control.Foreground%2A>가 <xref:System.Windows.Media.SolidColorBrush>인 경우에는 <xref:System.Windows.Forms.Control.ForeColor%2A>에 대해 <xref:System.Windows.Media.SolidColorBrush.Color%2A>를 사용합니다.<br />-   <xref:System.Windows.Controls.Control.Foreground%2A>가 <xref:System.Windows.Media.GradientBrush>인 경우에는 <xref:System.Windows.Media.GradientStop>의 색상을 <xref:System.Windows.Forms.Control.ForeColor%2A>의 가장 낮은 오프셋 값으로 사용합니다.<br />-   다른 <xref:System.Windows.Media.Brush> 형식의 경우에는 <xref:System.Windows.Forms.Control.ForeColor%2A>를 변경하지 않고 그대로 둡니다.  즉, 기본값이 사용됩니다.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>가 설정되어 있으면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 호스팅된 컨트롤에 <xref:System.Windows.Forms.Control.Enabled%2A> 속성을 설정합니다.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 있는 <xref:System.Windows.Forms.Control.Padding%2A> 속성의 네 개의 값 모두는 동일한 <xref:System.Windows.Thickness> 값으로 설정됩니다.<br /><br /> -   <xref:System.Int32.MaxValue>보다 큰 값은 <xref:System.Int32.MaxValue>로 설정됩니다.<br />-   <xref:System.Int32.MinValue>보다 낮은 값은 <xref:System.Int32.MinValue>로 설정됩니다.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility>은 <xref:System.Windows.Forms.Control.Visible%2A> \= `true`에 매핑됩니다.  호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 표시됩니다.  호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 `false`로 명시적으로 설정하는 것은 권장되지 않습니다.<br />-   <xref:System.Windows.Visibility>는 <xref:System.Windows.Forms.Control.Visible%2A> \= `true` 또는 `false`에 매핑됩니다.  호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 그려지지 않고 해당 영역은 축소됩니다.<br />-   <xref:System.Windows.Visibility>: 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 레이아웃에서 공간을 차지하지만 표시되지 않습니다.  이 경우 <xref:System.Windows.Forms.Control.Visible%2A> 속성이 `true`로 설정됩니다.  호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 `false`로 명시적으로 설정하는 것은 권장되지 않습니다.|  
  
 컨테이너 요소에 연결된 속성은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에서 완전히 지원됩니다.  
  
 자세한 내용은 [연습: WindowsFormsHost 요소를 사용하여 속성 매핑](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)을 참조하십시오.  
  
## 부모 속성에 대한 업데이트  
 최상위 부모 속성을 변경하면 호스팅된 자식 컨트롤에 알림을 보냅니다.  다음 목록에서는 값이 변경될 때 알림을 보내지 않는 속성을 설명합니다.  
  
-   <xref:System.Windows.Controls.Control.Background%2A>  
  
-   <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
-   <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
-   <xref:System.Windows.UIElement.Visibility%2A>  
  
 예를 들어 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Controls.Control.Background%2A> 속성 값을 변경하는 경우 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성은 변경되지 않습니다.  
  
## ElementHost 컨트롤로 속성 매핑  
 다음 속성은 기본 제공 변경 알림을 제공합니다.  다음과 같은 속성을 매핑할 때는 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 메서드를 호출하지 마십시오.  
  
-   AutoSize  
  
-   BackColor  
  
-   BackgroundImage  
  
-   BackgroundImageLayout  
  
-   BindingContext  
  
-   CausesValidation  
  
-   ContextMenu  
  
-   ContextMenuStrip  
  
-   커서  
  
-   Dock  
  
-   Enabled  
  
-   글꼴  
  
-   ForeColor  
  
-   위치  
  
-   Margin  
  
-   안쪽 여백  
  
-   부모  
  
-   Region  
  
-   RightToLeft  
  
-   크기  
  
-   TabIndex  
  
-   TabStop  
  
-   Text  
  
-   Visible  
  
 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 다음 변환 표를 사용하여 기본 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 속성을 이에 상응하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]로 변환합니다.  
  
 자세한 내용은 [연습: ElementHost 컨트롤을 사용하여 속성 매핑](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)을 참조하십시오.  
  
|Windows Forms 호스팅|Windows Presentation Foundation|상호 운용 동작|  
|-----------------------|-------------------------------------|--------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 호스팅된 요소에 있는 \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\)|이 속성을 설정하면 <xref:System.Windows.Media.ImageBrush>로 강제로 다시 칠합니다.  <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 속성이 `false`\(기본값\)로 설정되어 있으면 이 <xref:System.Windows.Media.ImageBrush>가 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 모양을 기준으로 합니다. 이 기준에는 해당 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> 속성 및 연결된 모든 Paint 처리기가 포함됩니다.<br /><br /> <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 속성이 `true`로 설정되어 있으면 이 <xref:System.Windows.Media.ImageBrush>가 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 부모의 모양을 기준으로 합니다. 이 기준에는 부모의 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> 속성 및 연결된 모든 Paint 처리기가 포함됩니다.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> \(<xref:System.Drawing.Image?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 호스팅된 요소에 있는 \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\)|이 속성을 설정하면 <xref:System.Windows.Forms.Control.BackColor%2A> 매핑에 대해 설명된 것과 동일한 동작이 발생합니다.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 호스팅된 요소에 있는 \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\)|이 속성을 설정하면 <xref:System.Windows.Forms.Control.BackColor%2A> 매핑에 대해 설명된 것과 동일한 동작이 발생합니다.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> \(<xref:System.Windows.Forms.Cursor?displayProperty=fullName>\)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> \(<xref:System.Windows.Input.Cursor?displayProperty=fullName>\)|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 표준 커서는 상응하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 표준 커서로 변환됩니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]가 표준 커서가 아니면 기본값이 할당됩니다.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>가 설정되어 있으면 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 호스팅된 요소에 <xref:System.Windows.UIElement.IsEnabled%2A> 속성을 설정합니다.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> \(<xref:System.Drawing.Font?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A> 값은 상응하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 글꼴 속성의 집합으로 변환됩니다.|  
|<xref:System.Drawing.Font.Bold%2A>|호스팅된 요소에 있는 <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Bold%2A>가 `true`이면 <xref:System.Windows.Controls.Control.FontWeight%2A>가 <xref:System.Windows.FontWeights.Bold%2A>로 설정됩니다.<br /><br /> <xref:System.Drawing.Font.Bold%2A>이 `false`이면 <xref:System.Windows.Controls.Control.FontWeight%2A>가 <xref:System.Windows.FontWeights.Normal%2A>로 설정됩니다.|  
|<xref:System.Drawing.Font.Italic%2A>|호스팅된 요소에 있는 <xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Italic%2A>이 `true`이면 <xref:System.Windows.Controls.Control.FontStyle%2A>이 <xref:System.Windows.FontStyles.Italic%2A>으로 설정됩니다.<br /><br /> <xref:System.Drawing.Font.Italic%2A>이 `false`이면 <xref:System.Windows.Controls.Control.FontStyle%2A>이 <xref:System.Windows.FontStyles.Normal%2A>로 설정됩니다.|  
|<xref:System.Drawing.Font.Strikeout%2A>|호스팅된 요소에 있는 <xref:System.Windows.TextDecorations>|<xref:System.Windows.Controls.TextBlock> 컨트롤을 호스팅할 때만 적용됩니다.|  
|<xref:System.Drawing.Font.Underline%2A>|호스팅된 요소에 있는 <xref:System.Windows.TextDecorations>|<xref:System.Windows.Controls.TextBlock> 컨트롤을 호스팅할 때만 적용됩니다.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> \(<xref:System.Windows.Forms.RightToLeft?displayProperty=fullName>\)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> \(<xref:System.Windows.FlowDirection>\)|<xref:System.Windows.Forms.RightToLeft>는 <xref:System.Windows.FlowDirection>에 매핑됩니다.<br /><br /> <xref:System.Windows.Forms.RightToLeft>는 <xref:System.Windows.FlowDirection>에 매핑됩니다.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 다음 규칙을 사용하여 호스팅된 요소에 <xref:System.Windows.UIElement.Visibility%2A> 속성을 설정합니다.<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> \= `true`는 <xref:System.Windows.Visibility>에 매핑됩니다.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> \= `false`는 <xref:System.Windows.Visibility>에 매핑됩니다.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [WPF 및 Windows Forms 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)   
 [연습: WindowsFormsHost 요소를 사용하여 속성 매핑](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)   
 [연습: ElementHost 컨트롤을 사용하여 속성 매핑](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)