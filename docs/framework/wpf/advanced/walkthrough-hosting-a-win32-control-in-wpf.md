---
title: "연습: WPF에서 Win32 컨트롤 호스팅 | Microsoft Docs"
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
  - "WPF에서 Win32 컨트롤 호스팅"
  - "Win32 코드, WPF 상호 운용"
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 연습: WPF에서 Win32 컨트롤 호스팅
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다.  그러나 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 코드에 상당한 노력을 기울인 경우 이 코드를 완전히 다시 작성하지 않고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 코드의 일부만이라도 다시 사용하는 것이 더 효율적일 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에서 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창을 호스팅하는 간단한 메커니즘을 제공합니다.  
  
 이 항목에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 목록 상자 컨트롤을 호스팅하는 응용 프로그램인 [Hosting a Win32 ListBox Control in WPF 샘플](http://go.microsoft.com/fwlink/?LinkID=159998)을 예로 들어 설명합니다.  이러한 일반 절차를 확장하여 원하는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창을 호스팅할 수 있습니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="requirements"></a>   
## 요구 사항  
 이 항목에서는 사용자가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그래밍의 기본 사항에 대해 잘 알고 있다고 가정합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그래밍에 대한 소개는 [시작](../../../../docs/framework/wpf/getting-started/index.md)을 참조하십시오.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그래밍에 대한 소개는 관련된 수많은 서적이 있지만, 특히 Charles Petzold의 *Programming Windows*가 도움이 될 것입니다.  
  
 이 항목과 함께 제공되는 샘플은 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]에서 구현되기 때문에 [!INCLUDE[TLA#tla_pinvoke](../../../../includes/tlasharptla-pinvoke-md.md)]를 사용하여 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]에 액세스합니다.  [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)]에 대해 알고 있으면 도움이 되겠지만 알지 못해도 상관없습니다.  
  
> [!NOTE]
>  이 항목에는 관련 샘플에 있는 많은 코드 예제가 포함되어 있지만  편의상 전체 샘플 코드는 제공하지 않습니다.  전체 코드는 [Hosting a Win32 ListBox Control in WPF 샘플](http://go.microsoft.com/fwlink/?LinkID=159998)에서 볼 수 있습니다.  
  
<a name="basic_procedure"></a>   
## 기본 절차  
 이 단원에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에 호스팅하기 위한 기본 절차를 개괄적으로 설명합니다.  나머지 단원에서는 각 단계를 자세히 안내합니다.  
  
 기본 호스팅 절차는 다음과 같습니다.  
  
1.  창을 호스팅할 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지를 구현합니다.  이를 위한 한 가지 방법은 <xref:System.Windows.Controls.Border> 요소를 만들어서 호스팅되는 창을 위한 페이지 부분을 확보하는 것입니다.  
  
2.  <xref:System.Windows.Interop.HwndHost>에서 상속하는 컨트롤을 호스팅할 클래스를 구현합니다.  
  
3.  이 클래스에서 <xref:System.Windows.Interop.HwndHost> 클래스 멤버 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>를 재정의합니다.  
  
4.  호스팅되는 창을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지가 포함된 창의 자식으로 만듭니다.  일반적인 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그래밍에서는 이를 명시적으로 사용할 필요가 없지만 호스팅 페이지는 핸들\(HWND\)이 있는 창입니다.  페이지 HWND는 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> 메서드의 `hwndParent` 매개 변수를 통해 수신됩니다.  따라서 호스팅되는 창을 이 HWND의 자식으로 만들어야 합니다.  
  
5.  호스트 창을 만든 뒤에는 호스팅되는 창의 HWND를 반환합니다.  하나 이상의 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨트롤을 호스팅하려면 일반적으로 호스트 창을 HWND의 자식으로 만들고 컨트롤을 해당 호스트 창의 자식으로 만듭니다.  컨트롤을 호스트 창에 래핑하면 간단하게 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지가 컨트롤에서 알림을 수신하도록 할 수 있습니다. 이 페이지는 HWND 경계를 넘어 전송되는 알림과 관련된 몇 가지 특정 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 문제를 처리합니다.  
  
6.  자식 컨트롤에서 전송되는 알림과 같은 호스트 창으로 전송된 선택된 메시지를 처리합니다.  이렇게 하는 데는 두 가지 방법이 있습니다.  
  
    -   호스팅 클래스에서 메시지를 처리하려는 경우에는 <xref:System.Windows.Interop.HwndHost> 클래스의 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 메서드를 재정의합니다.  
  
    -   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 메시지를 처리하도록 하려면 <xref:System.Windows.Interop.HwndHost> 클래스의 <xref:System.Windows.Interop.HwndHost.MessageHook> 이벤트를 코드 숨김에서 처리합니다.  호스팅된 창이 수신하는 모든 메시지에 대해 이 이벤트가 발생합니다.  이 옵션을 선택한 경우에도 <xref:System.Windows.Interop.HwndHost.WndProc%2A>를 재정의해야 하지만 최소한의 구현만 필요합니다.  
  
7.  <xref:System.Windows.Interop.HwndHost>의 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 및 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 메서드를 재정의합니다.  <xref:System.Windows.Interop.HwndHost> 계약을 충족하려면 이러한 메서드를 재정의해야 하지만 최소한의 구현만 제공하면 됩니다.  
  
8.  코드 숨김 파일에서 컨트롤 호스팅 클래스의 인스턴스를 만들고 이를 창을 호스팅할 <xref:System.Windows.Controls.Border> 요소의 자식으로 만듭니다.  
  
9. 호스팅된 창에 [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] 메시지를 보내고 컨트롤에서 보낸 알림과 같이 자식 창에서 전송된 메시지를 처리함으로써 호스팅된 창과 통신합니다.  
  
<a name="page_layout"></a>   
## 페이지 레이아웃 구현  
 ListBox 컨트롤을 호스팅하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지의 레이아웃은 두 영역으로 구성됩니다.  페이지의 왼쪽에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨트롤을 조작하는 데 사용할 수 있는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]를 제공하는 몇 개의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 호스팅합니다.  페이지의 오른쪽 위에서는 호스팅되는 ListBox 컨트롤을 위한 사각형 영역이 있습니다.  
  
 이 레이아웃을 구현하기 위한 코드는 꽤 간단합니다.  루트 요소는 두 개의 자식 요소가 있는 <xref:System.Windows.Controls.DockPanel>입니다.  첫 번째는 ListBox 컨트롤을 호스팅하는 <xref:System.Windows.Controls.Border> 요소입니다.  이는 페이지 오른쪽 위에 200x200 크기의 사각형으로 표시됩니다.  두 번째는 정보를 표시하며 노출된 상호 운영 속성을 설정하여 ListBox 컨트롤을 조작할 수 있도록 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 집합이 들어 있는 <xref:System.Windows.Controls.StackPanel> 요소입니다.  <xref:System.Windows.Controls.StackPanel>의 자식인 각 요소에 대해서는 이러한 요소에 대한 정의와 역할에 대해 자세히 설명하는 여러 요소에 대한 참고 자료를 참조하십시오. 이러한 요소는 아래 예제 코드에 나열되어 있지만 여기서는 설명하지 않습니다. 이러한 요소는 기본 상호 운영 모델에는 필요하지 않으며 샘플에는 대화형 작업을 추가하기 위해 사용되었습니다.  
  
 [!code-xml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## Microsoft Win32 컨트롤을 호스팅할 클래스 구현  
 이 샘플의 핵심은 실제로 컨트롤을 호스팅하는 클래스인 ControlHost.cs입니다.  이 클래스는 <xref:System.Windows.Interop.HwndHost>에서 상속합니다.  생성자는 ListBox 컨트롤을 호스팅하는 <xref:System.Windows.Controls.Border> 요소의 높이와 너비에 해당하는 height 및 width의 두 매개 변수를 사용합니다.  이들 값은 나중에 컨트롤 크기가 <xref:System.Windows.Controls.Border> 요소와 일치하는지 확인하는 데 사용됩니다.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 상수 집합도 있습니다.  이러한 상수는 대부분 Winuser.h에서 가져오며 이를 통해 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수를 호출할 때 일반적인 이름을 사용할 수 있습니다.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### BuildWindowCore를 재정의하여 Microsoft Win32 창 만들기  
 이 메서드를 재정의하여 페이지에서 호스팅되는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창을 만들고 창과 페이지를 연결합니다.  이 샘플은 ListBox 컨트롤 호스팅과 관련되므로 두 개의 창을 만듭니다.  첫 번째는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에서 실제로 호스팅되는 창입니다.  ListBox 컨트롤은 이 창의 자식으로 만들어집니다.  
  
 이러한 방법을 사용하는 이유는 컨트롤에서 알림을 받는 프로세스를 단순화하기 위해서입니다.  <xref:System.Windows.Interop.HwndHost> 클래스를 사용하여 호스팅된 창으로 전송된 메시지를 처리할 수 있습니다.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨트롤을 직접 호스팅하면 컨트롤의 내부 메시지 루프로 전송된 메시지가 수신됩니다.  컨트롤을 표시하고 컨트롤에 메시지를 전송할 수 있지만 컨트롤이 부모 창에 보내는 알림을 수신할 수는 없습니다.  즉, 사용자가 컨트롤과 상호 작용하는 시기를 감지할 방법이 없습니다.  대신 호스트 창을 만들고 컨트롤을 해당 창의 자식으로 만듭니다.  이렇게 하면 컨트롤이 보낸 알림을 포함하여 호스트 창에 대한 메시지를 처리할 수 있습니다.  호스트 창은 컨트롤에 대한 다소 간단한 래퍼이므로 편의상 패키지를 ListBox 컨트롤이라고 하겠습니다.  
  
<a name="create_the_window_and_listbox"></a>   
#### 호스트 창과 ListBox 컨트롤 만들기  
 [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)]를 사용하여 창 클래스를 만들고 등록하는 등의 작업을 통해 컨트롤에 대한 호스트 창을 만들 수 있습니다.  하지만 미리 정의된 "static" 창 클래스로 창을 만드는 방법이 훨씬 더 간단합니다.  이렇게 하면 컨트롤에서 알림을 수신하기 위해 필요한 창 프로시저를 사용할 수 있으며 작성해야 할 코드도 최소화됩니다.  
  
 컨트롤의 HWND는 읽기 전용 속성을 통해 노출되며 호스트 페이지는 이를 사용하여 컨트롤에 메시지를 보낼 수 있습니다.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 ListBox 컨트롤은 호스트 창의 자식으로 만들어집니다.  두 창의 높이와 너비는 위에서 설명한 생성자에 전달되는 값으로 설정됩니다.  이를 통해 호스트 창과 컨트롤의 크기가 페이지의 예약된 영역과 같아집니다.  창을 만든 뒤 샘플에서는 호스트 창의 HWND가 포함된 <xref:System.Runtime.InteropServices.HandleRef> 개체를 반환합니다.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### DestroyWindow 및 WndProc 구현  
 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> 이외에도 <xref:System.Windows.Interop.HwndHost>의 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 및 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 메서드도 재정의해야 합니다.  이 예제에서는 컨트롤에 대한 메시지가 <xref:System.Windows.Interop.HwndHost.MessageHook> 처리기에서 처리되므로 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 및 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>의 구현이 최소화됩니다.  <xref:System.Windows.Interop.HwndHost.WndProc%2A>의 경우에는 `handled`를 `false`로 설정하여 메시지가 처리되지 않았음을 나타내고 0을 반환합니다.  <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>의 경우에는 단순하게 창을 소멸합니다.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## 페이지에 컨트롤 호스팅  
 페이지에 컨트롤을 호스팅하려면 먼저 `ControlHost` 클래스의 새 인스턴스를 만듭니다.  컨트롤\(`ControlHostElement`\)이 포함된 테두리 요소의 높이와 너비를 `ControlHost` 생성자에 전달합니다.  이를 통해 ListBox의 크기가 올바르게 조정됩니다.  그런 다음 `ControlHost` 개체를 호스트 <xref:System.Windows.Controls.Border>의 <xref:System.Windows.Controls.Decorator.Child%2A> 속성에 할당하여 페이지에 컨트롤을 호스팅합니다.  
  
 샘플에서는 처리기를 `ControlHost`의 <xref:System.Windows.Interop.HwndHost.MessageHook> 이벤트에 연결하여 컨트롤에서 메시지를 수신합니다.  이 이벤트는 호스팅된 창으로 전송되는 모든 메시지에 대해 발생합니다.  이 경우의 메시지는 컨트롤에서 전송되는 알림을 포함하여 실제 ListBox 컨트롤을 래핑하는 창으로 전송되는 메시지입니다.  샘플에서는 SendMessage를 호출하여 컨트롤에서 정보를 가져오고 그 내용을 수정합니다.  페이지가 컨트롤과 통신하는 방법에 대해서는 다음 단원에서 자세히 설명합니다.  
  
> [!NOTE]
>  SendMessage에 대해 두 개의 [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] 선언이 있습니다.  하나는 `wParam` 매개 변수를 사용하여 문자열을 전달하고 다른 하나는 이 매개 변수를 사용하여 정수를 전달하기 때문에 두 개 모두 필요합니다.  데이터가 올바르게 마샬링되도록 하기 위해 각 시그니처마다 별도의 선언이 필요합니다.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## 컨트롤과 페이지 간의 통신 구현  
 컨트롤에 [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)] 메시지를 전송하여 컨트롤을 조작합니다.  컨트롤은 해당 호스트 창에 알림을 전송하여 사용자가 컨트롤과 상호 작용하는 시점을 알립니다.  [Hosting a Win32 ListBox Control in WPF 샘플](http://go.microsoft.com/fwlink/?LinkID=159998)에는 이 작업이 수행되는 방법에 대한 몇 가지 예제를 제공하는 UI가 들어 있습니다.  
  
-   목록의 끝에 항목을 추가합니다.  
  
-   선택한 항목을 목록에서 제거합니다.  
  
-   현재 선택된 항목의 텍스트를 표시합니다.  
  
-   목록의 항목 수를 표시합니다.  
  
 사용자는 일반적인 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램에서처럼 목록 상자의 항목을 클릭하여 선택할 수도 있습니다.  표시되는 데이터는 사용자가 항목을 선택하거나 추가하여 목록 상자의 상태를 변경할 때마다 업데이트됩니다.  
  
 항목을 추가하려면 목록 상자에 LB\_ADDSTRING 메시지를 전송합니다.  항목을 삭제하려면 LB\_GETCURSEL을 전송하여 현재 선택 항목의 인덱스를 가져온 다음 LB\_DELETESTRING을 전송하여 항목을 삭제합니다.  샘플에서는 LB\_GETCOUNT도 전송한 다음 반환된 값을 사용하여 표시되는 항목 수를 업데이트합니다.  SendMessage의 이 두 인스턴스 모두 이전 단원에서 설명한 [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] 선언 중 하나를 사용합니다.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 사용자가 항목을 선택하고 선택 사항을 변경하면 컨트롤은 WM\_COMMAND 메시지를 전송하여 호스트 창에 알립니다. 이 때 페이지에 대한 <xref:System.Windows.Interop.HwndHost.MessageHook> 이벤트가 발생합니다.  처리기는 호스트 창의 기본 창 프로시저와 같은 정보를 수신합니다.  또한 부울 값 `handled`에 대한 참조도 전달합니다.  `handled`를 `true`로 설정하여 메시지를 처리했으며 추가 처리가 필요하지 않음을 지정합니다.  
  
 WM\_COMMAND는 여러 이유로 인해 전송되므로 알림 ID를 확인하여 처리할 이벤트인지 확인해야 합니다.  ID는 `wParam` 매개 변수의 상위 워드에 들어 있습니다.  [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]에는 HIWORD 매크로가 없기 때문에 샘플에서는 비트 연산자를 사용하여 ID를 추출합니다.  사용자가 선택하거나 선택을 변경하면 ID는 LBN\_SELCHANGE가 됩니다.  
  
 LBN\_SELCHANGE가 수신되면 샘플은 컨트롤에 LB\_GETCURSEL 메시지를 전송하여 선택된 항목의 인덱스를 가져옵니다.  텍스트를 가져오려면 먼저 <xref:System.Text.StringBuilder>를 만듭니다.  그런 다음 컨트롤에 LB\_GETTEXT 메시지를 전송합니다.  빈 <xref:System.Text.StringBuilder> 개체를 `wParam` 매개 변수로 전달합니다.  SendMessage가 반환될 때 <xref:System.Text.StringBuilder>에는 선택된 항목의 텍스트가 포함됩니다.  SendMessage를 이와 같이 사용하려면 추가 [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] 선언이 필요합니다.  
  
 마지막으로, `handled`를 `true`로 설정하여 메시지가 처리되었음을 지정합니다.  
  
## 참고 항목  
 <xref:System.Windows.Interop.HwndHost>   
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)