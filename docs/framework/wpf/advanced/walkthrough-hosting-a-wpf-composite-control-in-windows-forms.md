---
title: "연습: Windows Forms에서 WPF 복합 컨트롤 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 965136c94b696fc182537b60dde71ee4f02afe7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>연습: Windows Forms에서 WPF 복합 컨트롤 호스팅
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다. 그러나에 있는 경우 상당한 투자 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 코드는 것이 보다 효율적으로 기존 확장을 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 인 응용 프로그램이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 처음부터 다시 작성 하기 보다는 합니다. 일반적인 시나리오는 컨트롤을 더 사용 하 여 구현 하거나 하나를 포함할 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내 프로그램 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 응용 프로그램입니다. WPF 컨트롤을 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)합니다.  
  
 이 연습 단계를 안내 응용 프로그램을 호스팅하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 합성 컨트롤에서 데이터 입력을 수행 하는 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 응용 프로그램입니다. 복합 컨트롤은 DLL로 패키지됩니다. 이 일반적인 절차는 더 복잡한 응용 프로그램 및 컨트롤로 확장할 수 있습니다. 이 연습에서 모양과 기능을 거의 동일한 [연습: WPF의 Windows Forms 합성 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)합니다. 주요 차이점은 호스팅 시나리오가 반대라는 점입니다.  
  
 이 연습은 두 개의 섹션으로 구분됩니다. 첫 번째 섹션 구현에 간략하게 설명 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 합성 컨트롤입니다. 두 번째 섹션에서 복합 컨트롤을 호스트 하는 방법을 자세히 설명 된 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 응용 프로그램의 컨트롤에서 이벤트를 수신 및 컨트롤의 속성 중 일부에 액세스 합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   WPF 복합 컨트롤 구현  
  
-   Windows Forms 호스트 응용 프로그램 구현  
  
 이 연습에서 설명 하는 작업의 전체 코드 목록을 보려면 [Windows Forms 예제에서 복합 WPF 컨트롤 호스트](http://go.microsoft.com/fwlink/?LinkID=159996)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="implementing-the-wpf-composite-control"></a>WPF 복합 컨트롤 구현  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이 예제에서 사용 하는 복합 컨트롤은 사용자의 이름 및 주소를 사용 하는 간단한 데이터 입력 폼입니다. 사용자가 작업이 완료되었음을 나타내는 두 개의 단추 중 하나를 클릭하면 컨트롤에서 사용자 지정 이벤트가 발생하여 해당 정보가 호스트에 반환됩니다. 다음 그림에서는 렌더링된 컨트롤을 보여 줍니다.  
  
 ![간단한 WPF 컨트롤](../../../../docs/framework/wpf/advanced/media/avaloncontrol.png "AvalonControl")  
WPF 복합 컨트롤  
  
### <a name="creating-the-project"></a>프로젝트 만들기  
 프로젝트를 시작하려면  
  
1.  시작 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], 열 및는 **새 프로젝트** 대화 상자.  
  
2.  Visual C# 및 Windows 범주에서 선택 된 **WPF 사용자 정의 컨트롤 라이브러리** 템플릿.  
  
3.  새 프로젝트의 이름을 `MyControls`합니다.  
  
4.  위치에 대 한 최상위 폴더를 편리 하 게 명명 된 같은 지정한 `WindowsFormsHostingWpfControl`합니다. 나중에 이 폴더에 호스트 응용 프로그램을 넣습니다.  
  
5.  클릭 **확인** 프로젝트를 만듭니다. 라는 단일 컨트롤을 포함 하는 기본 프로젝트 `UserControl1`합니다.  
  
6.  솔루션 탐색기에서 이름을 바꿀 `UserControl1` 를 `MyControl1`합니다.  
  
 프로젝트에는 다음과 같은 시스템 DLL에 대한 참조가 있어야 합니다. 이러한 DLL이 기본적으로 포함되지 않은 경우 프로젝트에 추가합니다.  
  
-   PresentationCore  
  
-   PresentationFramework  
  
-   시스템  
  
-   WindowsBase  
  
### <a name="creating-the-user-interface"></a>사용자 인터페이스 만들기  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 합성 컨트롤은 사용 하 여 구현에 대 한 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다. 복합 컨트롤 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 5 이루어져 <xref:System.Windows.Controls.TextBox> 요소입니다. 각 <xref:System.Windows.Controls.TextBox> 요소에 연결 된 <xref:System.Windows.Controls.TextBlock> 레이블로 사용 하는 요소입니다. 두 개의 <xref:System.Windows.Controls.Button> 요소 아래에 **확인** 및 **취소**합니다. 사용자가 이 단추 중 하나를 클릭하면 컨트롤에서 사용자 지정 이벤트가 발생하여 호스트에 정보가 반환됩니다.  
  
#### <a name="basic-layout"></a>기본 레이아웃  
 다양 한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소에 포함 됩니다는 <xref:System.Windows.Controls.Grid> 요소입니다. 사용할 수 있습니다 <xref:System.Windows.Controls.Grid> 거의 복합의 내용을 제어 동일한 정렬 방식으로 사용 합니다는 `Table` 요소 내에 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 <xref:System.Windows.Documents.Table> 요소인 하지만 <xref:System.Windows.Controls.Grid> 가 더 가볍고 단순 레이아웃 작업에 보다 적합 합니다.  
  
 다음 XAML에서는 기본 레이아웃을 보여 줍니다. 이 XAML 열 수를 지정 하 여 컨트롤의 전체 구조를 정의 하 고에 행이 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
 MyControl1.xaml에서 기존 XAML을 다음 XAML로 바꿉니다.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>그리드에 TextBlock 및 TextBox 요소 추가  
 배치는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 설정 하 여 표의 요소 <xref:System.Windows.Controls.Grid.RowProperty> 및 <xref:System.Windows.Controls.Grid.ColumnProperty> 특성을 적절 한 행 및 열 번호입니다. 행 및 열 번호는 0부터 시작해야 합니다. 설정 하 여 여러 열을 포함 하는 요소를 사용할 수 있습니다는 <xref:System.Windows.Controls.Grid.ColumnSpanProperty> 특성입니다. 에 대 한 자세한 내용은 <xref:System.Windows.Controls.Grid> 요소 참조 [Grid 요소를 만들](../../../../docs/framework/wpf/controls/how-to-create-a-grid-element.md)합니다.  
  
 다음 XAML 복합 컨트롤의 표시 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.TextBlock> 요소를 자신의 <xref:System.Windows.Controls.Grid.RowProperty> 및 <xref:System.Windows.Controls.Grid.ColumnProperty> 눈금에는 요소를 제대로 배치로 설정 되는 특성입니다.  
  
 MyControl1.xaml, 추가 내에서 다음 XAML은 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>UI 요소 스타일 지정  
 데이터 입력 폼의 요소는 대부분 모양이 비슷합니다. 즉, 이러한 요소의 여러 속성 설정이 동일합니다. 앞의 XAML 사용 하 여 각 요소의 특성을 따로 설정 하지 않고 <xref:System.Windows.Style> 요소의 클래스에 대 한 표준 속성 설정을 정의 하는 요소입니다. 이 방법을 사용하면 컨트롤의 복잡도를 줄이고 하나의 스타일 특성을 통해 여러 요소의 모양을 변경할 수 있습니다.  
  
 <xref:System.Windows.Style> 요소에 포함 됩니다는 <xref:System.Windows.Controls.Grid> 요소의 <xref:System.Windows.FrameworkElement.Resources%2A> 속성, 컨트롤의 모든 요소에서 사용할 수 있도록 합니다. 지정 하는 경우에 적용할 있습니다 요소를 추가 하 여 한 <xref:System.Windows.Style> 요소 스타일 이름으로 설정 합니다. 이름이 지정되지 않은 스타일은 요소의 기본 스타일이 됩니다. 에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스타일 참조 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)합니다.  
  
 에서는 다음 XAML은 <xref:System.Windows.Style> 복합 컨트롤에 대 한 요소입니다. 스타일이 요소에 어떻게 적용되는지 확인하려면 앞의 XAML을 참조하세요. 예를 들어 마지막 <xref:System.Windows.Controls.TextBlock> 요소에는 `inlineText` 스타일 및 마지막 <xref:System.Windows.Controls.TextBox> 요소의 기본 스타일을 사용 합니다.  
  
 MyControl1.xaml를 다음 XAML을 추가 바로 뒤의 <xref:System.Windows.Controls.Grid> 요소를 시작 합니다.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>확인 및 취소 단추 추가  
 복합 컨트롤의 마지막 요소는 **확인** 및 **취소** <xref:System.Windows.Controls.Button> 의 마지막 행의 처음 두 열을 차지 하는 요소는 <xref:System.Windows.Controls.Grid>합니다. 이러한 요소에 공통 이벤트 처리기를 사용 하 여 `ButtonClicked`, 및 기본 <xref:System.Windows.Controls.Button> 이전 XAML에 정의 된 스타일입니다.  
  
 MyControl1.xaml, 마지막 뒤에 다음 XAML 추가 <xref:System.Windows.Controls.TextBox> 요소입니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 복합 컨트롤의 일부로 완료 되었습니다.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>코드 숨김 파일 구현  
 코드 숨김 파일인 MyControl1.xaml.cs, 세 가지 필수 작업을 구현합니다.
  
1.  사용자가 단추 중 하나를 클릭할 때 발생하는 이벤트를 처리합니다.  
  
2.  데이터를 검색 하는 <xref:System.Windows.Controls.TextBox> 요소를 사용자 지정 이벤트 인수 개체에 패키지 하 고 있습니다.  
  
3.  발생 시켜 `OnButtonClick` 이벤트를 사용자가 완료 되 고 호스트에 데이터를 전달 합니다. 호스트에 알립니다.  
  
 또한 컨트롤에서는 모양을 변경하는 데 사용할 수 있는 많은 수의 색 및 글꼴 속성을 노출합니다. 와 달리는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스는 사용 되는 호스트에는 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤은 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 클래스를 노출 <xref:System.Windows.Controls.Panel.Background%2A> 속성에만 해당 합니다. 이 코드 예제에서 설명한 예제 사이의 유사성을 유지 하기 위해 [연습: Windows Forms 합성 컨트롤 wpf에서 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md), 컨트롤 나머지 속성을 직접 노출 합니다.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>코드 숨김 파일의 기본 구조  
 코드 숨김 파일 단일 네임 스페이스가 이루어져 `MyControls`, 두 개의 클래스를 포함 하 `MyControl1` 및 `MyControlEventArgs`합니다.  
  
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
  
 첫 번째 클래스 `MyControl1`의 기능을 구현 하는 코드를 포함 하는 partial 클래스는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] MyControl1.xaml에 정의 되어 있습니다. MyControl1.xaml 구문 분석할 때는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 동일한 부분 클래스에 변환 및 두 개의 부분 클래스 컴파일된 컨트롤 병합 됩니다. 따라서 코드 숨김 파일의 클래스 이름이 MyControl1.xaml에 할당된 클래스 이름과 일치해야 하며 컨트롤의 루트 요소에서 상속되어야 합니다. 두 번째 클래스 `MyControlEventArgs`는 다시 호스트에 데이터를 보내는 데 사용 되는 이벤트 인수 클래스입니다.  
  
 MyControl1.xaml.cs를 엽니다. 선언을 변경 하 여 기존 클래스에서 상속 하 고 다음 이름을 갖고 있도록 <xref:System.Windows.Controls.Grid>합니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>컨트롤 초기화  
 다음 코드에서는 다음과 같은 몇 가지 기본 작업을 구현합니다.  
  
-   Private 이벤트 선언 `OnButtonClick`, 및 관련된 대리자, `MyControlEventHandler`합니다.  
  
-   사용자 데이터를 저장하는 여러 private 전역 변수를 만듭니다. 이 데이터는 해당 속성을 통해 노출됩니다.  
  
-   처리기를 구현 `Init`, 컨트롤의에 대 한 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다. 이 처리기에서는 MyControl1.xaml에 정의된 값을 할당하여 전역 변수를 초기화합니다. 이 위해 사용 하 여는 <xref:System.Windows.FrameworkElement.Name%2A> 일반적인에 할당 된 <xref:System.Windows.Controls.TextBlock> 요소인 `nameLabel`, 해당 요소의 속성 설정에 액세스 합니다.  
  
 기존 생성자를 삭제 하 고 다음 코드를 추가 하면 `MyControl1` 클래스입니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>단추의 클릭 이벤트 처리  
 사용자 중 하나를 클릭 하 여 데이터 입력 작업 완료를 나타내는 **확인** 단추 또는 **취소** 단추입니다. 두 단추를 사용 하는 동일한 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기 `ButtonClicked`합니다. 두 단추에 이름이 `btnOK` 또는 `btnCancel`의 값을 검사 하 여 클릭 한 단추를 결정 하는 처리기 수 있도록 하는 `sender` 인수입니다. 처리기에서는 다음 작업을 수행합니다.  
  
-   만듭니다는 `MyControlEventArgs` 개체에서 데이터를 포함 하는 <xref:System.Windows.Controls.TextBox> 요소입니다.  
  
-   사용자가 클릭 한 경우는 **취소** 단추 집합에서 `MyControlEventArgs` 개체의 `IsOK` 속성을 `false`합니다.  
  
-   발생 된 `OnButtonClick` 이벤트를 사용자가 완료 되 고 수집 된 데이터를 다시 전달 호스트에 알리기.  
  
 다음 코드를 추가 하 여 `MyControl1` 후 클래스는 `Init` 메서드.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>속성 만들기  
 클래스의 나머지 부분에서는 위에서 설명한 전역 변수에 해당하는 속성을 노출하기만 합니다. 속성이 변경되면 set 접근자가 해당 요소 속성을 변경하고 기본 전역 변수를 업데이트하여 컨트롤 모양을 수정합니다.  
  
 다음 코드를 추가 하 여 `MyControl1` 클래스입니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>데이터를 다시 호스트에 보내기  
 파일의 마지막 구성 요소는 `MyControlEventArgs` 다시 호스트에 수집 된 데이터를 보내는 데 사용 되는 클래스입니다.  
  
 다음 코드를 추가 하 여 `MyControls` 네임 스페이스입니다. 구현 방법은 간단하므로 자세히 설명하지 않습니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 솔루션을 빌드합니다. 빌드하면 MyControls.dll이라는 DLL이 생성됩니다.  
  
<a name="winforms_host_section"></a>   
## <a name="implementing-the-windows-forms-host-application"></a>Windows Forms 호스트 응용 프로그램 구현  
 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 사용 하 여 응용 프로그램 호스트는 <xref:System.Windows.Forms.Integration.ElementHost> 호스트 개체는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 합성 컨트롤입니다. 응용 프로그램 핸들이 `OnButtonClick` 합성 컨트롤에서 데이터를 받을 이벤트입니다. 또한 응용 프로그램은 컨트롤 모양을 수정하는 데 사용할 수 있는 옵션 단추 집합도 포함합니다. 다음 그림에서는 응용 프로그램을 보여 줍니다.  
  
 ![Windows Form Hosting Avalon 컨트롤](../../../../docs/framework/wpf/advanced/media/wfhost.png "WFHost")  
Windows Forms 응용 프로그램에서 호스트되는 WPF 복합 컨트롤  
  
### <a name="creating-the-project"></a>프로젝트 만들기  
 프로젝트를 시작하려면  
  
1.  시작 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], 열 및는 **새 프로젝트** 대화 상자.  
  
2.  Visual C# 및 Windows 범주에서 선택 된 **Windows Forms 응용 프로그램** 템플릿.  
  
3.  새 프로젝트의 이름을 `WFHost`합니다.  
  
4.  위치에는 MyControls 프로젝트를 포함하는 동일한 최상위 폴더를 지정합니다.  
  
5.  클릭 **확인** 프로젝트를 만듭니다.  
  
 포함 된 DLL에 대 한 참조를 추가 해야 `MyControl1` 및 기타 어셈블리입니다.  
  
1.  솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 추가**합니다.  
  
2.  클릭는 **찾아보기** 탭을 MyControls.dll 포함 된 폴더로 이동 합니다. 이 연습에서 이 폴더는 MyControls\bin\Debug입니다.  
  
3.  MyControls.dll를 선택한 다음 클릭 **확인**합니다.  
  
4.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   System.Xaml  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
### <a name="implementing-the-user-interface-for-the-application"></a>응용 프로그램에 대한 사용자 인터페이스 구현  
 Windows Form 응용 프로그램의 UI에는 WPF 복합 컨트롤과 상호 작용하는 여러 컨트롤이 포함되어 있습니다.  
  
1.  Windows Form 디자이너에서 Form1을 엽니다.  
  
2.  컨트롤 크기에 맞게 폼을 확장합니다.  
  
3.  폼의 오른쪽 위 모퉁이에 추가 <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> 보유 하는 컨트롤의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 합성 컨트롤입니다.  
  
4.  다음 추가 <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> 폼에 컨트롤을 합니다.  
  
    |name|텍스트|  
    |----------|----------|  
    |groupBox1|배경색|  
    |groupBox2|전경색|  
    |groupBox3|글꼴 크기|  
    |groupBox4|글꼴 패밀리|  
    |groupBox5|글꼴 스타일|  
    |groupBox6|글꼴 두께|  
    |groupBox7|컨트롤의 데이터|  
  
5.  다음 추가 <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> 컨트롤을 <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> 컨트롤입니다.  
  
    |GroupBox|name|텍스트|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|원래 색|  
    |groupBox1|radioBackgroundLightGreen|LightGreen|  
    |groupBox1|radioBackgroundLightSalmon|LightSalmon|  
    |groupBox2|radioForegroundOriginal|원래 색|  
    |groupBox2|radioForegroundRed|빨강|  
    |groupBox2|radioForegroundYellow|노랑|  
    |groupBox3|radioSizeOriginal|원래 색|  
    |groupBox3|radioSizeTen|10|  
    |groupBox3|radioSizeTwelve|12|  
    |groupBox4|radioFamilyOriginal|원래 색|  
    |groupBox4|radioFamilyTimes|궁서|  
    |groupBox4|radioFamilyWingDings|WingDings|  
    |groupBox5|radioStyleOriginal|보통|  
    |groupBox5|radioStyleItalic|기울임꼴|  
    |groupBox6|radioWeightOriginal|원래 색|  
    |groupBox6|radioWeightBold|Bold|  
  
6.  다음 추가 <xref:System.Windows.Forms.Label?displayProperty=nameWithType> 마지막 제어 <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>합니다. 반환 된 데이터를 표시 하는 이러한 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 합성 컨트롤입니다.  
  
    |GroupBox|name|텍스트|  
    |--------------|----------|----------|  
    |groupBox7|lblName|이름:|  
    |groupBox7|lblAddress|구/군/시:|  
    |groupBox7|lblCity|시/도:|  
    |groupBox7|lblState|상태:|  
    |groupBox7|lblZip|우편 번호:|  
  
### <a name="initializing-the-form"></a>폼 초기화  
 일반적으로 폼의 호스팅 코드를 구현 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다. 다음 코드는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에 대 한 처리기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 합성 컨트롤 <xref:System.Windows.FrameworkElement.Loaded> 이벤트와 나중에 사용 되는 몇 가지 전역 변수를 선언 합니다.  
  
 Windows Forms 디자이너에서 만드는 양식이 두 번 클릭 한 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다. Form1.cs의 위쪽에 다음 추가 `using` 문.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 기존 내용을 대체 `Form1` 를 다음 코드로 클래스입니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 `Form1_Load` 위의 코드에서 메서드를 호스트 하는 일반적인 절차를 보여 줍니다.는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제어:  
  
1.  새 <xref:System.Windows.Forms.Integration.ElementHost> 개체입니다.  
  
2.  컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>합니다.  
  
3.  추가 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.Controls%2A> 컬렉션입니다.  
  
4.  인스턴스를 만들고는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제어 합니다.  
  
5.  컨트롤을 할당 하 여 복합 컨트롤을 폼에 호스트 된 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성입니다.  
  
 나머지 두 줄은 `Form1_Load` 두 컨트롤 이벤트에 처리기를 연결 하는 메서드:  
  
-   `OnButtonClick`사용자가 클릭할 때 복합 컨트롤에 의해 발생 하는 사용자 지정 이벤트는 **확인** 또는 **취소** 단추입니다. 이 이벤트를 처리하여 사용자의 응답을 수신하고 사용자가 지정한 데이터를 수집합니다.  
  
-   <xref:System.Windows.FrameworkElement.Loaded>표준 이벤트에 의해 발생 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 완전히 로드 될 때 제어 합니다. 이 예제에서는 컨트롤의 속성을 사용하여 여러 전역 변수를 초기화해야 하기 때문에 이 이벤트가 사용됩니다. 폼의 당시의 <xref:System.Windows.Forms.Form.Load> 이벤트, 컨트롤 완전히 로드 되지 않습니다. 및 해당 값으로 설정 되며 여전히 `null`합니다. 컨트롤의 때까지 기다려야 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 발생 전에 해당 속성에 액세스할 수 있습니다.  
  
 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기 앞의 코드에 표시 됩니다. `OnButtonClick` 처리기는 다음 섹션에서 설명 합니다.  
  
### <a name="handling-onbuttonclick"></a>OnButtonClick 처리  
 `OnButtonClick` 이벤트를 클릭할 때 발생는 **확인** 또는 **취소** 단추입니다.  
  
 이벤트 처리기에서는 이벤트 인수 `IsOK` 필드를 클릭 한 단추를 확인 합니다. `lbl` *데이터* 에 해당 하는 변수는 <xref:System.Windows.Forms.Label> 앞서 설명한 컨트롤입니다. 사용자가 클릭할 경우는 **확인** 단추 컨트롤의 데이터로 <xref:System.Windows.Controls.TextBox> 컨트롤 해당에 할당 된 <xref:System.Windows.Forms.Label> 제어 합니다. 사용자가 클릭할 경우 **취소**, <xref:System.Windows.Forms.Label.Text%2A> 값이 기본 문자열로 설정 됩니다.  
  
 다음 단추를 추가 이벤트 처리기 코드를 클릭 하 고 `Form1` 클래스입니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 응용 프로그램을 빌드 및 실행합니다. WPF 복합 컨트롤에 텍스트를 추가 하 고 클릭 **확인**합니다. 텍스트가 레이블에 나타납니다. 현재는 라디오 단추를 처리하는 코드가 추가되지 않았습니다.  
  
### <a name="modifying-the-appearance-of-the-control"></a>컨트롤의 모양 수정  
 <xref:System.Windows.Forms.RadioButton> 폼에서 컨트롤에 따르면 변경 하려면 사용자는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤의 전경색과 배경색 및 여러 글꼴 속성에 색을 지정 합니다. 명령 프롬프트 창의 배경색에 의해 노출 되는 <xref:System.Windows.Forms.Integration.ElementHost> 개체입니다. 나머지 속성은 컨트롤의 사용자 지정 속성으로 노출됩니다.  
  
 각각 두 번 클릭 <xref:System.Windows.Forms.RadioButton> 만들 양식에서 컨트롤 <xref:System.Windows.Forms.RadioButton.CheckedChanged> 이벤트 처리기입니다. 대체는 <xref:System.Windows.Forms.RadioButton.CheckedChanged> 다음 코드를 사용 하 여 이벤트 처리기입니다.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 응용 프로그램을 빌드 및 실행합니다. WPF 복합 컨트롤에 대한 효과를 확인하려면 다른 라디오 단추를 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 디자이너](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [연습: Windows Forms에서 3-D WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
