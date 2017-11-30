---
title: "WPF에서 Win32 콘텐츠 호스팅"
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
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e82d18cd765fc3ac4f4982a71d187a3741f4f03a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="hosting-win32-content-in-wpf"></a>WPF에서 Win32 콘텐츠 호스팅
## <a name="prerequisites"></a>필수 구성 요소  
 참조 [WPF 및 Win32 상호 운용](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)합니다.  
  
## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Windows Presentation Framework (HwndHost) 안에 win32 연습  
 다시 사용 하려면 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 내부 콘텐츠 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 사용 하 여 <xref:System.Windows.Interop.HwndHost>, Hwnd 같이 표시 하는 컨트롤이 변수인 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠입니다.  와 같은 <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> 간단 하 게 사용 하는:에서 파생 <xref:System.Windows.Interop.HwndHost> 하 고 구현 `BuildWindowCore` 및 `DestroyWindowCore` 메서드를 인스턴스화할 프로그램 <xref:System.Windows.Interop.HwndHost> 클래스를 파생 하 고 안에 넣습니다 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  
  
 경우에 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 논리를 컨트롤로 이미 패키지 된 않다면 `BuildWindowCore` 구현에 대 한 호출 보다 약간 더는 `CreateWindow`합니다.  예를 들어 한 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX 컨트롤의 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:  
  
```  
virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {  
    HWND handle = CreateWindowEx(0, L"LISTBOX",   
    L"this is a Win32 listbox",  
    WS_CHILD | WS_VISIBLE | LBS_NOTIFY  
    | WS_VSCROLL | WS_BORDER,  
    0, 0, // x, y  
    30, 70, // height, width  
    (HWND) hwndParent.Handle.ToPointer(), // parent hwnd  
    0, // hmenu  
    0, // hinstance  
    0); // lparam  
  
    return HandleRef(this, IntPtr(handle));  
}  
  
virtual void DestroyWindowCore(HandleRef hwnd) override {  
    // HwndHost will dispose the hwnd for us  
}  
```  
  
 가정 하지만 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 코드 그리 자체 포함 됩니다? 만들 수 있습니다는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 대화 상자를 더 큰에 해당 내용을 포함 한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  이 샘플에서이 보여 줍니다 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 및 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]다른 언어에서 또는 명령줄에서이 작업을 수행할 수도 있지만, 합니다.  
  
 컴파일되는 간단한 대화 상자와 시작는 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 프로젝트.  
  
 다음으로,이 대화 상자를 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램:  
  
-   컴파일하는 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 관리 되는 것 (`/clr`)  
  
-   대화 상자 컨트롤에 설정  
  
-   파생된 클래스의 정의 <xref:System.Windows.Interop.HwndHost> 와 `BuildWindowCore` 및 `DestroyWindowCore` 메서드  
  
-   재정의 `TranslateAccelerator` 대화 상자 키를 처리 하는 메서드  
  
-   재정의 `TabInto` 탭 이동을 지원 하도록 메서드  
  
-   재정의 `OnMnemonic` 니모닉을 지원 하도록 메서드  
  
-   인스턴스화하는 <xref:System.Windows.Interop.HwndHost> 하위 클래스와 오른쪽에서 관리 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소  
  
### <a name="turn-the-dialog-into-a-control"></a>대화 상자 컨트롤에 설정  
 자식 WS_CHILD 및 DS_CONTROL 스타일을 사용 하 여 HWND에는 대화 상자를 설정할 수 있습니다.  대화가 정의 되어 있는 리소스 파일 (.rc)에 이동 하 고 대화 상자의 정의의 시작 부분을 찾습니다.  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 두 번째 줄을 변경 합니다.  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 이 작업 않습니다; 자체 포함 된 컨트롤에 해당 패키지 완벽 하 게 호출 해야 `IsDialogMessage()` 하므로 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 특정 메시지를 처리할 수 않지만 다른 HWND 내부 이러한 컨트롤의 예는 직관적인 방식 제공 컨트롤을 변경 합니다.  
  
## <a name="subclass-hwndhost"></a>HwndHost 하위 클래스  
 다음 네임 스페이스를 가져옵니다.  
  
```  
namespace ManagedCpp  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Input;  
    using namespace System::Windows::Media;  
    using namespace System::Runtime::InteropServices;  
```  
  
 다음의 파생된 클래스를 만들어 <xref:System.Windows.Interop.HwndHost> 재정의 `BuildWindowCore` 및 `DestroyWindowCore` 메서드:  
  
```  
public ref class MyHwndHost : public HwndHost, IKeyboardInputSink {  
    private:  
        HWND dialog;  
  
    protected:   
        virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {  
            InitializeGlobals();   
            dialog = CreateDialog(hInstance,   
                MAKEINTRESOURCE(IDD_DIALOG1),   
                (HWND) hwndParent.Handle.ToPointer(),  
                (DLGPROC) About);   
            return HandleRef(this, IntPtr(dialog));  
        }  
  
        virtual void DestroyWindowCore(HandleRef hwnd) override {  
            // hwnd will be disposed for us  
        }  
```  
  
 사용 하는 여기에서 `CreateDialog` 컨트롤은 실제로 대화 상자를 만듭니다.  이 내부에서 호출 하는 첫 번째 방법 중 하나는 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], 몇 가지 일반적인 수행 해야 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 나중 정의한 함수를 호출 하 여 초기화 호출 `InitializeGlobals()`:  
  
```  
bool initialized = false;  
    void InitializeGlobals() {  
        if (initialized) return;  
        initialized = true;  
  
        // TODO: Place code here.  
        MSG msg;  
        HACCEL hAccelTable;  
  
        // Initialize global strings  
        LoadString(hInstance, IDS_APP_TITLE, szTitle, MAX_LOADSTRING);  
        LoadString(hInstance, IDC_TYPICALWIN32DIALOG, szWindowClass, MAX_LOADSTRING);  
        MyRegisterClass(hInstance);  
```  
  
### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>대화 상자 키를 처리 하려면 TranslateAccelerator 메서드를 재정의 합니다.  
 이 샘플을 실행 하는 경우 이제, 화면에 표시 되는 대화 상자 컨트롤을 얻을 수는 있지만 처리 하는 키보드의 모든 대화 상자가 기능 대화 상자는 무시 됩니다.  재정의 해야는 `TranslateAccelerator` 구현 (에서 제공 되는 `IKeyboardInputSink`, 인터페이스는 <xref:System.Windows.Interop.HwndHost> 구현)입니다.  이 메서드는 응용 프로그램이 WM_KEYDOWN 및 WM_SYSKEYDOWN 받으면 호출을 가져옵니다.  
  
```  
#undef TranslateAccelerator  
        virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
            ModifierKeys modifiers) override   
        {  
            ::MSG m = ConvertMessage(msg);  
  
            // Win32's IsDialogMessage() will handle most of our tabbing, but doesn't know   
            // what to do when it reaches the last tab stop  
            if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {  
                HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
                HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
                TraversalRequest^ request = nullptr;  
  
                if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {  
                    // this code should work, but there’s a bug with interop shift-tab in current builds                      
                    request = gcnew TraversalRequest(FocusNavigationDirection::Last);  
                }  
                else if (!GetKeyState(VK_SHIFT) && GetFocus() == lastTabStop) {  
                    request = gcnew TraversalRequest(FocusNavigationDirection::Next);  
                }  
  
                if (request != nullptr)  
                    return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);  
  
            }  
  
            // Only call IsDialogMessage for keys it will do something with.  
            if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {  
                switch (m.wParam) {  
                    case VK_TAB:  
                    case VK_LEFT:  
                    case VK_UP:  
                    case VK_RIGHT:  
                    case VK_DOWN:  
                    case VK_EXECUTE:  
                    case VK_RETURN:  
                    case VK_ESCAPE:  
                    case VK_CANCEL:  
                        IsDialogMessage(dialog, &m);  
                        // IsDialogMessage should be called ProcessDialogMessage --  
                        // it processes messages without ever really telling you  
                        // if it handled a specific message or not  
                        return true;  
                }  
            }  
  
            return false; // not a key we handled  
        }  
```  
  
 이 보다 자세한 설명을 사용할 수 있습니다 하나에 코드를 많이 합니다.  첫째, 사용 하 여 코드 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] 및 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] 매크로; 라는 매크로 이미는 해야 `TranslateAccelerator`, winuser.h에 정의 된:  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 정의할 수 있는지 확인 한 `TranslateAccelerator` 메서드 및 not는 `TranslateAcceleratorW` 메서드.  
  
 마찬가지로, 없는 관리 되지 않는 winuser.h 메시지와 관리 되는 모두 `Microsoft::Win32::MSG` 구조체입니다.  사용 하 여 두 구분할 수 있습니다는 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` 연산자입니다.  
  
```  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 모두 Msg 동일한 데이터를 모두 제공 되었으나는이 샘플에는 명확한 변환 루틴을 정의할 수 있도록 관리 되지 않는 정의 작업할 쉽게:  
  
```  
::MSG ConvertMessage(System::Windows::Interop::MSG% msg) {  
    ::MSG m;  
    m.hwnd = (HWND) msg.hwnd.ToPointer();  
    m.lParam = (LPARAM) msg.lParam.ToPointer();  
    m.message = msg.message;  
    m.wParam = (WPARAM) msg.wParam.ToPointer();  
  
    m.time = msg.time;  
  
    POINT pt;  
    pt.x = msg.pt_x;  
    pt.y = msg.pt_y;  
    m.pt = pt;  
  
    return m;  
}  
```  
  
 돌아가기 `TranslateAccelerator`합니다.  기본적으로 호출 하는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수 `IsDialogMessage` 최대한 많은 작업을 수행할 수 있지만 `IsDialogMessage` 대화 상자 외에 다른 동작에 대 한 액세스가 없습니다. 포커스를 설정 해야 하는 대화 상자에서 이동할 때 주위 사용자 탭이 대화 상자에서 마지막 컨트롤 실행 되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 호출 하 여 부분 `IKeyboardInputSite::OnNoMoreStops`합니다.  
  
```  
// Win32's IsDialogMessage() will handle most of the tabbing, but doesn't know   
// what to do when it reaches the last tab stop  
if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {  
    HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
    HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
    TraversalRequest^ request = nullptr;  
  
    if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {  
        request = gcnew TraversalRequest(FocusNavigationDirection::Last);  
    }  
    else if (!GetKeyState(VK_SHIFT) && GetFocus() ==  lastTabStop) { {  
        request = gcnew TraversalRequest(FocusNavigationDirection::Next);  
    }  
  
    if (request != nullptr)  
        return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);  
}  
```  
  
 마지막으로 `IsDialogMessage`를 호출합니다.  하지만의 업무 중 하나는 `TranslateAccelerator` 메서드 보면서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 키 입력 처리 여부. 처리 하지 않은 경우에 입력된 이벤트 터널링 할 수 있습니다 및 응용 프로그램의 나머지 부분에 버블링 됩니다. 키보드 기초적인 처리와 특성에 입력된 아키텍처에는 노출 여기서 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]합니다. 그러나 `IsDialogMessage` 특정 키를 처리 하는지 여부를 어떤 방식으로든에서 반환 하지 않습니다.  설상가상으로 호출 합니다 `DispatchMessage()` 처리 하지 않도록 하는 키 입력에!  리버스 엔지니어링 필요가 `IsDialogMessage`만 알고 있는 키를 처리할에 대 한 호출:  
  
```  
// Only call IsDialogMessage for keys it will do something with.  
if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {  
    switch (m.wParam) {  
        case VK_TAB:  
        case VK_LEFT:  
        case VK_UP:  
        case VK_RIGHT:  
        case VK_DOWN:  
        case VK_EXECUTE:  
        case VK_RETURN:  
        case VK_ESCAPE:  
        case VK_CANCEL:  
            IsDialogMessage(dialog, &m);  
            // IsDialogMessage should be called ProcessDialogMessage --  
            // it processes messages without ever really telling you  
            // if it handled a specific message or not  
            return true;  
    }  
```  
  
### <a name="override-tabinto-method-to-support-tabbing"></a>탭 이동을 지원 하려면 TabInto 메서드를 재정의 합니다.  
 구현 했으므로 `TranslateAccelerator`, 사용자는 대화 상자 내 주위 탭 수 상자와 탭 옵트아웃 큼에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  하지만 대화 상자에 다시 사용자 탭 수 없습니다.  재정의 하는 문제를 해결 하려면 `TabInto`:  
  
```  
public:   
    virtual bool TabInto(TraversalRequest^ request) override {  
        if (request->FocusNavigationDirection == FocusNavigationDirection::Last) {  
            HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
            SetFocus(lastTabStop);  
        }  
        else {  
            HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
            SetFocus(firstTabStop);  
        }  
        return true;  
    }  
```  
  
 `TraversalRequest` 매개 변수를 알려 탭 또는 shift 탭 탭 작업 인지 합니다.  
  
### <a name="override-onmnemonic-method-to-support-mnemonics"></a>니모닉을 지원 하도록 OnMnemonic 메서드 재정의  
 키보드 처리 거의 완료 되었습니다. 하지만 하나도 가지 빠진 니모닉 작동 하지 않습니다.  포커스 doe로 이동 하지 않습니다는 사용자가 alt + F를 누르면는 "이름:" 상자를 편집 합니다. 재정의 하는 등의 `OnMnemonic` 메서드:  
  
```  
virtual bool OnMnemonic(System::Windows::Interop::MSG% msg, ModifierKeys modifiers) override {  
    ::MSG m = ConvertMessage(msg);  
  
    // If it's one of our mnemonics, set focus to the appropriate hwnd  
    if (msg.message == WM_SYSCHAR && GetKeyState(VK_MENU /*alt*/)) {  
        int dialogitem = 9999;  
        switch (m.wParam) {  
            case 's': dialogitem = IDOK; break;  
            case 'c': dialogitem = IDCANCEL; break;  
            case 'f': dialogitem = IDC_EDIT1; break;  
            case 'l': dialogitem = IDC_EDIT2; break;  
            case 'p': dialogitem = IDC_EDIT3; break;  
            case 'a': dialogitem = IDC_EDIT4; break;  
            case 'i': dialogitem = IDC_EDIT5; break;  
            case 't': dialogitem = IDC_EDIT6; break;  
            case 'z': dialogitem = IDC_EDIT7; break;  
        }  
        if (dialogitem != 9999) {  
            HWND hwnd = GetDlgItem(dialog, dialogitem);  
            SetFocus(hwnd);  
            return true;  
        }  
    }  
    return false; // key unhandled  
};  
```  
  
 호출 하지 않는 이유 `IsDialogMessage` 여기?  알릴 수 있게 되기를 원하는-하기 전에 동일한 문제가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 여부, 사용자 코드 처리 키 입력으로 처리 되는지를 코드 및 `IsDialogMessage` 할 수 없습니다.  또한 두 번째 문제 때문에 않습니다 `IsDialogMessage` 니모닉 포커스가 지정 된 HWND 대화 상자 안에 없는 경우 처리를 거부 합니다.  
  
### <a name="instantiate-the-hwndhost-derived-class"></a>인스턴스화하는 HwndHost 파생 클래스  
 마지막으로, 모든 키 및 탭 지원이 이면 했으므로 넣을 수 있습니다 프로그램 <xref:System.Windows.Interop.HwndHost> 를 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  주 응용 프로그램에서 작성 된 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 빈 상태로 유지 하는 적절 한 위치에 배치 하는 가장 쉬운 방법은 <xref:System.Windows.Controls.Border> 배치 하려면 요소는 <xref:System.Windows.Interop.HwndHost>합니다.  만들 여기는 <xref:System.Windows.Controls.Border> 라는 `insertHwndHostHere`:  
  
```  
<Window x:Class="WPFApplication1.Window1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    Title="Windows Presentation Framework Application"  
    Loaded="Window1_Loaded"  
    >  
    <StackPanel>  
        <Button Content="WPF button"/>  
        <Border Name="insertHwndHostHere" Height="200" Width="500"/>  
        <Button Content="WPF button"/>  
    </StackPanel>  
</Window>  
```  
  
 다음 남았습니다 좋은 위치를 인스턴스화하는 코드 시퀀스에서 찾을 수는 <xref:System.Windows.Interop.HwndHost> 에 연결 된 <xref:System.Windows.Controls.Border>합니다.  이 예제에서는 넣는 것에 대 한 생성자 내부는 <xref:System.Windows.Window> 파생 클래스:  
  
```  
public partial class Window1 : Window {  
    public Window1() {  
    }  
  
    void Window1_Loaded(object sender, RoutedEventArgs e) {  
        HwndHost host = new ManagedCpp.MyHwndHost();  
        insertHwndHostHere.Child = host;  
    }  
}  
```  
  
 제공합니다.  
  
 ![WPF 응용 프로그램 스크린 샷](../../../../docs/framework/wpf/advanced/media/interoparch09.PNG "InteropArch09")  
  
## <a name="see-also"></a>참고 항목  
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
