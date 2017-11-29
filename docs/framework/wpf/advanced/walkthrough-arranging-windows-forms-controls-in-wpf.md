---
title: "연습: WPF에서 Windows Forms 컨트롤 정렬"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f78da83657c4c1bd913f67c9e612264cc5dbdf99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>연습: WPF에서 Windows Forms 컨트롤 정렬
이 연습에서는 사용 하는 방법을 보여 줍니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃을 정렬 하는 기능 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 하이브리드 응용 프로그램의 컨트롤입니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   프로젝트 만들기.  
  
-   기본 레이아웃 설정 사용  
  
-   콘텐츠에 맞게 크기 조정  
  
-   절대 위치 사용  
  
-   명시적으로 크기 지정  
  
-   레이아웃 속성 설정  
  
-   z 순서 제한 사항 이해  
  
-   도킹  
  
-   표시 유형 설정  
  
-   늘어나지 않는 컨트롤 호스트  
  
-   배율 조정  
  
-   회전  
  
-   안쪽 여백 및 여백 설정  
  
-   동적 레이아웃 컨테이너 사용  
  
 이 연습에서 설명 하는 작업의 전체 코드 목록을 보려면 [WPF 샘플에서 Windows Forms 컨트롤 정렬](http://go.microsoft.com/fwlink/?LinkID=159971)합니다.  
  
 작업을 완료 하는 경우 이해 것 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 레이아웃 기능에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
  
#### <a name="to-create-and-set-up-the-project"></a>프로젝트를 만들고 설정하려면  
  
1.  이라는 WPF 응용 프로그램 프로젝트 만들기 `WpfLayoutHostingWf`합니다.  
  
2.  솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
    -   System.Drawing  
  
3.  MainWindow.xaml을 두 번 클릭하여 XAML 보기에서 엽니다.  
  
4.  에 <xref:System.Windows.Window> 요소를 다음 추가 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 네임 스페이스 매핑을 합니다.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  에 <xref:System.Windows.Controls.Grid> 요소 집합에서 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 속성을 `true` 5 개의 행과 열을 정의 합니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a>기본 레이아웃 설정 사용  
 기본적으로는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 호스팅된에 대 한 레이아웃을 처리 하는 요소 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.  
  
#### <a name="to-use-default-layout-settings"></a>기본 레이아웃 설정을 사용하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> 컨트롤이에 표시 되는 <xref:System.Windows.Controls.Canvas>합니다. 호스팅된 컨트롤이 해당 내용에 따라 크기가 및 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 호스팅된 컨트롤에 맞게 크기가 조정 됩니다.  
  
## <a name="sizing-to-content"></a>콘텐츠에 맞게 크기 조정  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 호스팅된 컨트롤의 내용을 제대로 표시의 확인 합니다.  
  
#### <a name="to-size-to-content"></a>콘텐츠 크기를 조정하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. 긴 텍스트 문자열과 글꼴 크기를 올바르게 표시 하려면 두 개의 새 단추 컨트롤의 크기가 및 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 호스트 된 컨트롤에 맞게 크기가 조정 됩니다.  
  
## <a name="using-absolute-positioning"></a>절대 위치 사용  
 절대 위치를 배치 하는 데 사용할 수는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 사용자 인터페이스 (UI)에 있는 요소입니다.  
  
#### <a name="to-use-absolute-positioning"></a>절대 위치를 사용하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 표 형태 셀의 위쪽에서 20 픽셀, 왼쪽에서 20 픽셀 요소가 배치 됩니다.  
  
## <a name="specifying-size-explicitly"></a>명시적으로 크기 지정  
 크기를 지정할 수는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 사용 하 여 요소는 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성입니다.  
  
#### <a name="to-specify-size-explicitly"></a>명시적으로 크기를 지정하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 기본 레이아웃 설정 보다 작은 70 픽셀 너비 50 픽셀의 크기를 설정 됩니다. 콘텐츠는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 그에 따라 다시 정렬 합니다.  
  
## <a name="setting-layout-properties"></a>레이아웃 속성 설정  
 속성을 사용 하 여 호스팅된 컨트롤에 레이아웃 관련 속성을 항상 설정 된 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다. 호스트된 컨트롤에서 직접 레이아웃 속성을 설정하면 의도하지 않은 결과가 생성됩니다.  
  
 호스팅된 컨트롤에 대해 레이아웃 관련 속성을 설정 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 영향을 주지 않습니다.  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>호스트된 컨트롤에서 속성 설정의 결과를 확인하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  솔루션 탐색기에서 MainWindow.xaml. vb 또는 MainWindow.xaml.cs를 두 번 클릭하여 코드 편집기에서 엽니다.  
  
3.  다음 코드를 복사는 `MainWindow` 클래스 정의 합니다.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
5.  클릭는 **Click me** 단추입니다. `button1_Click` 이벤트 처리기 설정은 <xref:System.Windows.Forms.Control.Top%2A> 및 <xref:System.Windows.Forms.Control.Left%2A> 호스팅된 컨트롤의 속성에 있습니다. 이 인해 내 재배치 호스팅된 컨트롤에서 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다. 호스트는 동일한 화면 영역을 유지하지만 호스트된 컨트롤은 잘립니다. 호스팅된 컨트롤을 채우는 항상 대신는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.  
  
## <a name="understanding-z-order-limitations"></a>Z 순서 제한 사항 이해  
 기본적으로 표시 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 항상의 맨 위에 그려집니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 z-순서에 따라 영향을 받지 않습니다. Z 순서 지정을 활성화 하려면 설정는 <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> 의 속성은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> true로 및 <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> 속성을 <xref:System.Windows.Interop.CompositionMode.Full> 또는 <xref:System.Windows.Interop.CompositionMode.OutputOnly>합니다.  
  
#### <a name="to-see-the-default-z-order-behavior"></a>기본 z 순서 동작을 확인하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> label 요소 위에 그려집니다.  
  
#### <a name="to-see-the-z-order-behavior-when-isredirected-is-true"></a>IsRedirected가 true일 때 z 순서 동작을 확인하려면  
  
1.  다음 XAML 개씩을 z 순서를 바꿉니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#8b)]  
  
     F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. Label 요소 위에 그려집니다는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.  
  
## <a name="docking"></a>도킹  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>요소는 지원 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 도킹 합니다. 설정의 <xref:System.Windows.Controls.DockPanel.Dock%2A> 연결 된 속성에서 호스팅된 컨트롤에 도킹을 <xref:System.Windows.Controls.DockPanel> 요소입니다.  
  
#### <a name="to-dock-a-hosted-control"></a>호스트된 컨트롤을 도킹하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 오른쪽에 도킹 된 <xref:System.Windows.Controls.DockPanel> 요소입니다.  
  
## <a name="setting-visibility"></a>표시 유형 설정  
 만들 수 있습니다 프로그램 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 보이지 않는 제어 하거나 설정 하 여 축소할 수는 <xref:System.Windows.UIElement.Visibility%2A> 속성에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다. 컨트롤이 보이지 않으면 표시되지는 않지만 레이아웃 공간은 사용합니다. 컨트롤이 축소되면 표시되지 않고 레이아웃 공간도 자치하지 않습니다.  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a>호스트된 컨트롤의 표시 유형을 설정하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 다음 코드를 클래스 정의에 복사합니다.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
4.  클릭는 **보이지 않도록 하려면 클릭** 단추를 눌러는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 보이지 않는 요소입니다.  
  
5.  클릭는 **축소 하려면 클릭** 단추를 숨기는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 레이아웃에서 요소 완전히 합니다. 경우는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 축소 되는 경우 요소는 해당 공간을 차지 하도록 다시 정렬 됩니다.  
  
## <a name="hosting-a-control-that-does-not-stretch"></a>늘어나지 않는 컨트롤 호스트  
 일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 크기가 고정 되어 있으며 레이아웃의 사용 가능한 공간을 채우기 위해 늘여 지지 않습니다. 예를 들어는 <xref:System.Windows.Forms.MonthCalendar> 컨트롤 고정 된 공간에 월을 표시 합니다.  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a>늘어나지 않는 컨트롤을 호스트하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 가운데에 그리드 행에 있지만 사용 가능한 공간을 채우기 위해 늘어나지 않습니다. 호스팅된 하 여 표시 되는 월을 두 개 이상의 창 충분히 클 경우 표시 될 수 있습니다 <xref:System.Windows.Forms.MonthCalendar> 컨트롤 이지만 이러한 행에 가운데 맞춤 됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 엔진의 크기를 사용 가능한 공간을 채울 수 있는 요소에 중점을 합니다.  
  
## <a name="scaling"></a>배율 조정  
 와 달리 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소, 대부분 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 지속적으로 확장 가능 하지 않습니다. 기본적으로는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 가능한 경우 호스팅된 컨트롤의 크기를 조정 합니다.  완전 한 확장을 사용 하려면 설정는 <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> 의 속성은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> true로 및 <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> 속성을 <xref:System.Windows.Interop.CompositionMode.Full> 또는 <xref:System.Windows.Interop.CompositionMode.OutputOnly>합니다.  
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>기본 동작을 사용하여 호스트된 컨트롤의 배율을 조정하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. 호스트된 컨트롤과 해당 주변 요소가 0.5의 비율로 배율 조정됩니다. 그러나 호스트된 컨트롤의 글꼴은 배율 조정되지 않습니다.  
  
#### <a name="to-scale-a-hosted-control-by-setting-isredirected-to-true"></a>IsRedirected를 true로 설정하여 호스트된 컨트롤의 배율을 조정하려면  
  
1.  위의 배율 조정 예제를 다음 XAML로 바꿉니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#12b)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. 호스트된 컨트롤, 주변 요소 및 호스트된 컨트롤의 글꼴이 0.5의 비율로 배율 조정됩니다.  
  
## <a name="rotating"></a>회전  
 와 달리 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 회전을 지원 하지 않습니다. 기본적으로는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 다른 요소를 회전 하지 않습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 회전 변환을 적용 하는 경우 요소입니다. 180도 발생 이외의 회전 값에서 <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 이벤트입니다.  다른 각도로 회전을 사용 하려면 설정는 <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> 의 속성은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> true로 및 <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> 속성을 <xref:System.Windows.Interop.CompositionMode.Full> 또는 <xref:System.Windows.Interop.CompositionMode.OutputOnly>합니다.  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>혼합 응용 프로그램에서 회전의 결과를 확인하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. 호스트된 컨트롤은 회전되지 않지만 주변 요소는 180도 각도로 회전됩니다. 요소를 표시하려면 창의 크기를 조정해야 할 수 있습니다.  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application-when-isredirected-is-true"></a>IsRedirected가 true인 경우 혼합 응용 프로그램에서 회전의 결과를 확인하려면  
  
1.  위의 회전 예제를 다음 XAML로 바꿉니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#13b)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. 호스트된 컨트롤이 회전됩니다.  <xref:System.Windows.Media.RotateTransform.Angle%2A> 속성 값으로 설정할 수 있습니다. 요소를 표시하려면 창의 크기를 조정해야 할 수 있습니다.  
  
## <a name="setting-padding-and-margins"></a>안쪽 여백 및 여백 설정  
 안쪽 여백 및 안쪽 여백을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃은 안쪽 여백 및 여백을 유사 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]합니다. 설정 하기만 <xref:System.Windows.Controls.Control.Padding%2A> 및 <xref:System.Windows.FrameworkElement.Margin%2A> 속성에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>호스트된 컨트롤에 대해 안쪽 여백 및 여백을 설정하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. 안쪽 여백 및 여백 설정이 적용 될 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 적용 될 것 같은 방식으로 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]합니다.  
  
## <a name="using-dynamic-layout-containers"></a>동적 레이아웃 컨테이너 사용  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]두 개의 동적 레이아웃 컨테이너를 제공 <xref:System.Windows.Forms.FlowLayoutPanel> 및 <xref:System.Windows.Forms.TableLayoutPanel>합니다. 이러한 컨테이너에 사용할 수도 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 합니다.  
  
#### <a name="to-use-a-dynamic-layout-container"></a>동적 레이아웃 컨테이너를 사용하려면  
  
1.  다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 다음 코드를 클래스 정의에 복사합니다.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  에 대 한 호출 추가 `InitializeFlowLayoutPanel` 생성자에서 메서드.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 입력의 <xref:System.Windows.Controls.DockPanel>, 및 <xref:System.Windows.Forms.FlowLayoutPanel> 해당 자식 컨트롤을 기본에서 정렬 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 디자이너](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [WindowsFormsHost 요소에 대한 레이아웃 고려 사항](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [WPF 샘플에서 정렬 Windows Forms 컨트롤](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
