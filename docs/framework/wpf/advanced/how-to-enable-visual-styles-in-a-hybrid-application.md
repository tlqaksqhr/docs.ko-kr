---
title: "방법: 혼합 응용 프로그램에서 비주얼 스타일 사용 | Microsoft Docs"
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
  - "혼합 응용 프로그램[WPF 상호 운용성]"
  - "비주얼 스타일[Windows Forms]"
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 혼합 응용 프로그램에서 비주얼 스타일 사용
이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기반 응용 프로그램에 호스팅되는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 비주얼 스타일을 사용하는 방법을 보여 줍니다.  
  
 응용 프로그램에서 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드를 호출하면 대부분의 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서는 응용 프로그램이 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]에서 실행될 경우 자동으로 비주얼 스타일을 사용합니다.  자세한 내용은 [비주얼 스타일을 사용하여 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)을 참조하십시오.  
  
 이 항목에서 설명하는 작업의 전체 코드 목록은 [Enabling Visual Styles in a Hybrid Application 샘플](http://go.microsoft.com/fwlink/?LinkID=159986)을 참조하십시오.  
  
## Windows Forms 비주얼 스타일 사용  
  
#### Windows Forms 비주얼 스타일을 사용하려면  
  
1.  `HostingWfWithVisualStyles`라는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 프로젝트를 만듭니다.  
  
2.  솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  도구 상자에서 <xref:System.Windows.Controls.Grid> 아이콘을 두 번 클릭하여 디자인 화면에 <xref:System.Windows.Controls.Grid> 요소를 배치합니다.  
  
4.  속성 창에서 <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Width%2A> 속성의 값을 **Auto**로 설정합니다.  
  
5.  디자인 뷰 또는 XAML 뷰에서 <xref:System.Windows.Window>를 선택합니다.  
  
6.  속성 창에서 **이벤트** 탭을 클릭합니다.  
  
7.  <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 두 번 클릭합니다.  
  
8.  MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 다음 코드를 삽입하여 <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리합니다.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
     [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 비주얼 스타일로 그려집니다.  
  
## Windows Forms 비주얼 스타일 사용 안 함  
 비주얼 스타일을 사용하지 않으려면 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드에 대한 호출을 제거하기만 하면 됩니다.  
  
#### Windows Forms 비주얼 스타일을 사용하지 않으려면  
  
1.  코드 편집기에서 MainWindow.xaml.vb 또는 MainWindow.xaml.cs를 엽니다.  
  
2.  <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드에 대한 호출을 주석으로 처리합니다.  
  
3.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
     [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 기본 시스템 스타일로 그려집니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>   
 <xref:System.Windows.Forms.VisualStyles>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [비주얼 스타일을 사용하여 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)   
 [연습: WPF에서 Windows Forms 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)