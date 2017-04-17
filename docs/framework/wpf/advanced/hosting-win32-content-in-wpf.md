---
title: "WPF에서 Win32 콘텐츠 호스팅 | Microsoft Docs"
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
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# WPF에서 Win32 콘텐츠 호스팅
## 사전 요구 사항  
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)를 참조하십시오.  
  
## Windows Presentation Foundation 내의 Win32에 대한 연습\(HwndHost\)  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 내부의 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 콘텐츠를 다시 사용하려면 HWND를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠처럼 보이게 만드는 <xref:System.Windows.Interop.HwndHost> 컨트롤을 사용합니다.  <xref:System.Windows.Interop.HwndSource>와 마찬가지로 <xref:System.Windows.Interop.HwndHost>도 사용하기가 쉽습니다. 먼저 <xref:System.Windows.Interop.HwndHost>에서 파생시키고 `BuildWindowCore` 및 `DestroyWindowCore` 메서드를 구현한 다음 <xref:System.Windows.Interop.HwndHost> 파생 클래스를 인스턴스화하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 내부에 배치합니다.  
  
 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 논리가 이미 컨트롤로 패키지된 경우에는 `CreateWindow` 호출과 약간의 추가 작업으로 `BuildWindowCore`를 구현할 수 있습니다.  예를 들어 다음과 같은 방법으로 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]에서 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX 컨트롤을 만들 수 있습니다.  
  
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
  
 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 코드만으로는 부족하다고 느껴지는 경우에는  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 대화 상자를 만들고 해당 콘텐츠를 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 포함시킬 수 있습니다.  이 방법을 보여 주는 샘플이 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 및 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]에 있기는 하지만 다른 언어나 명령줄을 통해서도 이 작업을 수행할 수 있습니다.  
  
 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 프로젝트로 컴파일되는 간단한 대화 상자로 시작합니다.  
  
 그런 다음 이 대화 상자를 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 포함시킵니다.  
  
-   [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]을 관리되는 상태로 컴파일\(`/clr`\)  
  
-   대화 상자를 컨트롤로 변환  
  
-   `BuildWindowCore` 및 `DestroyWindowCore` 메서드로 <xref:System.Windows.Interop.HwndHost> 파생 클래스 정의  
  
-   `TranslateAccelerator` 메서드가 대화 상자 키를 처리하도록 재정의  
  
-   `TabInto` 메서드가 탭 기능을 지원하도록 재정의  
  
-   `OnMnemonic` 메서드가 니모닉을 지원하도록 재정의  
  
-   <xref:System.Windows.Interop.HwndHost> 서브클래스를 인스턴스화하여 올바른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 아래에 배치  
  
### 대화 상자를 컨트롤로 변환  
 WS\_CHILD 및 DS\_CONTROL 스타일을 사용하여 대화 상자를 자식 HWND로 변환할 수 있습니다.  대화 상자가 정의되어 있는 리소스 파일\(.rc\)로 이동하여 대화 상자 정의의 시작 부분을 찾습니다.  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 두 번째 줄을 다음과 같이 변경합니다.  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 이 작업은 독립적으로 유지되는 컨트롤로 완전히 패키지되지 않기 때문에 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]에서 특정 메시지를 처리하려면 여전히 `IsDialogMessage()`를 호출해야 합니다. 하지만 컨트롤을 변경하면 이러한 컨트롤을 다른 HWND 내부에 간편하게 배치할 수 있습니다.  
  
## 서브클래스 HwndHost  
 다음 네임스페이스를 가져옵니다.  
  
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
  
 그런 다음 <xref:System.Windows.Interop.HwndHost>의 파생 클래스를 만들고 `BuildWindowCore` 및 `DestroyWindowCore` 메서드를 재정의합니다.  
  
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
  
 여기에서 `CreateDialog`를 사용하여 대화 상자를 만듭니다. 실제로 이 대화 상자가 컨트롤입니다.  이 메서드는 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 내부에서 처음 호출되는 메서드 중 하나이므로 이후의 과정에서 정의하게 될 `InitializeGlobals()`이라는 함수를 호출하여 몇 가지 표준 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 초기화를 수행해야 합니다.  
  
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
  
### TranslateAccelerator 메서드가 대화 상자 키를 처리하도록 재정의  
 지금 이 샘플을 실행하면 화면에 표시되는 대화 상자 컨트롤을 얻을 수 있지만 대화 상자의 기능을 수행하는 모든 키보드 처리가 무시됩니다.  따라서 `TranslateAccelerator` 구현\(<xref:System.Windows.Interop.HwndHost>가 구현하는 인터페이스인 `IKeyboardInputSink`에서 파생됨\)을 재정의해야 합니다.  이 메서드는 응용 프로그램이 WM\_KEYDOWN 및 WM\_SYSKEYDOWN 메시지를 받으면 호출됩니다.  
  
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
  
 이는 많은 코드가 하나에 포함되어 있는 것이므로 보다 자세한 설명을 사용할 수 있습니다.  먼저 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] 및 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] 매크로를 사용하는 코드가 있습니다. winuser.h에 정의되어 있는 `TranslateAccelerator`라는 매크로가 이미 있다는 것을 알아야 합니다.  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 따라서 `TranslateAcceleratorW` 메서드가 아니라 `TranslateAccelerator` 메서드를 정의해야 합니다.  
  
 마찬가지로 관리되지 않는 winuser.h MSG와 관리되는 `Microsoft::Win32::MSG` struct가 모두 있습니다.  이 둘은 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` 연산자를 사용하여 구분할 수 있습니다.  
  
```  
  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 두 MSG 모두 동일한 데이터를 사용하지만 관리되지 않는 정의로 작업하는 것이 쉬운 경우가 있으므로 이 샘플에서는 명확한 변환 루틴을 정의할 수 있습니다.  
  
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
  
 `TranslateAccelerator`로 돌아갑니다.  기본 원칙은 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수인 `IsDialogMessage`를 호출하여 가능한 한 많은 작업을 수행하는 것이지만 `IsDialogMessage`로는 대화 상자 외부에 있는 항목에 액세스할 수 없습니다. 사용자가 대화 상자에서 탭 기능을 사용하다 보면 대화 상자의 마지막 컨트롤을 지나게 되므로 `IKeyboardInputSite::OnNoMoreStops`를 호출하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 부분에 포커스를 설정해야 합니다.  
  
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
  
 마지막으로 `IsDialogMessage`를 호출합니다.  하지만 `TranslateAccelerator` 메서드가 수행해야 하는 기능 중 하나는 사용자가 키 입력을 처리했는지 여부를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 알리는 것입니다.  사용자가 키 입력을 처리하지 않는 경우 입력 이벤트가 응용 프로그램의 다른 부분으로 전달되어 예기치 않게 처리될 수 있습니다.  여기에서는 기초적인 키보드 메시지 처리와 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]의 입력 아키텍처 특성에 대해 다룹니다.  그러나 아쉽게도 `IsDialogMessage`에는 특정 키 입력이 처리되었는지 여부를 반환하는 방법이 없습니다.  더 나쁜 것은 처리해서는 안 되는 키 입력에 대해서 `DispatchMessage()`를 호출한다는 것입니다.  따라서 `IsDialogMessage`를 리버스 엔지니어링하여 처리가 필요한 키에 대해서만 호출되게 만들어야 합니다.  
  
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
  
### TabInto 메서드가 탭 기능을 지원하도록 재정의  
 이제 `TranslateAccelerator`를 구현했습니다. 사용자는 대화 상자 내부에서 탭 기능을 사용할 수 있으며 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램으로 탭 기능을 확장할 수 있습니다.  하지만 탭 기능을 사용하여 대화 상자로 돌아올 수 없습니다.  이 문제를 해결하려면 `TabInto`를 재정의합니다.  
  
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
  
 `TraversalRequest` 매개 변수는 탭 작업이 Tab인지 Shift\+Tab인지를 알려 줍니다.  
  
### OnMnemonic 메서드가 니모닉을 지원하도록 재정의  
 키보드 처리가 거의 완료되었지만 한 가지 빠진 것이 있습니다. 바로 니모닉이 작동하지 않는 것입니다.  사용자가 Alt\-F를 눌러도 포커스가 "이름:" 입력란으로 이동하지 않습니다.  따라서 `OnMnemonic` 메서드를 재정의해야 합니다.  
  
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
  
 여기서 `IsDialogMessage`를 호출하지 않는 이유는 무엇일까요?  그것은 이전과 같은 문제가 있기 때문입니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 코드에 키 입력을 처리했는지 여부를 알릴 수 있어야 하지만 `IsDialogMessage`는 그러한 작업을 수행할 수 없습니다.  그리고 한 가지 문제가 더 있습니다. 포커스가 있는 HWND가 대화 상자 내부에 있지 않으면 `IsDialogMessage`는 니모닉 처리를 거부합니다.  
  
### HwndHost 파생 클래스 인스턴스화  
 드디어 모든 키 및 탭 지원이 추가되었습니다. 이제 <xref:System.Windows.Interop.HwndHost>를 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 포함시킬 수 있습니다.  주 응용 프로그램이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]로 작성된 경우 이를 올바른 위치에 배치하는 가장 쉬운 방법은 <xref:System.Windows.Interop.HwndHost>를 배치하려는 위치에 빈 <xref:System.Windows.Controls.Border> 요소를 남겨 두는 것입니다.  여기에서는 `insertHwndHostHere`라는 <xref:System.Windows.Controls.Border>를 만듭니다.  
  
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
  
 이제 남은 작업은 코드 시퀀스에서 <xref:System.Windows.Interop.HwndHost>를 인스턴스화하고 <xref:System.Windows.Controls.Border>에 연결할 위치를 결정하는 것입니다.  이 예제에서는 <xref:System.Windows.Window> 파생 클래스에 대한 생성자 내부에 배치합니다.  
  
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
  
 결과는 다음과 같습니다.  
  
 ![WPF 응용 프로그램 스크린 샷](../../../../docs/framework/wpf/advanced/media/interoparch09.png "InteropArch09")  
  
## 참고 항목  
 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)