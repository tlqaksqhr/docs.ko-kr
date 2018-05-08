---
title: '방법: Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: fbcafae2cb4e4cc320c31794269355d6312b95b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용
<xref:System.Windows.Forms.DataGridView> 컨트롤에서 열 다시 정렬을 사용하도록 설정하면 사용자가 마우스로 열 머리글을 끌어서 열을 새 위치로 이동할 수 있습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤에서 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 속성 값은 사용자가 열을 다른 위치로 이동할 수 있는지 여부를 결정합니다.  
  
 Visual Studio에서는 이 작업이 지원됩니다.  또한 참조 [하는 방법: 열 다시 정렬 사용에 Windows Forms DataGridView 컨트롤 디자이너 사용](http://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))  
  
### <a name="to-enable-column-reordering-programmatically"></a>프로그래밍 방식으로 열 다시 정렬을 사용하도록 설정하려면 다음을 수행합니다.  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 속성을 `true`으로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>  
 [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤에서 열 고정](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
