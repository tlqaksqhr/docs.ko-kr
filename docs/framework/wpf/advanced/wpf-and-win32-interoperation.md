---
title: "WPF 및 Win32 상호 운용성 | Microsoft Docs"
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
  - "Win32 창에서 WPF 콘텐츠 호스팅"
  - "HWND interop[WPF]"
  - "상호 운용성[WPF], Win32"
  - "Win32 코드, WPF 상호 운용"
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# WPF 및 Win32 상호 운용성
이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 코드의 상호 운용 방법에 대해 전반적으로 살펴봅니다.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다.  [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 코드를 작성하는 데 많은 시간과 비용을 투자했다면 이러한 코드의 일부를 다시 사용하는 것이 더 효과적일 것입니다.  
  
   
  
<a name="basics"></a>   
## WPF 및 Win32 상호 운용성 기본 사항  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 코드를 상호 운용하려는 경우 기본적으로 다음과 같은 두 가지 방법을 사용할 수 있습니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에서 호스팅합니다.  이 방법을 사용할 경우 표준 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창 및 응용 프로그램의 프레임워크 내에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 고급 그래픽 기능을 사용할 수 있습니다.  
  
-   [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠에서 호스팅합니다.  이 방법을 사용할 경우 기존의 사용자 지정 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨트롤을 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠의 컨텍스트에서 사용할 수 있으며 경계를 넘어 데이터를 전달할 수 있습니다.  
  
 이 항목에서는 각 방법을 개념적인 측면에서 소개합니다.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 호스팅하는 것에 대한 코드 기반 설명을 보려면 [연습: Win32에서 WPF 콘텐츠 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)을 참조하십시오.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]를 호스팅하는 것에 대한 코드 기반 설명을 보려면 [연습: WPF에서 Win32 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)을 참조하십시오.  
  
<a name="projects"></a>   
## WPF 상호 운용 프로젝트  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]는 관리 코드이지만 대부분의 기존 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그램은 비관리 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)]로 작성되었습니다.  완전한 비관리 프로그램에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 호출할 수 없습니다.  하지만 [!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)] 컴파일러를 `/clr` 옵션과 함께 사용하면 관리 및 비관리 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 호출을 완벽하게 혼합할 수 있는 관리\/비관리 혼합형 프로그램을 만들 수 있습니다.  
  
 이 경우 프로젝트 수준에서 한 가지 문제가 발생하는데, 바로 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일을 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 프로젝트로 컴파일할 수 없다는 것입니다.  이 문제는 다음과 같은 몇 가지 프로젝트 분리 방법을 통해 해결할 수 있습니다.  
  
-   모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 컴파일된 어셈블리로 포함하는 [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] DLL을 만든 다음 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 실행 파일에 해당 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]을 참조로 포함합니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠에 대한 [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] 실행 파일을 만든 다음 이 실행 파일이 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 콘텐츠가 포함된 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]을 참조하도록 설정합니다.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 컴파일하는 대신 <xref:System.Windows.Markup.XamlReader.Load%2A>를 사용하여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 런타임에 로드합니다.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하는 대신 <xref:System.Windows.Application>에서 요소 트리를 만들어 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 코드에서 작성합니다.  
  
 자신에게 가장 잘 맞는 방법을 사용하는 것이 좋습니다.  
  
> [!NOTE]
>  사용 하지 않은 경우 [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] 전에, 일부 "새로운" 키워드를 같이 알 수 있습니다 `gcnew` 및 `nullptr` 상호 운용 코드 예제에서입니다. 이러한 키워드는 이전의 이중 밑줄 구문 대체 \(`__gc`\)의 관리 코드에 보다 적합 한 구문을 제공 하 고 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)].  [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]의 관리되는 기능에 대한 자세한 내용은 [런타임 플랫폼의 구성 요소 확장](../Topic/Component%20Extensions%20for%20Runtime%20Platforms.md) 및 [Hello, C\+\+\/CLI](http://go.microsoft.com/fwlink/?LinkId=98739)를 참조하십시오.  
  
<a name="hwnds"></a>   
## WPF에서 HWND를 사용하는 방법  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] "HWND interop"을 최대한 활용하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 HWND를 사용하는 방법을 이해하고 있어야 합니다.  어떤 HWND의 경우에도 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링을 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 렌더링 또는 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] \/ [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)] 렌더링과 혼합하여 사용할 수 없습니다.  여기에는 많은 의미가 내포되어 있습니다.  먼저, 이와 같은 여러 렌더링 모델을 혼합하려면 상호 운용 솔루션을 만들어야 합니다. 또한 사용하려고 선택한 각 렌더링 모델에 지정된 상호 운용 세그먼트를 사용해야 합니다.  이러한 문제 외에도 렌더링 동작은 상호 운용 솔루션으로 수행하는 작업에 대해 "에어스페이스" 제한을 부여합니다.  "에어스페이스"의 개념에 대해서는 [기술 영역 개요](../../../../docs/framework/wpf/advanced/technology-regions-overview.md) 항목에 보다 자세히 설명되어 있습니다.  
  
 화면의 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소는 궁극적으로 HWND에 기반을 둡니다.  사용자가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>를 만들면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 최상위 HWND를 만든 다음 <xref:System.Windows.Interop.HwndSource>를 사용하여 <xref:System.Windows.Window>와 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 HWND 내에 배치합니다.  응용 프로그램의 나머지 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠는 단일 HWND를 공유합니다.  메뉴, 콤보 상자 드롭다운 및 기타 팝업은 예외입니다.  이러한 요소는 고유한 최상위 창을 만듭니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메뉴가 자신이 포함된 창 HWND의 가장자리를 벗어날 수 있는 것도 이 때문입니다.  사용자가 <xref:System.Windows.Interop.HwndHost>를 사용하여 HWND를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내에 배치하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND의 위치를 기준으로 새로운 자식 HWND를 배치하는 방법을 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]에 알려 줍니다.  
  
 HWND와 관련된 개념은 해당 HWND 내에서, 그리고 각 HWND 간에 투명합니다.  이에 대해서도 [기술 영역 개요](../../../../docs/framework/wpf/advanced/technology-regions-overview.md) 항목에 자세히 설명되어 있습니다.  
  
<a name="hosting_a_wpf_page"></a>   
## Microsoft Win32 창에서 WPF 콘텐츠 호스팅  
 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 호스팅하는 데 핵심적인 역할을 하는 요소는 <xref:System.Windows.Interop.HwndSource> 클래스입니다.  이 클래스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창 안에 래핑하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠가 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 자식 창으로 통합되도록 합니다.  다음에 나오는 방법에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 단일 응용 프로그램에 통합합니다.  
  
1.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠\(콘텐츠 루트 요소\)를 관리되는 클래스로 구현합니다.  일반적으로 클래스는 여러 자식 요소를 포함할 수 있거나 <xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.Controls.Page>와 같이 루트 요소로 사용할 수 있는 클래스 중 하나에서 상속합니다.  이후 단계에서는 이 클래스를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 클래스라고 하고 이 클래스의 인스턴스를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체라고 합니다.  
  
2.  [!INCLUDE[TLA2#tla_cppcli](../../../../includes/tla2sharptla-cppcli-md.md)]를 사용하여 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램을 구현합니다.  기존의 관리되지 않는 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 응용 프로그램을 사용하는 경우, 일반적으로 `/clr` 컴파일러 플래그를 포함하도록 프로젝트 설정을 변경하여 응용 프로그램에서 관리 코드를 호출하도록 할 수 있습니다. 이 항목에서는 `/clr` 컴파일을 지원하는 데 필요한 작업에 대해 자세히 다루지 않습니다.  
  
3.  스레딩 모델을 STA\(단일 스레드 아파트\)로 설정합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 이 스레딩 모델을 사용합니다.  
  
4.  창 프로시저에서 WM\_CREATE 알림을 처리합니다.  
  
5.  처리기 또는 처리기가 호출하는 함수 내에서 다음을 수행합니다.  
  
    1.  부모 창 HWND를 `parent` 매개 변수로 사용하여 새 <xref:System.Windows.Interop.HwndSource> 개체를 만듭니다.  
  
    2.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 클래스의 인스턴스를 만듭니다.  
  
    3.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체에 대한 참조를 <xref:System.Windows.Interop.HwndSource> 개체의 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 속성에 할당합니다.  
  
    4.  <xref:System.Windows.Interop.HwndSource> 개체의 <xref:System.Windows.Interop.HwndSource.Handle%2A> 속성에는 창 핸들\(HWND\)이 포함됩니다.  응용 프로그램의 관리되지 않는 부분에서 사용할 수 있는 HWND를 가져오려면 `Handle.ToPointer()`를 HWND로 캐스팅합니다.  
  
6.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체에 대한 참조를 보유하는 정적 필드가 포함된 관리되는 클래스를 구현합니다.  이 클래스를 사용하면 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 코드에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체에 대한 참조를 가져올 수 있습니다. 또한 이 클래스는 <xref:System.Windows.Interop.HwndSource>가 실수로 가비지 수집되지 않도록 방지하는 중요한 기능도 수행합니다.  
  
7.  하나 이상의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체 이벤트에 처리기를 연결하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체에서 알림을 받습니다.  
  
8.  통신은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 집합 속성, 메서드를 호출 하는 정적 필드에 저장 하는 참조를 사용 하 여 콘텐츠 개체.  
  
> [!NOTE]
>  일부 또는 전부를 수행할 수 있습니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐트 클래스 정의 대 한 하나의 단계에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 는 별도 어셈블리를 생성 하 고이 참조 하는 경우, 콘텐츠 클래스의 기본 partial 클래스를 사용 하 여. 일반적으로 포함 되지만 <xref:System.Windows.Application> 개체를 컴파일하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 어셈블리로 사용 하 여 결국 하지 않습니다 <xref:System.Windows.Application> 상호 운용성의 일부로 루트 클래스 중 하나를 사용 하면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 응용 프로그램에서 참조 하 고 해당 partial 클래스를 참조 합니다.  절차의 나머지 단계는 앞에 설명된 단계와 비슷합니다.  
>   
>  각 단계에 대해서는 [연습: Win32에서 WPF 콘텐츠 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md) 항목에서 코드를 통해 자세히 보여 줍니다.  
  
<a name="hosting_an_hwnd"></a>   
## WPF에서 Microsoft Win32 창 호스팅  
 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 내에서 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창을 호스팅하는 데 핵심적인 역할을 하는 요소는 <xref:System.Windows.Interop.HwndHost> 클래스입니다.  이 클래스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 트리에 추가할 수 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 내에 창을 래핑합니다.  또한 <xref:System.Windows.Interop.HwndHost>는 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 지원하므로 호스팅된 창의 메시지를 처리하는 등의 작업을 수행할 수 있습니다.  기본 절차는 다음과 같습니다.  
  
1.  코드나 태그를 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 대한 요소 트리를 만듭니다.  요소 트리 내에서 <xref:System.Windows.Interop.HwndHost> 구현을 자식 요소로 추가할 수 있는 적합한 위치를 찾습니다.  이후 단계에서는 이 요소를 예약 요소라고 합니다.  
  
2.  <xref:System.Windows.Interop.HwndHost>에서 파생하여 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 콘텐츠를 포함하는 개체를 만듭니다.  
  
3.  이 호스트 클래스에서 <xref:System.Windows.Interop.HwndHost> 메서드 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>를 재정의합니다.  호스팅된 창의 HWND를 반환합니다.  실제 컨트롤을 반환된 창의 자식 창으로 래핑할 수 있습니다. 이 경우 호스트 창에 컨트롤을 래핑하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠가 컨트롤로부터 간단하게 알림을 받도록 할 수 있습니다.  이 방법은 호스팅되는 컨트롤 경계에서의 메시지 처리와 관련된 몇 가지 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 문제를 해결하는 데 유용합니다.  
  
4.  <xref:System.Windows.Interop.HwndHost> 메서드 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 및 <xref:System.Windows.Interop.HwndHost.WndProc%2A>을 재정의합니다.  이렇게 하는 이유는 호스팅된 콘텐츠에 대한 참조의 정리 및 제거 작업을 처리하기 위해서이며, 특히 관리되지 않는 개체에 대한 참조를 만든 경우에 필요합니다.  
  
5.  코드 숨김 파일에서 컨트롤 호스팅 클래스의 인스턴스를 만들어 예약 요소의 자식 요소로 설정합니다.  <xref:System.Windows.FrameworkElement.Loaded>와 같은 이벤트 처리기를 사용하거나 partial 클래스 생성자를 사용하는 것이 일반적이지만  런타임 동작을 통해 상호 운용 콘텐츠를 추가할 수도 있습니다.  
  
6.  컨트롤 알림과 같은 선택된 창 메시지를 처리합니다.  이를 수행하는 방법은 두 가지입니다.  두 방법이 메시지 스트림에 동일하게 액세스하므로 프로그래밍하기에 편리한 방법을 선택하면 됩니다.  
  
    -   재정의한 <xref:System.Windows.Interop.HwndHost> 메서드 <xref:System.Windows.Interop.HwndHost.WndProc%2A>의 종료 메시지를 비롯한 모든 메시지에 대한 메시지 처리를 구현합니다.  
  
    -   호스팅 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소가 <xref:System.Windows.Interop.HwndHost.MessageHook> 이벤트를 처리하여 메시지를 처리하도록 합니다.  이 이벤트는 호스팅된 창의 기본 창 프로시저로 전송된 모든 메시지에 대해 발생합니다.  
  
    -   프로세스 외부에 있는 창의 메시지는 <xref:System.Windows.Interop.HwndHost.WndProc%2A>을 사용하여 처리할 수 없습니다.  
  
7.  P\/Invoke 호출을 통해 관리되지 않는 `SendMessage` 함수를 호출하여 호스팅된 창과 통신합니다.  
  
 다음 단계에 따라 마우스 입력이 작동하는 응용 프로그램을 만듭니다.  <xref:System.Windows.Interop.IKeyboardInputSink> 인터페이스를 구현하면 호스팅된 창에 탭 이동 지원을 추가할 수 있습니다.  
  
 각 단계에 대해서는 [연습: WPF에서 Win32 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md) 항목에서 코드를 통해 자세히 보여 줍니다.  
  
### WPF 내의 HWND  
 <xref:System.Windows.Interop.HwndHost>는 특수 컨트롤이라고 할 수 있습니다.  기술적으로 <xref:System.Windows.Interop.HwndHost>는 <xref:System.Windows.Controls.Control> 파생 클래스가 아니라 <xref:System.Windows.FrameworkElement> 파생 클래스이지만 상호 운용 용도의 컨트롤로 생각할 수 있습니다. 또한 <xref:System.Windows.Interop.HwndHost>는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 나머지 부분에서 호스팅된 콘텐츠를 다른 컨트롤과 비슷하게 입력을 렌더링하고 처리하는 개체로 간주하도록 호스팅된 콘텐츠의 기본 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 특성을 추상화합니다.  <xref:System.Windows.Interop.HwndHost>는 일반적으로 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>와 비슷하게 동작합니다. 단, 기본 HWND의 지원에는 한계가 있으므로 출력\(그리기 및 그래픽\)과 입력\(마우스 및 키보드\)에 있어서 몇 가지 중요한 차이점은 있습니다.  
  
#### 출력 동작의 주요 차이점  
  
-   <xref:System.Windows.Interop.HwndHost> 기본 클래스인 <xref:System.Windows.FrameworkElement>에는 UI를 변경할 수 있는 몇 가지 속성이 있습니다.  여기에는 부모 요소 내에 있는 요소의 레이아웃을 변경하는 <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=fullName>과 같은 속성이 포함됩니다.  하지만 이러한 속성 중 대부분은 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]에 대응되는 속성이 있더라도 해당 속성에 매핑되지 않습니다.  이러한 속성 및 속성의 의미는 렌더링 기술마다 많이 다르므로 매핑의 실효성이 없습니다.  따라서 <xref:System.Windows.Interop.HwndHost>에 <xref:System.Windows.FrameworkElement.FlowDirection%2A>과 같은 속성을 설정해도 아무런 효과가 없습니다.  
  
-   <xref:System.Windows.Interop.HwndHost>는 회전하거나 배율을 조정하거나 기울일 수 없으며 변환을 통해 달리 변경할 수 없습니다.  
  
-   <xref:System.Windows.Interop.HwndHost>는 <xref:System.Windows.UIElement.Opacity%2A> 속성\(알파 혼합\)을 지원하지 않습니다.  <xref:System.Windows.Interop.HwndHost> 내의 콘텐츠가 알파 정보가 포함된 <xref:System.Drawing> 작업을 수행하는 경우 작업 자체는 제한을 위반하지 않지만 <xref:System.Windows.Interop.HwndHost>가 투명도 \= 1.0\(100%\)만 지원합니다.  
  
-   <xref:System.Windows.Interop.HwndHost>는 같은 최상위 창에 있는 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소의 위에 나타납니다.  하지만 <xref:System.Windows.Controls.ToolTip> 또는 <xref:System.Windows.Controls.ContextMenu>에서 생성된 메뉴는 별도의 최상위 창이므로 <xref:System.Windows.Interop.HwndHost>와 함께 올바르게 동작합니다.  
  
-   <xref:System.Windows.Interop.HwndHost>는 부모 <xref:System.Windows.UIElement>의 클리핑 영역을 무시합니다.  이 때문에 스크롤 영역 또는 <xref:System.Windows.Controls.Canvas> 내에 <xref:System.Windows.Interop.HwndHost> 클래스를 배치하려는 경우 문제가 발생할 수 있습니다.  
  
#### 입력 동작의 주요 차이점  
  
-   일반적으로 입력 장치는 그 범위가 <xref:System.Windows.Interop.HwndHost> 호스팅 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 영역으로 제한되지만 입력 이벤트는 곧바로 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]에 전달됩니다.  
  
-   마우스가 <xref:System.Windows.Interop.HwndHost> 위에 있는 동안에는 응용 프로그램에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 마우스 이벤트를 수신하지 않으며 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 <xref:System.Windows.UIElement.IsMouseOver%2A>의 값이 `false`가 됩니다.  
  
-   <xref:System.Windows.Interop.HwndHost>에 키보드 포커스가 있는 동안에는 응용 프로그램에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 키보드 이벤트를 수신하지 않으며 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>의 값이 `false`가 됩니다.  
  
-   포커스가 <xref:System.Windows.Interop.HwndHost> 내에 있다가 <xref:System.Windows.Interop.HwndHost> 내의 다른 컨트롤로 변경될 때는 응용 프로그램에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 <xref:System.Windows.UIElement.GotFocus> 또는 <xref:System.Windows.UIElement.LostFocus>를 수신하지 않습니다.  
  
-   관련 스타일러스 속성과 이벤트는 비슷합니다. 스타일러스가 <xref:System.Windows.Interop.HwndHost> 위에 있는 동안에는 정보를 보고하지 않습니다.  
  
<a name="tabbing_mnemonics_accelerators"></a>   
## 탭 이동, 니모닉 및 액셀러레이터 키  
 <xref:System.Windows.Interop.IKeyboardInputSink> 및 <xref:System.Windows.Interop.IKeyboardInputSite> 인터페이스를 사용하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\/[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 혼합형 응용 프로그램을 위한 완벽한 키보드 환경을 만들 수 있습니다.  
  
-   [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구성 요소 간 탭 이동  
  
-   포커스가 Win32 구성 요소 내에 있을 때와 포커스가 WPF 구성 요소 내에 있을 때 모두 작동하는 니모닉 및 액셀러레이터 키  
  
 <xref:System.Windows.Interop.HwndHost> 및 <xref:System.Windows.Interop.HwndSource> 클래스는 둘 다 <xref:System.Windows.Interop.IKeyboardInputSink>의 구현을 제공하지만 고급 시나리오에 필요한 입력 메시지를 모두 처리하지는 못합니다.  이 경우 적절한 메서드를 재정의하여 원하는 키보드 동작을 만들 수 있습니다.  
  
 인터페이스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 영역 간에 전환할 때 발생하는 작업에 대한 지원만을 제공합니다.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 영역 내에서의 탭 이동 동작은 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]에 구현된 탭 이동 논리\(있는 경우\)에 의해 전적으로 제어됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Interop.HwndHost>   
 <xref:System.Windows.Interop.HwndSource>   
 <xref:System.Windows.Interop>   
 [연습: WPF에서 Win32 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)   
 [연습: Win32에서 WPF 콘텐츠 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)