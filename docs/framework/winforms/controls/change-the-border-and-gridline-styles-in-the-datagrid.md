---
title: "방법: Windows Forms DataGridView 컨트롤의 테두리 및 모눈선 스타일 변경 | Microsoft Docs"
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
  - "데이터 표, 테두리 스타일 변경"
  - "데이터 표, 모눈선 스타일 변경"
  - "DataGridView 컨트롤[Windows Forms], 테두리 스타일"
  - "DataGridView 컨트롤[Windows Forms], 모눈선 스타일"
  - "모눈선, 스타일 변경"
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Forms DataGridView 컨트롤의 테두리 및 모눈선 스타일 변경
<xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하면 사용자가 컨트롤의 테두리 및 모눈선의 모양을 지정하여 사용자 환경을 향상시킬 수 있습니다.  컨트롤 내 셀의 테두리 스타일 외에도 모눈선 색과 컨트롤 테두리 스타일을 수정할 수 있습니다.  일반 셀, 행 머리글 셀 및 열 머리글 셀에 대해 다른 셀 테두리 스타일을 적용할 수도 있습니다.  
  
> [!NOTE]
>  모눈선 색은 <xref:System.Windows.Forms.DataGridViewCellBorderStyle> 열거형의 <xref:System.Windows.Forms.DataGridViewCellBorderStyle>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle> 및 <xref:System.Windows.Forms.DataGridViewCellBorderStyle> 값과 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> 열거형의 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> 값에만 사용됩니다.  이러한 열거형의 다른 값에서는 운영 체제에 지정된 색을 사용합니다.  또한 Windows XP 및 Windows Server 2003 제품군에서 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName> 메서드를 통해 비주얼 스타일을 사용하는 경우에는 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성 값이 사용되지 않습니다.  
  
### 프로그래밍 방식으로 모눈선 색을 변경하려면  
  
-   <xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### 프로그래밍 방식으로 전체 DataGridView 컨트롤의 테두리 스타일을 변경하려면  
  
-   <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> 속성을 <xref:System.Windows.Forms.BorderStyle> 열거형 값 중 하나로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### 프로그래밍 방식으로 DataGridView 셀의 테두리 스타일을 변경하려면  
  
-   <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> 속성을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## 예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> 및 <xref:System.Drawing?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.BorderStyle>   
 <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellBorderStyle>   
 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>   
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)