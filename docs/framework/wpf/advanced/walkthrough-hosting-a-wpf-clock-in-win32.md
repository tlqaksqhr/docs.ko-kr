---
title: "연습: Win32에서 WPF 시계 호스팅 | Microsoft Docs"
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
  - "상호 운용성[WPF], 자습서"
  - "상호 운용성[WPF], Win32"
  - "Win32 코드, WPF 상호 운용"
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 연습: Win32에서 WPF 시계 호스팅
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램 내부에 배치하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 포함하는 HWND를 제공하는 <xref:System.Windows.Interop.HwndSource>를 사용합니다.  먼저 <xref:System.Windows.Interop.HwndSource>를 만들어 CreateWindow와 유사한 매개 변수를 제공합니다.  그런 다음 <xref:System.Windows.Interop.HwndSource>로 내부에 포함할 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 전달합니다.  마지막으로 <xref:System.Windows.Interop.HwndSource>에서 HWND를 가져옵니다.  이 연습에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램 내부에 운영 체제 **날짜 및 시간 속성** 대화 상자를 다시 구현하는 혼합 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 생성하는 방법에 대해 설명합니다.  
  
## 사전 요구 사항  
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)를 참조하십시오.  
  
## 이 자습서를 사용하는 방법  
 이 자습서에서는 상호 운용 응용 프로그램을 만드는 중요 단계에 대해 집중적으로 설명합니다.  또한 [Win32 Clock Interoperation 샘플](http://go.microsoft.com/fwlink/?LinkID=160051)도 제공하지만 이 샘플에는 최종 제품이 반영되어 있습니다.  이 자습서에서는 기존에 직접 만든 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트부터 시작하여 호스팅되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 응용 프로그램에 추가하는 단계를 설명합니다.  최종 제품을 [Win32 Clock Interoperation 샘플](http://go.microsoft.com/fwlink/?LinkID=160051)과 비교할 수 있습니다.  
  
## Windows Presentation Foundation 내의 Win32에 대한 연습\(HwndSource\)  
 다음 그래픽에서는 이 자습서의 최종 결과물을 보여 줍니다.  
  
 ![날짜 및 시간 속성 대화 상자](../../../../docs/framework/wpf/advanced/media/interoparch06.png "InteropArch06")  
  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]에서 C\+\+ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트를 만들고 대화 상자 편집기로 다음을 만들어 이 대화 상자를 다시 생성할 수 있습니다.  
  
 ![날짜 및 시간 속성 대화 상자](../../../../docs/framework/wpf/advanced/media/interoparch07.png "InteropArch07")  
  
 <xref:System.Windows.Interop.HwndSource>를 사용하기 위해 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]를 사용할 필요가 없으며 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그램을 작성하기 위해 C\+\+를 사용할 필요가 없지만 이러한 도구를 사용하는 것이 작업을 수행하는 일반적인 방식이며 자습서의 단계별 설명에 적합합니다.  
  
 대화 상자에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계를 배치하려면 다음과 같은 다섯 가지 하위 단계를 완료해야 합니다.  
  
1.  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]에서 프로젝트 설정을 변경하여 관리 코드\(**\/clr**\)를 호출하는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트를 활성화합니다.  
  
2.  별도의 DLL에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>를 만듭니다.  
  
3.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>를 <xref:System.Windows.Interop.HwndSource> 내부에 배치합니다.  
  
4.  <xref:System.Windows.Interop.HwndSource.Handle%2A> 속성을 사용하여 해당 <xref:System.Windows.Controls.Page>에 대한 HWND를 가져옵니다.  
  
5.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]를 사용하여 더 큰 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램 내에서 HWND를 배치할 위치를 결정합니다.  
  
## \/clr  
 첫 번째 단계는 이 관리되지 않는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트를 관리 코드를 호출할 수 있는 프로젝트로 변환하는 것입니다.  \/clr 컴파일러 옵션을 사용합니다. 그러면 사용할 필수 DLL에 링크되고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 사용할 Main 메서드가 수정됩니다.  
  
 C\+\+ 프로젝트 내부에서 관리 코드를 사용할 수 있으려면 win32clock 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  **일반** 속성 페이지\(기본값\)에서 CLR\(공용 언어 런타임\) 지원을 `/clr`로 변경합니다.  
  
 그런 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 필요한 DLL인 PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll 및 UIAutomationTypes.dll에 대한 참조를 추가합니다.  다음 지침에서는 운영 체제가 C: 드라이브에 설치되어 있다고 가정합니다.  
  
1.  win32clock 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조...**를 선택한 다음 대화 상자 내부에서 다음을 수행합니다.  
  
2.  win32clock 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조...**를 선택합니다.  
  
3.  **새 참조 추가**를 클릭하고 **찾아보기** 탭을 클릭한 다음 C:\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\PresentationCore.dll을 입력하고 **확인**을 클릭합니다.  
  
4.  PresentationFramework.dll\(C:\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\PresentationFramework.dll\)에 대해서도 이 과정을 반복합니다.  
  
5.  WindowsBase.dll\(C:\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\WindowsBase.dll\)에 대해서도 이 과정을 반복합니다.  
  
6.  UIAutomationTypes.dll\(C:\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\UIAutomationTypes.dll\)에 대해서도 이 과정을 반복합니다.  
  
7.  UIAutomationProvider.dll\(C:\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\UIAutomationProvider.dll\)에 대해서도 이 과정을 반복합니다.  
  
8.  **새 참조 추가**를 클릭한 다음 System.dll을 선택하고 **확인**을 클릭합니다.  
  
9. **확인**을 클릭하여 참조를 추가하는 데 사용되는 win32clock 속성 페이지를 종료합니다.  
  
 마지막으로, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 사용할 `_tWinMain` 메서드에 `STAThreadAttribute`를 추가합니다.  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 이 특성을 사용하면 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]에서 [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]을 초기화할 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에 필요한 STA\(단일 스레드 아파트 모델\)를 사용하게 만들 수 있습니다.  
  
## Windows Presentation Framework 페이지 만들기  
 다음으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>를 정의하는 DLL을 만듭니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>를 독립 실행형 응용 프로그램으로 만들고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 부분을 작성한 후 디버그하는 것이 가장 쉬운 방법인 경우가 많습니다.  작업을 마친 후에는 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭한 다음 응용 프로그램으로 이동하여 출력 형식을 Windows Class Library로 변경함으로써 프로젝트를 DLL로 변환할 수 있습니다.  
  
 그런 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll 프로젝트를 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트\(두 개의 프로젝트가 들어 있는 솔루션 하나\)로 결합할 수 있습니다. 이를 위해서는 솔루션을 마우스 오른쪽 단추로 클릭하고 **기존 프로젝트 추가**를 선택합니다.  
  
 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트에서 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll을 사용하려면 참조를 추가해야 합니다.  
  
1.  win32clock 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조...**를 선택합니다.  
  
2.  **새 참조 추가**를 클릭합니다.  
  
3.  **프로젝트** 탭을 클릭합니다.  WPFClock을 선택하고 **확인**을 클릭합니다.  
  
4.  **확인**을 클릭하여 참조를 추가하는 데 사용되는 win32clock 속성 페이지를 종료합니다.  
  
## HwndSource  
 다음으로 <xref:System.Windows.Interop.HwndSource>를 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>를 HWND처럼 만듭니다.  다음 코드 블록을 C\+\+ 파일에 추가합니다.  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
  
    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
        HwndSource^ source = gcnew HwndSource(  
            0, // class style  
            WS_VISIBLE | WS_CHILD, // style  
            0, // exstyle  
            x, y, width, height,  
            "hi", // NAME  
            IntPtr(parent)        // parent window   
            );  
  
        UIElement^ page = gcnew WPFClock::Clock();  
        source->RootVisual = page;  
        return (HWND) source->Handle.ToPointer();  
    }  
}  
}  
```  
  
 이는 조금 더 자세한 설명이 필요한 긴 코드입니다.  첫 번째 부분에는 모든 호출을 정규화할 필요가 없도록 다양한 절이 있습니다.  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 다음으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 만들고 이 콘텐츠를 둘러싸는 <xref:System.Windows.Interop.HwndSource>를 만든 다음 HWND를 반환하는 함수를 정의합니다.  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 먼저 CreateWindow와 비슷한 매개 변수를 갖는 <xref:System.Windows.Interop.HwndSource>를 만듭니다.  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 다음으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 생성자를 호출하여 해당 콘텐츠 클래스를 만듭니다.  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 그런 다음 페이지를 <xref:System.Windows.Interop.HwndSource>에 연결합니다.  
  
```  
source->RootVisual = page;  
```  
  
 마지막 줄에서 <xref:System.Windows.Interop.HwndSource>에 대한 HWND가 반환됩니다.  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## Hwnd 위치 지정  
 이제 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계를 포함하는 HWND가 만들어졌으므로 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 대화 상자 내부에 이 HWND를 배치해야 합니다.  HWND를 배치할 위치를 알고 있다면 앞서 정의한 `GetHwnd` 함수에 크기와 위치만 전달하면 됩니다.  하지만 리소스 파일을 사용하여 대화 상자를 정의한 경우에는 HWND 배치 위치를 정확히 모를 수도 있습니다.  이 경우 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 대화 상자 편집기를 사용하여 시계를 배치할 위치\("Insert clock here"\)에 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC 컨트롤을 놓고 해당 컨트롤을 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계의 위치를 지정합니다.  
  
 WM\_INITDIALOG를 처리하는 위치에서 `GetDlgItem`을 사용하여 자리 표시자 STATIC에 대한 HWND를 검색합니다.  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 그런 다음 해당 자리 표시자 STATIC의 크기와 위치를 계산하여 해당 위치에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계를 배치할 수 있습니다.  
  
 RECT rectangle;  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 계속해서 자리 표시자 STATIC을 숨깁니다.  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 해당 위치에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계 HWND를 만듭니다.  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 자습서를 재미 있게 만들고 실제적인 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계를 작성하기 위해서는 이 시점에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계 컨트롤을 만들어야 합니다.  대부분의 작업은 태그에서 수행할 수 있으며 몇 가지 이벤트 처리기만 코드 숨김으로 처리합니다.  이 자습서는 컨트롤 디자인이 아닌 상호 운용에 대한 것이므로 여기에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계에 대한 전체 코드가 개별적인 빌드 지침이나 각 부분의 의미에 대한 설명 없이 코드 블록으로 제공됩니다.  이 코드를 자유롭게 사용하여 컨트롤의 모양과 동작 및 기능을 변경합니다.  
  
 다음은 태그입니다.  
  
 [!code-xml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 다음은 함께 제공된 코드 숨김입니다.  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 최종 결과는 다음과 같습니다.  
  
 ![날짜 및 시간 속성 대화 상자](../../../../docs/framework/wpf/advanced/media/interoparch08.png "InteropArch08")  
  
 이 스크린 샷을 생성하는 데 사용된 코드와 최종 결과를 비교하려면 [Win32 Clock Interoperation 샘플](http://go.microsoft.com/fwlink/?LinkID=160051)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Interop.HwndSource>   
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Win32 Clock Interoperation 샘플](http://go.microsoft.com/fwlink/?LinkID=160051)