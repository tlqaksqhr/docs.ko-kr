---
title: "방법: 디자인 타임에 ElementHost 컨트롤 복사하여 붙여넣기 | Microsoft Docs"
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
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 디자인 타임에 ElementHost 컨트롤 복사하여 붙여넣기
이 절차에서는 Windows Forms에 WPF\(Windows Presentation Foundation\) 컨트롤을 복사하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자인 타임에 ElementHost 컨트롤을 복사하여 붙여넣으려면  
  
1.  새 WPF <xref:System.Windows.Controls.UserControl>을 Windows Forms 프로젝트에 추가합니다.  컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.  자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)를 참조하십시오.  
  
2.  **속성** 창에서 `UserControl1`의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성 값을 `200`으로 설정합니다.  
  
3.  <xref:System.Windows.Controls.Control.Background%2A> 속성 값을 `Blue`로 설정합니다.  
  
4.  프로젝트를 빌드합니다.  
  
5.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
6.  **도구 상자**에서 `UserControl1`의 인스턴스를 폼으로 끌어 옵니다.  
  
     `UserControl1`의 인스턴스는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤\(`elementHost1`\)에서 호스팅됩니다.  
  
7.  `elementHost1`을 선택한 상태로 Ctrl\+C를 눌러 컨트롤을 클립보드로 복사합니다.  
  
8.  Ctrl\+V를 눌러 복사한 컨트롤을 폼에 붙여넣습니다.  
  
     새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤\(`elementHost2`\)이 폼에 만들어집니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [연습: ElementHost 컨트롤을 복사하여 다른 Windows Forms에 붙여넣기](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)   
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [WPF 컨트롤 사용](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)