---
title: "방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기 | Microsoft Docs"
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
  - "DataGridView 컨트롤[Windows Forms], 선택 항목 가져오기"
  - "선택 항목 가져오기, DataGridView 컨트롤[Windows Forms]"
  - "선택, DataGridView 컨트롤[Windows Forms]"
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기
<xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 및 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 중 해당하는 속성을 사용하여 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 선택한 셀, 행 또는 열을 가져올 수 있습니다.  다음 절차에서는 선택한 셀을 가져온 다음 이 셀의 행 및 열 인덱스를 <xref:System.Windows.Forms.MessageBox>에 표시합니다.  
  
### DataGridView 컨트롤에서 선택한 셀을 가져오려면  
  
-   <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 속성을 사용합니다.  
  
    > [!NOTE]
    >  너무 많은 셀을 표시하지 않도록 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 메서드를 사용합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### DataGridView 컨트롤에서 선택한 행을 가져오려면  
  
-   <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 속성을 사용합니다.  사용자가 행을 선택할 수 있게 하려면 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode>로 설정해야 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### DataGridView 컨트롤에서 선택한 열을 가져오려면  
  
-   <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 속성을 사용합니다.  사용자가 열을 선택할 수 있게 하려면 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode>로 설정해야 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `selectedCellsButton`, `selectedRowsButton` 및 `selectedColumnsButton`이라는 각각 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 처리기가 첨부된 <xref:System.Windows.Forms.Button> 컨트롤  
  
-   이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> 및 <xref:System.Text?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 강력한 프로그래밍  
 이 항목에서 설명된 컬렉션은 많은 수의 셀, 행 또는 열을 선택한 경우 효율적으로 수행되지 않습니다.  이러한 컬렉션을 많은 양의 데이터에 사용하는 방법은 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>   
 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>   
 [Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)