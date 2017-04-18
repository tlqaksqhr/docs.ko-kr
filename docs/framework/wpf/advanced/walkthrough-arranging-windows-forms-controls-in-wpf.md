---
title: "연습: WPF에서 Windows Forms 컨트롤 정렬 | Microsoft Docs"
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
  - "컨트롤 정렬"
  - "혼합 응용 프로그램[WPF 상호 운용성]"
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# 연습: WPF에서 Windows Forms 컨트롤 정렬
이 연습에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 기능을 사용하여 혼합 응용 프로그램에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 정렬하는 방법을 보여 줍니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   프로젝트 만들기  
  
-   기본 레이아웃 설정 사용  
  
-   콘텐츠에 맞게 크기 조정  
  
-   절대 위치 사용  
  
-   명시적으로 크기 지정  
  
-   레이아웃 속성 설정  
  
-   Z 순서 제한 이해  
  
-   도킹  
  
-   표시 유형 설정  
  
-   확장되지 않는 컨트롤 호스팅  
  
-   배율 조정  
  
-   회전  
  
-   안쪽 여백 및 여백 설정  
  
-   동적 레이아웃 컨테이너 사용  
  
 이 연습에서 설명하는 작업의 전체 코드 목록은 [Arranging Windows Forms Controls in WPF 샘플](http://go.microsoft.com/fwlink/?LinkID=159971)을 참조하십시오.  
  
 연습을 마치면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기반 응용 프로그램에서의 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 레이아웃 기능을 이해할 수 있게 됩니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## 프로젝트 만들기  
  
#### 프로젝트를 만들고 설정하려면  
  
1.  `WpfLayoutHostingWf`라는 WPF 응용 프로그램 프로젝트를 만듭니다.  
  
2.  솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
    -   System.Drawing  
  
3.  MainWindow.xaml을 두 번 클릭하여 XAML 뷰에서 엽니다.  
  
4.  <xref:System.Windows.Window> 요소에서 다음 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 네임스페이스 매핑을 추가합니다.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <xref:System.Windows.Controls.Grid> 요소에서 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 속성을 `true`로 설정하고 다섯 개의 행과 세 개의 열을 정의합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## 기본 레이아웃 설정 사용  
 기본적으로 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에서는 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 레이아웃을 처리합니다.  
  
#### 기본 레이아웃 설정을 사용하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=fullName> 컨트롤이 <xref:System.Windows.Controls.Canvas>에 나타납니다.  호스팅된 컨트롤의 크기가 해당 콘텐츠에 맞게 조정되고 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 크기가 호스팅된 컨트롤에 맞게 조정됩니다.  
  
## 콘텐츠에 맞게 크기 조정  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에서는 호스팅된 컨트롤이 해당 콘텐츠를 적절하게 표시할 수 있는 크기인지 확인합니다.  
  
#### 콘텐츠에 맞게 크기를 조정하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  새로운 두 단추 컨트롤의 크기가 긴 텍스트 문자열과 큰 글꼴 크기를 적절하게 표시할 수 있도록 조정되고 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 크기가 호스팅된 컨트롤에 맞게 조정됩니다.  
  
## 절대 위치 사용  
 절대 위치를 사용하여 UI\(사용자 인터페이스\)에서 임의의 위치에 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 배치할 수 있습니다.  
  
#### 절대 위치를 사용하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 표 셀의 위쪽에서 20픽셀, 왼쪽에서 20픽셀 떨어진 위치에 배치됩니다.  
  
## 명시적으로 크기 지정  
 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 사용하여 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 크기를 지정할 수 있습니다.  
  
#### 크기를 명시적으로 지정하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 기본 레이아웃 설정보다 작은 너비 50픽셀, 높이 70픽셀의 크기로 설정됩니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 콘텐츠가 적절하게 다시 정렬됩니다.  
  
## 레이아웃 속성 설정  
 호스팅된 컨트롤의 레이아웃 관련 속성은 항상 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 속성을 사용하여 설정합니다.  레이아웃 속성을 직접 호스팅된 컨트롤에 대해 설정하면 원치 않는 결과가 발생합니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 호스팅된 컨트롤에 대해 레이아웃 관련 속성을 설정해도 아무런 영향을 주지 않습니다.  
  
#### 호스팅된 컨트롤의 속성을 설정한 결과를 확인하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  솔루션 탐색기에서 MainWindow.xaml.vb  또는 MainWindow.xaml.cs를 두 번 클릭하여 코드 편집기에서 엽니다.  
  
3.  다음 코드를 `MainWindow` 클래스 정의에 복사합니다.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
5.  **Click me** 단추를 클릭합니다.  `button1_Click` 이벤트에서 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.Top%2A> 및 <xref:System.Windows.Forms.Control.Left%2A> 속성을 설정합니다.  그러면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 내에서 호스팅된 컨트롤의 위치가 변경됩니다.  호스트에서는 동일한 화면 크기를 유지하지만 호스팅된 컨트롤이 잘립니다.  대신 호스팅된 컨트롤에서 항상 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 채워야 합니다.  
  
## Z 순서 제한 이해  
 기본적으로 보이는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 위에 그려진 됩니다 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 및가 수 없습니다 z 축에 영향을 받는.  Z 순서를 사용 하도록 설정의 <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> 속성에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> true로 하는 <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> 속성에 <xref:System.Windows.Interop.CompositionMode.Full> 또는 <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### 기본 z 순서 동작을 보려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 레이블 요소 위에 그려집니다.  
  
#### Isredirected이 true 일 때의 z 순서 동작을 보려면  
  
1.  Z 축에서 앞의 예제는 다음 XAML을 대체 합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#8b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#8b)]  
  
     F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  Label 요소 위에 그려지는 지는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.  
  
## 도킹  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 도킹을 지원합니다.  <xref:System.Windows.Controls.DockPanel.Dock%2A> 연결 속성을 사용하여 <xref:System.Windows.Controls.DockPanel> 요소에서 호스팅된 컨트롤을 도킹하도록 설정합니다.  
  
#### 호스팅된 컨트롤을 도킹하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 <xref:System.Windows.Controls.DockPanel> 요소의 오른쪽에 도킹됩니다.  
  
## 표시 유형 설정  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.UIElement.Visibility%2A> 속성을 사용하여 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서 해당 요소를 보이지 않거나 축소되도록 만들 수 있습니다.  컨트롤이 보이지 않는 경우 컨트롤이 표시되지는 않지만 레이아웃 공간을 계속 차지합니다.  컨트롤이 축소되는 경우 컨트롤이 표시되지도 않고 레이아웃 공간을 차지하지도 않습니다.  
  
#### 호스팅된 컨트롤의 표시 유형을 설정하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 클래스 정의에 다음 코드를 복사합니다.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
4.  **Click to make invisible** 단추를 눌러 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 보이지 않게 만듭니다.  
  
5.  **Click to collapse** 단추를 눌러 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 레이아웃에서 완전히 숨깁니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 축소되는 경우 주변 요소가 해당 공간을 차지하도록 다시 정렬됩니다.  
  
## 확장되지 않는 컨트롤 호스팅  
 일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 고정된 크기를 가지며 레이아웃에서 사용 가능한 공간을 채우도록 확장되지 않습니다.  예를 들어 <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 고정된 공간에 월을 표시합니다.  
  
#### 확장되지 않는 컨트롤을 호스팅하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 표 행에서 가운데에 맞춰지지만 사용 가능한 공간을 채우도록 확장되지 않습니다.  창의 크기가 충분한 경우 호스팅된 <xref:System.Windows.Forms.MonthCalendar> 컨트롤에서 두 개 이상의 월을 표시하지만 이러한 값이 행의 가운데에 정렬됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 엔진에서는 사용 가능한 공간을 채우도록 크기 조정될 수 없는 요소를 가운데에 정렬합니다.  
  
## 배율 조정  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소와 달리 대부분의 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 계속해서 확장될 수 없습니다.  기본적으로 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 가능 하면 호스팅된 컨트롤의 배율을 조정 합니다.  완전 한 크기 조정을 사용 하려면 설정의 <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> 속성에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> true로 하는 <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> 속성에 <xref:System.Windows.Interop.CompositionMode.Full> 또는 <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### 호스팅된 컨트롤의 기본 동작을 사용 하 여 크기를 조정 하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  호스팅된 컨트롤과 주위 요소가 계수 0.5만큼 배율 조정됩니다.  그러나 호스팅된 컨트롤의 글꼴은 배율 조정되지 않습니다.  
  
#### Isredirected를 true로 설정 하 여 호스팅된 컨트롤의 크기를 조정 하려면  
  
1.  이전 예제를 확장 다음 XAML로 바꿉니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#12b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#12b)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  호스팅된 컨트롤, 주변 요소 및 호스팅된 컨트롤의 글꼴을 계수 0.5 만큼 배율 조정 됩니다.  
  
## 회전  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소와 달리 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서는 회전을 지원하지 않습니다.  기본적으로 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소와 회전 하지 않습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 회전 변환을 적용 하면 요소입니다.  180도 이외의 회전 값을 지정하면 <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 이벤트가 발생합니다.  회전 각도를 설정 하려면 설정의 <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> 속성에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> true로 하는 <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> 속성에 <xref:System.Windows.Interop.CompositionMode.Full> 또는 <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### 혼합 응용 프로그램에서 회전의 결과를 확인하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  호스팅된 컨트롤은 회전되지 않지만 주변 요소는 180도씩 회전합니다.  창의 크기를 조정해야 요소가 표시되는 경우도 있습니다.  
  
#### Isredirected가 true 이면 혼합 응용 프로그램에서 회전의 결과 보려면  
  
1.  이전 회전 예제를 다음 XAML로 바꿉니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#13b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#13b)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  호스팅된 컨트롤을 회전 합니다.  참고 해당 <xref:System.Windows.Media.RotateTransform.Angle%2A> 속성을 모든 값으로 설정할 수 있습니다.  창의 크기를 조정해야 요소가 표시되는 경우도 있습니다.  
  
## 안쪽 여백 및 여백 설정  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃에서 안쪽 여백 및 여백은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에서의 안쪽 여백 및 여백과 유사합니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에서 <xref:System.Windows.Controls.Control.Padding%2A> 및 <xref:System.Windows.FrameworkElement.Margin%2A> 속성을 설정하면 됩니다.  
  
#### 호스팅된 컨트롤의 안쪽 여백 및 여백을 설정하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  안쪽 여백 및 여백 설정은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에서 적용되는 것과 동일한 방식으로 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 적용됩니다.  
  
## 동적 레이아웃 컨테이너 사용  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에서는 <xref:System.Windows.Forms.FlowLayoutPanel> 및 <xref:System.Windows.Forms.TableLayoutPanel>이라는 두 가지 동적 레이아웃 컨테이너를 제공합니다.  또한 이러한 컨테이너를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃에서 사용할 수도 있습니다.  
  
#### 동적 레이아웃 컨테이너를 사용하려면  
  
1.  다음 XAML을 <xref:System.Windows.Controls.Grid> 요소에 복사합니다.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 클래스 정의에 다음 코드를 복사합니다.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  `InitializeFlowLayoutPanel` 메서드에 대한 호출을 생성자에 추가합니다.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 <xref:System.Windows.Controls.DockPanel>을 채우고 <xref:System.Windows.Forms.FlowLayoutPanel>에서 해당 자식 컨트롤을 기본 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>으로 정렬합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)   
 [WindowsFormsHost 요소에 대한 레이아웃 고려 사항](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)   
 [Arranging Windows Forms Controls in WPF 샘플](http://go.microsoft.com/fwlink/?LinkID=159971)   
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)