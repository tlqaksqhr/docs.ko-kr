---
title: "Windows Forms 및 WPF 상호 운용성 입력 아키텍처 | Microsoft Docs"
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
  - "ElementHost 키보드 및 메시지"
  - "입력 아키텍처[WPF 상호 운용성]"
  - "상호 운용성[WPF], Windows Forms"
  - "키보드 상호 운용[WPF]"
  - "메시지[WPF]"
  - "모덜리스 대화 상자[WPF]"
  - "모덜리스 폼"
  - "Windows Forms[WPF], 상호 운용성"
  - "Windows Forms, WPF 상호 운용"
  - "WindowsFormsHost 키보드 및 메시지"
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Windows Forms 및 WPF 상호 운용성 입력 아키텍처
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 간의 상호 운용성을 위해서는 두 기술 모두에서 키보드 입력을 적절하게 처리해야 합니다.  이 항목에서는 이러한 기술에서 키보드 및 메시지 처리를 구현하여 혼합 응용 프로그램에서 원활하게 상호 운용할 수 있도록 하는 방법을 설명합니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
-   모덜리스 폼 및 대화 상자  
  
-   WindowsFormsHost 키보드 및 메시지 처리  
  
-   ElementHost 키보드 및 메시지 처리  
  
## 모덜리스 폼 및 대화 상자  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기반 응용 프로그램에서 모덜리스 폼 또는 대화 상자를 열려면 <xref:System.Windows.Forms.Integration.WindowsFormsHost>의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> 메서드를 호출합니다.  
  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 기반 응용 프로그램에서 모덜리스 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지를 열려면 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> 메서드를 호출합니다.  
  
## WindowsFormsHost 키보드 및 메시지 처리  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기반 응용 프로그램에서 호스팅할 경우 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 키보드 및 메시지 처리는 다음으로 이루어집니다.  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스는 <xref:System.Windows.Interop.ComponentDispatcher> 클래스에서 구현하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메시지 루프에서 메시지를 가져옵니다.  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스는 일반적인 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 키보드 처리가 발생할 수 있도록 서로게이트 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 메시지 루프를 만듭니다.  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스는 <xref:System.Windows.Interop.IKeyboardInputSink> 인터페이스를 구현하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 포커스 관리를 조정합니다.  
  
-   <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은 자신을 등록하고 해당 메시지 루프를 시작합니다.  
  
 다음 단원에서는 이러한 프로세스 부분에 대해 자세히 설명합니다.  
  
### WPF 메시지 루프에서 메시지 가져오기  
 <xref:System.Windows.Interop.ComponentDispatcher> 클래스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 메시지 루프 관리자를 구현합니다.  <xref:System.Windows.Interop.ComponentDispatcher> 클래스는 외부 클라이언트가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 메시지를 처리하기 전에 메시지를 필터링할 수 있도록 후크를 제공합니다.  
  
 상호 운용성 구현에서는 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName> 이벤트를 처리하여 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤보다 먼저 메시지를 처리할 수 있게 합니다.  
  
### 서로게이트 Windows Forms 메시지 루프  
 기본적으로 <xref:System.Windows.Forms.Application?displayProperty=fullName> 클래스에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램에 대한 기본 메시지 루프가 포함됩니다.  상호 운용될 때 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 메시지 루프에서는 메시지를 처리하지 않습니다.  따라서 이 논리를 재현해야 합니다.  <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName> 이벤트의 처리기는 다음과 같은 단계를 수행합니다.  
  
1.  <xref:System.Windows.Forms.IMessageFilter> 인터페이스를 사용하여 메시지를 필터링합니다.  
  
2.  <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=fullName> 메서드를 호출합니다.  
  
3.  필요한 경우 메시지를 변환하고 디스패치합니다.  
  
4.  다른 컨트롤에서 메시지를 처리하지 않는 경우 메시지를 호스팅 컨트롤에 전달합니다.  
  
### IKeyboardInputSink 구현  
 서로게이트 메시지 루트에서 키보드 관리를 처리합니다.  따라서 <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=fullName> 메서드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스에서 구현해야 하는 유일한 <xref:System.Windows.Interop.IKeyboardInputSink> 멤버입니다.  
  
 기본적으로 <xref:System.Windows.Interop.HwndHost> 클래스는 <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> 구현에 대해 `false`를 반환합니다.  따라서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤로 이동할 수 없습니다.  
  
 <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=fullName> 메서드의 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 구현에서는 다음 단계를 수행합니다.  
  
1.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에 포함되어 있고 포커스를 수신할 수 있는 첫 번째 또는 마지막 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 찾습니다.  통과 정보에 따라 컨트롤 선택이 달라집니다.  
  
2.  포커스를 컨트롤로 설정하고 `true`를 반환합니다.  
  
3.  컨트롤에서 포커스를 수신할 수 없으면 `false`를 반환합니다.  
  
### WindowsFormsHost 등록  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤의 창 핸들이 만들어지면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에서는 메시지 루프에 자신을 등록하는 internal static 메서드를 호출합니다.  
  
 등록하는 동안 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은 메시지 루프를 검사합니다.  메시지 루프가 시작되지 않은 경우 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName> 이벤트 처리기가 만들어집니다.  <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName> 이벤트 처리기가 연결되어 있으면 메시지 루프가 실행되고 있는 것으로 간주됩니다.  
  
 창 핸들이 삭제되면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은 등록에서 자신을 제거합니다.  
  
## ElementHost 키보드 및 메시지 처리  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 기반 응용 프로그램에서 호스팅할 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 키보드 및 메시지 처리는 다음으로 이루어집니다.  
  
-   <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink> 및 <xref:System.Windows.Interop.IKeyboardInputSite> 인터페이스 구현  
  
-   탭 이동 및 화살표 키  
  
-   명령 키 및 대화 상자 키  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 액셀레이터 키 처리  
  
 다음 단원에서는 이러한 부분에 대해 자세히 설명합니다.  
  
### 인터페이스 구현  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에서 키보드 메시지는 포커스가 있는 컨트를의 창 핸들로 라우트됩니다.  <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 이러한 메시지는 호스팅된 요소로 라우트됩니다.  이를 위해 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서는 <xref:System.Windows.Interop.HwndSource> 인스턴스를 제공합니다.  <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에 포커스가 있는 경우 <xref:System.Windows.Interop.HwndSource> 인스턴스는 대부분의 키보드 입력을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> 클래스에서 처리할 수 있도록 라우트합니다.  
  
 <xref:System.Windows.Interop.HwndSource> 클래스는 <xref:System.Windows.Interop.IKeyboardInputSink> 및 <xref:System.Windows.Interop.IKeyboardInputSite> 인터페이스를 구현합니다.  
  
 키보드 상호 운용에서는 <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> 메서드를 구현하여 호스트된 요소 밖으로 포커스를 이동하는 Tab 키 및 화살표 키 입력을 처리합니다.  
  
### 탭 이동 및 화살표 키  
 Tab 및 화살표 키 탐색을 구현하기 위해 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 선택 논리가 <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> 및 <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> 메서드에 매핑됩니다.  <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> 메서드를 재정의하여 이러한 매핑을 수행할 수 있습니다.  
  
### 명령 키 및 대화 상자 키  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 맨 처음에 명령 키 및 대화 상자 키를 처리할 수 있게 하려면 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 명령 전처리를 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> 메서드에 연결합니다.  <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=fullName> 메서드를 재정의하면 두 기술이 연결됩니다.  
  
 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> 메서드를 사용하면 호스트된 요소에서 Tab, Enter, Esc와 같은 명령 키와 화살표 키를 포함하여 WM\_KEYDOWN, WM\_KEYUP, WM\_SYSKEYDOWN, WM\_SYSKEYUP 등의 키 메시지를 처리할 수 있습니다.  키 메시지가 처리되지 않으면 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 상위 계층 구조로 보내 처리하게 합니다.  
  
### 액셀레이터 키 처리  
 액셀러레이터 키를 올바로 처리하려면 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 액셀러레이터 처리가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> 클래스에 연결되어 있어야 합니다.  또한 모든 WM\_CHAR 메시지가 호스트된 요소로 올바로 라우트되어야 합니다.  
  
 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> 메서드의 기본 <xref:System.Windows.Interop.HwndSource> 구현에서는 `false`를 반환하므로 WM\_CHAR 메시지는 다음 논리를 사용하여 처리됩니다.  
  
-   모든 WM\_CHAR 메시지가 호스트된 요소에 전달되도록 <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=fullName> 메서드를 재정의합니다.  
  
-   Alt 키를 누르면 메시지는 WM\_SYSCHAR이 됩니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에서는 이 메시지를 <xref:System.Windows.Forms.Control.IsInputChar%2A> 메서드를 통해 처리하지 않습니다.  따라서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager>를 쿼리하여 등록된 액셀러레이터 키가 있는지 확인하도록 <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> 메서드를 재정의합니다.  등록된 액셀레이터 키가 있으면 <xref:System.Windows.Input.AccessKeyManager>에서 이 키를 처리합니다.  
  
-   Alt 키를 누르지 않으면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> 클래스에서 처리되지 않은 입력을 처리합니다.  입력이 액셀레이터 키인 경우 <xref:System.Windows.Input.AccessKeyManager>에서 처리합니다.  처리되지 않은 WM\_CHAR 메시지의 경우 <xref:System.Windows.Input.InputManager.PostProcessInput> 이벤트가 처리됩니다.  
  
 사용자가 Alt 키를 누르면 전체 폼에 액셀레이터 키의 시각적 힌트가 표시됩니다.  이 동작을 지원하기 위해 어떤 컨트롤에 포커스가 있는지에 관계없이 활성 폼의 모든 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 WM\_SYSKEYDOWN 메시지를 수신합니다.  
  
 메시지는 활성 폼의 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤로만 전송됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>   
 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>   
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)