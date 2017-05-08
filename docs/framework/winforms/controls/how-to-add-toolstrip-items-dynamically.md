---
title: "방법: 동적으로 ToolStrip 항목 추가 | Microsoft Docs"
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
  - "ContextMenuStrip 컨트롤[Windows Forms]"
  - "도구 모음[Windows Forms], 동적으로 항목 추가"
  - "ToolStrip 컨트롤[Windows Forms]"
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 동적으로 ToolStrip 항목 추가
메뉴가 열릴 때 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 메뉴 항목 컬렉션을 동적으로 채울 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤에 항목을 동적으로 추가하는 방법을 보여 줍니다.  예제에서는 양식에서 세 가지 다른 컨트롤에 대해 같은 <xref:System.Windows.Forms.ContextMenuStrip>을 다시 사용하는 방법도 보여 줍니다.  
  
 예제에서 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트 처리기는 메뉴 항목 컬렉션을 채웁니다.  <xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트 처리기는 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=fullName> 및 <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=fullName> 속성을 검사하고 소스 컨트롤을 설명하는 <xref:System.Windows.Forms.ToolStripItem>을 추가합니다.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 <xref:System.Windows.Forms.ToolStripDropDownButton>   
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)