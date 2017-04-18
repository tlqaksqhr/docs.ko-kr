---
title: "인코딩 및 Windows Forms 전역화 | Microsoft Docs"
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
  - "DateTimePicker 컨트롤[Windows Forms], 유니코드 지원 문제"
  - "전역화[Windows Forms], 문자 집합"
  - "ImageList 구성 요소[Windows Forms], 유니코드 지원 문제"
  - "국가별 응용 프로그램[Windows Forms], 문자 표시"
  - "국가별 문자"
  - "ListView 컨트롤[Windows Forms], 유니코드 지원 문제"
  - "지역화[Windows Forms], 문자 집합"
  - "MonthCalendar 컨트롤[Windows Forms], 유니코드 지원 문제"
  - "ProgressBar 컨트롤[Windows Forms], 유니코드 사용 폼"
  - "StatusBar 컨트롤[Windows Forms], 유니코드 지원 문제"
  - "TabControl 컨트롤[Windows Forms], 유니코드 지원 문제"
  - "ToolBar 컨트롤[Windows Forms], 유니코드 지원 문제"
  - "TrackBar 컨트롤[Windows Forms], 유니코드 지원 문제"
  - "TreeView 컨트롤[Windows Forms], 유니코드 지원 문제"
  - "유니코드[Windows Forms]"
  - "Windows Forms, 인코딩"
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 인코딩 및 Windows Forms 전역화
Windows Forms 응용 프로그램은 완전히 유니코드를 사용할 수 있으므로 플랫폼, 프로그램 또는 언어에 관계없이 각 문자가 고유한 숫자로 표시됩니다.  유니코드에 대한 자세한 내용은 [유니코드 컨소시엄 웹 사이트](http://www.unicode.org)\(영문\)를 참조하세요.  
  
## 유니코드의 이점  
 유니코드 사용 폼의 이점에는 힌디어와 같은 유니코드 전용 스크립트로 작업할 수 있는 기능이 포함됩니다.  또한 단일 폼에서 여러 언어를 사용할 수 있습니다.  유니코드에서는 모든 문자가 2바이트 길이이므로 더블바이트 문자를 나타내기 위한 특별한 작업이 필요하지 않습니다.  모든 플랫폼에서 작동하는 단일 코드 집합을 작성할 수도 있습니다.  이는 Windows NT, [!INCLUDE[win98](../../../../includes/win98-md.md)] 등의 플랫폼마다 각기 다른 코드를 작성해야 했던 이전 버전의 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]에서 변경된 내용입니다.  
  
 그러나 특정 컨트롤은 [!INCLUDE[win98](../../../../includes/win98-md.md)] 및 Windows Millennium Edition에서 유니코드를 지원하지 않습니다.  모두 공용 컨트롤에서 상속되는 이러한 컨트롤은 Windows 코드 페이지에서 [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)]로 데이터를 처리합니다.  해당 컨트롤은 <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar> 및 <xref:System.Windows.Forms.StatusBar>입니다.  따라서 나열된 플랫폼의 이 컨트롤에는 유니코드 데이터를 표시할 수 없습니다.  예를 들어 영어 [!INCLUDE[win98](../../../../includes/win98-md.md)] 운영 체제에서는 일본어 문자를 표시할 수 없습니다.  
  
 <xref:System.Windows.Forms.ToolBar> 및 <xref:System.Windows.Forms.StatusBar> 컨트롤에 대한 유니코드 인식 대체 항목으로 이러한 이전 컨트롤을 대체하는 <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 사용합니다.  응용 프로그램에서 시각적 요소 간에 비슷한 모양과 느낌을 유지 관리하려면 <xref:System.Windows.Forms.MainMenu> 대신 메뉴 렌더링에 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용합니다.  <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.StatusStrip>과 마찬가지로, <xref:System.Windows.Forms.MenuStrip>도 유니코드 문자를 처리하고 표시할 수 있습니다.  
  
## 참고 항목  
 [Windows Forms 전역화](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)