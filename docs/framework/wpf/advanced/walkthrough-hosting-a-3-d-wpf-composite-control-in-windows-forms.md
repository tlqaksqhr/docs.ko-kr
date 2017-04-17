---
title: "연습: Windows Forms에서 3-D WPF 복합 컨트롤 호스팅 | Microsoft Docs"
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
  - "복합 컨트롤, WPF 호스팅"
  - "Windows Forms에서 WPF 콘텐츠 호스팅"
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# 연습: Windows Forms에서 3-D WPF 복합 컨트롤 호스팅
이 연습에서는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 컨트롤을 만들어 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 및 폼에서 호스팅할 수 있는 방법을 보여 줍니다.  
  
 이 연습에서는 두 개의 자식 컨트롤이 포함된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>을 구현합니다.  <xref:System.Windows.Controls.UserControl>은 3차원\(3\-D\) 원뿔형을 표시합니다.  3차원 개체 렌더링은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에서 보다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 훨씬 더 쉽습니다.  따라서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에서 3차원 그래픽을 만드는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 클래스를 호스팅하는 것이 좋습니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 만들기  
  
-   Windows Forms 호스트 프로젝트 만들기  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 호스팅  
  
 이 연습에서 설명하는 작업의 전체 코드 목록은 [Hosting a 3\-D WPF Composite Control in Windows Forms 샘플](http://go.microsoft.com/fwlink/?LinkID=160001)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
<a name="To_Create_the_UserControl"></a>   
## UserControl 만들기  
  
#### UserControl을 만들려면  
  
1.  `HostingWpfUserControlInWf`라는 WPF 사용자 컨트롤 라이브러리 프로젝트를 만듭니다.  
  
2.  [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]에서 UserControl1.xaml을 엽니다.  
  
3.  생성된 코드를 다음 코드로 바꿉니다.  
  
     이 코드는 두 개의 자식 컨트롤이 포함된 <xref:System.Windows.Controls.UserControl?displayProperty=fullName>을 정의합니다.  첫 번째 자식 컨트롤은 <xref:System.Windows.Controls.Label?displayProperty=fullName> 컨트롤이며 두 번째 자식 컨트롤은 3차원 원뿔형을 표시하는 <xref:System.Windows.Controls.Viewport3D> 컨트롤입니다.  
  
     [!code-xml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## Windows Forms 호스트 프로젝트 만들기  
  
#### 호스트 프로젝트를 만들려면  
  
1.  `WpfUserControlHost`라는 Windows 응용 프로그램 프로젝트를 솔루션에 추가합니다.  자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/ko-kr/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하십시오.  
  
2.  솔루션 탐색기에서 WindowsFormsIntegration.dll이라는 WindowsFormsIntegration 어셈블리에 대한 참조를 추가합니다.  
  
3.  다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리에 참조를 추가합니다.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
4.  `HostingWpfUserControlInWf` 프로젝트에 참조를 추가합니다.  
  
5.  솔루션 탐색기에서 `WpfUserControlHost` 프로젝트가 시작 프로젝트가 되도록 설정합니다.  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## Windows Presentation Foundation UserControl 호스팅  
  
#### UserControl을 호스팅하려면  
  
1.  Windows Forms 디자이너에서 Form1을 엽니다.  
  
2.  속성 창에서 **이벤트**를 클릭한 다음 <xref:System.Windows.Forms.Form.Load> 이벤트를 두 번 클릭하여 이벤트 처리기를 만듭니다.  
  
     새로 생성한 `Form1_Load` 이벤트 처리기에 대해 코드 편집기가 열립니다.  
  
3.  Form1.cs의 코드를 다음 코드로 바꿉니다.  
  
     `Form1_Load` 이벤트 처리기는 `UserControl1`의 인스턴스를 만들어 `` 자식 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 컬렉션에 추가합니다.  <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 자식 컨트롤의 폼 컬렉션에 추가됩니다.  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  F5 키를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)   
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Hosting a WPF Composite Control in Windows Forms 샘플](http://go.microsoft.com/fwlink/?LinkID=160001)