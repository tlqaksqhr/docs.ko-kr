---
title: "연습: Windows Forms에서 WPF 복합 컨트롤 호스팅 | Microsoft Docs"
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
  - "Windows Forms에서 WPF 콘텐츠 호스팅"
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# 연습: Windows Forms에서 WPF 복합 컨트롤 호스팅
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다.  그러나 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 코드에 상당한 노력을 기울인 경우 이 코드를 처음부터 다시 작성하지 않고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]을 사용하여 기존 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램을 확장하는 것이 더 효율적일 수 있습니다.  일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 구현한 하나 이상의 컨트롤을 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 응용 프로그램 내에 포함할 수 있습니다.  WPF 컨트롤 사용자 지정에 대한 자세한 내용은 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)을 참조하십시오.  
  
 이 연습에서는 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 응용 프로그램에서 데이터 입력을 수행하기 위한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤을 호스팅하는 응용 프로그램을 설명합니다.  복합 컨트롤은 DLL 파일로 패키지됩니다.  이러한 일반 절차를 확장하여 보다 복잡한 응용 프로그램과 컨트롤에 적용할 수 있습니다.  이 연습에서 다루는 복합 컨트롤은 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)의 복합 컨트롤과 모양 및 기능이 매우 비슷하게 디자인되었습니다.  주된 차이점은 호스팅 시나리오가 반대로 되어 있다는 것입니다.  
  
 이 연습은 두 단원으로 나뉘어져 있습니다.  첫 번째 단원에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤의 구현에 대해 간략히 설명합니다.  두 번째 단원에서는 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 응용 프로그램에서 이 복합 컨트롤을 호스팅하고 컨트롤의 이벤트를 수신하고 컨트롤의 일부 속성에 액세스하는 방법에 대해 자세히 설명합니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   WPF 복합 컨트롤 구현  
  
-   Windows Forms 호스트 응용 프로그램 구현  
  
 이 연습에서 설명하는 작업의 전체 코드 목록은 [Hosting a WPF Composite Control in Windows Forms 샘플](http://go.microsoft.com/fwlink/?LinkID=159996)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## WPF 복합 컨트롤 구현  
 이 예제에서 사용되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤은 사용자의 이름과 주소를 입력하는 간단한 데이터 입력 폼입니다.  사용자가 작업이 완료되었음을 나타내는 두 개의 단추 중 하나를 클릭하면 컨트롤에서 사용자 지정 이벤트가 발생하여 해당 정보가 호스트에 반환됩니다.  다음 그림에서는 렌더링된 컨트롤을 보여 줍니다.  
  
 ![간단한 WPF 컨트롤](../../../../docs/framework/wpf/advanced/media/avaloncontrol.png "AvalonControl")  
WPF 복합 컨트롤  
  
### 프로젝트 만들기  
 프로젝트를 시작하려면  
  
1.  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]을 시작하고 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  Visual C\# 및 Windows 범주에서 **WPF 사용자 정의 컨트롤 라이브러리** 템플릿을 선택합니다.  
  
3.  새 프로젝트의 이름을 `MyControls`로 지정합니다.  
  
4.  위치로는 `WindowsFormsHostingWpfControl`과 같은 편리한 이름의 최상위 폴더를 지정합니다.  나중에 호스트 응용 프로그램도 이 폴더에 넣습니다.  
  
5.  **확인**을 클릭하여 프로젝트를 만듭니다.  기본 프로젝트에는 `UserControl1`이라는 컨트롤 하나가 포함되어 있습니다.  
  
6.  솔루션 탐색기에서 `UserControl1`의 이름을 `MyControl1`로 변경합니다.  
  
 이 프로젝트에서는 다음과 같은 시스템 DLL에 대한 참조를 포함해야 합니다.  이러한 DLL이 기본적으로 포함되지 않는 경우 프로젝트에 추가합니다.  
  
-   PresentationCore  
  
-   PresentationFramework  
  
-   시스템  
  
-   WindowsBase  
  
### 사용자 인터페이스 만들기  
 이 복합 컨트롤의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]로 구현됩니다.  복합 컨트롤 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 다섯 개의 <xref:System.Windows.Controls.TextBox> 요소로 구성됩니다.  각 <xref:System.Windows.Controls.TextBox> 요소에는 레이블로 사용되는 <xref:System.Windows.Controls.TextBlock> 요소가 연결됩니다.  아래쪽에는 **확인** 및 **취소**라는 두 개의 <xref:System.Windows.Controls.Button> 요소가 있습니다.  사용자가 이 단추 중 하나를 클릭하면 컨트롤에서 사용자 지정 이벤트가 발생하여 호스트에 정보가 반환됩니다.  
  
#### 기본 레이아웃  
 다양한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소가 <xref:System.Windows.Controls.Grid> 요소에 포함됩니다.  <xref:System.Windows.Controls.Grid>를 사용하면 HTML의 `Table` 요소와 같은 방법으로 복합 컨트롤의 내용을 정렬할 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 <xref:System.Windows.Documents.Table> 요소도 있지만 <xref:System.Windows.Controls.Grid>가 더 가볍고 단순한 레이아웃 작업에 보다 적합합니다.  
  
 다음 XAML에서는 기본적인 레이아웃을 보여 줍니다.  이 XAML에서는 <xref:System.Windows.Controls.Grid> 요소의 열 및 행 수를 지정하여 컨트롤의 전체 구조를 정의합니다.  
  
 MyControl1.xaml에서 기존 XAML을 다음 XAML로 바꿉니다.  
  
 [!code-xml[WindowsFormsHostingWpfControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xml[WindowsFormsHostingWpfControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### 표에 TextBlock 및 TextBox 요소 추가  
 표 요소의 <xref:System.Windows.Controls.Grid.RowProperty> 및 <xref:System.Windows.Controls.Grid.ColumnProperty> 특성을 해당 행 및 열 번호로 설정하여 표에서 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 배치합니다.  행 및 열 번호는 0부터 시작합니다.  요소의 <xref:System.Windows.Controls.Grid.ColumnSpanProperty> 특성을 설정하면 요소가 여러 열에 걸쳐 있을 수 있습니다.  <xref:System.Windows.Controls.Grid> 요소에 대한 자세한 내용은 [Grid 요소 만들기](../../../../docs/framework/wpf/controls/how-to-create-a-grid-element.md)를 참조하십시오.  
  
 다음 XAML에서는 복합 컨트롤의 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.TextBlock> 요소를 보여 줍니다. 여기서는 요소의 <xref:System.Windows.Controls.Grid.RowProperty> 및 <xref:System.Windows.Controls.Grid.ColumnProperty> 특성을 설정하여 표에서 해당 요소를 적절히 배치합니다.  
  
 MyControl1.xaml에서 <xref:System.Windows.Controls.Grid> 요소 내에 다음 XAML을 추가합니다.  
  
 [!code-xml[WindowsFormsHostingWpfControl#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### UI 요소 스타일 지정  
 데이터 입력 폼의 요소는 대부분 모양이 비슷합니다. 즉, 이러한 요소의 여러 속성 설정이 동일합니다.  위의 XAML에서는 각 요소의 특성을 따로 설정하지 않고 <xref:System.Windows.Style> 요소를 사용하여 요소의 클래스에 대한 표준 속성 설정을 정의합니다.  이 방법을 사용하면 컨트롤의 복잡도를 줄이고 하나의 스타일 특성을 통해 여러 요소의 모양을 변경할 수 있습니다.  
  
 <xref:System.Windows.Style> 요소는 <xref:System.Windows.Controls.Grid> 요소의 <xref:System.Windows.FrameworkElement.Resources%2A> 속성에 포함되어 있으므로 컨트롤의 모든 요소에서 사용할 수 있습니다.  스타일의 이름을 지정하는 경우 요소에 스타일을 적용하려면 <xref:System.Windows.Style> 요소 집합을 해당 스타일 이름에 추가합니다.  이름을 지정하지 않은 스타일은 요소의 기본 스타일이 됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스타일에 대한 자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)를 참조하십시오.  
  
 다음 XAML에서는 복합 컨트롤의 <xref:System.Windows.Style> 요소를 보여 줍니다.  스타일이 요소에 어떻게 적용되는지 확인하려면 앞의 XAML을 참조하십시오.  예를 들어 마지막 <xref:System.Windows.Controls.TextBlock> 요소는 `inlineText` 스타일을 사용하고 마지막 <xref:System.Windows.Controls.TextBox> 요소는 기본 스타일을 사용합니다.  
  
 MyControl1.xaml에서 <xref:System.Windows.Controls.Grid> 시작 요소 바로 뒤에 다음 XAML을 추가합니다.  
  
 [!code-xml[WindowsFormsHostingWpfControl#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### 확인 및 취소 단추 추가  
 복합 컨트롤의 마지막 요소는 **확인** 및 **취소** <xref:System.Windows.Controls.Button> 요소입니다. 이들 요소는 <xref:System.Windows.Controls.Grid>의 마지막 행에서 처음 두 열을 사용합니다.  이러한 요소에서는 공용 이벤트 처리기 `ButtonClicked`와 앞의 XAML에서 정의한 기본 <xref:System.Windows.Controls.Button> 스타일을 사용합니다.  
  
 MyControl1.xaml에서 마지막 <xref:System.Windows.Controls.TextBox> 요소 뒤에 다음 XAML을 추가합니다.  이것으로 복합 컨트롤의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 부분을 완료했습니다.  
  
 [!code-xml[WindowsFormsHostingWpfControl#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### 코드 숨김 파일 구현  
 코드 숨김 파일 MyControl1.xaml.cs에서는 다음과 같은 세 가지 필수 작업을 구현합니다.  
  
1.  사용자가 단추 중 하나를 클릭할 때 발생하는 이벤트를 처리합니다.  
  
2.  <xref:System.Windows.Controls.TextBox> 요소에서 데이터를 검색하고 그 결과를 사용자 지정 이벤트 인수 개체에 패키지합니다.  
  
3.  `OnButtonClick` 이벤트를 발생시켜 사용자가 완료했음을 호스트에 알리고 데이터를 다시 호스트에 전달합니다.  
  
 또한 컨트롤에서는 모양을 변경하는 데 사용할 수 있는 많은 수의 색 및 글꼴 속성을 노출합니다.  [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤을 호스팅하는 데 사용되는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스와 달리 <xref:System.Windows.Forms.Integration.ElementHost> 클래스에서는 컨트롤의 <xref:System.Windows.Controls.Panel.Background%2A> 속성만 노출합니다.  이 코드 예제와 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)에서 설명하는 예제 사이의 유사성을 유지하기 위해 이 컨트롤에서는 나머지 속성을 직접 노출합니다.  
  
#### 코드 숨김 파일의 기본 구조  
 코드 숨김 파일은 하나의 네임스페이스 `MyControls`로 구성되며, 이 네임스페이스는 `MyControl1` 및 `MyControlEventArgs`라는 두 개의 클래스를 포함합니다.  
  
```  
  
namespace MyControls  
{  
  public partial class MyControl1 : Grid  
  {  
    //...  
  }  
  public class MyControlEventArgs : EventArgs  
  {  
    //...  
  }  
}  
  
```  
  
 첫 번째 클래스 `MyControl1`은 MyControl1.xaml에서 정의한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 기능을 구현하는 코드를 포함하는 partial 클래스입니다.  MyControl1.xaml을 구문 분석할 때 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]이 동일한 partial 클래스로 변환되고 두 partial 클래스가 병합되어 컴파일된 컨트롤을 형성합니다.  따라서 코드 숨김 파일의 코드 이름이 MyControl1.xaml에 할당된 클래스 이름과 일치해야 하며 컨트롤의 루트 요소에서 상속해야 합니다.  두 번째 클래스 `MyControlEventArgs`는 데이터를 다시 호스트에 보내는 데 사용되는 이벤트 인수 클래스입니다.  
  
 MyControl1.xaml.cs를 엽니다.  다음 이름을 갖고 <xref:System.Windows.Controls.Grid>에서 상속되도록 기존 클래스 선언을 변경합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### 컨트롤 초기화  
 다음 코드에서는 다음과 같은 몇 가지 기본 작업을 구현합니다.  
  
-   Private 이벤트 `OnButtonClick` 및 관련 대리자 `MyControlEventHandler`를 선언합니다.  
  
-   사용자 데이터를 저장하는 여러 private 전역 변수를 만듭니다.  이 데이터는 해당 속성을 통해 노출됩니다.  
  
-   컨트롤의 <xref:System.Windows.FrameworkElement.Loaded> 이벤트에 대한 `Init` 처리기를 구현합니다.  이 처리기에서는 MyControl1.xaml에서 정의한 값을 할당하여 전역 변수를 초기화합니다.  이를 위해 일반적인 <xref:System.Windows.Controls.TextBlock> 요소 `nameLabel`에 할당된 <xref:System.Windows.FrameworkElement.Name%2A>을 사용하여 해당 요소의 속성 설정에 액세스합니다.  
  
 기존 생성자를 삭제하고 `MyControl1` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### 단추의 클릭 이벤트 처리  
 사용자는 **확인** 단추나 **취소** 단추를 클릭하여 데이터 입력 작업을 완료했음을 표시합니다.  두 단추에서는 모두 동일한 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기 `ButtonClicked`를 사용합니다.  두 단추의 이름은 `btnOK` 또는 `btnCancel`입니다. 처리기에서 `sender` 인수의 값을 검사하여 어떤 단추가 클릭되었는지 확인할 때 이 이름을 사용합니다.  처리기에서 수행하는 작업은 다음과 같습니다.  
  
-   <xref:System.Windows.Controls.TextBox> 요소의 데이터를 포함하는 `MyControlEventArgs` 개체를 만듭니다.  
  
-   사용자가 **취소** 단추를 클릭하면 `MyControlEventArgs` 개체의 `IsOK` 속성을 `false`로 설정합니다.  
  
-   `OnButtonClick` 이벤트를 발생시켜 사용자가 완료했음을 호스트에 알리고 수집한 데이터를 다시 전달합니다.  
  
 `MyControl1` 클래스의 `Init` 메서드 뒤에 다음 코드를 추가합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### 속성 만들기  
 클래스의 나머지 부분에서는 위에서 설명한 전역 변수에 해당하는 속성을 노출하기만 합니다.  속성이 변경되면 set 접근자가 해당 요소 속성을 변경하고 기본 전역 변수를 업데이트하여 컨트롤 모양을 수정합니다.  
  
 `MyControl1` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### 데이터를 다시 호스트에 보내기  
 파일의 마지막 구성 요소는 수집한 데이터를 호스트에 다시 보내는 데 사용되는 `MyControlEventArgs` 클래스입니다.  
  
 `MyControls` 네임스페이스에 다음 코드를 추가합니다.  구현 방법은 간단하므로 자세히 설명하지 않습니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 솔루션을 빌드합니다.  이 빌드에서는 MyControls.dll이라는 DLL이 생성됩니다.  
  
<a name="winforms_host_section"></a>   
## Windows Forms 호스트 응용 프로그램 구현  
 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 호스트 응용 프로그램은 <xref:System.Windows.Forms.Integration.ElementHost> 개체를 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤을 호스팅합니다.  이 응용 프로그램에서는 `OnButtonClick` 이벤트를 처리하여 복합 컨트롤에서 데이터를 수신합니다.  또한 컨트롤 모양을 수정하는 데 사용할 수 있는 옵션 단추 집합도 포함합니다.  다음 그림에서는 응용 프로그램을 보여 줍니다.  
  
 ![Windows Form Hosting Avalon 컨트롤](../../../../docs/framework/wpf/advanced/media/wfhost.png "WFHost")  
Windows Forms 응용 프로그램에서 호스팅되는 WPF 복합 컨트롤  
  
### 프로젝트 만들기  
 프로젝트를 시작하려면  
  
1.  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]을 시작하고 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  Visual C\# 및 Windows 범주에서 **Windows Forms 응용 프로그램** 템플릿을 선택합니다.  
  
3.  새 프로젝트의 이름을 `WFHost`로 지정합니다.  
  
4.  위치에서 MyControls 프로젝트가 포함된 동일한 최상위 폴더를 지정합니다.  
  
5.  **확인**을 클릭하여 프로젝트를 만듭니다.  
  
 또한 `MyControl1` 및 다른 어셈블리를 포함하는 DLL에 대한 참조도 추가해야 합니다.  
  
1.  솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.  
  
2.  **찾아보기** 탭을 클릭하고 MyControls.dll이 들어 있는 폴더로 이동합니다.  이 연습의 경우 이 폴더는 MyControls\\bin\\Debug입니다.  
  
3.  MyControls.dll을 선택하고 **확인**을 클릭합니다.  
  
4.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   System.Xaml  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
### 응용 프로그램의 사용자 인터페이스 구현  
 Windows Form 응용 프로그램의 UI에는 WPF 복합 컨트롤과 상호 작용하는 여러 컨트롤이 포함되어 있습니다.  
  
1.  Windows Form 디자이너에서 Form1을 엽니다.  
  
2.  컨트롤 크기에 맞게 폼을 확장합니다.  
  
3.  폼의 오른쪽 위에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤을 보관할 <xref:System.Windows.Forms.Panel?displayProperty=fullName> 컨트롤을 추가합니다.  
  
4.  폼에 다음 <xref:System.Windows.Forms.GroupBox?displayProperty=fullName> 컨트롤을 추가합니다.  
  
    |Name|Text|  
    |----------|----------|  
    |groupBox1|배경색|  
    |groupBox2|전경색|  
    |groupBox3|글꼴 크기|  
    |groupBox4|글꼴 패밀리|  
    |groupBox5|글꼴 스타일|  
    |groupBox6|글꼴 두께|  
    |groupBox7|컨트롤의 데이터|  
  
5.  <xref:System.Windows.Forms.GroupBox?displayProperty=fullName> 컨트롤에 다음 <xref:System.Windows.Forms.RadioButton?displayProperty=fullName> 컨트롤을 추가합니다.  
  
    |GroupBox|Name|Text|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|원래 설정|  
    |groupBox1|radioBackgroundLightGreen|연한 녹색|  
    |groupBox1|radioBackgroundLightSalmon|연한 연어살색|  
    |groupBox2|radioForegroundOriginal|원래 설정|  
    |groupBox2|radioForegroundRed|빨강|  
    |groupBox2|radioForegroundRed|노랑|  
    |groupBox3|radioSizeOriginal|원래 설정|  
    |groupBox3|radioSizeTen|10|  
    |groupBox3|radioSizeTwelve|12|  
    |groupBox4|radioFamilyOriginal|원래 설정|  
    |groupBox4|radioFamilyTimes|Times New Roman|  
    |groupBox4|radioFamilyWingDings|WingDings|  
    |groupBox5|radioStyleOriginal|보통|  
    |groupBox5|radioStyleItalic|기울임꼴|  
    |groupBox6|radioWeightOriginal|원래 설정|  
    |groupBox6|radioWeightBold|굵게|  
  
6.  마지막 <xref:System.Windows.Forms.GroupBox?displayProperty=fullName>에 다음 <xref:System.Windows.Forms.Label?displayProperty=fullName> 컨트롤을 추가합니다.  이러한 컨트롤에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤에서 반환하는 데이터를 표시합니다.  
  
    |GroupBox|Name|Text|  
    |--------------|----------|----------|  
    |groupBox7|lblName|이름:|  
    |groupBox7|lblAddress|주소:|  
    |groupBox7|lblCity|구\/군\/시:|  
    |groupBox7|lblState|시\/도:|  
    |groupBox7|lblZip|우편 번호:|  
  
### 폼 초기화  
 일반적으로 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 호스팅 코드를 구현합니다.  다음 코드에서는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤 <xref:System.Windows.FrameworkElement.Loaded> 이벤트에 대한 처리기 및 나중에 사용하는 여러 전역 변수에 대한 선언을 보여 줍니다.  
  
 Windows Forms 디자이너에서 폼을 두 번 클릭하여 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기를 만듭니다.  Form1.cs 맨 위에 다음 `using` 문을 추가합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 기존 `Form1` 클래스의 내용을 다음 코드로 바꿉니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 앞의 코드에서 `Form1_Load` 메서드는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 호스팅하는 다음과 같은 일반적인 절차를 보여 줍니다.  
  
1.  새 <xref:System.Windows.Forms.Integration.ElementHost> 개체를 만듭니다.  
  
2.  컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle?displayProperty=fullName>로 설정합니다.  
  
3.  <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.Controls%2A> 컬렉션에 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 추가합니다.  
  
4.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 인스턴스를 만듭니다.  
  
5.  <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성에 컨트롤을 할당하여 폼에서 복합 컨트롤을 호스팅합니다.  
  
 `Form1_Load` 메서드에서 나머지 두 줄은 처리기를 다음의 두 가지 컨트롤 이벤트에 연결합니다.  
  
-   `OnButtonClick`은 복합 컨트롤에서 사용자가 **확인** 또는 **취소** 단추를 클릭할 때 발생하는 사용자 지정 이벤트입니다.  이 이벤트를 처리하여 사용자의 응답을 수신하고 사용자가 지정한 데이터를 수집합니다.  
  
-   <xref:System.Windows.FrameworkElement.Loaded>는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 완전히 로드되면 발생하는 표준 이벤트입니다.  이 예제에서는 컨트롤의 속성을 사용하여 여러 전역 변수를 초기화해야 하기 때문에 이 이벤트가 사용됩니다.  폼의 <xref:System.Windows.Forms.Form.Load> 이벤트가 발생할 때는 컨트롤이 완전히 로드되지 않았으므로 이 값은 여전히 `null`로 설정되어 있습니다.  이러한 속성에 액세스할 수 있으려면 컨트롤의 <xref:System.Windows.FrameworkElement.Loaded> 이벤트가 발생할 때까지 기다려야 합니다.  
  
 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기는 앞의 코드에 나와 있습니다.  `OnButtonClick` 처리기는 다음 단원에서 설명합니다.  
  
### OnButtonClick 처리  
 `OnButtonClick` 이벤트는 사용자가 **확인** 또는 **취소** 단추를 클릭할 때 발생합니다.  
  
 이 이벤트의 처리기에서는 이벤트 인수의 `IsOK` 필드를 확인하여 어떤 단추를 클릭했는지 확인합니다.  `lbl`*data* 변수는 앞에서 설명한 <xref:System.Windows.Forms.Label> 컨트롤에 해당합니다.  사용자가 **확인** 단추를 클릭한 경우 컨트롤의 <xref:System.Windows.Controls.TextBox> 컨트롤 데이터가 해당하는 <xref:System.Windows.Forms.Label> 컨트롤에 할당됩니다.  사용자가 **취소**를 클릭한 경우 <xref:System.Windows.Forms.Label.Text%2A> 값이 기본 문자열로 설정됩니다.  
  
 `Form1` 클래스에 다음과 같은 단추 클릭 이벤트 처리기 코드를 추가합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 응용 프로그램을 빌드하고 실행합니다.  WPF 복합 컨트롤에 텍스트를 추가하고 **확인**을 클릭합니다.  텍스트가 레이블에 나타납니다.  현재는 라디오 단추를 처리하는 코드가 추가되지 않았습니다.  
  
### 컨트롤 모양 수정  
 폼의 <xref:System.Windows.Forms.RadioButton> 컨트롤을 사용하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤의 전경색, 배경색 및 여러 글꼴 속성을 변경할 수 있습니다.  배경색은 <xref:System.Windows.Forms.Integration.ElementHost> 개체에 의해 노출됩니다.  나머지 속성은 컨트롤의 사용자 지정 속성으로 노출됩니다.  
  
 폼에서 각 <xref:System.Windows.Forms.RadioButton> 컨트롤을 두 번 클릭하여 <xref:System.Windows.Forms.RadioButton.CheckedChanged> 이벤트 처리기를 만듭니다.  <xref:System.Windows.Forms.RadioButton.CheckedChanged> 이벤트 처리기를 다음 코드로 바꿉니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 응용 프로그램을 빌드하고 실행합니다.  다른 라디오 단추를 클릭하여 WPF 복합 컨트롤의 효과를 확인합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)   
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [연습: Windows Forms에서 3\-D WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)