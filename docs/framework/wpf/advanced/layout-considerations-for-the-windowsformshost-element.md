---
title: "WindowsFormsHost 요소에 대한 레이아웃 고려 사항 | Microsoft Docs"
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
  - "장치 독립적 픽셀"
  - "동적 레이아웃[WPF 상호 운용성]"
  - "상호 운용성[WPF], Windows Forms"
  - "Windows Forms[WPF], 상호 운용성"
  - "Windows Forms, WPF 상호 운용"
  - "WindowsFormsHost 요소 레이아웃 고려 사항"
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# WindowsFormsHost 요소에 대한 레이아웃 고려 사항
이 항목에서는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템과 어떻게 상호 작용하는지를 설명합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]은 폼 또는 페이지에서 요소의 크기와 위치를 조정하는 서로 다르지만 유사한 논리를 지원합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]를 호스팅하는 혼합 UI\(사용자 인터페이스\)를 만들면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 두 레이아웃 스키마를 통합합니다.  
  
## WPF 및 Windows Forms 간의 레이아웃 차이점  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 해상도의 영향을 받지 않는 레이아웃을 사용합니다.  모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 크기는 *장치 독립적 픽셀*을 사용하여 지정됩니다.  장치 독립적 픽셀은 크기가 1\/96인치이며 해상도의 영향을 받지 않기 때문에 72dpi 모니터에 렌더링하거나 19,200dpi 프린터에 렌더링하거나 동일한 결과를 얻습니다.  
  
 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 *동적 레이아웃*을 기반으로 합니다.  이는 콘텐츠, 부모 레이아웃 컨테이너 및 사용 가능한 화면 크기에 따라 UI 요소가 폼 또는 페이지에 자동으로 정렬된다는 것을 의미합니다.  동적 레이아웃은 포함된 문자열의 길이가 변경될 때 UI 요소의 크기와 위치를 자동으로 조정함으로써 지역화를 수월하게 만듭니다.  
  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]의 레이아웃은 장치의 영향을 받지 않으며 보다 정적입니다.  일반적으로 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 하드웨어 픽셀로 지정된 크기를 사용하여 폼에 절대적으로 배치됩니다.  그러나 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]는 다음 표에 요약된 것처럼 일부 동적 레이아웃 기능을 지원합니다.  
  
|레이아웃 기능|설명|  
|-------------|--------|  
|자동 크기 조정|일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 콘텐츠를 제대로 표시하기 위해 크기가 자동으로 조정됩니다.  자세한 내용은 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)를 참조하십시오.|  
|고정 및 도킹|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 부모 컨테이너를 기준으로 위치 및 크기를 조정합니다.  자세한 내용은 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=fullName> 및 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=fullName>를 참조하십시오.|  
|자동 배율 조정|컨테이너 컨트롤은 출력 장치 또는 기본 컨테이너 글꼴의 픽셀 단위 크기를 기준으로 자체 크기 및 자식 항목의 크기를 조정합니다.  자세한 내용은 [Windows Forms의 자동 배율 조정](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)을 참조하십시오.|  
|레이아웃 컨테이너|<xref:System.Windows.Forms.FlowLayoutPanel> 및 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 콘텐츠에 따라 자식 컨트롤을 정렬하고 자체 크기를 조정합니다.|  
  
## 레이아웃 제한  
 일반적으로 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 가능한 범위까지 확장되거나 변환될 수 없습니다.  다음 목록은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템에 통합하려고 할 때의 알려진 제한에 대해 설명합니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 크기를 조정할 수 없거나 특정 치수로만 크기를 조정할 수 있는 경우가 있습니다.  예를 들어 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> 컨트롤은 컨트롤의 글꼴 크기에 의해 정의되는 단일 높이만 지원합니다.  따라서 요소를 세로로 늘릴 수 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 동적 레이아웃에서 호스팅된 <xref:System.Windows.Forms.ComboBox> 컨트롤이 예상만큼 늘어나지 않습니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 회전하거나 기울일 수 없습니다.  기울이기 또는 회전 변환을 적용하는 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 이벤트를 발생시킵니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 이벤트를 처리하지 않으면 <xref:System.InvalidOperationException>이 발생됩니다.  
  
-   대부분의 경우 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서는 비율 크기 조정을 지원하지 않습니다.  컨트롤의 전체 치수의 크기가 조정되어도 컨트롤의 자식 컨트롤 및 구성 요소 크기는 예상한 대로 조정되지 않습니다.  이러한 제한은 각 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 크기 조정을 얼마나 잘 지원하는지에 따라 다릅니다.  또한 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 0 픽셀의 크기로 조정할 수는 없습니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 폼의 크기가 자동으로 조정되고 해당 컨트롤의 크기가 글꼴 크기에 따라 자동으로 조정되는 자동 배율 조정을 지원합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서는 개별 요소의 크기가 동적으로 조정될 수 있어도 글꼴 크기를 조정할 때 전체 레이아웃의 크기가 조정되지 않습니다.  
  
### Z 순서  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서 요소의 Z 순서를 변경하여 겹치기 동작을 제어할 수 있습니다.  호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 위에서 그려지므로 개별 HWND에서 그려집니다.  
  
 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤도 <xref:System.Windows.Documents.Adorner> 요소의 위에 그려집니다.  
  
## 레이아웃 동작  
 다음 단원에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 호스팅할 때 레이아웃 동작의 특정 측면에 대해 설명합니다.  
  
### 배율 조정, 단위 변환 및 장치 독립성  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 크기와 관련된 작업을 수행할 때마다 두 개의 좌표계가 사용됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 장치 독립적 픽셀이 사용되고, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에는 하드웨어 픽셀이 사용됩니다.  따라서 일관된 레이아웃을 유지하기 위해서는 적절한 단위 및 배율 변환을 적용해야 합니다.  
  
 좌표계 간의 변환은 현재 장치 해상도와 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소나 해당 상위 항목에 적용된 레이아웃 또는 렌더링 변환에 따라 다릅니다.  
  
 출력 장치가 96dpi이고 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에 배율 조정이 적용되지 않은 경우에는 1 장치 독립적 픽셀이 1 하드웨어 픽셀과 일치합니다.  
  
 그 외의 모든 경우에는 좌표계 배율 조정이 필요합니다.  호스팅된 컨트롤은 크기가 조정되지 않습니다.  대신 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 호스팅된 컨트롤과 모든 자식 컨트롤의 배율을 조정하려고 시도합니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]는 배율 조정을 완전히 지원하지 않기 때문에 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 특정 컨트롤이 지원하는 정도까지만 배율을 조정합니다.  
  
 호스팅된 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤의 사용자 지정 배율 조정 동작을 제공하도록 <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> 메서드를 재정의하십시오.  
  
 배율 조정 외에도 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 다음 표에서 설명된 대로 반올림 및 오버플로를 처리합니다.  
  
|변환 문제|설명|  
|-----------|--------|  
|반올림|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 장치 독립적 픽셀 크기는 `double`로 지정되고 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 하드웨어 픽셀 크기는 `int`로 지정됩니다.  `double` 기반 크기가 `int` 기반 크기로 변환되는 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 표준 반올림 규칙을 사용합니다. 따라서 0.5 미만의 소수 값은 0이 됩니다.|  
|오버플로가 발생했습니다.|<xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 `double` 값에서 `int` 값으로 변환될 때 오버플로가 발생할 수 있습니다.  <xref:System.Int32.MaxValue>보다 큰 값은 <xref:System.Int32.MaxValue>로 설정됩니다.|  
  
### 레이아웃 관련 속성  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소에서 레이아웃 동작을 제어하는 속성은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에 의해 적절하게 매핑됩니다.  자세한 내용은 [Windows Forms 및 WPF 속성 매핑](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)을 참조하십시오.  
  
### 호스팅된 컨트롤에서의 레이아웃 변경 사항  
 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서의 레이아웃 변경 사항은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 전파되어 레이아웃 업데이트를 트리거합니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost>의 <xref:System.Windows.UIElement.InvalidateMeasure%2A> 메서드는 호스팅된 컨트롤에서의 레이아웃 변경 사항으로 인해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 엔진이 실행되도록 합니다.  
  
### 연속 크기 조정된 Windows Forms 컨트롤  
 연속 배율 조정을 지원하는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템과 완전히 상호 작용합니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 평소처럼 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드를 사용하여 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 정렬하고 크기를 조정합니다.  
  
### 크기 조정 알고리즘  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 다음 절차를 따라 호스팅된 컨트롤의 크기를 조정합니다.  
  
1.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드를 재정의합니다.  
  
2.  호스팅된 컨트롤의 크기를 결정하기 위해 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 메서드가 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 메서드를 호출합니다. 이때 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 메서드에 전달된 제약 조건으로부터 변환된 제약 조건이 적용됩니다.  
  
3.  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드가 호스팅된 컨트롤을 지정된 크기 제약 조건으로 설정하려고 시도합니다.  
  
4.  호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.Size%2A> 속성이 지정된 제약 조건과 일치하는 경우 호스팅된 컨트롤이 제약 조건 크기로 조정됩니다.  
  
 <xref:System.Windows.Forms.Control.Size%2A> 속성이 지정된 제약 조건과 일치하지 않는 경우 호스팅된 컨트롤은 연속 크기 조정을 지원하지 않습니다.  예를 들어 <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 불연속 크기만 허용합니다.  이 컨트롤에 허용되는 크기는 높이와 너비 모두 개월 수를 나타내는 정수로 구성됩니다.  이와 같은 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 다음과 같이 동작합니다.  
  
-   <xref:System.Windows.Forms.Control.Size%2A> 속성이 지정된 제약 조건보다 큰 값을 반환하는 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 호스팅된 컨트롤을 자릅니다.  높이와 너비가 따로 처리되기 때문에 호스팅된 컨트롤이 어느 방향에서나 잘릴 수 있습니다.  
  
-   <xref:System.Windows.Forms.Control.Size%2A> 속성이 지정된 제약 조건보다 작은 값을 반환하는 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost>는 이 크기 값을 받아들이고 해당 값을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템에 반환합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [연습: WPF에서 Windows Forms 컨트롤 정렬](../../../../docs/framework/wpf/advanced/walkthrough-arranging-windows-forms-controls-in-wpf.md)   
 [Windows Forms 컨트롤 샘플 WPF에서에서 정렬](http://go.microsoft.com/fwlink/?LinkID=159971)   
 [Windows Forms 및 WPF 속성 매핑](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)