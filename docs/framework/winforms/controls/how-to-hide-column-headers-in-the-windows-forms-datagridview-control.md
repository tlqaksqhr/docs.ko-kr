---
title: "방법: Windows Forms DataGridView 컨트롤에서 열 머리글 숨기기 | Microsoft Docs"
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
  - "열 머리글, 숨기기"
  - "열[Windows Forms], 열 머리글 숨기기"
  - "DataGridView 컨트롤[Windows Forms], 열 머리글"
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms DataGridView 컨트롤에서 열 머리글 숨기기
열 머리글 없이 <xref:System.Windows.Forms.DataGridView>를 표시할 수도 있습니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤에서 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> 속성 값은 열 머리글 표시 여부를 결정합니다.  
  
### 열 머리글을 숨기려면  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=fullName> 속성을 `false`으로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)