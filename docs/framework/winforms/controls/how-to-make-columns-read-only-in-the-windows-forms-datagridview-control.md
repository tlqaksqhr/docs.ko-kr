---
title: "방법: Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정 | Microsoft Docs"
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
  - "데이터 표, 읽기 전용 열"
  - "DataGridView 컨트롤[Windows Forms], 읽기 전용 열"
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정
일부 데이터는 편집할 수 없습니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤에서 열의 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 속성 값은 사용자가 해당 열의 셀을 편집할 수 있는지 여부를 결정합니다.  컨트롤을 완전히 읽기 전용으로 설정하는 방법에 대한 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)를 참조하세요.  
  
 Visual Studio에서는 이 작업이 지원됩니다.  [방법: Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정](http://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\))을 참조하세요.  
  
### 프로그래밍 방식으로 열을 읽기 전용으로 설정하려면  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName> 속성을 `true`으로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   이름이 `CompanyName`인 열을 포함하는 이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)