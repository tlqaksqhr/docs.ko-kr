---
title: "연습: WPF에서 Windows Forms 복합 컨트롤 호스팅 | Microsoft Docs"
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
  - "복합 컨트롤, WPF에서 호스팅"
  - "WPF에서 Windows Forms 컨트롤 호스팅"
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# 연습: WPF에서 Windows Forms 복합 컨트롤 호스팅
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다.  그러나 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 코드에 상당한 노력을 기울인 경우 이 코드를 처음부터 다시 작성하지 않고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 코드의 일부만이라도 다시 사용하는 것이 더 효율적일 수 있습니다.  기존 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤을 사용하는 것이 가장 일반적인 시나리오입니다.  경우에 따라 이러한 컨트롤의 소스 코드에 액세스하지 못할 수도 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 이러한 컨트롤을 호스팅하기 위한 간단한 프로시저를 제공합니다.  예를 들어 대부분의 프로그래밍에서 특수화된 <xref:System.Windows.Forms.DataGridView> 컨트롤을 호스팅할 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용할 수 있습니다.  
  
 이 연습에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 데이터 입력을 수행하기 위해 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 복합 컨트롤을 호스팅하는 과정을 단계별로 설명합니다.  복합 컨트롤은 DLL 파일로 패키지됩니다.  이러한 일반 절차를 확장하여 보다 복잡한 응용 프로그램과 컨트롤에 적용할 수 있습니다.  이 연습에서 다루는 복합 컨트롤은 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)의 복합 컨트롤과 모양 및 기능이 매우 비슷하게 디자인되었습니다.  주된 차이점은 호스팅 시나리오가 반대로 되어 있다는 것입니다.  
  
 이 연습은 두 단원으로 나뉘어져 있습니다.  첫 번째 단원에서는 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 복합 컨트롤의 구현에 대해 간략히 설명합니다.  두 번째 단원에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 이 복합 컨트롤을 호스팅하고 컨트롤의 이벤트를 수신하고 컨트롤의 일부 속성에 액세스하는 방법에 대해 자세히 설명합니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   Windows Forms 복합 컨트롤 구현  
  
-   WPF 호스트 응용 프로그램 구현  
  
 이 연습에서 설명하는 작업의 전체 코드 목록은 [Hosting a Windows Forms Composite Control in WPF 샘플](http://go.microsoft.com/fwlink/?LinkID=159999)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Windows Forms 복합 컨트롤 구현  
 이 예제에서 사용하는 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 복합 컨트롤은 간단한 데이터 입력 폼입니다.  이 폼에서는 사용자의 이름과 주소를 입력으로 받고 사용자 지정 이벤트를 사용하여 해당 정보를 호스트에 반환합니다.  다음 그림에서는 렌더링된 컨트롤을 보여 줍니다.  
  
 ![단순 Windows Forms 컨트롤](../../../../docs/framework/wpf/advanced/media/wfcontrol.png "WFControl")  
Windows Forms 복합 컨트롤  
  
### 프로젝트 만들기  
 프로젝트를 시작하려면  
  
1.  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]을 시작하고 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  Windows 범주에서 **Windows Forms 컨트롤 라이브러리** 템플릿을 선택합니다.  
  
3.  새 프로젝트의 이름을 `MyControls`로 지정합니다.  
  
4.  위치로는 `WpfHostingWindowsFormsControl`과 같은 편리한 이름의 최상위 폴더를 지정합니다.  나중에 호스트 응용 프로그램도 이 폴더에 넣습니다.  
  
5.  **확인**을 클릭하여 프로젝트를 만듭니다.  기본 프로젝트에는 `UserControl1`이라는 컨트롤 하나가 포함되어 있습니다.  
  
6.  솔루션 탐색기에서 `UserControl1`의 이름을 `MyControl1`로 변경합니다.  
  
 이 프로젝트에서는 다음과 같은 시스템 DLL에 대한 참조를 포함해야 합니다.  이러한 DLL이 기본적으로 포함되지 않는 경우 프로젝트에 추가합니다.  
  
-   시스템  
  
-   System.Data  
  
-   System.Drawing  
  
-   System.Windows.Forms  
  
-   System.Xml  
  
### 폼에 컨트롤 추가  
 폼에 컨트롤을 추가하려면  
  
-   디자이너에서 `MyControl1`을 엽니다.  
  
 다섯 개의 <xref:System.Windows.Forms.Label> 컨트롤과 해당하는 <xref:System.Windows.Forms.TextBox> 컨트롤을 앞의 그림과 같이 크기 조정 및 정렬하여 폼에 배치합니다.  이 예제에서는 <xref:System.Windows.Forms.TextBox> 컨트롤의 이름을 다음과 같이 지정합니다.  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 **OK** 및 **Cancel**이라는 레이블이 붙은 두 개의 <xref:System.Windows.Forms.Button> 컨트롤을 추가합니다.  이 예제에서 단추의 이름은 각각 `btnOK` 및 `btnCancel`입니다.  
  
### 지원 코드 구현  
 코드 뷰에서 폼을 엽니다.  컨트롤에서는 사용자 지정 `OnButtonClick` 이벤트를 발생시켜 수집한 데이터를 호스트에 반환합니다.  데이터는 이벤트 인수 개체에 포함되어 있습니다.  다음 코드에서는 이벤트 및 대리자 선언을 보여 줍니다.  
  
 `MyControl1` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 `MyControlEventArgs` 클래스에는 호스트에 반환할 정보가 포함됩니다.  
  
 폼에 다음 클래스를 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 사용자가 **OK** 또는 **Cancel** 단추를 클릭하면 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서 데이터를 포함하고 `OnButtonClick` 이벤트를 발생시키는 `MyControlEventArgs` 개체를 만듭니다.  두 처리기는 이벤트 인수의 `IsOK` 속성만 서로 다릅니다.  이 속성을 통해 호스트에서 클릭된 단추를 확인할 수 있습니다.  이 속성은 **OK** 단추를 클릭한 경우 `true`로 설정되고 **Cancel** 단추를 클릭한 경우 `false`로 설정됩니다.  다음 코드에서는 두 개의 단추 처리기를 보여 줍니다.  
  
 `MyControl1` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### 어셈블리에 강력한 이름 지정 및 어셈블리 빌드  
 이 어셈블리를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 참조하려면 어셈블리에 강력한 이름이 있어야 합니다.  강력한 이름을 만들려면 Sn.exe를 사용하여 키 파일을 만들고 프로젝트에 추가합니다.  
  
1.  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 명령 프롬프트를 엽니다.  이렇게 하려면 **시작** 메뉴를 클릭하고 **모든 프로그램\/Microsoft Visual Studio 2010\/Visual Studio Tools\/Visual Studio 명령 프롬프트**를 선택합니다.  그러면 사용자 지정된 환경 변수와 함께 콘솔 창이 시작됩니다.  
  
2.  명령 프롬프트에서 `cd` 명령을 사용하여 프로젝트 폴더로 이동합니다.  
  
3.  다음 명령을 실행하여 MyControls.snk라는 키 파일을 생성합니다.  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  키 파일을 프로젝트에 포함하려면 솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  프로젝트 디자이너에서 **서명** 탭을 클릭하고 **어셈블리 서명** 확인란을 선택한 다음 키 파일로 이동합니다.  
  
5.  솔루션을 빌드합니다.  이 빌드에서는 MyControls.dll이라는 DLL이 생성됩니다.  
  
## WPF 호스트 응용 프로그램 구현  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 호스트 응용 프로그램에서는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤을 사용하여 `MyControl1`을 호스트합니다.  이 응용 프로그램에서는 `OnButtonClick` 이벤트를 처리하여 컨트롤에서 데이터를 수신합니다.  또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 컨트롤의 일부 속성을 변경하는 데 사용할 수 있는 옵션 단추 컬렉션도 포함합니다.  다음 그림에서는 완료된 응용 프로그램을 보여 줍니다.  
  
 ![WPF 페이지에 포함된 컨트롤](../../../../docs/framework/wpf/advanced/media/avalonhost.png "AvalonHost")  
WPF 응용 프로그램에 포함된 컨트롤을 보여 주는 전체 응용 프로그램  
  
### 프로젝트 만들기  
 프로젝트를 시작하려면  
  
1.  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]를 열고 **새 프로젝트**를 선택합니다.  
  
2.  Window 범주에서 **WPF 응용 프로그램** 템플릿을 선택합니다.  
  
3.  새 프로젝트의 이름을 `WpfHost`로 지정합니다.  
  
4.  위치에서 MyControls 프로젝트가 포함된 동일한 최상위 폴더를 지정합니다.  
  
5.  **확인**을 클릭하여 프로젝트를 만듭니다.  
  
 또한 `MyControl1` 및 다른 어셈블리를 포함하는 DLL에 대한 참조도 추가해야 합니다.  
  
1.  솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.  
  
2.  **찾아보기** 탭을 클릭하고 MyControls.dll이 들어 있는 폴더로 이동합니다.  이 연습의 경우 이 폴더는 MyControls\\bin\\Debug입니다.  
  
3.  MyControls.dll을 선택하고 **확인**을 클릭합니다.  
  
4.  WindowsFormsIntegration.dll이라는 WindowsFormsIntegration 어셈블리에 대한 참조를 추가합니다.  
  
### 기본 레이아웃 구현  
 호스트 응용 프로그램의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]는 MainWindow.xaml에서 구현합니다.  이 파일은 레이아웃을 정의하는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 태그를 포함하며 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤을 호스팅합니다.  이 응용 프로그램은 다음과 같은 세 가지 영역으로 나뉘어 있습니다.  
  
-   **Control Properties** 패널 \- 호스팅된 컨트롤의 다양한 속성을 수정하는 데 사용할 수 있는 옵션 단추의 컬렉션을 포함합니다.  
  
-   **Data from Control** 패널 \- 호스팅된 컨트롤에서 반환된 데이터를 표시하는 여러 <xref:System.Windows.Controls.TextBlock> 요소를 포함합니다.  
  
-   호스팅된 컨트롤 자체  
  
 다음 XAML에서는 기본적인 레이아웃을 보여 줍니다.  `MyControl1`을 호스팅하는 데 필요한 태그는 이 예제에서 생략되었으며 나중에 설명합니다.  
  
 MyControl1.xaml의 XAML을 다음으로 바꿉니다.  Visual Basic을 사용하는 경우에는 클래스를 `x:Class="MainWindow"`로 변경합니다.  
  
 [!code-xml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 첫 번째 <xref:System.Windows.Controls.StackPanel> 요소에는 호스팅된 컨트롤의 다양한 기본 속성을 수정하는 데 사용할 수 있는 여러 <xref:System.Windows.Controls.RadioButton> 컨트롤 집합이 포함되어 있습니다.  그 다음에 오는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 `MyControl1`을 호스팅합니다.  마지막의 <xref:System.Windows.Controls.StackPanel> 요소에는 호스팅된 컨트롤에서 반환되는 데이터를 표시하는 여러 <xref:System.Windows.Controls.TextBlock> 요소가 포함됩니다.  요소 순서와 <xref:System.Windows.Controls.DockPanel.Dock%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 특성 설정에 따라 호스팅된 컨트롤이 창에 간격이나 왜곡 없이 포함됩니다.  
  
#### 컨트롤 호스팅  
 이전 XAML을 편집한 다음 버전에서는 `MyControl1`을 호스팅하는 데 필요한 요소를 중점적으로 보여 줍니다.  
  
 [!code-xml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 `xmlns` 네임스페이스 매핑 특성은 호스팅된 컨트롤을 포함하는 `MyControls` 네임스페이스에 대한 참조를 만듭니다.  이 매핑을 사용하여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 `MyControl1`을 `<mcl:MyControl1>`로 표시할 수 있습니다.  
  
 XAML에서 다음 두 요소가 호스팅을 처리합니다.  
  
-   `WindowsFormsHost`는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤을 호스팅하는 데 사용할 수 있는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 나타냅니다.  
  
-   `MyControl1`을 나타내는 `mcl:MyControl1`. 이 요소는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 자식 컬렉션에 추가합니다.  따라서 이 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 창의 일부로 렌더링되므로 응용 프로그램에서 이 컨트롤과 통신할 수 있습니다.  
  
### 코드 숨김 파일 구현  
 코드 숨김 파일인 MainWindow.xaml.vb 또는 MainWindow.xaml.cs에는 앞 단원에서 설명한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 기능을 구현하는 프로시저 코드를 포함합니다.  이 파일을 구현하기 위한 기본 작업은 다음과 같습니다.  
  
-   `MyControl1`의 `OnButtonClick` 이벤트에 이벤트 처리기 연결  
  
-   옵션 단추 컬렉션이 설정된 방법에 따라 `MyControl1`의 다양한 속성 수정  
  
-   컨트롤에서 수집한 데이터 표시  
  
#### 응용 프로그램 초기화  
 초기화 코드는 창의 <xref:System.Windows.FrameworkElement.Loaded> 이벤트에 대한 이벤트 처리기에 포함되며 컨트롤의 `OnButtonClick` 이벤트에 이벤트 처리기를 연결합니다.  
  
 MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 `MainWindow` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 앞에서 설명한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 `MyControl1`을 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 자식 요소 컬렉션에 추가했으므로 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A>를 캐스팅하여 `MyControl1`에 대한 참조를 가져올 수 있습니다.  그런 다음 해당 참조를 사용하여 `OnButtonClick`에 이벤트 처리기를 연결할 수 있습니다.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>는 컨트롤 자체에 대한 참조를 제공할 뿐만 아니라 응용 프로그램에서 조작할 수 있는 여러 컨트롤 속성을 노출합니다.  초기화 코드에서는 나중에 응용 프로그램에서 사용하기 위해 이러한 값을 private 전역 변수에 할당합니다.  
  
 `MyControls` DLL의 형식에 쉽게 액세스할 수 있도록 다음 `Imports` 또는 `using` 문을 파일의 맨 위에 추가합니다.  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### OnButtonClick 이벤트 처리  
 `MyControl1`에서는 사용자가 컨트롤의 단추 중 하나를 클릭할 때 `OnButtonClick` 이벤트가 발생합니다.  
  
 `MainWindow` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 텍스트 상자의 데이터는 `MyControlEventArgs` 개체에 채워집니다.  사용자가 **OK** 단추를 클릭하면 이벤트 처리기에서는 데이터를 추출하여 `MyControl1` 아래의 패널에 표시합니다.  
  
#### 컨트롤 속성 수정  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에서는 호스팅된 컨트롤의 여러 기본 속성을 노출합니다.  따라서 컨트롤의 모양을 페이지의 응용 프로그램 스타일에 더 가깝게 변경할 수 있습니다.  왼쪽 패널의 옵션 단추 집합을 사용하면 여러 색과 글꼴 속성을 수정할 수 있습니다.  각 단추 집합의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기에서는 사용자의 옵션 단추 선택을 감지하고 컨트롤의 해당하는 속성을 변경합니다.  
  
 `MainWindow` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 응용 프로그램을 빌드하고 실행합니다.  Windows Forms 복합 컨트롤에 텍스트를 추가하고 **확인**을 클릭합니다.  텍스트가 레이블에 나타납니다.  다른 라디오 단추를 클릭하여 컨트롤의 효과를 확인합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)   
 [연습: WPF에서 Windows Forms 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)