---
title: '방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: a1d2338250abbced89ef7821d02edc654d26d7fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539108"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기
선택한 셀, 행 또는 열을 가져올 수는 <xref:System.Windows.Forms.DataGridView> 해당 속성을 사용 하 여 컨트롤: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, 및 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>합니다. 다음 절차에서 있습니다는 선택한 셀 가져오고 표시에서 해당 행 및 열 인덱스는 <xref:System.Windows.Forms.MessageBox>합니다.  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a>DataGridView 컨트롤에서 선택한 셀을 얻으려면  
  
-   <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 속성을 사용합니다.  
  
    > [!NOTE]
    >  사용 된 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 메서드를 잠재적으로 많은 수의 셀을 표시 하지 않도록 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a>DataGridView 컨트롤에서 선택한 행을 가져오려면  
  
-   <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 속성을 사용합니다. 사용자가 행을 선택할 수 있도록 설정 해야 합니다는 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a>DataGridView 컨트롤의 선택 된 열을 가져오려면  
  
-   <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 속성을 사용합니다. 사용자가 열을 선택할 수 있도록 설정 해야 합니다는 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Windows.Forms.Button> 라는 컨트롤 `selectedCellsButton`, `selectedRowsButton`, 및 `selectedColumnsButton`, 각각에 대 한 처리기는 <xref:System.Windows.Forms.Control.Click> 연결 이벤트입니다.  
  
-   `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Text?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 이 항목에 설명 된 컬렉션은 많은 수의 셀, 행 또는 열을 선택한 경우 효율적으로 수행 하지 않습니다. 이러한 컬렉션을 사용 하 여 많은 양의 데이터에 대 한 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 크기 조정에 대 한 유용한](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>  
 [Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
