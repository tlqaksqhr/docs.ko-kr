---
title: "방법: TreeView 노드에 바로 가기 메뉴 연결 | Microsoft Docs"
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
  - "바로 가기 메뉴, TreeView 컨트롤에 추가"
  - "TreeView 컨트롤의 트리 노드, 바로 가기 메뉴"
  - "TreeView 컨트롤[Windows Forms], 바로 가기 메뉴 추가"
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: TreeView 노드에 바로 가기 메뉴 연결
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤은 Windows 탐색기의 왼쪽 창에 파일과 폴더가 표시되는 방식과 비슷한 방식으로 노드의 계층 구조를 표시하는 데 사용됩니다.  <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 설정하면 사용자가 <xref:System.Windows.Forms.TreeView> 컨트롤을 마우스 오른쪽 단추로 클릭할 경우 상황에 맞는 작업을 제공할 수 있습니다.  <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 개별 <xref:System.Windows.Forms.TreeNode> 항목과 연결하면 <xref:System.Windows.Forms.TreeView> 컨트롤에 사용자 지정된 수준의 바로 가기 메뉴 기능을 추가할 수 있습니다.  
  
### 바로 가기 메뉴를 TreeNode와 프로그래밍 방식으로 연결하려면  
  
1.  적절한 속성 설정을 사용하여 <xref:System.Windows.Forms.TreeView> 컨트롤을 인스턴스화하고 루트 <xref:System.Windows.Forms.TreeNode>를 만든 다음 하위 노드를 추가합니다.  
  
2.  <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 인스턴스화한 다음, 런타임에 사용할 수 있도록 할 각 작업에 대한 <xref:System.Windows.Forms.ToolStripMenuItem>을 추가합니다.  
  
3.  적절한 <xref:System.Windows.Forms.TreeNode>의 <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> 속성을 해당 바로 가기 메뉴로 설정합니다.  
  
4.  이 속성이 설정되어 있을 때 노드를 마우스 오른쪽 단추로 클릭하면 바로 가기 메뉴가 표시됩니다.  
  
 다음 코드 예제에서는 <xref:System.Windows.Forms.TreeView>의 루트 <xref:System.Windows.Forms.TreeNode>와 연결된 기본 <xref:System.Windows.Forms.TreeView> 및 <xref:System.Windows.Forms.ContextMenuStrip>을 만듭니다.  개발 중인 <xref:System.Windows.Forms.TreeView>에 맞게 메뉴 선택을 사용자 지정해야 합니다.  또한 해당 메뉴 항목에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트를 처리하는 코드를 작성할 수 있습니다.  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Forms.ContextMenuStrip>   
 [TreeView 컨트롤](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)