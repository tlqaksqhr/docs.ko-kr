---
title: "Win32와 WPF 간에 메시지 루프 공유 | Microsoft Docs"
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
  - "상호 운용성[WPF], Win32"
  - "메시지 루프[WPF]"
  - "메시지 루프 공유"
  - "Win32 코드, 메시지 루프 공유"
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Win32와 WPF 간에 메시지 루프 공유
이 항목에서는 <xref:System.Windows.Threading.Dispatcher>에서 노출하는 기존 메시지 루프를 사용하거나 상호 작용 코드의 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 쪽에서 별도의 메시지 루프를 생성하여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]와의 상호 작용을 위한 메시지 루프를 구현하는 방법에 대해 설명합니다.  
  
## ComponentDispatcher와 메시지 루프  
 상호 운용과 키보드 이벤트 지원을 위한 일반적인 시나리오는 <xref:System.Windows.Interop.IKeyboardInputSink>를 구현하거나 <xref:System.Windows.Interop.HwndSource> 또는 <xref:System.Windows.Interop.HwndHost>처럼 이미 <xref:System.Windows.Interop.IKeyboardInputSink>가 구현되어 있는 클래스에서 서브클래싱하는 것입니다.  하지만 키보드 싱크를 지원한다고 해서 상호 운용 경계를 통해 메시지를 보내고 받을 때 발생할 수 있는 모든 가능한 메시지 루프 요구 사항이 해결되는 것은 아닙니다.  응용 프로그램 메시지 루프 아키텍처를 쉽게 형식화할 수 있도록 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 메시지 루프가 따라야 하는 간단한 프로토콜을 정의하는 <xref:System.Windows.Interop.ComponentDispatcher> 클래스를 제공합니다.  
  
 <xref:System.Windows.Interop.ComponentDispatcher>는 다양한 멤버를 노출하는 정적 클래스입니다.  각 메서드의 범위는 암시적으로 호출 스레드에 연결됩니다.  다음 단원에서 설명하는 중요한 시점에서는 메시지 루프가 이러한 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 중 일부를 호출해야 합니다.  
  
 <xref:System.Windows.Interop.ComponentDispatcher>는 키보드 싱크와 같은 다른 구성 요소에서 수신할 수 있는 이벤트를 제공합니다.  <xref:System.Windows.Threading.Dispatcher> 클래스는 적절한 순서로 적절한 <xref:System.Windows.Interop.ComponentDispatcher> 메서드를 호출합니다.  고유한 메시지 루프를 구현하는 경우에는 코드에서 유사한 방식으로 <xref:System.Windows.Interop.ComponentDispatcher> 메서드를 호출해야 합니다.  
  
 스레드에서 <xref:System.Windows.Interop.ComponentDispatcher> 메서드를 호출하면 해당 스레드에서 등록한 이벤트 처리기만 호출됩니다.  
  
## 메시지 루프 작성  
 다음은 고유한 메시지 루프를 작성할 경우 사용하게 되는 <xref:System.Windows.Interop.ComponentDispatcher> 멤버의 검사 목록입니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: 스레드가 모달임을 나타내려면 메시지 루프에서 이 메서드를 호출해야 합니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: 스레드가 모달이 아닌 스레드로 되돌려졌음을 나타내려면 메시지 루프에서 이 메서드를 호출해야 합니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: <xref:System.Windows.Interop.ComponentDispatcher>가 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> 이벤트를 발생시켜야 한다는 것을 나타내려면 메시지 루프에서 이 메서드를 호출해야 합니다.  <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>이 `true`인 경우 <xref:System.Windows.Interop.ComponentDispatcher>는 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> 이벤트를 발생시키지 않지만 <xref:System.Windows.Interop.ComponentDispatcher>가 모달 상태인 동안 <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> 이벤트에 응답할 수 없는 경우에도 메시지 루프에서 해당 이벤트를 선택적으로 호출할 수 있습니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: 새 메시지를 사용할 수 있음을 나타내려면 메시지 루프에서 이 메서드를 호출해야 합니다.  반환 값은 <xref:System.Windows.Interop.ComponentDispatcher> 이벤트 수신기가 메시지를 처리했는지 여부를 나타냅니다.  <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>에서 `true`\(처리됨\)를 반환하는 경우 디스패처는 더 이상 메시지를 처리하지 않습니다.  반환 값이 `false`이면 디스패처는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수인 `TranslateMessage`를 호출한 다음 `DispatchMessage`를 호출해야 합니다.  
  
## ComponentDispatcher 및 기존 메시지 처리 사용  
 다음은 고유한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메시지 루프에 의존하는 경우 사용하게 되는 <xref:System.Windows.Interop.ComponentDispatcher> 멤버의 검사 목록입니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: 응용 프로그램이 모달 상태가 되었는지 여부\(예: 모달 메시지 루프가 푸시되었는지 여부\)를 반환합니다.  <xref:System.Windows.Interop.ComponentDispatcher> 클래스는 메시지 루프의 <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> 및 <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> 호출 횟수를 유지하기 때문에 이 상태를 추적할 수 있습니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> 및 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 이벤트는 대리자 호출에 대한 표준 규칙을 따릅니다.  대리자는 임의의 순서로 호출되며 첫 번째 대리자가 메시지를 처리된 것으로 표시하는 경우에도 모든 대리자가 호출됩니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: 유휴 상태를 처리할 수 있는 적당하고 효율적인 시간\(스레드에 다른 보류 중인 메시지가 없는 시간\)을 나타냅니다.  스레드가 모달인 경우 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>이 발생하지 않습니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: 메시지 펌프를 처리하는 모든 메시지에서 발생합니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> 중에 처리되지 않은 모든 메시지에서 발생합니다.  
  
 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> 이벤트나 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 이벤트가 발생한 후 이벤트 데이터에서 참조로 전달되는 `handled` 매개 변수가 `true`이면 메시지가 처리된 것으로 간주됩니다.  `handled`가 `true`이면 다른 처리기에서 메시지를 먼저 처리했다는 의미이므로 이벤트 처리기가 메시지를 무시해야 합니다.  두 이벤트에 대한 이벤트 처리기는 메시지를 수정합니다.  디스패처는 변경되지 않은 원래 메시지가 아니라 수정된 메시지를 디스패치해야 합니다.  <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>가 모든 수신기로 전달되지만 아키텍처상의 용도는 메시지의 대상인 HWND를 포함하는 최상위 창에서만 메시지에 대한 응답으로 코드를 호출하는 것입니다.  
  
## HwndSource에서 ComponentDispatcher 이벤트를 처리하는 방법  
 <xref:System.Windows.Interop.HwndSource>가 최상위 창인 경우\(부모 HWND가 없는 경우\) <xref:System.Windows.Interop.ComponentDispatcher>에 등록됩니다.  <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>가 발생하고 메시지가 <xref:System.Windows.Interop.HwndSource> 또는 자식 창에서 사용되는 경우 <xref:System.Windows.Interop.HwndSource>는 해당 <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> 키보드 싱크 시퀀스를 호출합니다.  
  
 <xref:System.Windows.Interop.HwndSource>가 최상위 창이 아닌 경우\(부모 HWND가 있는 경우\) 처리가 수행되지 않습니다.  최상위 창만 처리를 수행해야 하며 상호 운용 시나리오의 일부로 키보드 싱크를 지원하는 최상위 창이 있어야 합니다.  
  
 <xref:System.Windows.Interop.HwndSource>의 <xref:System.Windows.Interop.HwndHost.WndProc%2A>가 먼저 호출되는 적절한 키보드 싱크 메서드 없이 호출되면 응용 프로그램은 <xref:System.Windows.UIElement.KeyDown>과 같은 더 높은 수준의 키보드 이벤트를 받게 됩니다.  하지만 어떠한 키보드 싱크 메서드도 호출되지 않으므로 선택키 지원과 같은 원하는 키보드 입력 모델을 사용할 수 없게 됩니다.  메시지 루프가 <xref:System.Windows.Interop.ComponentDispatcher>에서 관련 스레드를 올바르게 통지하지 않거나 부모 HWND가 적절한 키보드 싱크 응답을 호출하지 않은 경우 이러한 현상이 발생할 수 있습니다.  
  
 <xref:System.Windows.Interop.HwndSource.AddHook%2A> 메서드를 사용하여 키보드 싱크로 전달되는 메시지에 대한 후크를 추가한 경우 해당 메시지가 HWND로 전송되지 않을 수 있습니다.  이 메시지가 메시지 펌프 수준에서 처리되고 `DispatchMessage` 함수로 제출되지 않을 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Interop.ComponentDispatcher>   
 <xref:System.Windows.Interop.IKeyboardInputSink>   
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [스레딩 모델](../../../../docs/framework/wpf/advanced/threading-model.md)   
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)