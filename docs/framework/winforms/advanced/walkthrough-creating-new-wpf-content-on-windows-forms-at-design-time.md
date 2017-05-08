---
title: "연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ElementHost 컨트롤"
  - "Windows Forms에서 WPF 콘텐츠 호스팅"
  - "상호 운용성, WPF 및 Windows Forms"
  - "WPF 콘텐츠, Windows Forms에서 호스팅"
  - "WPF 사용자 정의 컨트롤, Windows Forms에서 호스팅"
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기
이 항목에서는 Windows Forms 기반 응용 프로그램에서 사용할 WPF\(Windows Presentation Foundation\) 컨트롤을 만드는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트를 만듭니다.  
  
-   새 WPF 컨트롤을 만듭니다.  
  
-   새 WPF 컨트롤을 Windows Form에 추가합니다.  WPF 컨트롤이 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## 프로젝트 만들기  
 첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.  
  
> [!NOTE]
>  WPF 콘텐츠를 호스트하는 경우 C\# 및 Visual Basic 프로젝트만 지원됩니다.  
  
#### 프로젝트를 만들려면  
  
-   Visual Basic 또는 Visual C\#에서 `HostingWpf`라는 새 Windows Forms 응용 프로그램 프로젝트를 만듭니다.  
  
## 새 WPF 컨트롤 만들기  
 새 WPF 컨트롤을 만들고 프로젝트에 추가하는 작업은 다른 항목을 프로젝트에 추가하는 것만큼 쉽습니다.  Windows Forms 디자이너는 *복합 컨트롤* 또는 *사용자 정의 컨트롤*이라는 특정 종류의 컨트롤에서 작동합니다.  WPF 사용자 정의 컨트롤에 대한 자세한 내용은 <xref:System.Windows.Controls.UserControl>을 참조하세요.  
  
> [!NOTE]
>  WPF용 <xref:System.Windows.Controls.UserControl?displayProperty=fullName> 형식은 Windows Forms에서 제공하는 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>이라는 사용자 정의 컨트롤 형식과 별개입니다.  
  
#### 새 WPF 컨트롤을 만들려면  
  
1.  **솔루션 탐색기**에서 새 **WPF 사용자 정의 컨트롤 라이브러리** 프로젝트를 솔루션에 추가합니다.  컨트롤 라이브러리의 기본 이름인 `WpfControlLibrary1`을 사용합니다.  기본 컨트롤 이름은 `UserControl1.xaml`입니다.  
  
     새 컨트롤을 추가하면 다음과 같은 효과가 있습니다.  
  
    -   UserControl1.xaml 파일이 추가됩니다.  
  
    -   UserControl1.xaml.cs 또는 UserControl1.xaml.vb 파일이 추가됩니다.  이 파일에는 이벤트 처리기 및 기타 구현에 대한 코드 숨김이 포함됩니다.  
  
    -   WPF 어셈블리에 대한 참조가 추가됩니다.  
  
    -   UserControl1.xaml 파일이 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]에서 열립니다.  
  
2.  디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.  자세한 내용은 [방법: 디자인 화면의 요소 선택 및 이동](http://msdn.microsoft.com/ko-kr/54cb70b6-b35b-46e4-a0cc-65189399c474)을 참조하세요.  
  
3.  **속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성의 값을 `200`으로 설정합니다.  
  
4.  **도구 상자**에서 <xref:System.Windows.Controls.TextBox?displayProperty=fullName> 컨트롤을 디자인 화면으로 끕니다.  
  
5.  **속성** 창에서 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 값을 Hosted Content로 설정합니다.  
  
    > [!NOTE]
    >  일반적으로 더 복잡한 WPF 콘텐츠를 호스트해야 합니다.  <xref:System.Windows.Controls.TextBox?displayProperty=fullName> 컨트롤은 여기서 설명 목적으로만 사용됩니다.  
  
6.  프로젝트를 빌드합니다.  
  
## Windows Form에 WPF 컨트롤 추가  
 폼에서 새 WPF 컨트롤을 사용할 준비가 되었습니다.  Windows Forms는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 사용하여 WPF 콘텐츠를 호스트합니다.  
  
#### Windows Form에 WPF 컨트롤을 추가하려면  
  
1.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
2.  **도구 상자**에서 **WPFUserControlLibrary WPF 사용자 정의 컨트롤** 레이블이 있는 탭을 찾습니다.  
  
3.  `UserControl1` 인스턴스를 폼으로 끕니다.  
  
    -   WPF 컨트롤을 호스트할 폼에 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 자동으로 만들어집니다.  
  
    -   <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 이름이 `elementHost1`로 지정되고, **속성** 창에서 해당 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성이 **UserControl1**로 설정된 것을 확인할 수 있습니다.  
  
    -   WPF 어셈블리에 대한 참조가 프로젝트에 추가됩니다.  
  
    -   `elementHost1` 컨트롤에는 사용 가능한 호스팅 옵션을 표시하는 스마트 태그 패널이 있습니다.  
  
4.  **ElementHost 작업** 스마트 태그 패널에서 **부모 컨테이너에서 도킹**을 선택합니다.  
  
5.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
## 다음 단계  
 Windows Forms와 WPF는 서로 다른 기술이지만 긴밀하게 상호 운용하도록 설계되었습니다.  응용 프로그램에서 다양한 모양과 동작을 제공하려면 다음을 시도합니다.  
  
-   WPF 페이지에서 Windows Forms 컨트롤을 호스트합니다.  자세한 내용은 [연습: WPF에서 Windows Forms 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)를 참조하세요.  
  
-   WPF 콘텐츠에 Windows Forms 시각적 스타일을 적용합니다.  자세한 내용은 [방법: 혼합 응용 프로그램에서 비주얼 스타일 사용](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)을 참조하세요.  
  
-   WPF 콘텐츠의 스타일을 변경합니다.  자세한 내용은 [연습: WPF 콘텐츠 스타일 지정](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [WPF 컨트롤 사용](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)