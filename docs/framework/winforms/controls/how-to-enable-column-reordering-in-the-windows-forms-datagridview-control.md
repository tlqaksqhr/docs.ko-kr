---
title: "방법: Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용 | Microsoft Docs"
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
  - "열[Windows Forms], 다시 정렬"
  - "데이터 표, 열 다시 정렬"
  - "DataGridView 컨트롤[Windows Forms], 열 순서"
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용
<xref:System.Windows.Forms.DataGridView> 컨트롤에서 열 다시 정렬을 사용하도록 설정하면 사용자가 마우스로 열 머리글을 끌어서 열을 새 위치로 이동할 수 있습니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤에서 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName> 속성 값은 사용자가 열을 다른 위치로 이동할 수 있는지 여부를 결정합니다.  
  
 Visual Studio에서는 이 작업이 지원됩니다.  [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용](http://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))을 참조하세요.  
  
### 프로그래밍 방식으로 열 다시 정렬을 사용하도록 설정하려면 다음을 수행합니다.  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName> 속성을 `true`으로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 열 고정](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)