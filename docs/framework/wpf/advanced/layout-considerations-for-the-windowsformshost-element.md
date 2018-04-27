---
title: WindowsFormsHost 요소에 대한 레이아웃 고려 사항
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element layout considerations [WPF]
- dynamic layout [WPF interoperability]
- device-independent pixels
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b915d3cdaebc862534c2ba6bd006d3b447e2a651
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>WindowsFormsHost 요소에 대한 레이아웃 고려 사항
이 항목에서는 설명 방법을 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소와 상호 작용 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 를 조정 하 고 폼 이나 페이지에서 요소 위치 지정 다르지만, 비슷한 논리를 지원 합니다. 하이브리드 사용자 인터페이스 (UI)를 만들 때 해당 호스트 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Forms.Integration.WindowsFormsHost> 두 레이아웃 스키마를 통합 하는 요소입니다.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>WPF 및 Windows Forms 간에 레이아웃의 차이점  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 해상도 독립적인 레이아웃을 사용합니다. 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 차원을 사용 하 여 지정 *장치 독립적 픽셀*합니다. 장치 독립적 픽셀 1/96 인치 크기 및 해상도 독립적인 이므로 72 dpi 모니터 또는 19200 dpi 프린터에 렌더링 하는 여부에 관계 없이 비슷한 결과 가져옵니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 또한 기반 *동적 레이아웃*합니다. 이 UI 요소에 자동으로 정렬 폼 또는 페이지의 내용, 해당 부모 레이아웃 컨테이너 및 사용 가능한 화면 크기에 따라 의미 합니다. 동적 레이아웃은 자동으로 포함 하는 문자열 길이 변경할 때 UI 요소의 위치와 크기를 조정 하 여 지역화를 지원 합니다.  
  
 레이아웃에 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 장치 종속적 고 정적일 가능성이 높습니다. 일반적으로 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 절대적으로 하드웨어 픽셀로 지정 된 차원을 사용 하 여 폼에 배치 됩니다. 그러나 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 는 다음 표에 요약 된 것 처럼 일부 동적 레이아웃 기능을 지원 합니다.  
  
|레이아웃 기능|설명|  
|--------------------|-----------------|  
|크기 자동 조정|일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 크기가 콘텐츠를 올바르게 표시 하는 자동으로 조정 합니다. 자세한 내용은 참조 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)합니다.|  
|고정 및 도킹|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 배치 하 고 부모 컨테이너에 따라 크기 조정 지원. 자세한 내용은 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>를 참조하세요.|  
|자동 크기 조정|자신 및 출력 장치 또는 기본 컨테이너 글꼴을 픽셀 단위로 크기, 해상도에 따라 자식 컨테이너 컨트롤의 크기를 조정 합니다. 자세한 내용은 참조 [Windows Forms의 자동 크기 조정을](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)합니다.|  
|레이아웃 컨테이너|<xref:System.Windows.Forms.FlowLayoutPanel> 및 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 컨트롤은 자식 컨트롤을 정렬 하 고 해당 내용에 따라 자체 크기입니다.|  
  
## <a name="layout-limitations"></a>레이아웃 제한  
 일반적으로 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 크기가 조정 하 고 변환 하는 범위 내에서 가능한 없습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다. 다음과 같은 알려진된 제한 사항에 설명 때는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 호스팅된 통합 하려고 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템입니다.  
  
-   경우에 따라 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 크기를 조정할 수 없거나 특정 차원으로만 크기를 조정할 수 있습니다. 예를 들어 한 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> 컨트롤은 컨트롤의 글꼴 크기에 의해 정의 된 단일 높이 지원 합니다. 에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 동적 레이아웃에 요소를 세로로 확장할 수는 호스팅 <xref:System.Windows.Forms.ComboBox> 예상 대로 컨트롤이 늘어나지 것입니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 회전하거나 기울일 수 없습니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 를 발생 시키는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 기울이기 또는 회전 변환을 적용 하는 경우에 이벤트입니다. 처리 하지 않는 경우는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 이벤트는 <xref:System.InvalidOperationException> 발생 합니다.  
  
-   대부분의 경우 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 서는 비례하여 크기 조정을 지원하지 않습니다. 컨트롤의 전체 크기는 조정할 수 있지만, 컨트롤의 구성 요소와 자식 컨트롤의 크기가 예상대로 조정되지 않을 수 있습니다. 이 제한 사항은 각 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서 얼마나 효과적으로 크기 조정을 지원하는지에 따라 달라집니다. 또한 확장할 수 없으며 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 0 픽셀의 크기로 컨트롤입니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에는 폼은 자동으로 조정 하 고 해당 컨트롤의 글꼴 크기에 따라 자동 크기 조정을 지원 합니다. 개별 요소의 크기는 동적으로 조정할 수 있지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서 글꼴 크기를 변경해도 전체 레이아웃의 크기는 조정되지 않습니다.  
  
### <a name="z-order"></a>Z 순서  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서 겹치는 동작을 제어하기 위해 요소의 z 순서를 변경할 수 있습니다. 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 개별 HWND에서 그려지므로 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 위에 그려집니다.  
  
 호스팅 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 위에 그려집니다 <xref:System.Windows.Documents.Adorner> 요소입니다.  
  
## <a name="layout-behavior"></a>레이아웃 동작  
 다음 섹션에서는 호스트 하는 경우 레이아웃 동작의 특정 측면을 설명 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>크기 조정, 단위 변환 및 장치 독립성  
 때마다는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 작업 등의 작업을 수행 하는 요소 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 관련 된 차원, 두 개의 좌표 시스템:에 대 한 장치 독립적 픽셀 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에 대 한 하드웨어 픽셀 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]합니다. 따라서 일관 된 레이아웃을 달성 하기 위해 적절 한 단위 및 배율 변환을 적용 해야 합니다.  
  
 렌더링 변환에 적용 된 또는 현재 장치 해상도 모든 레이아웃에 따라 다릅니다 좌표 시스템 간의 변환은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 또는 해당 상위 항목입니다.  
  
 출력 장치 96dpi 있고 경우에 적용 된 크기가 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 하나의 장치 독립적 픽셀은 하나의 하드웨어 픽셀입니다.  
  
 다른 모든 경우 좌표계 크기 조정 해야합니다. 호스팅된 컨트롤 조정 되지 않습니다. 대신,는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 호스팅된 컨트롤 및 모든 해당 자식 컨트롤의 크기를 조정 하려고 합니다. 때문에 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 크기 조정을 완전히 지원 하지 않습니다는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 특정 컨트롤에서 지원 되는 정도 요소까지 확장 합니다.  
  
 재정의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> 호스팅된 Windows Forms 컨트롤에 대 한 사용자 지정 크기 조정 동작을 제공 하는 메서드.  
  
 를 확장 하는 것 외에도 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 다음 표에 설명 된 대로 반올림 및 오버플로 처리 합니다.  
  
|변환 문제|설명|  
|----------------------|-----------------|  
|반올림|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 장치 독립적 픽셀 치수도 지정 된 `double`, 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 으로 지정 된 하드웨어 픽셀 치수 `int`합니다. 경우에서 여기서 `double`-기반된 크기로 변환 됩니다 `int`-차원 기반는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 표준 반올림 되므로 사용 하 여 0으로 0.5 보다 작은 소수 자릿수 값 반올림 됩니다.|  
|오버플로|경우는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에서 변환 `double` 값을 `int` 값 오버플로 가능 합니다. 보다 큰 값은 <xref:System.Int32.MaxValue> 로 설정 <xref:System.Int32.MaxValue>합니다.|  
  
### <a name="layout-related-properties"></a>레이아웃 관련 속성  
 레이아웃 동작을 제어 하는 속성 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소에서 적절 하 게 매핑됩니다는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다. 자세한 내용은 [Windows Forms 및 WPF 속성 매핑](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)을 참조하세요.  
  
### <a name="layout-changes-in-the-hosted-control"></a>호스팅된 컨트롤에서 레이아웃 변경  
 호스팅된의 레이아웃 변경 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어에 전파 됩니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 업데이트를 트리거합니다. <xref:System.Windows.UIElement.InvalidateMeasure%2A> 메서드를 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 호스팅된 컨트롤에서 레이아웃 변경을 통해는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 엔진을 실행 합니다.  
  
### <a name="continuously-sized-windows-forms-controls"></a>지속적으로 Windows Forms 컨트롤 크기의  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 와 상호 작용 연속 배율을 완벽 하 게 지 원하는 컨트롤의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템입니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 사용 하 여는 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 평소와 같이 정렬 하 고 크기 호스팅된 메서드 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.  
  
### <a name="sizing-algorithm"></a>크기 조정 알고리즘  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 다음 절차를 사용 하 여 호스트 된 컨트롤 크기를 조정 합니다.  
  
1.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 재정의 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드.  
  
2.  호스팅된 컨트롤의 크기를 결정 하는 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 호스팅된 컨트롤의 메서드를 호출 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 에 전달 된 제약 조건에서 번역 된 제약 조건으로 메서드는 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 메서드.  
  
3.  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드 주어진된 크기 제약 조건에 호스트 된 컨트롤을 설정 하려고 시도 합니다.  
  
4.  경우 호스트 된 컨트롤의 <xref:System.Windows.Forms.Control.Size%2A> 속성에 지정 된 제약 조건과 일치, 제약 조건에 호스팅된 컨트롤 크기가 조정 됩니다.  
  
 경우는 <xref:System.Windows.Forms.Control.Size%2A> 속성이 지정 된 제약 조건 일치 하지 않으면, 호스팅된 컨트롤에 연속 크기 조정을 지원 하지 않습니다. 예를 들어는 <xref:System.Windows.Forms.MonthCalendar> 컨트롤 불연속 크기만 허용 합니다. 이 컨트롤에 허용 되는 크기 (개월 수를 나타내는) 정수 높이 너비에 대 한 구성 됩니다. 이와 같은 경우에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 다음과 같이 동작 합니다.  
  
-   경우는 <xref:System.Windows.Forms.Control.Size%2A> 지정 된 제약 조건 보다 더 큰 크기를 반환 하는 속성의 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 호스팅된 컨트롤을 자르는 합니다. 호스팅된 컨트롤에서 양방향 잘릴 수도 있습니다 하므로 높이 너비 별도로 처리 됩니다.  
  
-   경우는 <xref:System.Windows.Forms.Control.Size%2A> 속성에 지정 된 제약 조건 보다 더 작은 크기를 반환 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 크기 값이 허용 값을 반환 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [연습: WPF에서 Windows Forms 컨트롤 정렬](../../../../docs/framework/wpf/advanced/walkthrough-arranging-windows-forms-controls-in-wpf.md)  
 [WPF 샘플에서 정렬 Windows Forms 컨트롤](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [Windows Forms 및 WPF 속성 매핑](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
