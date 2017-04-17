---
title: "HelpProvider 구성 요소 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "HelpProvider"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "대화 상자, 상황에 맞는 도움말"
  - "F1 도움말, Windows Forms에 추가"
  - "도움말, Windows 응용 프로그램에 추가"
  - "HelpProvider 구성 요소[Windows Forms], HelpProvider 구성 요소 정보"
  - "Windows Forms, 상황에 맞는 도움말"
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# HelpProvider 구성 요소 개요(Windows Forms)
Windows Forms [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)구성 요소를 사용하여 HTML Help 1.x 도움말 파일\(HTML Help Workshop으로 만든 .chm 또는 .htm 파일\)을 Windows 응용 프로그램에 연결할 수 있습니다.  다음과 같은 다양한 방식으로 도움말을 제공할 수 있습니다.  
  
-   Windows Forms의 컨트롤에 대한 상황에 맞는 도움말을 제공합니다.  
  
-   특정 대화 상자나 대화 상자의 특정 컨트롤에 대한 상황에 맞는 도움말을 제공합니다.  
  
-   목차의 기본 페이지, 색인, 검색 기능 등의 특정 영역에서 도움말 파일을 엽니다.  
  
## Help Provider 사용  
 Windows Form에 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 추가하면 폼의 다른 컨트롤에서 <xref:System.Windows.Forms.HelpProvider> 구성 요소의 도움말 속성을 노출할 수 있습니다.  따라서 Windows Form의 컨트롤에 대한 도움말을 제공할 수 있습니다.  <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 속성을 사용하여 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 도움말 파일과 연결할 수 있습니다.  <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A>를 호출하고 지정한 컨트롤에 대한 <xref:System.Windows.Forms.HelpNavigator> 열거형의 값을 ㅈ공하여 도움말 형식을 지정합니다.  <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> 메서드를 호출하여 도움말에 대한 키워드 또는 항목을 제공합니다.  
  
 필요에 따라 특정 도움말 문자열을 다른 컨트롤과 연결하려면 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 메서드를 사용합니다.  컨트롤에 포커스가 있을 때 F1 키를 누르면 이 메서드를 사용하여 컨트롤과 연결한 문자열이 팝업 창에 표시됩니다.  
  
 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>를 설정하지 않았으면 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>을 사용하여 도움말 텍스트를 제공해야 합니다.  <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>와 도움말 문자열을 모두 설정한 경우에는 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>를 사용하는 도움말이 우선합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.HelpProvider> 컨트롤의 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 속성 또는 <xref:System.Windows.Forms.Help.ShowHelp%2A> 메서드에 도움말 파일에 대한 경로를 지정할 때 상대 경로를 사용하면 문제가 발생할 수 있습니다.  그러므로 도움말 파일을 지정할 때는 절대 파일 경로를 사용해야 합니다.  
  
## 참고 항목  
 [Windows Forms 응용 프로그램의 도움말 시스템](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)