---
title: "방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정 | Microsoft Docs"
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
  - "셀, DataGridView 컨트롤에서 사용자 지정"
  - "데이터 표, 셀 사용자 지정"
  - "DataGridView 컨트롤[Windows Forms], 셀 사용자 지정"
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정
<xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellPainting> 이벤트를 처리하여 모든 셀의 모양을 사용자 지정할 수 있습니다.  <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>의 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> 속성에서 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Drawing.Graphics>를 추출할 수 있습니다.  <xref:System.Drawing.Graphics>를 사용하여 전체 <xref:System.Windows.Forms.DataGridView> 컨트롤의 모양을 변경할 수 있지만 일반적으로 현재 그리고 있는 셀의 모양만 변경하려는 경우에는  <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>의 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> 속성을 사용하여 현재 그리고 있는 셀로 그리기 작업을 제한할 수 있습니다.  
  
 다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 색 구성표를 사용하여 `ContactName` 열의 모든 셀을 그립니다.  각 셀의 텍스트 내용은 <xref:System.Drawing.Color.Crimson%2A>으로 그려지고 셀 테두리 사각형은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성과 동일한 색으로 그려집니다.  
  
## 예제  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스의 Customers 테이블에 있는 것과 같은 `ContactName` 열을 포함하는 `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   System, System.Windows.Forms 및 System.Drawing 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CellPainting>   
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)