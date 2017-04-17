---
title: "WPF 및 Windows Forms 상호 운용성 | Microsoft Docs"
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
  - "혼합 컨트롤[WPF 상호 운용성]"
  - "상호 운용성[WPF], Windows Forms"
  - "중첩된 상호 운용[WPF]"
  - "Windows Forms[WPF], 상호 운용성"
  - "Windows Forms, WPF 상호 운용"
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# WPF 및 Windows Forms 상호 운용성
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에서는 응용 프로그램 인터페이스를 만들기 위한 두 가지 서로 다른 아키텍처를 제공합니다.  <xref:System.Windows.Forms.Integration?displayProperty=fullName> 네임스페이스는 일반적인 상호 운영 시나리오를 위한 클래스를 제공합니다.  상호 운영 기능을 구현하는 두 가지 주요 클래스는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 및 <xref:System.Windows.Forms.Integration.ElementHost>입니다.  이 항목에서는 지원되는 상호 운영 시나리오 및 지원되지 않는 상호 운영 시나리오에 대해 설명합니다.  
  
> [!NOTE]
>  *혼합 컨트롤* 시나리오에는 특별한 주의가 필요합니다.  혼합 컨트롤에서는 한 기술의 컨트롤이 다른 기술의 컨트롤에 중첩되어 있습니다.  이를 *중첩된 상호 운영*이라고 부릅니다.  *여러 수준 혼합 컨트롤*에는 두 수준 이상의 혼합 컨트롤 중첩이 있습니다.  여러 수준의 중첩된 상호 운영에 대한 예는 다른 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 포함된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤입니다.  여러 수준 혼합 컨트롤은 지원되지 않습니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## WPF에서 Windows Forms 컨트롤 호스팅  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤을 호스팅하는 경우 다음과 같은 상호 운영 시나리오가 지원됩니다.  
  
-   XAML을 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서 하나 이상의 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 호스팅할 수 있습니다.  
  
-   코드를 사용하여 WPF 컨트롤에서 하나 이상의 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 호스팅할 수 있습니다.  
  
-   WPF 컨트롤에서 다른 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 포함된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨테이너 컨트롤을 호스팅할 수 있습니다.  
  
-   WPF 컨트롤에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 마스터 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 세부를 사용하는 마스터\/세부 폼을 호스팅할 수 있습니다.  
  
-   WPF 컨트롤에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 마스터 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 세부를 사용하는 마스터\/세부 폼을 호스팅할 수 있습니다.  
  
-   WPF 컨트롤에서 하나 이상의 [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] 컨트롤을 호스팅할 수 있습니다.  
  
-   WPF 컨트롤이 하나 이상의 복합 컨트롤을 호스팅할 수 있습니다.  
  
-   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 WPF 컨트롤에서 혼합 컨트롤을 호스팅할 수 있습니다.  
  
-   코드를 사용하여 WPF 컨트롤에서 혼합 컨트롤을 호스팅할 수 있습니다.  
  
### 레이아웃 지원  
 다음 목록은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템에 통합하려고 할 때의 알려진 제한에 대해 설명합니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 크기를 조정할 수 없거나 특정 치수로만 크기를 조정할 수 있는 경우가 있습니다.  예를 들어 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> 컨트롤은 컨트롤의 글꼴 크기에 의해 정의되는 단일 높이만 지원합니다.  요소를 세로로 확장할 수 있다고 가정하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 동적 레이아웃에서는 호스팅된 <xref:System.Windows.Forms.ComboBox> 컨트롤이 예상한 대로 확장되지 않습니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 회전하거나 기울일 수 없습니다.  예를 들어 사용자 인터페이스를 90도 회전하는 경우 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 수직 위치를 유지합니다.  
  
-   대부분의 경우 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서는 비율 크기 조정을 지원하지 않습니다.  컨트롤의 전체 치수의 크기가 조정되어도 컨트롤의 자식 컨트롤 및 구성 요소 크기는 예상한 대로 조정되지 않습니다.  이러한 제한은 각 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 크기 조정을 얼마나 잘 지원하는지에 따라 다릅니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서 요소의 Z 순서를 변경하여 겹치기 동작을 제어할 수 있습니다.  호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 위에서 그려지므로 개별 HWND에서 그려집니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 글꼴 크기를 기반으로 하는 자동 크기 조정을 지원합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서는 개별 요소의 크기가 동적으로 조정될 수 있어도 글꼴 크기를 조정할 때 전체 레이아웃의 크기가 조정되지 않습니다.  
  
### 앰비언트 속성  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 일부 앰비언트 속성에는 이에 해당하는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 앰비언트 속성이 있습니다.  이러한 앰비언트 속성은 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤로 전파되고 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤의 공용 속성으로 노출됩니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은 각 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 앰비언트 속성을 이에 해당하는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 앰비언트 속성으로 변환합니다.  
  
 자세한 내용은 [Windows Forms 및 WPF 속성 매핑](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)을 참조하십시오.  
  
### 동작  
 다음 표에서는 상호 운용 동작에 대해 설명합니다.  
  
|동작|지원됨|지원 안 함|  
|--------|---------|------------|  
|투명도|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 렌더링에서는 투명도를 지원합니다.  부모 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 배경은 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 배경이 될 수 있습니다.|일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 투명도를 지원하지 않습니다.  예를 들어 <xref:System.Windows.Forms.TextBox> 및 <xref:System.Windows.Forms.ComboBox> 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 의해 호스팅될 때 투명하지 않습니다.|  
|탭|호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 탭 순서는 이러한 컨트롤이 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 기반 응용 프로그램에서 호스팅되는 경우의 탭 순서와 같습니다.<br /><br /> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤로의 탭은 일반적인 경우와 같이 Tab 키와 Shift\+Tab을 사용하여 작동합니다.<br /><br /> <xref:System.Windows.Forms.Control.TabStop%2A> 속성 값이 `false`인 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 사용자가 컨트롤 사이에서 탭 작업을 수행할 때 포커스를 받지 않습니다.<br /><br /> -   각 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> 값이 있습니다. 이 값은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에서 포커스를 받는 경우를 결정합니다.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨테이너 내에 포함된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성에서 지정하는 순서를 따릅니다.  마지막 탭 인덱스에서 탭을 사용하면 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤\(하나라도 있는 경우\)이 포커스를 받습니다.  포커스를 받을 수 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 없으면 탭 순서의 첫 번째 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤로 탭이 되돌아갑니다.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 내에 있는 컨트롤의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> 값은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에 포함된 형제 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 상대적입니다.<br />-   탭은 컨트롤 관련 동작의 영향을 받습니다.  예를 들어 <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> 속성 값이 `true`인 <xref:System.Windows.Forms.TextBox> 컨트롤에서 Tab 키를 누르면 포커스를 이동하는 대신 텍스트 상자에 탭이 입력됩니다.|해당 사항 없음.|  
|화살표 키를 사용하여 탐색|-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에서 화살표 키를 사용하여 탐색하는 작업은 일반적인 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨테이너 컨트롤에서 화살표 키를 사용하여 탐색하는 작업과 동일합니다. 위쪽 화살표 및 왼쪽 화살표 키는 이전 컨트롤을 선택하고 아래쪽 화살표 및 오른쪽 화살표 키는 다음 컨트롤을 선택합니다.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에 포함되어 있는 첫 번째 컨트롤의 위쪽 화살표 및 왼쪽 화살표 키는 Shift\+Tab 바로 가기 키와 동일한 동작을 수행합니다.  포커스를 받을 수 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 있는 경우 포커스는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 외부로 이동합니다.  이러한 동작은 마지막 컨트롤로의 래핑이 발생하지 않는다는 점에서 표준 <xref:System.Windows.Forms.ContainerControl> 동작과 다릅니다.  포커스를 받을 수 있는 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 없으면 포커스가 탭 순서의 마지막 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤로 되돌아갑니다.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에 포함되어 있는 마지막 컨트롤의 아래쪽 화살표 및 오른쪽 화살표 키는 Tab 키와 동일한 동작을 수행합니다.  포커스를 받을 수 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 있는 경우 포커스는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 외부로 이동합니다.  이러한 동작은 첫 번째 컨트롤로의 래핑이 발생하지 않는다는 점에서 표준 <xref:System.Windows.Forms.ContainerControl> 동작과 다릅니다.  포커스를 받을 수 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 없으면 포커스가 탭 순서의 첫 번째 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤로 되돌아갑니다.|해당 사항 없음.|  
|액셀러레이터|액셀러레이터는 "지원 안 함" 열에 명시된 경우를 제외하고 평소대로 작동합니다.|기술 간에 중복된 액셀러레이터는 일반적인 중복된 액셀러레이터와 같이 작동하지 않습니다.  액셀러레이터가 기술 간에 중복되는 경우, 즉 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 하나 이상이, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에 다른 하나가 있는 경우 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 항상 액셀러레이터를 받습니다.  중복된 액셀러레이터를 누를 때 컨트롤 사이에 포커스가 전환되지 않습니다.|  
|바로 가기 키|액셀러레이터 키는 "지원 안 함" 열에 명시된 경우를 제외하고 평소대로 작동합니다.|-   전처리 단계에서 처리되는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 바로 가기 키는 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 바로 가기 키보다 우선적으로 적용됩니다.  예를 들어 Ctrl\+S 바로 가기 키가 정의된 <xref:System.Windows.Forms.ToolStrip> 컨트롤이 있으며 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 명령이 Ctrl\+S에 바인딩되어 있는 경우 포커스에 상관없이 항상 <xref:System.Windows.Forms.ToolStrip> 컨트롤 처리기가 먼저 호출됩니다.<br />-   <xref:System.Windows.Forms.Control.KeyDown> 이벤트에 의해 처리되는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 바로 가기 키는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 마지막으로 처리됩니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 <xref:System.Windows.Forms.Control.IsInputKey%2A> 메서드를 재정의하거나 <xref:System.Windows.Forms.Control.PreviewKeyDown> 이벤트를 처리하여 이 동작이 발생하지 않도록 지정할 수 있습니다.  <xref:System.Windows.Forms.Control.IsInputKey%2A> 메서드에서 `true`를 반환하거나 <xref:System.Windows.Forms.Control.PreviewKeyDown> 이벤트 처리기에서 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=fullName> 속성의 값을 `true`로 설정합니다.|  
|AcceptsReturn, AcceptsTab 및 기타 컨트롤 관련 동작|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 <xref:System.Windows.Forms.Control.IsInputKey%2A> 메서드를 재정의하여 `true`를 반환한다는 가정하에서 기본 키보드 동작을 변경하는 속성은 평소대로 작동합니다.|<xref:System.Windows.Forms.Control.KeyDown> 이벤트를 처리하여 기본 키보드 동작을 변경하는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 호스트 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서 마지막으로 처리됩니다.  이러한 컨트롤은 마지막으로 처리되기 때문에 예상치 못한 동작을 발생시킬 수 있습니다.|  
|시작 및 종료 이벤트|포함하는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에 포커스가 지정되지 않는 경우 단일 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에서 포커스가 변경되는 경우 시작 및 종료 이벤트가 평소대로 발생합니다.|다음과 같이 포커스가 변경되는 경우에는 시작 및 종료 이벤트가 발생하지 않습니다.<br /><br /> -   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 내부에서 외부로의 포커스 변경<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 외부에서 내부로의 포커스 변경<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 외부의 포커스 변경<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서 동일한 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 내에 호스팅된 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤로의 포커스 변경|  
|다중 스레딩|모든 형태의 다중 스레딩이 지원됩니다.|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 기술과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기술 모두 단일 스레드 동시성 모델을 사용합니다.  디버깅 동안 다른 스레드에서 프레임워크 개체로 호출하면 예외가 발생하여 이 요구 사항이 강제 적용됩니다.|  
|보안|모든 상호 운용 시나리오에서는 완전 신뢰가 필요합니다.|부분 신뢰에서는 상호 운용 시나리오를 사용할 수 없습니다.|  
|내게 필요한 옵션|모든 내게 필요한 옵션 시나리오가 지원됩니다.  보조 기술 제품 기능은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 모두 포함하는 혼합 응용 프로그램에 사용되는 경우 제대로 작동합니다.|해당 사항 없음.|  
|클립보드|모든 클립보드 작업은 평소대로 작동합니다.  이러한 작업에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 사이에서의 잘라내기 및 붙여넣기 작업이 포함됩니다.|해당 사항 없음.|  
|끌어서 놓기 기능|모든 끌어서 놓기 작업은 평소대로 작동합니다.  이 작업에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 사이의 작업이 포함됩니다.|해당 사항 없음.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## Windows Forms에서 WPF 컨트롤 호스팅  
 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 호스팅하는 경우 다음과 같은 상호 운영 시나리오가 지원됩니다.  
  
-   코드를 사용하여 하나 이상의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 호스팅  
  
-   하나 이상의 호스팅된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에 속성 시트 연결  
  
-   폼에서 하나 이상의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지 호스팅  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 창 시작  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 마스터 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 세부를 사용하는 마스터\/세부 폼 호스팅  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 마스터 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 세부를 사용하는 마스터\/세부 폼 호스팅  
  
-   사용자 지정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 호스팅  
  
-   혼합 컨트롤 호스팅  
  
### 앰비언트 속성  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 일부 앰비언트 속성에는 이에 해당하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 앰비언트 속성이 있습니다.  이러한 앰비언트 속성은 호스팅된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤로 전파되고 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 공용 속성으로 노출됩니다.  <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 각 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 앰비언트 속성을 이에 해당하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 앰비언트 속성으로 변환합니다.  
  
 자세한 내용은 [Windows Forms 및 WPF 속성 매핑](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)을 참조하십시오.  
  
### 동작  
 다음 표에서는 상호 운용 동작에 대해 설명합니다.  
  
|동작|지원됨|지원 안 함|  
|--------|---------|------------|  
|투명도|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 렌더링에서는 투명도를 지원합니다.  부모 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 배경은 호스팅된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 배경이 될 수 있습니다.|해당 사항 없음.|  
|다중 스레딩|모든 형태의 다중 스레딩이 지원됩니다.|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 기술과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기술 모두 단일 스레드 동시성 모델을 사용합니다.  디버깅 동안 다른 스레드에서 프레임워크 개체로 호출하면 예외가 발생하여 이 요구 사항이 강제 적용됩니다.|  
|보안|모든 상호 운용 시나리오에서는 완전 신뢰가 필요합니다.|부분 신뢰에서는 상호 운용 시나리오를 사용할 수 없습니다.|  
|내게 필요한 옵션|모든 내게 필요한 옵션 시나리오가 지원됩니다.  보조 기술 제품 기능은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 모두 포함하는 혼합 응용 프로그램에 사용되는 경우 제대로 작동합니다.|해당 사항 없음.|  
|클립보드|모든 클립보드 작업은 평소대로 작동합니다.  이러한 작업에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 사이에서의 잘라내기 및 붙여넣기 작업이 포함됩니다.|해당 사항 없음.|  
|끌어서 놓기 기능|모든 끌어서 놓기 작업은 평소대로 작동합니다.  이 작업에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 사이의 작업이 포함됩니다.|해당 사항 없음.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [연습: WPF에서 Windows Forms 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Windows Forms 및 WPF 속성 매핑](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)