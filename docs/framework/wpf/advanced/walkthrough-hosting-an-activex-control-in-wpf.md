---
title: "연습: WPF에서 ActiveX 컨트롤 호스팅 | Microsoft Docs"
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
  - "ActiveX 컨트롤[WPF 상호 운용성]"
  - "ActiveX 컨트롤 호스팅"
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# 연습: WPF에서 ActiveX 컨트롤 호스팅
브라우저와의 상호 작용을 개선하기 위해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기반 응용 프로그램에서 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 컨트롤을 사용할 수 있습니다.  이 연습에서는 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)]를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지의 컨트롤로 호스팅하는 방법을 보여 줍니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   프로젝트 만들기  
  
-   ActiveX 컨트롤 만들기  
  
-   WPF 페이지에서 ActiveX 컨트롤 호스팅  
  
 이 연습을 마치면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기반 응용 프로그램에서 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 컨트롤을 사용하는 방법을 이해하게 됩니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]가 설치된 컴퓨터에 설치된 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)]  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## 프로젝트 만들기  
  
#### 프로젝트를 만들고 설정하려면  
  
1.  `HostingAxInWpf`라는 WPF 응용 프로그램 프로젝트를 만듭니다.  
  
2.  Windows Forms 컨트롤 라이브러리 프로젝트를 솔루션에 추가하고 프로젝트의 이름을 `WmpAxLib`로 지정합니다.  
  
3.  WmpAxLib 프로젝트에서 wmp.dll이라는 Windows Media Player 어셈블리에 대한 참조를 추가합니다.  
  
4.  **도구 상자**를 엽니다.  
  
5.  **도구 상자**에서 마우스 오른쪽 단추를 클릭한 다음 **항목 선택**을 클릭합니다.  
  
6.  **COM 구성 요소** 탭을 클릭하고 **Windows Media Player** 컨트롤을 선택한 다음 **확인**을 클릭합니다.  
  
     Windows Media Player 컨트롤이 **도구 상자**에 추가됩니다.  
  
7.  솔루션 탐색기에서 **UserControl1** 파일을 마우스 오른쪽 단추로 클릭한 다음 **이름 바꾸기**를 클릭합니다.  
  
8.  언어에 따라 이름을 `WmpAxControl.vb` 또는 `WmpAxControl.cs`로 변경합니다.  
  
9. 모든 참조의 이름을 바꾸라는 메시지가 나타나면 **예**를 클릭합니다.  
  
## ActiveX 컨트롤 만들기  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]에서는 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 컨트롤이 디자인 화면에 추가되면 이 컨트롤에 대한 <xref:System.Windows.Forms.AxHost> 래퍼 클래스를 자동으로 생성합니다.  다음 절차에서는 AxInterop.WMPLib.dll이라는 관리되는 어셈블리를 만듭니다.  
  
#### ActiveX 컨트롤을 만들려면  
  
1.  Windows Forms 디자이너에서 WmpAxControl.vb 또는 WmpAxControl.cs를 엽니다.  
  
2.  **도구 상자**에서 Windows Media Player 컨트롤을 디자인 화면에 추가합니다.  
  
3.  속성 창에서 Windows Media Player 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  
  
4.  WmpAxLib 컨트롤 라이브러리 프로젝트를 빌드합니다.  
  
## WPF 페이지에서 ActiveX 컨트롤 호스팅  
  
#### ActiveX 컨트롤을 호스팅하려면  
  
1.  HostingAxInWpf 프로젝트에서 생성된 [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] 상호 운용성 어셈블리에 대한 참조를 추가합니다.  
  
     이 어셈블리는 이름이 AxInterop.WMPLib.dll이며 Windows Media Player 컨트롤을 가져올 때 WmpAxLib 프로젝트의 Debug 폴더에 추가되었습니다.  
  
2.  WindowsFormsIntegration.dll이라는 WindowsFormsIntegration 어셈블리에 대한 참조를 추가합니다.  
  
3.  System.Windows.Forms.dll이라는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 어셈블리에 대한 참조를 추가합니다.  
  
4.  WPF Designer에서 MainWindow.xaml을 엽니다.  
  
5.  <xref:System.Windows.Controls.Grid> 요소의 이름을 `grid1`로 지정합니다.  
  
     [!code-xml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  디자인 뷰 또는 XAML 뷰에서 <xref:System.Windows.Window> 요소를 선택합니다.  
  
7.  속성 창에서 **이벤트** 탭을 클릭합니다.  
  
8.  <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 두 번 클릭합니다.  
  
9. 다음 코드를 삽입하여 <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리합니다.  
  
     이 코드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤의 인스턴스를 만들고 `AxWindowsMediaPlayer` 컨트롤의 인스턴스를 자식으로 추가합니다.  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)   
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)