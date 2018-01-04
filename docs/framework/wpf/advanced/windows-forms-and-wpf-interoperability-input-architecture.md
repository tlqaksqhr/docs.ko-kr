---
title: "Windows Forms 및 WPF 상호 운용성 입력 아키텍처"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- input architecture [WPF interoperability]
- messages [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- modeless forms [WPF]
- ElementHost keyboard and messages [WPF]
- keyboard interoperation [WPF]
- WindowsFormsHost keyboard and messages [WPF]
- modeless dialog boxes [WPF]
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a246a3297d212eabc31bf2ac9d000aeb56329d09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Windows Forms 및 WPF 상호 운용성 입력 아키텍처
간의 상호 운용성은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 두 기술 모두에서 해당 하는 키보드 입력된 처리 해야 합니다. 이 항목에서는 이러한 기술을 키보드와 매끄럽게 상호 운용 혼합 응용 프로그램에서 사용 하도록 설정 하기 위해 메시지 처리를 구현 하는 방법을 설명 합니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
-   모덜리스 양식과 대화 상자  
  
-   WindowsFormsHost 키보드 및 메시지 처리  
  
-   ElementHost 키보드 및 메시지 처리  
  
## <a name="modeless-forms-and-dialog-boxes"></a>모덜리스 양식과 대화 상자  
 호출는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> 에서 메서드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 에서 모덜리스 양식 또는 대화 상자를 열려면 요소는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.  
  
 호출는 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> 에서 메서드는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 열어는 모덜리스 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-기반 응용 프로그램입니다.  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>WindowsFormsHost 키보드 및 메시지 처리  
 호스팅되는 경우는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 키보드 및 메시지 처리는 다음으로 이루어집니다.  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스는 메시지를 가져옵니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 구현 하는 메시지 루프는 <xref:System.Windows.Interop.ComponentDispatcher> 클래스입니다.  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스 만듭니다 서로게이트 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 일반적인 되도록 메시지 루프 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 키보드 처리가 발생 합니다.  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스가 구현 하는 <xref:System.Windows.Interop.IKeyboardInputSink> 인터페이스를 사용 하 여 포커스 관리 조정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 등록 되며 메시지 루프를 시작 합니다.  
  
 다음 섹션에서는 이러한 부분은 과정을 자세히 설명합니다.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>WPF 메시지 루프에서 메시지를 획득합니다.  
 <xref:System.Windows.Interop.ComponentDispatcher> 클래스 구현에 대 한 메시지 루프 관리자 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다. <xref:System.Windows.Interop.ComponentDispatcher> 외부 클라이언트 하기 전에 메시지를 필터링 하는 후크를 제공 하는 클래스 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 처리 합니다.  
  
 상호 운용성 구현 핸들의 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 매핑함으로써 이벤트 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 하기 전에 메시지를 처리 하는 컨트롤 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤입니다.  
  
### <a name="surrogate-windows-forms-message-loop"></a>서로게이트 Windows Forms 메시지 루프  
 기본적으로는 <xref:System.Windows.Forms.Application?displayProperty=nameWithType> 에 대 한 기본 메시지 루프를 포함 하는 클래스 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램입니다. 의 상호 운용 하는 동안는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 메시지 루프는 메시지를 처리 하지 않습니다. 따라서이 논리를 재현해 야 합니다. 에 대 한 처리기는 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 이벤트는 다음 단계를 수행 합니다.  
  
1.  사용 하 여 메시지 필터는 <xref:System.Windows.Forms.IMessageFilter> 인터페이스입니다.  
  
2.  호출 된 <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> 메서드.  
  
3.  변환 하 고 필요한 경우에 메시지를 디스패치합니다.  
  
4.  다른 컨트롤이 없는 메시지를 처리 하는 경우에 호스팅 컨트롤에 메시지를 전달 합니다.  
  
### <a name="ikeyboardinputsink-implementation"></a>IKeyboardInputSink 구현  
 서로게이트 메시지 루프 키보드 관리를 처리합니다. 따라서는 <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> 메서드는 유일한 <xref:System.Windows.Interop.IKeyboardInputSink> 멤버의 구현이 필요로 하는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스입니다.  
  
 기본적으로는 <xref:System.Windows.Interop.HwndHost> 반환 클래스 `false` 에 대 한 해당 <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> 구현 합니다. 이렇게에서 탭을 사용 하면 한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 구현의 <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> 메서드는 다음 단계를 수행 합니다.  
  
1.  찾은 첫 번째 또는 마지막 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 포함 된는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤이 포커스를 받을 수 있습니다. 컨트롤 선택 통과 정보에 따라 달라 집니다.  
  
2.  컨트롤에 포커스를 설정 하 고 반환 `true`합니다.  
  
3.  컨트롤이 포커스를 받을 수 있으면 반환 `false`합니다.  
  
### <a name="windowsformshost-registration"></a>WindowsFormsHost 등록  
 에 대 한 창 핸들을 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤을 만든는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 메시지 루프에 대 한 존재를 등록 하는 내부 정적 메서드를 호출 합니다.  
  
 등록 하는 동안는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 메시지 루프를 검사 합니다. 메시지 루프가 시작 되지 않은 경우는 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 이벤트 처리기가 만들어집니다. 메시지 루프 때 실행 되 고으로 간주 되는 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 이벤트 처리기가 연결 합니다.  
  
 창 핸들이 소멸 될 때는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 등록에서 자신을 제거 합니다.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>ElementHost 키보드 및 메시지 처리  
 호스팅되는 경우는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 키보드 및 메시지 처리는 다음으로 이루어집니다.  
  
-   <xref:System.Windows.Interop.HwndSource><xref:System.Windows.Interop.IKeyboardInputSink>, 및 <xref:System.Windows.Interop.IKeyboardInputSite> 인터페이스 구현.  
  
-   탭 이동 하 고 화살표 키입니다.  
  
-   명령 키 및 대화 상자 키를 제공 합니다.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]액셀러레이터 키를 처리 합니다.  
  
 다음 섹션에서는 이러한 부분에서 자세히 설명합니다.  
  
### <a name="interface-implementations"></a>인터페이스 구현  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], 키보드 메시지가 라우트되는 포커스가 있는 컨트롤의 창 핸들입니다. 에 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 이러한 메시지는 호스팅된 요소에 라우팅됩니다. 이를 위해는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 제공 된 <xref:System.Windows.Interop.HwndSource> 인스턴스. 경우는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에 포커스가 <xref:System.Windows.Interop.HwndSource> 인스턴스가 대부분의 키보드 입력에서 처리할 수 있도록 경로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> 클래스입니다.  
  
 <xref:System.Windows.Interop.HwndSource> 클래스가 구현 하는 <xref:System.Windows.Interop.IKeyboardInputSink> 및 <xref:System.Windows.Interop.IKeyboardInputSite> 인터페이스입니다.  
  
 구현에 따라 달라 키보드 상호 운용은 <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> 메서드 핸들 TAB 키와 화살표 키 호스트 된 요소에서 포커스를 이동 하는 입력 합니다.  
  
### <a name="tabbing-and-arrow-keys"></a>Tabbing 키와 화살표 키  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 선택 논리에 매핑되어는 <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> 및 <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> 키를 누른 후 화살표를 구현 하는 메서드를 탐색 합니다. 재정의 <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> 메서드가이 매핑을 수행 합니다.  
  
### <a name="command-keys-and-dialog-box-keys"></a>명령 키 및 대화 상자 키  
 부여할 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 명령 키 및 대화 상자 키를 처리 하는 첫 번째 기회 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 에 연결 된 명령 전처리는 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> 메서드. 재정의 <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> 두 기술은 연결 합니다.  
  
 와 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> 메서드를 호스트 된 요소 WM_KEYDOWN, WM_KEYUP, WM_SYSKEYDOWN, 탭, ENTER, ESC, 및 화살표 키 등의 명령 키를 포함 하 여 WM_SYSKEYUP 등 모든 주요 메시지를 처리할 수 있습니다. 키 메시지 처리 되지 않은 경우 보내는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 처리에 대 한 상위 계층입니다.  
  
### <a name="accelerator-processing"></a>액셀러레이터 키 처리  
 정상적으로 처리 액셀러레이터 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 액셀러레이터 처리에 연결 되어야 합니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> 클래스입니다. 또한 요소를 호스트에 모든 WM_CHAR 메시지를 올바르게 라우팅하려면 해야 합니다.  
  
 때문에 기본 <xref:System.Windows.Interop.HwndSource> 구현의 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> 메서드가 반환 되 `false`, WM_CHAR 메시지는 다음과 같은 논리를 사용 하 여 처리 됩니다.  
  
-   <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> 메서드는 모든 WM_CHAR 메시지는 호스트 된 요소에 전달 되도록 보장 합니다.  
  
-   메시지 ALT 키를 누를 경우 wm_syschar입니다. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]통해이 메시지를 전처리 하지 않고 않습니다는 <xref:System.Windows.Forms.Control.IsInputChar%2A> 메서드. 따라서는 <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> 메서드는 쿼리에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> 등록 된 액셀러레이터 키입니다. 등록된 된 액셀러레이터 키가 있으면 <xref:System.Windows.Input.AccessKeyManager> 처리 합니다.  
  
-   ALT 키를 누르지 하는 경우는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> 처리 되지 않은 입력을 처리 하는 클래스입니다. 입력이 액셀러레이터의 <xref:System.Windows.Input.AccessKeyManager> 처리 합니다. <xref:System.Windows.Input.InputManager.PostProcessInput> 처리 되지 않은 WM_CHAR 메시지에 대 한 이벤트를 처리 합니다.  
  
 사용자가 ALT 키를 누르면 가속기 시각 신호 전체 폼에 표시 됩니다. 이 동작을 지원 하기 위해 모든 <xref:System.Windows.Forms.Integration.ElementHost> 현재 폼에 컨트롤에 관계 없이 컨트롤에 포커스가 WM_SYSKEYDOWN 메시지를 수신 합니다.  
  
 메시지에만 보내집니다 <xref:System.Windows.Forms.Integration.ElementHost> 현재 폼에서 컨트롤입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
