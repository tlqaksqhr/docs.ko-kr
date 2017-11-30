---
title: "Windows Forms 및 WPF 속성 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a0af1015747e2f27b19c2cac2c896dd60214264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Windows Forms 및 WPF 속성 매핑
[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기술은 두 개의 유사 하지만 서로 다른 속성 모델을 갖추고 있습니다. *속성 매핑* 두 아키텍처 간의 상호 운용을 지원 하며 다음과 같은 기능을 제공 합니다.  
  
-   호스팅된 컨트롤 또는 요소를 호스트 환경에서 관련 속성 변경 매핑할 쉽게 있습니다.  
  
-   속성을 사용 하는 가장 일반적으로 매핑하기 위한 기본 처리를 제공 합니다.  
  
-   쉽게 제거를, 재정의 또는 기본 속성을 확장할 수 있습니다.  
  
-   호스트에서 속성 값이 변경 자동으로 감지 및 호스팅된 컨트롤 또는 요소에 대 한 번역을 확인 합니다.  
  
> [!NOTE]
>  속성 변경 이벤트 호스팅 컨트롤 또는 요소 계층 구조를 전파 되지 않습니다. 속성의 로컬 값을 직접 설정, 스타일, 상속, 데이터 바인딩, 또는 속성의 값을 변경 하는 기타 메커니즘으로 인해 변경 되지 않는 경우에 속성 변환이 수행 되지 않습니다.  
  
 사용 하 여는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 속성에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 및 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 속성을 <xref:System.Windows.Forms.Integration.ElementHost> 속성 매핑에 액세스를 제어 합니다.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>WindowsFormsHost 요소와 속성 매핑  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 기본 변환 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성을 해당 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 다음 변환 표를 사용 하 여 해당 항목입니다.  
  
|Windows Presentation Foundation 호스팅|Windows Forms|상호 운용 동작|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 집합에서 <xref:System.Windows.Forms.Control.BackColor%2A> 호스팅된 컨트롤의 속성 및 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 호스팅된 컨트롤의 속성입니다. 매핑은 다음 규칙을 사용 하 여 수행 됩니다.<br /><br /> -If <xref:System.Windows.Controls.Control.Background%2A> 는 단색으로 변환 되 고 설정 하는 데는 <xref:System.Windows.Forms.Control.BackColor%2A> 호스팅된 컨트롤의 속성입니다. <xref:System.Windows.Forms.Control.BackColor%2A> 호스팅된 컨트롤의 값을 상속할 수 있으므로 호스팅된 컨트롤에 속성이 설정 되지 않았는지는 <xref:System.Windows.Forms.Control.BackColor%2A> 속성입니다. **참고:** 호스팅된 컨트롤 투명도 지원 하지 않습니다. 에 할당 된 모든 색 <xref:System.Windows.Forms.Control.BackColor%2A> 완전히 불투명 0xFF 알파 값을 사용 해야 합니다. <br /><br /> -If <xref:System.Windows.Controls.Control.Background%2A> 단색으로 않습니다는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에서 비트맵을 만듭니다는 <xref:System.Windows.Controls.Control.Background%2A> 속성입니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 할당이 비트맵에는 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 호스팅된 컨트롤의 속성입니다. 투명도 비슷한 효과 제공 합니다. **참고:** 이 동작을 재정의 하거나 제거할 수 있습니다는 <xref:System.Windows.Controls.Control.Background%2A> 속성 매핑.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|기본 매핑을 다시 할당 되지 않은, 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 된 상위 항목을 찾을 때까지 상위 계층 구조를 통과 해당 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성 집합입니다. 이 값은 가장 유사한 변환 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 커서입니다.<br /><br /> 경우에 대 한 기본 매핑을 <xref:System.Windows.FrameworkElement.ForceCursor%2A> 속성 다시 할당 되지 않은 경우, 순회가 있는 첫 번째 상위 항목에서 중지 <xref:System.Windows.FrameworkElement.ForceCursor%2A> 로 설정 `true`합니다.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight>은 <xref:System.Windows.Forms.RightToLeft.No>에 매핑됩니다.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft>은 <xref:System.Windows.Forms.RightToLeft.Yes>에 매핑됩니다.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit>매핑되지 않습니다.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType>은 <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>에 매핑됩니다.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A>호스팅된 컨트롤에서<xref:System.Drawing.Font?displayProperty=nameWithType>|집합이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성은 해당 변환할 <xref:System.Drawing.Font>합니다. 이러한 속성 중 하나가 변경 되 면 새 <xref:System.Drawing.Font> 만들어집니다. 에 대 한 <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic> 을 사용할 수 없습니다. 에 대 한 <xref:System.Windows.FontStyles.Italic%2A> 또는 <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle.Italic> 를 사용할 수 있습니다.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A>호스팅된 컨트롤에서<xref:System.Drawing.Font?displayProperty=nameWithType>|집합이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성은 해당 변환할 <xref:System.Drawing.Font>합니다. 이러한 속성 중 하나가 변경 되 면 새 <xref:System.Drawing.Font> 만들어집니다. 에 대 한 <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>, 또는 <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold> 를 사용할 수 있습니다. 에 대 한 <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>, 또는 <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold> 을 사용할 수 없습니다.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|집합이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성은 해당 변환할 <xref:System.Drawing.Font>합니다. 이러한 속성 중 하나가 변경 되 면 새 <xref:System.Drawing.Font> 만들어집니다. 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 글꼴 크기에 따라 크기가 조정 합니다.<br /><br /> 글꼴 크기 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 는 1/96 인치와로 표시 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 인치의 1/72 초까지 합니다. 해당 변환은 다음과 같습니다.<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]글꼴 크기 = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 글꼴 크기 * 72.0 96.0 / 합니다.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Foreground%2A> 속성 매핑은 다음 규칙을 사용 하 여 수행 됩니다.<br /><br /> -If <xref:System.Windows.Controls.Control.Foreground%2A> 는 <xref:System.Windows.Media.SolidColorBrush>를 사용 하 여 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 에 대 한 <xref:System.Windows.Forms.Control.ForeColor%2A>합니다.<br />-If <xref:System.Windows.Controls.Control.Foreground%2A> 는 <xref:System.Windows.Media.GradientBrush>의 색을 사용 하 여는 <xref:System.Windows.Media.GradientStop> 에 대 한 오프셋 값이 가장 낮은 <xref:System.Windows.Forms.Control.ForeColor%2A>합니다.<br />-에 대 한 다른 모든 <xref:System.Windows.Media.Brush> 입력으로 둡니다 <xref:System.Windows.Forms.Control.ForeColor%2A> 변경 되지 않습니다. 즉, 기본값이 사용 됩니다.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|때 <xref:System.Windows.UIElement.IsEnabled%2A> 설정 되어 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 집합에서 <xref:System.Windows.Forms.Control.Enabled%2A> 호스팅된 컨트롤에는 속성입니다.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|모든 4 개의 값은 <xref:System.Windows.Forms.Control.Padding%2A> 속성에 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 동일 하 게 설정 <xref:System.Windows.Thickness> 값입니다.<br /><br /> -보다 큰 값 <xref:System.Int32.MaxValue> 로 설정 <xref:System.Int32.MaxValue>합니다.<br />-값 보다 작은 <xref:System.Int32.MinValue> 로 설정 <xref:System.Int32.MinValue>합니다.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible>매핑될 <xref:System.Windows.Forms.Control.Visible%2A>  =  `true`합니다. 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 표시 됩니다. 명시적으로 설정 된 <xref:System.Windows.Forms.Control.Visible%2A> 에 호스팅된 컨트롤에서 속성 `false` 권장 되지 않습니다.<br />-   <xref:System.Windows.Visibility.Collapsed>매핑될 <xref:System.Windows.Forms.Control.Visible%2A>  =  `true` 또는 `false`합니다. 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 그리지 않습니다 및 그 영역이 축소 된 것입니다.<br />-   <xref:System.Windows.Visibility.Hidden>: 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서는 레이아웃에서 공간을 차지 하지만 표시 되지 않습니다. 이 경우에 <xref:System.Windows.Forms.Control.Visible%2A> 속성이 `true`합니다. 명시적으로 설정 된 <xref:System.Windows.Forms.Control.Visible%2A> 에 호스팅된 컨트롤에서 속성 `false` 권장 되지 않습니다.|  
  
 컨테이너 요소에 연결 된 속성에서 완전히 지원 되는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.  
  
 자세한 내용은 참조 [연습: WindowsFormsHost 요소를 사용 하 여 매핑 속성](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)합니다.  
  
## <a name="updates-to-parent-properties"></a>부모 속성에 대 한 업데이트  
 대부분의 부모 속성 변경이 호스팅된 자식 컨트롤에는 알림입니다. 다음 목록에는 해당 값이 변경 될 때 알림을 발생 하지 않는 속성을 설명 합니다.  
  
-   <xref:System.Windows.Controls.Control.Background%2A>  
  
-   <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
-   <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
-   <xref:System.Windows.UIElement.Visibility%2A>  
  
 예를 들어, 값을 변경 하는 경우는 <xref:System.Windows.Controls.Control.Background%2A> 속성의는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 <xref:System.Windows.Forms.Control.BackColor%2A> 호스팅된 컨트롤의 속성이 변경 되지 않습니다.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>ElementHost 컨트롤에서 속성 매핑  
 다음 속성에는 기본 제공 변경 알림을 제공합니다. 호출 하지 마십시오는 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 메서드가 이러한 속성을 매핑할 경우:  
  
-   AutoSize  
  
-   BackColor  
  
-   BackgroundImage  
  
-   BackgroundImageLayout  
  
-   BindingContext  
  
-   CausesValidation  
  
-   ContextMenu  
  
-   ContextMenuStrip  
  
-   Cursor  
  
-   도킹  
  
-   사용  
  
-   글꼴  
  
-   ForeColor  
  
-   위치  
  
-   여백  
  
-   안쪽 여백  
  
-   부모  
  
-   Region  
  
-   RightToLeft  
  
-   크기  
  
-   TabIndex  
  
-   TabStop  
  
-   텍스트  
  
-   표시  
  
 <xref:System.Windows.Forms.Integration.ElementHost> 제어 기본 변환 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 속성을 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다음 변환 표를 사용 하 여 해당 항목입니다.  
  
 자세한 내용은 참조 [연습: ElementHost 컨트롤을 사용 하 여 속성 매핑](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)합니다.  
  
|Windows Forms 호스팅|Windows Presentation Foundation|상호 운용 동작|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) 호스팅된 요소에|이 속성을 강제로 다시 그리도록와는 <xref:System.Windows.Media.ImageBrush>합니다. 경우는 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 속성이 `false` (기본값)이 <xref:System.Windows.Media.ImageBrush> 의 모양에 따라는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 포함 하 여 해당 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> 속성과 연결 된 모든 그리기 처리기입니다.<br /><br /> 경우는 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 속성이 `true`, <xref:System.Windows.Media.ImageBrush> 의 모양에 따라는 <xref:System.Windows.Forms.Integration.ElementHost> 부모 항목을 포함 하 여 컨트롤의 부모 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> 속성과 연결 된 모든 그리기 처리기입니다.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) 호스팅된 요소에|이 속성을 설정 하면 동일한 동작에 대 한 설명의 <xref:System.Windows.Forms.Control.BackColor%2A> 매핑.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) 호스팅된 요소에|이 속성을 설정 하면 동일한 동작에 대 한 설명의 <xref:System.Windows.Forms.Control.BackColor%2A> 매핑.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 해당 표준 커서는 변환 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 표준 커서입니다. 경우는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 표준 커서 않습니다 기본값이 할당 됩니다.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|때 <xref:System.Windows.Forms.Control.Enabled%2A> 설정 되 면는 <xref:System.Windows.Forms.Integration.ElementHost> 설정 제어는 <xref:System.Windows.UIElement.IsEnabled%2A> 호스팅된 요소에는 속성입니다.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A> 값은 해당 집합으로 변환 됩니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 글꼴 속성입니다.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A>호스팅된 요소에|<xref:System.Drawing.Font.Bold%2A>이`true`이면 <xref:System.Windows.Controls.Control.FontWeight%2A>가 <xref:System.Windows.FontWeights.Bold%2A>로 설정됩니다.<br /><br /> <xref:System.Drawing.Font.Bold%2A>이`false`이면 <xref:System.Windows.Controls.Control.FontWeight%2A>가 <xref:System.Windows.FontWeights.Normal%2A>로 설정됩니다.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A>호스팅된 요소에|<xref:System.Drawing.Font.Italic%2A>이`true`이면 <xref:System.Windows.Controls.Control.FontStyle%2A>가 <xref:System.Windows.FontStyles.Italic%2A>로 설정됩니다.<br /><br /> <xref:System.Drawing.Font.Italic%2A>이`false`이면 <xref:System.Windows.Controls.Control.FontStyle%2A>가 <xref:System.Windows.FontStyles.Normal%2A>로 설정됩니다.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations>호스팅된 요소에|호스트 하는 경우에 적용 되는 <xref:System.Windows.Controls.TextBlock> 컨트롤입니다.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations>호스팅된 요소에|호스트 하는 경우에 적용 되는 <xref:System.Windows.Controls.TextBlock> 컨트롤입니다.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No>은 <xref:System.Windows.FlowDirection.LeftToRight>에 매핑됩니다.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes>은 <xref:System.Windows.FlowDirection.RightToLeft>에 매핑됩니다.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Integration.ElementHost> 설정 제어는 <xref:System.Windows.UIElement.Visibility%2A> 다음 규칙을 사용 하 여 호스팅된 요소에는 속성:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true`매핑될 <xref:System.Windows.Visibility.Visible>합니다.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false`매핑될 <xref:System.Windows.Visibility.Hidden>합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [WPF 및 Windows Forms 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)  
 [연습: WindowsFormsHost 요소를 사용하여 속성 매핑](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)  
 [연습: ElementHost 컨트롤을 사용하여 속성 매핑](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)
