---
title: "연습: ElementHost 컨트롤을 복사하여 다른 Windows Forms에 붙여넣기 | Microsoft Docs"
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
  - "ElementHost 컨트롤, 디자인 타임에 복사 및 붙여넣기"
  - "상호 운용성[WPF]"
  - "Windows Forms, 콘텐츠 복사 및 붙여넣기"
  - "WPF 사용자 정의 컨트롤, Windows Forms에서 호스팅"
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 연습: ElementHost 컨트롤을 복사하여 다른 Windows Forms에 붙여넣기
이 연습에서는 Windows Forms 간에 WPF\(Windows Presentation Foundation\) 컨트롤을 복사하는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트를 만듭니다.  
  
-   WPF 컨트롤을 복사합니다.  
  
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
  
-   Visual Basic 또는 Visual C\#에서 `CopyElementHost`라는 새 Windows Forms 응용 프로그램 프로젝트를 만듭니다.  
  
## WPF 컨트롤 복사  
 프로젝트에 WPF 컨트롤을 추가한 후 프로젝트의 다른 폼에 복사할 수 있습니다.  
  
#### WPF 컨트롤을 복사하려면  
  
1.  새 WPF <xref:System.Windows.Controls.UserControl> 프로젝트를 솔루션에 추가합니다.  컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.  자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)를 참조하세요.  
  
2.  프로젝트를 빌드합니다.  
  
3.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
4.  **도구 상자**에서 `UserControl1` 인스턴스를 폼으로 끌어 옵니다.  
  
     `UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.  
  
5.  `elementHost1`을 선택하고 Ctrl\+C를 눌러 클립보드에 복사합니다.  
  
6.  새 Windows Form을 프로젝트에 추가합니다.  폼 형식의 기본 이름인 `Form2`를 사용합니다.  
  
7.  Windows Forms 디자이너에서 `Form2`를 열고 Ctrl\+V를 눌러 `elementHost1`의 복사본을 폼에 붙여넣습니다.  
  
     `Form2` 클래스의 전용 필드이므로 복사된 컨트롤의 이름도 `elementHost1`로 지정됩니다.  `Form1` 클래스에서 `elementHost1`과 이름 충돌이 발생하지 않습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [WPF 컨트롤 사용](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)