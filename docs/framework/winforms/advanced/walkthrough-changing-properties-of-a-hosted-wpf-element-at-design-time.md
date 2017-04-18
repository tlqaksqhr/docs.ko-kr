---
title: "연습: 디자인 타임에 호스팅된 WPF 요소의 속성 변경 | Microsoft Docs"
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
  - "상호 운용성[WPF]"
  - "Windows Forms, 디자인 타임에 WPF 콘텐츠의 속성 변경"
  - "WPF 콘텐츠[Windows Forms], 디자인 타임에 속성 변경"
  - "WPF 콘텐츠, Windows Forms에서 호스팅"
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 연습: 디자인 타임에 호스팅된 WPF 요소의 속성 변경
이 연습에서는 Windows Forms에 호스트된 WPF\(Windows Presentation Foundation\) 컨트롤의 속성 값을 변경하는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트를 만듭니다.  
  
-   WPF 컨트롤을 만듭니다.  
  
-   Windows Form에서 WPF 컨트롤을 호스트합니다.  
  
-   Visual Studio용 WPF 디자이너를 사용하여 속성 값을 변경합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## 프로젝트 만들기  
 첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.  
  
> [!NOTE]
>  WPF 콘텐츠를 호스트하는 경우 C\# 및 Visual Basic 프로젝트만 지원됩니다.  
  
#### 프로젝트를 만들려면  
  
-   Visual Basic 또는 Visual C\#에서 `WpfHost`라는 새 Windows Forms 응용 프로그램 프로젝트를 만듭니다.  
  
## WPF 컨트롤 만들기  
 프로젝트에 WPF 컨트롤을 추가한 후 폼에 정렬할 수 있습니다.  
  
#### WPF 컨트롤을 만들려면  
  
1.  프로젝트에 새 WPF <xref:System.Windows.Controls.UserControl>을 추가합니다.  컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.  자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)를 참조하세요.  
  
2.  **속성** 창에서 <xref:System.Windows.Controls.Control.Background%2A> 속성의 값을 `Blue`로 설정합니다.  
  
3.  프로젝트를 빌드합니다.  
  
## WPF 컨트롤의 속성 값 변경  
 <xref:System.Windows.Forms.Integration.ElementHost> 스마트 태그를 사용하면 WPF 디자이너에서 호스트된 WPF의 속성을 쉽게 변경할 수 있습니다.  
  
#### WPF 컨트롤을 호스트하려면  
  
1.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
2.  **도구 상자**의 **WPF 사용자 정의 컨트롤** 탭에서 `UserControl1`을 두 번 클릭하여 폼의 첫 번째 셀에 `UserControl1`의 인스턴스를 만듭니다.  
  
     `UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.  
  
3.  **ElementHost 작업** 스마트 태그 패널에서 **호스팅된 콘텐츠 편집**을 선택합니다.  
  
     UserControl1.xaml이 WPF 디자이너에서 열립니다.  
  
4.  **속성** 창에서 <xref:System.Windows.Controls.Control.Background%2A> 속성의 값을 `Red`로 설정합니다.  
  
5.  프로젝트를 다시 빌드합니다.  
  
6.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
     `UserControl1` 인스턴스의 배경색이 빨간색입니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)   
 [연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [WPF 컨트롤 사용](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)