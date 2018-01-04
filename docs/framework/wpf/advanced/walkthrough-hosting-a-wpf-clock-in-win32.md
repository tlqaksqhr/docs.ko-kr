---
title: "연습: Win32에서 WPF 시계 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: caf652f8a80da8e927a74ffc012d09b2389b1b09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>연습: Win32에서 WPF 시계 호스팅
넣을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램을 사용 하 여 <xref:System.Windows.Interop.HwndSource>를 포함 하는 HWND를 제공 하는 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠입니다. 먼저 만듭니다는 <xref:System.Windows.Interop.HwndSource>, CreateWindow 유사한 매개 변수를 제공 합니다.  그런는 <xref:System.Windows.Interop.HwndSource> 에 대 한는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내부 원하는 콘텐츠입니다.  HWND를 얻게 마지막으로 <xref:System.Windows.Interop.HwndSource>합니다. 이 연습에는 혼합 만드는 방법을 보여 주는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 운영 체제 상자 응용 프로그램 **날짜 및 시간 속성** 대화 상자.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 참조 [WPF 및 Win32 상호 운용](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)합니다.  
  
## <a name="how-to-use-this-tutorial"></a>이 자습서를 사용하는 방법  
 이 자습서는 상호 운용 응용 프로그램을 생성하는 중요한 단계에 대해 중점적으로 설명합니다. 이 자습서는 샘플을 뒷받침 되며 [Win32 클록의 상호 운용 샘플](http://go.microsoft.com/fwlink/?LinkID=160051)했지만 해당 샘플은 최종 제품의 반사입니다. 시작 하 여 기존 하는 경우이 자습서의 단계에 설명 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 자신만의 프로젝트 및 아마도 기존 프로젝트를 추가 하는 호스팅된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 있습니다. 포함 된 최종 제품을 비교할 수 [Win32 클록의 상호 운용 샘플](http://go.microsoft.com/fwlink/?LinkID=160051)합니다.  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Win32 내에서 Windows Presentation Framework의 연습(HwndSource)  
 다음 그래픽에서는 이 자습서의 의도된 최종 제품을 보여 줍니다.  
  
 ![날짜 및 시간 속성 대화 상자](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")  
  
 C + +를 만들어서이 대화 상자를 다시 만들 수 있습니다 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트에서 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], 대화 상자 편집기를 사용 하 여 다음을 만들려고 하 고 있습니다.  
  
 ![날짜 및 시간 속성 대화 상자](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")  
  
 (사용할 필요가 없습니다 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 사용할 <xref:System.Windows.Interop.HwndSource>, c + +를 사용 하 여 쓸 필요가 없습니다 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그램을 검사 하지만이 수행 하는 일반적인 방식 이며 자습서의 단계별 설명에 적합).  
  
 배치 하기 위해 5 개의 특정 하위 단계를 수행 해야 할는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록 대화 상자에:  
  
1.  사용 하도록 설정 하면 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 관리 되는 코드를 호출 하는 프로젝트 (**/clr**)에서 프로젝트 설정을 변경 하 여 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]합니다.  
  
2.  만들기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 별도 dll에서입니다.  
  
3.  넣습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 내는 <xref:System.Windows.Interop.HwndSource>합니다.  
  
4.  HWND는에 대 한 가져오기 <xref:System.Windows.Controls.Page> 를 사용 하는 <xref:System.Windows.Interop.HwndSource.Handle%2A> 속성입니다.  
  
5.  사용 하 여 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 내 더 큰 숫자에서 HWND를 배치할 위치를 결정할 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램  
  
## <a name="clr"></a>/clr  
 이 관리 되지 않는 첫 번째 단계는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트를 호출할 수 있는 관리 되는 코드입니다.  /Clr 컴파일러 옵션을 사용 하 고 Main 메서드를 사용 하기 위해 조정 하려는 필요한 Dll을 연결할을 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  
  
 C + + 프로젝트 내에서 관리 코드를 사용 하도록 설정 하려면: win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.  에 **일반** 속성 페이지 (기본값) 이면 변경 하려면 공용 언어 런타임 지원 `/clr`합니다.  
  
 다음으로 데 필요한 Dll에 대 한 참조를 추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll 및 UIAutomationTypes.dll 합니다. 다음 지침에서는 운영 체제가 C: 드라이브에 설치되어 있다고 가정합니다.  
  
1.  Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 중...** , 및 대화 상자 내부:  
  
2.  Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 중...** .  
  
3.  클릭 **새 참조 추가**찾아보기 탭을 클릭, C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll 입력 및 확인을 클릭 합니다.  
  
4.  PresentationFramework.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll)에 대해 반복합니다.  
  
5.  WindowsBase.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll)에 대해 반복합니다.  
  
6.  UIAutomationTypes.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll)에 대해 반복합니다.  
  
7.  UIAutomationProvider.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll)에 대해 반복합니다.  
  
8.  클릭 **새 참조 추가**, System.dll을 선택 하 고 클릭 **확인**합니다.  
  
9. 클릭 **확인** 참조를 추가 하기 위한 win32clock 속성 페이지를 종료 합니다.  
  
 마지막으로 추가 된 `STAThreadAttribute` 에 `_tWinMain` 을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 이 특성은 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 하을 초기화할 때 [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], 하는데 필요한 단일 스레드 아파트 모델 (STA)를 사용 해야 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).  
  
## <a name="create-a-windows-presentation-framework-page"></a>Windows Presentation Framework 페이지 만들기  
 다음으로 정의 하는 DLL을 만듭니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>합니다. 만드는 가장 쉬운 방식은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 독립 실행형 응용 프로그램 및 쓰기 및 디버그로는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이렇게 부분입니다.  클릭 하 고 프로젝트를 마우스 오른쪽 단추로 클릭 함으로써 DLL로 해당 프로젝트를 변환할 수 완료 되 면 **속성**는 응용 프로그램으로 이동 하 고 출력 형식을 Windows 클래스 라이브러리로 변경 합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll 프로젝트와 결합할 수 있습니다는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 선택 솔루션을 마우스 오른쪽 단추로 클릭 (하나의 솔루션에 두 개의 프로젝트가 포함 된) – 프로젝트 **Add\Existing 프로젝트**합니다.  
  
 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 dll의 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 에 대 한 참조를 추가 해야 프로젝트를:  
  
1.  Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 중...** .  
  
2.  클릭 **새 참조 추가**합니다.  
  
3.  **프로젝트** 탭을 클릭합니다.  WPFClock을 선택하고 [확인]을 클릭합니다.  
  
4.  클릭 **확인** 참조를 추가 하기 위한 win32clock 속성 페이지를 종료 합니다.  
  
## <a name="hwndsource"></a>HwndSource  
 다음을 사용 하 여 <xref:System.Windows.Interop.HwndSource> 있도록는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> HWND 같습니다.  다음 코드 블록을 C++ 파일에 추가합니다.  
  
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
  
 다음은 약간의 설명이 필요할 수 있는 긴 코드 조각입니다.  첫 번째 부분은 다양한 절이어서 모든 호출을 정규화할 필요가 없습니다.  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 만드는 함수를 정의한 다음는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 넣습니다는 <xref:System.Windows.Interop.HwndSource> 주위 HWND 반환 합니다.  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 먼저 만듭니다는 <xref:System.Windows.Interop.HwndSource>, 매개 변수를 가진 CreateWindow 비슷합니다.  
  
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
  
 다음 만듭니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 클래스의 생성자를 호출 하 여:  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 다음에 해당 페이지를 연결 된 <xref:System.Windows.Interop.HwndSource>:  
  
```  
source->RootVisual = page;  
```  
  
 마지막 줄에 대 한 HWND를 반환 하 고는 <xref:System.Windows.Interop.HwndSource>:  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a>Hwnd 위치 지정  
 포함 하는 HWND를 마쳤으므로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내 HWND를 배치 해야 하는 클록의 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 대화 상자.  HWND를 배치할 위치를 알고 있는 경우 전달 하면 해당 크기와 위치는 `GetHwnd` 앞에서 정의한 함수입니다.  그러나 리소스 파일을 사용하여 대화 상자를 정의했으므로 HWND를 배치할 위치를 정확하게 알 수 없습니다.  사용할 수 있습니다는 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 배치 하는 대화 상자 편집기는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 정적 클록 이동 하려는 위치를 제어 ("Insert 클록 여기")를 배치에 사용할는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록입니다.  
  
 WM_INITDIALOG를 처리 하면 위치도 사용 하 여 `GetDlgItem` 자리 표시자 정적 HWND를 검색할 수:  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 계산한 다음 크기와 위치 자리 표시자 정적 행과의 활용할 수 있도록는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록에 해당 합니다.  
  
 RECT 사각형의 경우입니다.  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 그런 다음 자리 표시자 STATIC을 숨깁니다.  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 만들고는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계 그 위치에는 HWND:  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 자습서를 재미 및 실제 생성을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록 있습니다 작성 해야 합니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이 시점에서 시계 컨트롤입니다. 코드 숨김에서 몇 개의 이벤트 처리기만 사용하여 태그에서 거의 모든 작업을 수행할 수 있습니다. 이 자습서의 상호 운용 하는 방법에 대 한 저장소와 컨트롤 디자인 대해서는 알아보지 때문 전체에 대 한 코드는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록은 제공 코드 블록 작성 하거나 각 부분의 의미에 대 한 개별적인 지침이 설명 없이 여기 합니다. 이 코드를 자유롭게 사용하여 컨트롤의 모양과 느낌 또는 기능을 변경해 보세요.  
  
 다음은 태그입니다.  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 다음은 함께 제공되는 코드 숨김입니다.  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 최종 결과는 다음과 같습니다.  
  
 ![날짜 및 시간 속성 대화 상자](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")  
  
 이 스크린 샷을 생성 하는 코드를 최종 결과 비교 하려면 참조 [Win32 클록의 상호 운용 샘플](http://go.microsoft.com/fwlink/?LinkID=160051)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Interop.HwndSource>  
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Win32 시계 상호 운용 샘플](http://go.microsoft.com/fwlink/?LinkID=160051)
