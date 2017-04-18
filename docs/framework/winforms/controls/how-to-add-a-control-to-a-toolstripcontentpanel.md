---
title: "방법: ToolStripContentPanel에 컨트롤 추가 | Microsoft Docs"
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
  - "ToolStripContentPanel[Windows Forms], 컨트롤 추가"
ms.assetid: fa410960-bf1a-42fc-80e8-f2e27fb3dbb8
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: ToolStripContentPanel에 컨트롤 추가
컨트롤 하나 이상을 프로그래밍 방식으로 <xref:System.Windows.Forms.ToolStripContentPanel>에 추가할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.RichTextBox>를 <xref:System.Windows.Forms.ToolStripContentPanel>에 추가하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripContainer/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripContainer/VB/Form1.vb#1)]  
  
## 코드 컴파일  
 이 코드 예제에는 다음이 필요합니다.  
  
-   System, System.Data 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) 또는 [ToolStripContainer 작업 대화 상자](http://msdn.microsoft.com/library/ms233647\(v=vs.110\))를 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStripContentPanel>   
 <xref:System.Windows.Forms.ToolStripContainer>   
 [ToolStripContainer 컨트롤](../../../../docs/framework/winforms/controls/toolstripcontainer-control.md)   
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)