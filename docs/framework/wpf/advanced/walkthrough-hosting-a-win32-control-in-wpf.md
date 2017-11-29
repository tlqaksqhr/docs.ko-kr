---
title: "연습: WPF에서 Win32 컨트롤 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 566be72cf330f6da83987f5e693176552471f091
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>연습: WPF에서 Win32 컨트롤 호스팅
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다. 그러나에 있는 경우 상당한 투자 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 코드는 것이 보다 효율적으로 이라도 다시 사용을 코드의 일부 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 완전히 다시 작성 하지 않고 응용 프로그램입니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]호스팅을 위한 간단한 메커니즘을 제공는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지.  
  
 이 항목에서는 응용 프로그램을 통해 [WPF 샘플에서 Win32 ListBox 컨트롤 호스팅](http://go.microsoft.com/fwlink/?LinkID=159998), 해당 호스트는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 목록 상자 컨트롤입니다. 하나를 호스팅하는 것이 일반적인 절차를 확장할 수 있습니다 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창.  
  
  
<a name="requirements"></a>   
## <a name="requirements"></a>요구 사항  
 이 항목에서는 둘 다에 대 한 기본 지식이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그래밍 합니다. 대 한 기본적인 소개 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그래밍 참조 [시작](../../../../docs/framework/wpf/getting-started/index.md)합니다. 에 대 한 소개 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] , 프로그래밍 참조 해야는 주제에 수많은 책의 모든 특히 *Windows 프로그래밍* Charles Petzold 여 합니다.  
  
 이 항목과 함께 제공 되는 샘플에 구현 되기 때문에 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], 것 활용 [!INCLUDE[TLA#tla_pinvoke](../../../../includes/tlasharptla-pinvoke-md.md)] 액세스로는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]합니다. 지식이 [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] 반드시 필요 하지는 않지만 도움은 됩니다.  
  
> [!NOTE]
>  이 항목에는 관련 샘플의 많은 코드 예제가 포함되어 있습니다. 그러나 가독성을 위해 전체 샘플 코드를 포함하지는 않습니다. 전체 코드를 확인 하거나 가져올 수 있습니다 [WPF 샘플에서 Win32 ListBox 컨트롤 호스팅](http://go.microsoft.com/fwlink/?LinkID=159998)합니다.  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>기본 절차  
 이 섹션에서는 호스팅에 대 한 기본 절차를 설명는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지. 나머지 섹션에서는 각 단계를 자세히 설명합니다.  
  
 기본 호스팅 절차는 다음과 같습니다.  
  
1.  구현 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 창을 호스팅할 페이지입니다. 기술 중 하나를 만드는 것을 <xref:System.Windows.Controls.Border> 호스트 창에 대 한 페이지의 섹션을 예약 하는 요소입니다.  
  
2.  상속 되는 컨트롤을 호스트 하는 클래스를 구현 <xref:System.Windows.Interop.HwndHost>합니다.  
  
3.  해당 클래스에서 재정의 된 <xref:System.Windows.Interop.HwndHost> 클래스 멤버 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>합니다.  
  
4.  포함 된 창의의 자식으로 호스트 된 창을 만들기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지. 하지만 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그래밍 하도록 명시적으로 지정 하지 않아도 사용 하는 호스팅 페이지는 창 핸들 (HWND)을 포함 합니다. HWND 페이지 수신 통해는 `hwndParent` 의 매개 변수는 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> 메서드. 호스트된 창은 이 HWND의 자식으로 만들어야 합니다.  
  
5.  호스트 창을 만들었으면 호스트된 창의 HWND를 반환합니다. 하나 이상의 호스트 하려는 경우 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨트롤을 일반적으로 호스 창 HWND의 자식으로 만들고 컨트롤을 자식 해당 호스트 창으로 확인 합니다. 에 대 한 간단한 방법을 제공 하는 호스 창에 컨트롤을 배치 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 몇몇 특정을 처리 하는 컨트롤에서 알림을 받을 페이지 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] HWND 경계를 넘어 알림 문제입니다.  
  
6.  자식 컨트롤의 알림과 같이 호스트 창으로 전송되는 선택한 메시지를 처리합니다. 이렇게 하는 데는 두 가지 방법이 있습니다.  
  
    -   호스팅 클래스에 메시지를 처리 하는 것을 선호 하는 경우 재정의 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 의 메서드는 <xref:System.Windows.Interop.HwndHost> 클래스입니다.  
  
    -   가 선호 하는 경우는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메시지 처리, 처리는 <xref:System.Windows.Interop.HwndHost> 클래스 <xref:System.Windows.Interop.HwndHost.MessageHook> 코드 숨김에서 이벤트입니다. 이 이벤트는 호스트된 창에서 받은 모든 메시지에 대해 발생합니다. 이 옵션을 선택 하면 여전히를 재정의 해야 <xref:System.Windows.Interop.HwndHost.WndProc%2A>, 하지만 최소한의 구현만 필요 합니다.  
  
7.  재정의 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 및 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 방식의 <xref:System.Windows.Interop.HwndHost>합니다. 충족 하기 위해 이러한 메서드를 재정의 해야 합니다는 <xref:System.Windows.Interop.HwndHost> 계약 하지만 최소한의 구현을 제공 해야 할 수 있습니다.  
  
8.  코드 숨김 파일에서 컨트롤 호스팅 클래스의 인스턴스를 만들고의 자식으로 만듭니다는 <xref:System.Windows.Controls.Border> 창을 호스팅할 하려고 하는 요소입니다.  
  
9. 전송 하 여 호스팅된 창의 통신할 [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] 메시지와 해당 자식 창의 컨트롤이 보내는 알림 같은 메시지를 처리 합니다.  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>페이지 레이아웃 구현  
 에 대 한 레이아웃의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지 ListBox 컨트롤을 호스팅하는 두 개의 영역으로 구성 됩니다. 여러 페이지의 왼쪽 호스트 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제공 하는 컨트롤은 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 조작 하는 데 사용할 수 있는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 제어 합니다. 페이지의 오른쪽 위에는 호스트된 ListBox 컨트롤에 대한 사각형 영역이 있습니다.  
  
 이 레이아웃을 구현 하기 위한 코드는 매우 간단 합니다. 루트 요소는 한 <xref:System.Windows.Controls.DockPanel> 두 개의 자식 요소가 있는 합니다. 첫 번째는는 <xref:System.Windows.Controls.Border> ListBox 컨트롤을 호스트 하는 요소입니다. 이 요소는 페이지의 오른쪽 위에 있는 200x200 정사각형을 사용합니다. 두 번째는는 <xref:System.Windows.Controls.StackPanel> 집합이 포함 된 요소 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 정보를 표시 하 고 설정 하 여 ListBox 컨트롤을 조작할 수 있도록 하는 컨트롤 상호 운용 속성을 노출 합니다. 각 자식 요소에 대해는 <xref:System.Windows.Controls.StackPanel>, 이러한 요소 또는 수행 되는 작업에 대 한 자세한 내용은 사용 되는 다양 한 요소에 대 한 참조 자료를 참조, 아래 예제 코드에 나열 된 이러한 있지만 되지 것입니다 (기본 아래의 설명 상호 운용성이 필요 하지 않을 그 중 하나, 제공 되는 일부 대화형 작업 샘플을 추가할).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Microsoft Win32 컨트롤을 호스트하는 클래스 구현  
 이 샘플의 핵심은 ControlHost.cs 컨트롤을 실제로 호스트하는 클래스입니다. 상속 된 <xref:System.Windows.Interop.HwndHost>합니다. 두 개의 매개 변수, 높이 너비, 높이 너비에 해당 하는 생성자는 <xref:System.Windows.Controls.Border> ListBox 컨트롤을 호스트 하는 요소입니다. 이러한 값은 일치 하는 컨트롤 항목 크기 되도록 나중에 사용 된 <xref:System.Windows.Controls.Border> 요소입니다.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 또한 상수 집합도 있습니다. 이러한 상수는 주로에서 Winuser.h 가져오고를 호출할 때 일반적인 이름을 사용할 수 있도록 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수입니다.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>BuildWindowCore를 재정의하여 Microsoft Win32 창 만들기  
 만들려면이 메서드를 재정의 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창 페이지에 의해 호스트 될 고 창과 페이지 간의 연결을 확인 합니다. 이 샘플에서는 ListBox 컨트롤을 호스트하므로 두 개의 창을 만듭니다. 첫 번째는 실제로에서 호스팅하는 창 고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지. ListBox 컨트롤은 해당 창의 자식으로 만듭니다.  
  
 이 방법은 컨트롤에서 알림을 받는 프로세스를 간소화하기 위해서 사용합니다. <xref:System.Windows.Interop.HwndHost> 클래스를 사용 하는 호스트 하는 창에 전송 된 메시지를 처리할 수 있습니다. 호스팅하는 경우는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 직접 제어 하 고, 컨트롤의 내부 메시지 루프에 전송 된 메시지를 수신 합니다. 컨트롤을 표시하고 메시지를 전송할 수 있지만 컨트롤이 해당 부모 창으로 전송된다는 알림은 받지 않습니다. 즉, 사용자가 컨트롤과 상호 작용하는 경우를 검색할 방법이 없습니다. 대신 호스트 창을 만들고 컨트롤을 해당 창의 자식으로 설정합니다. 이렇게 하면 컨트롤에서 전송한 알림을 포함하여 호스트 창에 대한 메시지를 처리할 수 있습니다. 호스트 창은 컨트롤에 대한 간단한 래퍼에 불과하므로 편의상 패키지를 ListBox 컨트롤이라고 합니다.  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>호스트 창 및 ListBox 컨트롤 만들기  
 사용할 수 있습니다 [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] 만들고 창 클래스를 등록 하 여 컨트롤에 대 한 호스트 창을 만들 수 있습니다. 그러나 미리 정의된 "정적" 창 클래스를 사용하여 창을 만드는 방법이 훨씬 더 간단합니다. 이 방법은 컨트롤에서 알림을 받기 위해 필요한 창 프로시저를 제공하며 최소한의 코딩이 필요합니다.  
  
 컨트롤의 HWND는 읽기 전용 속성을 통해 노출되므로 호스트 페이지에서 컨트롤로 메시지를 전송하는 데 사용할 수 있습니다.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 ListBox 컨트롤은 호스트 창의 자식으로 만듭니다. 두 창의 너비와 높이는 위에서 설명한 대로 생성자에 전달된 값으로 설정됩니다. 이렇게 하면 호스트 창과 컨트롤의 크기가 페이지에서 예약된 영역과 동일해집니다.  Windows를 만든 후 샘플 반환는 <xref:System.Runtime.InteropServices.HandleRef> 호스트 창의 HWND가 포함 된 개체입니다.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>DestroyWindow 및 WndProc 구현  
 외에 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>를 재정의 해야는 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 및 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 의 메서드는 <xref:System.Windows.Interop.HwndHost>합니다. 이 예제에서 컨트롤에 대 한 메시지를 처리는 <xref:System.Windows.Interop.HwndHost.MessageHook> 처리기의 구현이 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 및 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 최소화 됩니다. 경우 <xref:System.Windows.Interop.HwndHost.WndProc%2A>설정, `handled` 를 `false` 하는 메시지가 처리 되지 않았음을 나타내는 하 고 0을 반환 합니다. 에 대 한 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, 단순히 창을 소멸 합니다.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>페이지에서 컨트롤 호스트  
 페이지에 컨트롤을 호스트 하려면 먼저 만들어야의 새 인스턴스는 `ControlHost` 클래스입니다. 높이 컨트롤을 포함 하는 테두리 요소의 너비 (`ControlHostElement`)에 `ControlHost` 생성자입니다. 이렇게 하면 ListBox 크기가 정확하게 조정됩니다. 할당 하 여 다음 페이지에서 컨트롤을 호스트할는 `ControlHost` 개체는 <xref:System.Windows.Controls.Decorator.Child%2A> 호스트의 속성 <xref:System.Windows.Controls.Border>합니다.  
  
 샘플 연결 하는 처리기는 <xref:System.Windows.Interop.HwndHost.MessageHook> 의 이벤트는 `ControlHost` 컨트롤에서 메시지를 받도록 합니다. 이 이벤트는 호스트된 창으로 전송된 모든 메시지에 대해 발생됩니다. 이 경우 컨트롤의 알림을 포함하여 실제 ListBox 컨트롤을 래핑하는 창에 전송된 메시지입니다. 샘플에서는 SendMessage를 호출하여 컨트롤에서 정보를 가져오고 해당 내용을 수정합니다. 페이지가 컨트롤과 통신하는 방법에 대한 자세한 내용은 다음 섹션에서 설명합니다.  
  
> [!NOTE]
>  두 개의 [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] SendMessage에 대 한 선언이 있습니다. 하나를 사용 하므로이 작업이 필요는 `wParam` 전달할 문자열 및 다른 매개 변수를 사용 하 여 정수를 전달 합니다. 데이터가 올바르게 마샬링되도록 하려면 각 시그니처에 대해 별도의 선언이 필요합니다.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>컨트롤과 페이지 간의 통신 구현  
 전송 하 여 컨트롤을 조작 [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)] 메시지입니다. 컨트롤은 사용자가 호스트 창에 알림을 보내 상호 작용할 때 알려 줍니다. [WPF 샘플에서 Win32 ListBox 컨트롤 호스팅](http://go.microsoft.com/fwlink/?LinkID=159998) 샘플이 과정의 몇 가지 예제를 제공 하는 UI에 포함 되어 있습니다.  
  
-   목록에 항목을 추가합니다.  
  
-   선택한 항목을 목록에서 삭제합니다.  
  
-   현재 선택한 항목의 텍스트를 표시합니다.  
  
-   목록의 항목 수를 표시합니다.  
  
 사용자도 선택할 수 있는 항목 목록 상자에서,를 클릭 하 여는 일반적인 경우와 마찬가지로 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램입니다. 표시된 데이터는 사용자가 항목을 선택 또는 추가하여 목록 상자의 상태를 변경할 때마다 업데이트됩니다.  
  
 항목을 추가하려면 목록 상자에 LB_ADDSTRING 메시지를 전송합니다. 항목을 삭제하려면 LB_GETCURSEL을 전송하여 현재 선택 영역의 인덱스를 가져온 다음 LB_DELETESTRING을 전송하여 항목을 삭제합니다. 샘플에서도 LB_GETCOUNT를 전송하고 반환된 값을 사용하여 항목 수를 표시하는 디스플레이를 업데이트합니다. SendMessage의 이러한 두 인스턴스 중 하나를 사용 합니다.는 [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] 선언 이전 섹션에서 설명 합니다.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 컨트롤을 WM_COMMAND 메시지를 전송 하 여 호스트 창에 알립니다. 사용자가 항목을 선택 하거나 선택 변경는 <xref:System.Windows.Interop.HwndHost.MessageHook> 페이지에 대 한 이벤트입니다. 처리기는 호스트 창의 주 창 프로시저와 같은 정보를 수신합니다. 부울 값에 대 한 참조도 전달 `handled`합니다. 설정한 `handled` 를 `true` 표시 되는 메시지를 이미 처리 한 처리가 더 이상 필요 합니다.  
  
 WM_COMMAND는 다양한 이유로 전송되므로 알림 ID를 검사하여 처리하려는 이벤트인지 여부를 확인해야 합니다. ID의 상위 단어에 포함 되어는 `wParam` 매개 변수입니다. 이후 [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 않습니다 HIWORD 매크로 샘플 비트 연산자를 사용 하 여 ID를 추출 하지 사용자가 선택을 수행하거나 선택을 변경한 경우 ID는 LBN_SELCHANGE가 됩니다.  
  
 LBN_SELCHANGE를 받으면 샘플은 컨트롤에 LB_GETCURSEL 메시지를 전송하여 선택한 항목의 인덱스를 가져옵니다. 텍스트를 가져오려면 먼저 만들어야는 <xref:System.Text.StringBuilder>합니다. 그런 다음 컨트롤에 LB_GETTEXT 메시지를 전송합니다. 빈 전달 <xref:System.Text.StringBuilder> 개체로 `wParam` 매개 변수입니다. SendMessage가 반환 하는 경우, <xref:System.Text.StringBuilder> 선택한 항목의 텍스트를 포함 됩니다. SendMessage의이 사용이 아직 필요 다른 [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] 선언 합니다.  
  
 마지막으로, 설정 `handled` 를 `true` 에서 메시지가 처리 되었음을 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Interop.HwndHost>  
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)
