---
title: "방법: 전문적인 스타일의 ToolStrip 컨트롤 만들기 | Microsoft Docs"
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
  - "도구 모음[Windows Forms]"
  - "ToolStrip 컨트롤[Windows Forms]"
  - "ToolStripProfessionalRenderer 클래스[Windows Forms]"
  - "ToolStripRenderer 클래스[Windows Forms]"
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 전문적인 스타일의 ToolStrip 컨트롤 만들기
<xref:System.Windows.Forms.ToolStripProfessionalRenderer> 형식에서 파생된 고유한 클래스를 작성하여 응용 프로그램의 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 전문적인 모양과 동작\(모양 및 느낌\)을 제공할 수 있습니다.  
  
 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서는 이 기능이 광범위하게 지원됩니다.  
  
 [연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md)  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 사용하여 Microsoft® Outlook®에서 제공하는 **탐색 창**과 비슷한 복합 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기](http://msdn.microsoft.com/library/ms233664\(v=vs.110\))를 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [방법: 폼에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)