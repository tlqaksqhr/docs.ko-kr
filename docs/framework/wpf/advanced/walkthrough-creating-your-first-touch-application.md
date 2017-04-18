---
title: "연습: 첫 응용 프로그램 만들기 | Microsoft Docs"
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
  - "터치 스크린 응용 프로그램 만들기[WPF]"
  - "터치 지원 응용 프로그램 만들기[WPF]"
  - "터치 스크린 응용 프로그램[WPF], 만들기"
  - "터치 지원 응용 프로그램[WPF], 만들기"
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 연습: 첫 응용 프로그램 만들기
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하여 응용 프로그램이 터치에 응답할 수 있습니다.  예를 들어 터치 스크린과 같은 터치 인식 장치에서 손가락을 사용하여 응용 프로그램과 상호 작용할 수 있습니다. 이 연습에서는 터치를 통해 단일 개체를 이동, 크기 조정 또는 회전할 수 있는 응용 프로그램을 만듭니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7  
  
-   Windows Touch를 지원하는 터치 스크린과 같은 터치 입력을 허용하는 장치  
  
 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 응용 프로그램을 만드는 방법 특히, 이벤트를 구독하고 처리하는 방법을 기본적으로 알고 있어야 합니다.  자세한 내용은 [연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)을 참조하십시오.  
  
## 응용 프로그램 만들기  
  
#### 응용 프로그램을 만들려면  
  
1.  Visual Basic 또는 Visual C\#에서 `BasicManipulation`이라는 새 WPF 응용 프로그램 프로젝트를 만듭니다.  자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/ko-kr/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하십시오.  
  
2.  MainWindow.xaml의 내용을 다음 XAML로 바꿉니다.  
  
     이 태그는 <xref:System.Windows.Controls.Canvas>에서 빨간색 <xref:System.Windows.Shapes.Rectangle>을 포함하는 간단한 응용 프로그램을 만듭니다.  <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.UIElement.IsManipulationEnabled%2A> 속성은 조직 이벤트를 받도록 true로 설정되어 있습니다.  응용 프로그램에서는 <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta> 및 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트를 구독합니다.  이러한 이벤트에는 사용자가 조작할 때 <xref:System.Windows.Shapes.Rectangle>을 이동하기 위한 논리가 포함되어 있습니다.  
  
     [!code-xml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  Visual Basic을 사용하는 경우에는 MainWindow.xaml의 첫 번째 줄에서 `x:Class="BasicManipulation.MainWindow"`를 `x:Class="MainWindow"`로 바꿉니다.  
  
4.  `MainWindow` 클래스에서 다음 <xref:System.Windows.UIElement.ManipulationStarting> 이벤트 처리기를 추가합니다.  
  
     <xref:System.Windows.UIElement.ManipulationStarting> 이벤트는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 터치 입력을 통한 개체 조작을 감지하면 발생합니다.  이 코드에서는 <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> 속성을 설정하여 조작 위치가 <xref:System.Windows.Window>에 상대적이 되도록 지정합니다.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  `MainWindow` 클래스에서 다음 <xref:System.Windows.Input.ManipulationDelta> 이벤트 처리기를 추가합니다.  
  
     <xref:System.Windows.Input.ManipulationDelta> 이벤트는 터치 입력으로 위치를 변경할 때 발생하며 조작 중에 여러 번 발생할 수 있습니다.  손가락을 치운 이후에도 이벤트가 발생할 수 있습니다.  예를 들어 화면에서 손가락을 끌면 손가락이 움직이는 동안 <xref:System.Windows.Input.ManipulationDelta> 이벤트가 여러 번 발생합니다.  화면에서 손가락을 치워도 <xref:System.Windows.Input.ManipulationDelta> 이벤트가 계속 발생하여 관성의 법칙을 시뮬레이션합니다.  
  
     이 코드에서는 사용자의 터치 입력에 따라 이동하도록 <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A>을 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.UIElement.RenderTransform%2A>에 적용합니다.  또한 관성의 법칙이 적용되는 동안 이벤트가 발생할 때 <xref:System.Windows.Shapes.Rectangle>이 <xref:System.Windows.Window>의 범위를 벗어나는지 여부를 확인합니다.  범위를 벗어나면 응용 프로그램에서 <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=fullName> 메서드를 호출하여 조작을 종료합니다.  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  `MainWindow` 클래스에서 다음 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트 처리기를 추가합니다.  
  
     <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트는 화면에서 손가락을 모두 치우면 발생합니다.  이 코드에서는 사각형의 이동, 확장 및 회전에 대한 초기 속도와 선언을 설정합니다.  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  프로젝트를 빌드하고 실행합니다.  
  
     빨간색 사각형이 창에 나타납니다.  
  
## 응용 프로그램 테스트  
 응용 프로그램을 테스트하려면 다음 조작을 시도합니다.  다음 중 여러 작업을 동시에 수행할 수 있습니다.  
  
-   <xref:System.Windows.Shapes.Rectangle>을 이동하려면 <xref:System.Windows.Shapes.Rectangle>에 손가락을 놓고 화면에서 손가락을 이동합니다.  
  
-   <xref:System.Windows.Shapes.Rectangle>의 크기를 조정하려면 <xref:System.Windows.Shapes.Rectangle>에 두 손가락을 놓은 다음 손가락을 모으거나 벌립니다.  
  
-   <xref:System.Windows.Shapes.Rectangle>을 회전하려면 <xref:System.Windows.Shapes.Rectangle>에 두 손가락을 놓고 손가락을 서로 회전시킵니다.  
  
 관성이 작용하도록 하려면 이전 조작을 수행하면서 화면에서 손가락을 빠르게 치웁니다.  <xref:System.Windows.Shapes.Rectangle>이 2초 동안 계속 이동, 크기 조정 또는 회전하다가 멈춥니다.  
  
## 참고 항목  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=fullName>   
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=fullName>   
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=fullName>