---
title: '연습: WPF에서 Windows Forms 복합 컨트롤 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 5868ee8c5b781d5af75349a5950f7e1e1680d74d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>연습: WPF에서 Windows Forms 복합 컨트롤 호스팅
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다. 그러나에 있는 경우 상당한 투자 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 코드는 것이 보다 효율적으로 이라도 다시 사용을 코드의 일부 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램이 처음부터 다시 작성 하기 보다는 합니다. 가장 일반적인 시나리오는 기존 Windows Forms 컨트롤이 있는 경우입니다. 경우에 따라 이러한 컨트롤에 대한 소스 코드에 액세스하지 못할 수도 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이러한 컨트롤을 호스팅하기 위한 간단한 프로시저를 제공는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다. 사용할 수는 예를 들어 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 대부분의에서 특수화 된 호스팅하면서 프로그래밍에 대 한 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다.  
  
 이 연습 단계에서 데이터 입력을 수행 하 여 복합 Windows Forms 컨트롤을 호스팅하는 응용 프로그램을 통해 한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다. 복합 컨트롤은 DLL로 패키지됩니다. 이 일반적인 절차는 더 복잡한 응용 프로그램 및 컨트롤로 확장할 수 있습니다. 이 연습에서 모양과 기능을 거의 동일한 [연습: Windows Forms에서 WPF 합성 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)합니다. 주요 차이점은 호스팅 시나리오가 반대라는 점입니다.  
  
 이 연습은 두 개의 섹션으로 구분됩니다. 첫 번째 섹션 복합 Windows Forms 컨트롤의 구현을 간략하게 설명합니다. 두 번째 섹션에서 복합 컨트롤을 호스트 하는 방법을 자세히 설명 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 컨트롤에서 이벤트를 수신 및 컨트롤의 속성 중 일부에 액세스 합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   Windows Forms 복합 컨트롤 구현  
  
-   WPF 호스트 응용 프로그램 구현  
  
 이 연습에서 설명 하는 작업의 전체 코드 목록을 보려면 [WPF 샘플에서 Windows Forms 합성 컨트롤 호스팅](http://go.microsoft.com/fwlink/?LinkID=159999)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="implementing-the-windows-forms-composite-control"></a>Windows Forms 복합 컨트롤 구현  
 이 예제에서 사용 하 여 Windows Forms 복합 컨트롤에는 간단한 데이터 입력 형태입니다. 이 폼에서는 사용자의 이름 및 주소를 사용한 다음 사용자 지정 이벤트를 사용하여 해당 정보를 호스트에 반환합니다. 다음 그림에서는 렌더링된 컨트롤을 보여 줍니다.  
  
 ![단순 Windows Forms 컨트롤](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")  
Windows Forms 복합 컨트롤  
  
### <a name="creating-the-project"></a>프로젝트 만들기  
 프로젝트를 시작하려면  
  
1.  시작 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], 열 및는 **새 프로젝트** 대화 상자.  
  
2.  창의 범주에서 선택 된 **Windows Forms 컨트롤 라이브러리** 템플릿.  
  
3.  새 프로젝트의 이름을 `MyControls`로 지정합니다.  
  
4.  위치에 대 한 최상위 폴더를 편리 하 게 명명 된 같은 지정한 `WpfHostingWindowsFormsControl`합니다. 나중에 이 폴더에 호스트 응용 프로그램을 넣습니다.  
  
5.  **확인**을 클릭해 프로젝트를 만듭니다. 라는 단일 컨트롤을 포함 하는 기본 프로젝트 `UserControl1`합니다.  
  
6.  솔루션 탐색기에서 이름을 바꿀 `UserControl1` 를 `MyControl1`합니다.  
  
 프로젝트에는 다음과 같은 시스템 DLL에 대한 참조가 있어야 합니다. 이러한 DLL이 기본적으로 포함되지 않은 경우 프로젝트에 추가합니다.  
  
-   시스템  
  
-   System.Data  
  
-   System.Drawing  
  
-   System.Windows.Forms  
  
-   System.Xml  
  
### <a name="adding-controls-to-the-form"></a>폼에 컨트롤 추가  
 폼에 컨트롤을 추가하려면  
  
-   열기 `MyControl1` 디자이너에서 합니다.  
  
 다섯 개의 <xref:System.Windows.Forms.Label> 컨트롤과 해당 <xref:System.Windows.Forms.TextBox> 컨트롤, 크기 및 폼에 앞의 그림에 있는 것 처럼 정렬 합니다. 예제에서는 <xref:System.Windows.Forms.TextBox> 컨트롤에 이름이 지정 됩니다.  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 두 개의 추가 <xref:System.Windows.Forms.Button> 레이블이 표시 컨트롤 **확인** 및 **취소**합니다. 예제에서는 단추 이름이 `btnOK` 및 `btnCancel`각각.  
  
### <a name="implementing-the-supporting-code"></a>지원 코드 구현  
 코드 보기에서 폼을 엽니다. 컨트롤 사용자 지정을 발생 시켜 해당 호스트에 수집 된 데이터를 반환 `OnButtonClick` 이벤트입니다. 데이터는 이벤트 인수 개체에 포함되어 있습니다. 다음 코드에서는 이벤트 및 대리자 선언을 보여 줍니다.  
  
 `MyControl1` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 `MyControlEventArgs` 클래스는 호스트에 반환 될 정보를 포함 합니다.  
  
 다음 클래스를 폼에 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 사용자가 클릭할 때는 **확인** 또는 **취소** 단추를는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 만들기는 `MyControlEventArgs` 데이터를 포함 하는 개체를 발생 시킵니다는 `OnButtonClick` 이벤트입니다. 두 명의 처리기 간의 유일한 차이점은 이벤트 인수 `IsOK` 속성입니다. 이 속성을 통해 호스트는 클릭한 단추를 확인할 수 있습니다. 로 설정 된 `true` 에 대 한는 **확인** 단추 및 `false` 에 대 한는 **취소** 단추입니다. 다음 코드에서는 두 개의 단추 처리기를 보여 줍니다.  
  
 `MyControl1` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>어셈블리에 강력한 이름을 지정하고 어셈블리 빌드  
 이 어셈블리를 참조할 수는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서는, 강력한 이름이 있어야 합니다. 강력한 이름을 만들려면 Sn.exe와 키 파일을 만들고 프로젝트에 추가 합니다.  
  
1.  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 명령 프롬프트를 엽니다. 이렇게 하려면 클릭는 **시작** 메뉴를 선택한 후 **모든 프로그램/Microsoft Visual Studio 2010/Visual Studio 도구/Visual Studio 명령 프롬프트**합니다. 그러면 사용자 지정된 환경 변수가 있는 콘솔 창이 시작됩니다.  
  
2.  명령 프롬프트에서 사용 하 여는 `cd` 명령 프로젝트 폴더로 이동 합니다.  
  
3.  다음 명령을 실행하여 MyControls.snk라는 키 파일을 생성합니다.  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  프로젝트에서 키 파일을 포함 하려면 솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다. 프로젝트 디자이너에서 클릭는 **서명** 탭을는 **어셈블리에 서명** 확인란을 선택 하 고 다음 키 파일을 찾습니다.  
  
5.  솔루션을 빌드합니다. 빌드하면 MyControls.dll이라는 DLL이 생성됩니다.  
  
## <a name="implementing-the-wpf-host-application"></a>WPF 호스트 응용 프로그램 구현  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용 하 여 응용 프로그램 호스트는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤을 호스트 `MyControl1`합니다. 응용 프로그램 핸들이 `OnButtonClick` 컨트롤에서 데이터를 받을 이벤트입니다. 옵션 단추에서 컨트롤의 속성 중 일부를 변경할 수 있도록 하는 컬렉션에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다. 다음 그림에서는 완료된 응용 프로그램을 보여 줍니다.  
  
 ![WPF 페이지에 포함 된 컨트롤](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost")  
WPF 응용 프로그램에 포함된 컨트롤을 보여 주는 전체 응용 프로그램  
  
### <a name="creating-the-project"></a>프로젝트 만들기  
 프로젝트를 시작하려면  
  
1.  열기 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]를 선택 하 고 **새 프로젝트**합니다.  
  
2.  창의 범주에서 선택 된 **WPF 응용 프로그램** 템플릿.
  
3.  새 프로젝트의 이름을 `WpfHost`로 지정합니다.  
  
4.  위치에는 MyControls 프로젝트를 포함하는 동일한 최상위 폴더를 지정합니다.  
  
5.  **확인**을 클릭해 프로젝트를 만듭니다.  
  
 포함 된 DLL에 대 한 참조를 추가 해야 `MyControl1` 및 기타 어셈블리입니다.  
  
1.  솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 추가**합니다.  
  
2.  클릭는 **찾아보기** 탭을 MyControls.dll 포함 된 폴더로 이동 합니다. 이 연습에서 이 폴더는 MyControls\bin\Debug입니다.  
  
3.  MyControls.dll를 선택한 다음 클릭 **확인**합니다.  
  
4.  WindowsFormsIntegration.dll 라는 WindowsFormsIntegration 어셈블리에 대 한 참조를 추가 합니다.  
  
### <a name="implementing-the-basic-layout"></a>기본 레이아웃 구현  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 호스트의 응용 프로그램에서 MainWindow.xaml에서 구현 됩니다. 이 파일에 포함 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 레이아웃을 정의 하 고 Windows Forms 컨트롤을 호스트 하는 태그입니다. 응용 프로그램은 세 가지 영역으로 구분됩니다.  
  
-   **컨트롤 속성** 패널의 옵션 단추 호스팅된 컨트롤의 다양 한 속성을 수정 하는 데 사용할 수 있는 컬렉션을 포함 합니다.  
  
-   **데이터를 컨트롤에서에서** 몇 가지 들어 있는 패널 <xref:System.Windows.Controls.TextBlock> 호스팅된 컨트롤에서 데이터를 표시 하는 요소를 반환 합니다.  
  
-   호스트된 컨트롤 자체.  
  
 기본 레이아웃은 다음과 같은 XAML로 표시됩니다. 태그는 호스트에 `MyControl1` 이 예제에서 생략 되지만 나중에 설명 하겠습니다.  
  
 MainWindow.xaml의 XAML을 다음 코드로 바꿉니다. Visual Basic을 사용 하는 경우 클래스를 변경 `x:Class="MainWindow"`합니다.  
  
 [!code-xaml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 첫 번째 <xref:System.Windows.Controls.StackPanel> 요소 집합이 여러 개 포함 <xref:System.Windows.Controls.RadioButton> 호스팅된 컨트롤의 다양 한 기본 속성을 수정할 수 있도록 하는 컨트롤입니다. 이 뒤에 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 호스팅하고 `MyControl1`합니다. 최종 <xref:System.Windows.Controls.StackPanel> 몇 가지 요소 들어 <xref:System.Windows.Controls.TextBlock> 호스팅된 컨트롤에서 반환 되는 데이터를 표시 하는 요소입니다. 요소를 정렬 및 <xref:System.Windows.Controls.DockPanel.Dock%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 특성 설정을 간격이 나 왜곡 없이으로 구성 된 창에 호스트 된 컨트롤을 포함 합니다.  
  
#### <a name="hosting-the-control"></a>컨트롤 호스팅  
 필요한 요소를 중점적으로 편집한 다음 버전에서는 이전 XAML의 호스트에 `MyControl1`합니다.  
  
 [!code-xaml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xaml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 `xmlns` 네임 스페이스 매핑 특성에 대 한 참조를 만듭니다.는 `MyControls` 호스팅된 컨트롤이 있는 네임 스페이스입니다. 이 매핑을 사용 하 여 나타내기 위해 `MyControl1` 에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 으로 `<mcl:MyControl1>`합니다.  
  
 XAML의 두 요소가 호스팅을 처리합니다.  
  
-   `WindowsFormsHost` 나타냅니다는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 에 Windows Forms 컨트롤을 호스트할 수 있도록 하는 요소는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  
  
-   `mcl:MyControl1`를 나타내는 `MyControl1`에 추가 되는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 자식 컬렉션입니다. 이 Windows Forms 컨트롤의 일부로 렌더링 되는 결과적으로,는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 창, 응용 프로그램에서 제어와 통신할 수 있습니다.  
  
### <a name="implementing-the-code-behind-file"></a>코드 숨김 파일 구현  
 기능을 구현 하는 절차적 코드를 포함 하는 코드 숨김 파일의 MainWindow.xaml.vb 또는 MainWindow.xaml.cs는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 이전 섹션에서 설명 합니다. 기본 작업은 다음과 같습니다.  
  
-   이벤트 처리기를 연결 `MyControl1`의 `OnButtonClick` 이벤트입니다.  
  
-   다양 한 속성을 수정 `MyControl1`옵션 단추 모음을 설정 하는 방법에 따라 합니다.  
  
-   컨트롤에서 수집한 데이터 표시.  
  
#### <a name="initializing-the-application"></a>응용 프로그램 초기화  
 초기화 코드 창에 대 한 이벤트 처리기에 포함 된 <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 컨트롤의 이벤트 처리기를 연결 하 고 `OnButtonClick` 이벤트입니다.  
  
 MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 다음 코드를 추가 `MainWindow` 클래스입니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 때문에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이전에 추가한 설명 `MyControl1` 에 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 캐스팅할 수 요소의 자식 요소 컬렉션의 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 에 대 한 참조를 얻으려고 `MyControl1`합니다. 이벤트 처리기를 연결 하려면 해당 참조를 사용 다음 `OnButtonClick`합니다.  
  
 컨트롤 자체에 대 한 참조를 제공할 뿐 아니라 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 다양 한 응용 프로그램에서 조작할 수 있는 컨트롤의 속성을 노출 합니다. 초기화 코드는 나중에 응용 프로그램에서 사용할 수 있도록 private 전역 변수에 해당 값을 할당합니다.  
  
 형식에 쉽게 액세스할 수 있도록는 `MyControls` DLL의 경우 다음 추가 `Imports` 또는 `using` 문을 파일의 맨 위에 있습니다.  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### <a name="handling-the-onbuttonclick-event"></a>OnButtonClick 이벤트 처리  
 `MyControl1` 발생는 `OnButtonClick` 이벤트 사용자가 컨트롤의 단추 중 하나를 클릭 합니다.  
  
 `MainWindow` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 텍스트 상자에 데이터 압축은 `MyControlEventArgs` 개체입니다. 사용자가 클릭할 경우의 **확인** 단추 이벤트 처리기 데이터를 추출 하 고 아래쪽 패널에 표시 `MyControl1`합니다.  
  
#### <a name="modifying-the-controls-properties"></a>컨트롤의 속성 수정  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 몇 가지 호스팅된 컨트롤의 기본 속성을 노출 합니다. 결과적으로 응용 프로그램의 스타일과 더 가깝게 일치하도록 컨트롤의 모양을 변경할 수 있습니다. 왼쪽 패널의 옵션 단추 집합을 사용하여 사용자는 여러 가지 색 및 글꼴 속성을 수정할 수 있습니다. 단추의 각 집합에 대 한 처리기는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 사용자의 옵션 단추 선택 항목을 검색 하 고 컨트롤에 해당 속성을 변경 합니다.  
  
 `MainWindow` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 응용 프로그램을 빌드 및 실행합니다. 합성 Windows Forms 컨트롤의 텍스트를 추가 하 고 클릭 **확인**합니다. 텍스트가 레이블에 나타납니다. 컨트롤에 대한 효과를 확인하려면 다른 라디오 단추를 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [연습: WPF에서 Windows Forms 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
