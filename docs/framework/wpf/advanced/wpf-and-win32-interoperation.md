---
title: WPF 및 Win32 상호 운용성
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 8a0e27d46248bdfd782c2cf650faaf8f3bc29960
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="wpf-and-win32-interoperation"></a>WPF 및 Win32 상호 운용성
이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 코드를 상호 운용하는 방법을 개괄적으로 설명합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다. 그러나 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 코드에 상당한 투자를 한 경우 해당 코드 중 일부를 재사용하는 것이 더욱 효과적일 수 있습니다.  
  

  
<a name="basics"></a>   
## <a name="wpf-and-win32-interoperation-basics"></a>WPF 및 Win32 상호 운용성 기본 사항  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 코드 간에는 상호 운용성에 대한 두 가지 기본 기법이 있습니다.  
  
-   [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 호스팅합니다. 이 기법을 사용하면 표준 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창 및 응용 프로그램의 프레임워크 내에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 고급 그래픽 기능을 사용할 수 있습니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠에서 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창을 호스트합니다. 이 기법을 사용하면 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠의 컨텍스트에서 기존 사용자 지정 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨트롤을 사용하고 경계 간에 데이터를 전달할 수 있습니다.  
  
 이 항목에서는 이러한 각 기법을 개념적인 측면에서 소개합니다. [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 호스트하는 작업에 대한 자세한 코드 기반 설명은 [연습: Win32에서 WPF 콘텐츠 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)을 참조하세요. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]를 호스트하는 자세한 코드 중심 그림은 [연습: WPF에서 Win32 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)을 참조하세요.  
  
<a name="projects"></a>   
## <a name="wpf-interoperation-projects"></a>WPF 상호 운용 프로젝트  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]는 관리 코드이지만, 대부분의 기존 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그램은 관리되지 않는 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)]로 작성됩니다.  완전히 관리되지 않는 프로그램에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 호출할 수 없습니다. 그러나 `/clr` 옵션을 [!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)] 컴파일러와 함께 사용하면 혼합 관리-비관리 프로그램을 만들 수 있습니다. 이 프로그램에서는 관리 및 비관리 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 호출을 원활하게 혼합할 수 있습니다.  
  
 이 경우 프로젝트 수준에서 한 가지 문제가 발생하는데, 바로 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일을 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 프로젝트로 컴파일할 수 없다는 것입니다.  이 문제는 다음과 같은 몇 가지 프로젝트 분할 기법을 통해 해결할 수 있습니다.  
  
-   모두 포함 하는 C# DLL을 만드는 프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지도 컴파일된 어셈블리 한 후 프로그램 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 실행 파일을 포함 하는 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 참조로 합니다.  
  
-   만들 C#에 대 한 실행 파일의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 한 참조는 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 를 포함 하는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 콘텐츠입니다.  
  
-   사용 하 여 <xref:System.Windows.Markup.XamlReader.Load%2A> 로드할 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 컴파일하는 대신 런타임 시 프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.  
  
-   사용 하지 마십시오 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , 모든 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 요소 트리를 작성 하는 코드에서 <xref:System.Windows.Application>합니다.  
  
 가장 적합한 방법을 사용하세요.  
  
> [!NOTE]
>  전에 [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]를 사용한 적이 없는 경우 상호 운용 코드 예에 `gcnew` 및 `nullptr`과 같은 “새” 키워드가 표시됩니다. 이러한 키워드는 밑줄이 두 개인 이전 구문(`__gc`)을 대체하고 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)]의 관리 코드에 대해 좀 더 자연스러운 구문을 제공합니다.  [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] 관리 기능에 대해 자세히 알아보려면 [런타임 플랫폼의 구성 요소 확장](/cpp/windows/component-extensions-for-runtime-platforms) 및 [Hello, C++/CLI](http://go.microsoft.com/fwlink/?LinkId=98739)를 참조하세요.  
  
<a name="hwnds"></a>   
## <a name="how-wpf-uses-hwnds"></a>WPF에서 HWND를 사용하는 방법  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] "HWND interop"를 최대한 활용하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 HWND를 사용하는 방법을 이해해야 합니다. 어떠한 HWND의 경우에도 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링과 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 렌더링 또는 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] / [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)] 렌더링을 혼합할 수 없습니다. 여기에는 여러 가지 의미가 내포되어 있습니다. 기본적으로 이러한 렌더링 모델을 혼합하려면 상호 운용 솔루션을 만들고, 사용하도록 선택하는 각 렌더링 모델에 지정된 상호 운용 세그먼트를 사용해야 합니다. 또한, 렌더링 동작은 상호 운용 솔루션에서 수행할 수 있는 작업에 대한 “에어스페이스” 제한 사항도 만듭니다. “에어스페이스” 개념은 [기술 영역 개요](../../../../docs/framework/wpf/advanced/technology-regions-overview.md) 항목에 자세히 설명되어 있습니다.  
  
 화면의 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소는 궁극적으로 HWND를 통해 지원됩니다. 만들 때는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 최상위 HWND를 만들고 사용 하는 <xref:System.Windows.Interop.HwndSource> 배치 하는 <xref:System.Windows.Window> 및 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND 내부 콘텐츠입니다.  응용 프로그램의 나머지 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠에서 이 단일 HWND를 공유합니다. 예외는 메뉴, 콤보 상자 드롭다운 및 기타 팝업입니다. 이러한 요소는 고유한 최상위 창을 만듭니다. 따라서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메뉴가 포함된 창 HWND의 가장자리를 넘어 이동할 수 있습니다. 사용 하는 경우 <xref:System.Windows.Interop.HwndHost> 내 HWND를 넣을 수 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 알립니다 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 에 새 자식 HWND 상대 위치를 지정 하는 방법의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND입니다.  
  
 HWND와 관련된 개념은 각 HWND 내에서, 그리고 각 HWND 간에 투명합니다. 이 내용도 [기술 영역 개요](../../../../docs/framework/wpf/advanced/technology-regions-overview.md) 항목에서 설명되어 있습니다.  
  
<a name="hosting_a_wpf_page"></a>   
## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>Microsoft Win32 창에서 WPF 콘텐츠 호스팅  
 호스팅하는 데 핵심적인은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창이 <xref:System.Windows.Interop.HwndSource> 클래스입니다. 이 클래스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 자식 창으로 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 통합할 수 있도록 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 래핑합니다. 다음 접근 방식은 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 단일 응용 프로그램에 결합합니다.  
  
1.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠(콘텐츠 루트 요소)를 관리 클래스로 구현합니다. 여러 자식 요소를 포함할 수 및/또는 같은 루트 요소로 사용 하는 클래스 중 하나에서 클래스 상속 되는 일반적으로 <xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.Controls.Page>합니다. 후속 단계에서는 이 클래스를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 클래스라고 하며, 클래스 인스턴스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체라고 합니다.  
  
2.  
          [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]를 사용하여 [!INCLUDE[TLA2#tla_cppcli](../../../../includes/tla2sharptla-cppcli-md.md)] 응용 프로그램을 구현합니다. 기존의 관리되지 않는 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 응용 프로그램으로 시작하는 경우, 일반적으로 `/clr` 컴파일러 플래그를 포함하도록 프로젝트 설정을 변경하여 이 응용 프로그램에서 관리 코드를 호출할 수 있습니다. 이 항목에서는 `/clr` 컴파일을 지원하는 데 필요한 작업에 대해 자세히 다루지 않습니다.  
  
3.  스레딩 모델을 STA(단일 스레드 아파트)로 설정합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 이 스레딩 모델을 사용합니다.  
  
4.  창 프로시저에서 WM_CREATE 알림을 처리합니다.  
  
5.  처리기(또는 처리기에서 호출하는 함수)에서 다음을 수행합니다.  
  
    1.  새 <xref:System.Windows.Interop.HwndSource> 개체와 HWND 부모 창으로 해당 `parent` 매개 변수입니다.  
  
    2.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 클래스의 인스턴스를 만듭니다.  
  
    3.  할당에 대 한 참조는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체는 <xref:System.Windows.Interop.HwndSource> 개체 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 속성입니다.  
  
    4.  <xref:System.Windows.Interop.HwndSource> 개체 <xref:System.Windows.Interop.HwndSource.Handle%2A> 속성 창 핸들 (HWND)을 포함 합니다. 응용 프로그램의 관리되지 않는 부분에서 사용할 수 있는 HWND를 가져오려면 `Handle.ToPointer()`를 HWND로 캐스팅합니다.  
  
6.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체에 대한 참조를 보유하는 정적 필드가 포함된 관리 클래스를 구현합니다. 이 클래스에 대 한 참조를 가져올 수 있습니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체 프로그램 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 더 중요 한 것을 방지 하지만 코드를 프로그램 <xref:System.Windows.Interop.HwndSource> 실수로 가비지 수집 되지 않도록 합니다.  
  
7.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체 이벤트 중 하나 이상에 처리기를 연결하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체에서 알림을 받습니다.  
  
8.  속성, 호출 메서드 등을 설정하기 위해 정적 필드에 저장한 참조를 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체와 통신합니다.  
  
> [!NOTE]
>  별도의 어셈블리를 생성한 다음 이를 참조하는 경우 콘텐츠 클래스의 기본 부분 클래스를 사용하여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 1단계용 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 클래스 정의 중 일부 또는 모두를 수행할 수 있습니다. 일반적으로 포함 되지만 <xref:System.Windows.Application> 개체 컴파일하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 를 어셈블리로 있습니다 끝나지 않는 사용 하는 <xref:System.Windows.Application> 상호 운용성의 일환으로, 하면 방금 사용에 대 한 루트 클래스 중 하나 이상을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 참조 된 파일 응용 프로그램에서 해당 partial 클래스를 참조 합니다. 프로시저의 나머지 부분은 기본적으로 위에서 설명한 것과 비슷합니다.  
>   
>  이러한 각 단계는 [연습: Win32에서 WPF 콘텐츠 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md) 항목에서 코드를 통해 설명되어 있습니다.  
  
<a name="hosting_an_hwnd"></a>   
## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>WPF에서 Microsoft Win32 창 호스팅  
 호스팅하는 데 핵심적인은 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 다른 창을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠는는 <xref:System.Windows.Interop.HwndHost> 클래스입니다. 이 클래스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 트리에 추가될 수 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소에 창을 래핑합니다. <xref:System.Windows.Interop.HwndHost> 또한 지원 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 수 있는 호스트 창에 대 한 메시지를 처리 하는 등의 작업을 수행할 수 있습니다. 기본 절차는 다음과 같습니다.  
  
1.  코드 또는 태그를 통해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 요소 트리를 만듭니다. 요소 트리에서 허용 되 고 적절 한 지점을 검색 위치는 <xref:System.Windows.Interop.HwndHost> 구현 자식 요소로 추가할 수 있습니다. 이 단계의 나머지 부분에서는 이 요소를 예약 요소라고 합니다.  
  
2.  파생 <xref:System.Windows.Interop.HwndHost> 를 보유 하는 개체를 만들려면 프로그램 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 콘텐츠입니다.  
  
3.  해당 호스트 클래스에서 재정의 된 <xref:System.Windows.Interop.HwndHost> 메서드 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>합니다. 호스팅된 창의 HWND를 반환합니다. 실제 컨트롤을 반환된 창의 자식 창으로 래핑해야 할 수도 있습니다. 호스트 창에서 컨트롤을 래핑하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠가 간단한 방식으로 컨트롤에서 알림을 받을 수 있습니다. 이 기법을 사용하면 호스팅된 컨트롤 경계에서 메시지 처리에 관한 일부 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 문제를 정정할 수 있습니다.  
  
4.  재정의 <xref:System.Windows.Interop.HwndHost> 메서드 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 및 <xref:System.Windows.Interop.HwndHost.WndProc%2A>합니다. 이렇게 하는 이유는 프로세스를 정리하고 호스팅된 콘텐츠에 대한 참조를 정리하기 위해서입니다. 특히 관리되지 않는 개체의 참조를 만든 경우에 필요합니다.  
  
5.  코드 숨김 파일에서 컨트롤 호스팅 클래스의 인스턴스를 만들고 예약 요소의 하위로 설정합니다. 일반적으로 사용 이벤트 처리기와 같은 <xref:System.Windows.FrameworkElement.Loaded>, 또는 partial 클래스 생성자를 사용 합니다. 런타임 동작을 통해 상호 운용 콘텐츠도 추가할 수 있습니다.  
  
6.  컨트롤 알림과 같은 선택된 창 메시지를 처리합니다. 다음과 같이 두 가지 방법이 있습니다. 두 방법 모두 메시지 스트림에 대해 동일한 액세스 권한을 제공하므로, 프로그래밍 편리성에 따라 선택하면 됩니다.  
  
    -   메시지의 재정의의 모든 메시지 (뿐 아니라 종료 메시지)에 대 한 처리를 구현은 <xref:System.Windows.Interop.HwndHost> 메서드 <xref:System.Windows.Interop.HwndHost.WndProc%2A>합니다.  
  
    -   호스팅 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 처리 하 여 메시지를 처리 하는 요소는 <xref:System.Windows.Interop.HwndHost.MessageHook> 이벤트입니다. 이 이벤트는 호스팅된 창의 기본 창 프로시저에 전송된 모든 메시지에서 발생합니다.  
  
    -   사용 하 여 프로세스를 벗어난 창 메시지를 처리할 수 없지만 <xref:System.Windows.Interop.HwndHost.WndProc%2A>합니다.  
  
7.  관리되지 않는 `SendMessage` 함수를 호출하는 플랫폼 호출을 사용하여 호스팅된 창과 통신합니다.  
  
 다음 단계에 따라 마우스 입력을 사용하는 응용 프로그램을 만듭니다. 구현 하 여 호스트 창에 대 한 이동 하 여 원하는 지원을 추가할 수 있습니다는 <xref:System.Windows.Interop.IKeyboardInputSink> 인터페이스입니다.  
  
 이러한 각 단계는 [연습: WPF에서 Win32 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md) 항목에서 코드를 통해 설명되어 있습니다.  
  
### <a name="hwnds-inside-wpf"></a>WPF 내의 HWND  
 생각할 수 있으며 <xref:System.Windows.Interop.HwndHost> 는 특수 컨트롤 이라고 합니다. (기술적으로 <xref:System.Windows.Interop.HwndHost> 는 <xref:System.Windows.FrameworkElement> 파생 클래스가 아니라는 <xref:System.Windows.Controls.Control> 파생 클래스 이지만 상호 운용성의 목적을 위해 컨트롤 간주 될 수 있습니다.) <xref:System.Windows.Interop.HwndHost> 기본 추상화 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 호스팅된 콘텐츠의 특성 되도록의 나머지 부분에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 호스팅된 콘텐츠를 렌더링 하 고 입력을 처리 하는 다른 컨트롤 모양의 개체 수를 고려 합니다. <xref:System.Windows.Interop.HwndHost> 일반적으로 다른 모든 메서드처럼 동작 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>출력 (그리기 및 그래픽) 주위 중요 한 차이점이 몇 가지 및 어떤 기본 Hwnd의 제한 사항에 따라 입력 (마우스 및 키보드) 지원할 수 있지만, 합니다.  
  
#### <a name="notable-differences-in-output-behavior"></a>출력 동작의 주요 차이점  
  
-   <xref:System.Windows.FrameworkElement>즉는 <xref:System.Windows.Interop.HwndHost> 기본 클래스, UI 변경 내재 된 많은 속성이 있습니다. 여기에 속성와 같은 <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>, 요소 내에 부모 요소의 레이아웃이 변경 합니다. 그러나 이러한 속성의 대부분은 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]에 대응되는 속성이 있더라도 해당 속성에 매핑되지 않습니다. 이러한 속성 및 해당 의미는 렌더링 기술에 따라 많이 달라지므로 매핑이 실용적이지 않게 됩니다. 따라서 같은 속성을 설정 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 에 <xref:System.Windows.Interop.HwndHost> 영향을 주지 않습니다.  
  
-   <xref:System.Windows.Interop.HwndHost> 해야 회전, 크기 조정 된, 왜곡 된, 또는 그렇지 않으면 변환에 의해 영향을 합니다.  
  
-   <xref:System.Windows.Interop.HwndHost> 지원 하지 않습니다는 <xref:System.Windows.UIElement.Opacity%2A> 속성 (알파 혼합). 내부 콘텐츠 인 경우는 <xref:System.Windows.Interop.HwndHost> 수행 <xref:System.Drawing> 없는 자체 위반, 알파 정보를 포함 하는 작업 이지만 <xref:System.Windows.Interop.HwndHost> = 1.0 (100%) 전체 불투명도만 지원 합니다.  
  
-   <xref:System.Windows.Interop.HwndHost> 맨 위에 나타납니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 동일한 최상위 창에 있는 요소입니다. 그러나 한 <xref:System.Windows.Controls.ToolTip> 또는 <xref:System.Windows.Controls.ContextMenu> 생성 된 메뉴는 별도 최상위 창 및 하므로와 함께 올바르게 동작 <xref:System.Windows.Interop.HwndHost>합니다.  
  
-   <xref:System.Windows.Interop.HwndHost> 부모의 클립 영역을 지키지 않습니다 <xref:System.Windows.UIElement>합니다. 이 잠재적 문제는 배치 하려는 경우는 <xref:System.Windows.Interop.HwndHost> 스크롤 영역 내부에 클래스 또는 <xref:System.Windows.Controls.Canvas>합니다.  
  
#### <a name="notable-differences-in-input-behavior"></a>입력 동작의 주요 차이점  
  
-   일반적으로 입력된 장치 내로 범위가 지정 되는 <xref:System.Windows.Interop.HwndHost> 호스팅된 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 영역 입력된 이벤트로 이동 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]합니다.  
  
-   마우스가 동안는 <xref:System.Windows.Interop.HwndHost>, 응용 프로그램에서 수신 하지 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 의 값과 마우스 이벤트는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 <xref:System.Windows.UIElement.IsMouseOver%2A> 됩니다 `false`합니다.  
  
-   동안는 <xref:System.Windows.Interop.HwndHost> 키보드 포커스가 응용 프로그램을 받지 것입니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 키보드 이벤트 및의 값은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> 됩니다 `false`합니다.  
  
-   포커스가 있는 경우에 <xref:System.Windows.Interop.HwndHost> 및 내의 다른 컨트롤에 대 한 변경의 <xref:System.Windows.Interop.HwndHost>, 응용 프로그램을 받지 것입니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 <xref:System.Windows.UIElement.GotFocus> 또는 <xref:System.Windows.UIElement.LostFocus>합니다.  
  
-   관련 스타일러스 속성 및 이벤트는 비슷합니다 및 위에 있는 동안 정보를 보고 하지 않는 <xref:System.Windows.Interop.HwndHost>합니다.  
  
<a name="tabbing_mnemonics_accelerators"></a>   
## <a name="tabbing-mnemonics-and-accelerators"></a>탭 이동, 니모닉 및 액셀러레이터 키  
 <xref:System.Windows.Interop.IKeyboardInputSink> 및 <xref:System.Windows.Interop.IKeyboardInputSite> 인터페이스를 사용 하면 혼합에 대 한 완벽 한 키보드 자유로이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램:  
  
-   [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구성 요소 간 탭 이동  
  
-   포커스가 Win32 구성 요소 내에 있을 때와 WPF 구성 요소에 있을 때 모두 작동하는 니모닉 및 액셀러레이터 키.  
  
 <xref:System.Windows.Interop.HwndHost> 및 <xref:System.Windows.Interop.HwndSource> 클래스는 둘 다의 구현을 제공 <xref:System.Windows.Interop.IKeyboardInputSink>, 있지만 보다 고급 시나리오에 대해 원하는 모든 입력된 메시지를 처리 하지 않을 수 있습니다. 원하는 키보드 동작을 얻기 위해 적절한 메서드를 재정의합니다.  
  
 인터페이스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 영역 간에 전환할 때 발생하는 작업에 대해서만 지원합니다. [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 영역 내에서의 탭 이동 동작은 전적으로 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]에 구현된 탭 이동 논리를 통해서만 제어됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Interop.HwndHost>  
 <xref:System.Windows.Interop.HwndSource>  
 <xref:System.Windows.Interop>  
 [연습: WPF에서 Win32 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)  
 [연습: Win32에서 WPF 콘텐츠 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)
