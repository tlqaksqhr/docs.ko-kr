---
title: "Win32와 WPF 간에 메시지 루프 공유"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3122100f93d15c04c109564e1abd2dc13f37990
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Win32와 WPF 간에 메시지 루프 공유
와 상호 운용성에 대 한 메시지 루프를 구현 하는 방법에 설명 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], 기존 사용 하 여 메시지에 대 한 루프 노출을 <xref:System.Windows.Threading.Dispatcher> 또는 별도 메시지 루프에 만들어는 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 쪽 상호 작용 코드의 합니다.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher 및 메시지 루프  
 구현 하는 것의 상호 운용 및 키보드 이벤트 지원에 대 한 일반적인 시나리오는 <xref:System.Windows.Interop.IKeyboardInputSink>, 또는 이미 구현 하는 클래스에서 서브클래싱하 <xref:System.Windows.Interop.IKeyboardInputSink>와 같은 <xref:System.Windows.Interop.HwndSource> 또는 <xref:System.Windows.Interop.HwndHost>합니다. 그러나 키보드 싱크를 지 원하는 모든 가능한 메시지 루프의 요구에 상호 운용 경계 간에 메시지를 주고받을 때 할 수 있습니다를 다루지 않습니다. 쉽게 응용 프로그램 메시지 루프 아키텍처를 형식화할 수 있도록 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 제공는 <xref:System.Windows.Interop.ComponentDispatcher> 를 수행 하는 메시지 루프에 대 한 간단한 프로토콜을 정의 하는 클래스입니다.  
  
 <xref:System.Windows.Interop.ComponentDispatcher>여러 멤버를 노출 하는 정적 클래스가입니다. 각 메서드의 범위 암시적으로 호출 스레드에 연결 됩니다. 그 중 일부는 메시지 루프를 호출 해야 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] (다음 섹션에 정의 된)으로 중요 한 시간에 있습니다.  
  
 <xref:System.Windows.Interop.ComponentDispatcher>다른 구성 요소 (예: 키보드 싱크)에 수신할 수 있는 이벤트를 제공 합니다. <xref:System.Windows.Threading.Dispatcher> 적절 한 클래스 <xref:System.Windows.Interop.ComponentDispatcher> 메서드는 적절 한 순서로 합니다. 고유한 메시지 루프를 구현 하는 경우 코드에서 호출 담당 <xref:System.Windows.Interop.ComponentDispatcher> 비슷한 방식으로 메서드.  
  
 호출 <xref:System.Windows.Interop.ComponentDispatcher> 스레드에 대 한 메서드는 해당 스레드에서 등록 된 이벤트 처리기만 호출 됩니다.  
  
## <a name="writing-message-loops"></a>메시지 루프 작성  
 다음은의 검사 목록 <xref:System.Windows.Interop.ComponentDispatcher> 멤버 고유한 메시지 루프를 작성 하는 경우 사용 합니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: 메시지 루프 스레드가 모달 임을 나타내기 위해이 메서드를 호출 해야 합니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: 메시지 루프 스레드가 모달이으로 되돌려 졌음을 나타내기 위해이 메서드를 호출 해야 합니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: 메시지 루프를 호출 해야 함을 나타내려면이 <xref:System.Windows.Interop.ComponentDispatcher> 발생 시켜야는 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> 이벤트입니다. <xref:System.Windows.Interop.ComponentDispatcher>발생 하지 것입니다 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> 경우 <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> 은 `true`, 메시지 루프를 호출 하도록 선택할 수 있지만 <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> 경우에 <xref:System.Windows.Interop.ComponentDispatcher> 모달 상태에서 작업 하는 동안에 응답할 수 없습니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: 메시지 루프 새 메시지를 사용할 수 있음을 나타내기 위해이 메서드를 호출 해야 합니다. 반환 값은 나타냅니다 여부 수신기를는 <xref:System.Windows.Interop.ComponentDispatcher> 이벤트에서 메시지를 처리 합니다. 경우 <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> 반환 `true` (처리) 발송자 아무 작업도 하지 않도록 추가 메시지를 사용 합니다. 반환 값이 `false`, 디스패처는 호출 하는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수 `TranslateMessage`, 호출 `DispatchMessage`합니다.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>ComponentDispatcher를 사용 하 고 기존 메시지 처리  
 다음은의 검사 목록 <xref:System.Windows.Interop.ComponentDispatcher> 멤버 고유에 의존 하는 경우 사용할 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메시지 루프입니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: 응용 프로그램이 모달 상태가 있는지 여부를 반환 합니다 (예: 모달 메시지 루프가 밀어넣은). <xref:System.Windows.Interop.ComponentDispatcher>클래스의 수를 유지 하기 때문에이 상태를 추적할 수 <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> 및 <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> 메시지 루프에서 호출 합니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>및 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 이벤트 대리자 호출에 대 한 표준 규칙을 따릅니다. 대리자는 지정 되지 않은 순서로 호출 됩니다. 및 처리 된 것으로 첫 번째 메시지를 표시 하는 경우에 모든 대리자가 호출 됩니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: 유휴 상태를 처리 하는 적절 하 고 효율적인 시간을 나타냅니다 (스레드에 대 한 다른 보류 중인 메시지는 있음). <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>스레드가 모달이면 하지 발생 합니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: 메시지 펌프를 처리 하는 모든 메시지에서 발생 합니다.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: 발생 하는 동안 처리 되지 않은 모든 메시지에 대해 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>합니다.  
  
 메시지로 간주 됩니다 후 처리 된 경우에는 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> 이벤트 또는 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 이벤트는 `handled` 이벤트 데이터에 대 한 참조로 전달 되는 매개 변수는 `true`합니다. 이벤트 처리기는 메시지를 무시 해야 `handled` 은 `true`이므로 즉, 다른 처리기 먼저 메시지를 처리 합니다. 두 이벤트를 이벤트 처리기는 메시지를 수정할 수 있습니다. 수정된 된 메시지를 원래 변경 되지 않은 메시지가 아니라 발송자 발송 해야 합니다. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>모든 수신기 하지만 아키텍처 상의 용도에 전달 되는 대상 메시지는 메시지에 대 한 응답에서 코드를 호출 해야 하는 HWND를 포함 하는 최상위 창을 합니다.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>HwndSource는 ComponentDispatcher 이벤트를 처리 하는 방법  
 경우는 <xref:System.Windows.Interop.HwndSource> 최상위 창 (부모 HWND가 없는), 등록 됩니다 <xref:System.Windows.Interop.ComponentDispatcher>합니다. 경우 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 발생 메시지에 사용 되 고는 <xref:System.Windows.Interop.HwndSource> 또는 자식 창 <xref:System.Windows.Interop.HwndSource> 호출 해당 <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> 키보드 싱크 시퀀스입니다.  
  
 경우는 <xref:System.Windows.Interop.HwndSource> 최상위 창이 아닙니다 (부모 HWND에), 처리 하지 됩니다. 최상위 창이는 처리 작업을 수행할 필요 하며 키보드 싱크를 지 원하는 최상위 창이 운용 시나리오의 일부로 되도록 합니다.  
  
 경우 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 에 <xref:System.Windows.Interop.HwndSource> 라고 먼저 호출 되는 적절 한 키보드 싱크 메서드에 없이 응용 프로그램 받습니다 더 높은 수준의 키보드 이벤트와 같은 <xref:System.Windows.UIElement.KeyDown>합니다. 그러나 키보드 싱크 메서드가 없는 이름은, 액세스 키 지원 등의 원하는 키보드 입력된 모델 기능 메서드도입니다. 메시지 루프 알리지 못했습니다. 제대로 관련 스레드에 때문에 이러한 현상이 발생할 수 있습니다는 <xref:System.Windows.Interop.ComponentDispatcher>, 없거나 부모 HWND 적절 한 키보드 싱크 응답 호출이 호출 하지 못했습니다.  
  
 사용 하 여 해당 메시지에 대 한 후크를 추가한 경우 키보드 싱크로 이동 하는 메시지 HWND에 전송 되지 수는 <xref:System.Windows.Interop.HwndSource.AddHook%2A> 메서드. 메시지 제출 되지에 메시지 펌프 수준에서 처리 될 수 있습니다는 `DispatchMessage` 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Interop.ComponentDispatcher>  
 <xref:System.Windows.Interop.IKeyboardInputSink>  
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [스레딩 모델](../../../../docs/framework/wpf/advanced/threading-model.md)  
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)
