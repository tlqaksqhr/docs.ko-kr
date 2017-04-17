---
title: "방법: Control 클래스에서 상속 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Control 클래스, 상속"
  - "사용자 지정 컨트롤[Windows Forms], 만들기"
  - "사용자 지정 컨트롤[Windows Forms], 상속"
  - "상속, Windows Forms 사용자 지정 컨트롤"
  - "OnPaint 메서드[Windows Forms]"
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Control 클래스에서 상속
Windows Forms에서 사용할 완전한 사용자 지정 컨트롤을 만들려면 <xref:System.Windows.Forms.Control> 클래스에서 상속해야 합니다.  <xref:System.Windows.Forms.Control> 클래스에서 상속하려면 보다 많은 계획과 구현을 수행해야 하지만 이는 광범위한 옵션을 제공합니다.  <xref:System.Windows.Forms.Control>에서 상속할 때 컨트롤이 작동되도록 하는 기본 기능을 상속하게 됩니다.  <xref:System.Windows.Forms.Control> 클래스의 고유 기능은 키보드와 마우스를 통한 사용자 입력을 처리하고 컨트롤의 범위와 크기를 정의하고 창 핸들을 제공하며 메시지 처리 및 보안을 제공합니다.  이 클래스는 그리기\(이 경우 컨트롤 그래픽 인터페이스의 실제 렌더링\) 및 특정 사용자 상호 작용 기능을 통합하지 않습니다.  사용자 지정 코드를 통해 이러한 모든 특성을 제공해야 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 사용자 지정 컨트롤을 만들려면  
  
1.  **Windows 응용 프로그램** 또는 **Windows 컨트롤 라이브러리** 프로젝트를 만듭니다.  
  
2.  **프로젝트** 메뉴에서 **클래스 추가**를 선택합니다.  
  
3.  **새 항목 추가** 대화 상자에서 **사용자 지정 컨트롤**을 클릭합니다.  
  
     새 사용자 지정 컨트롤이 프로젝트에 추가됩니다.  
  
4.  F7 키를 눌러 사용자 지정 컨트롤에 대한 **코드 편집기**를 엽니다.  
  
5.  <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 찾습니다. 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출하는 경우가 아니면 이 메서드는 비어 있습니다.  
  
6.  코드를 수정하여 컨트롤에 사용할 사용자 지정 그리기를 구체화합니다.  
  
     컨트롤에 대한 그래픽을 렌더링하는 코드를 작성하는 방법은 [사용자 지정 컨트롤 그리기 및 렌더링](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)을 참조하십시오.  
  
7.  컨트롤이 구체화할 모든 사용자 지정 메서드, 속성 또는 이벤트를 구현합니다.  
  
8.  컨트롤을 저장한 다음 테스트합니다.  
  
## 참고 항목  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [방법: UserControl 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)   
 [방법: 기존 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)   
 [방법: Windows Forms 컨트롤 제작](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Troubleshooting Inherited Event Handlers in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)   
 [디자인할 때 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)