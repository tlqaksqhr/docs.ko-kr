---
title: "방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61b2a39943dfca412afa4b66265aabbf65b9ccf0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정
처리 하 여 모든 셀의 모양을 사용자 지정할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellPainting> 이벤트입니다. 추출할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Drawing.Graphics> 에서 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> 의 속성은 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>합니다. 이 <xref:System.Drawing.Graphics>, 전체의 모양에 영향을 줄 수 <xref:System.Windows.Forms.DataGridView> 컨트롤 있지만 일반적으로 현재 칠하고 있는 셀의 모양에만 영향을 줄 합니다. <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> 의 속성은 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> 그리기 작업을 현재 칠하고 있는 셀을 제한할 수 있습니다.  
  
 다음 코드 예제에서는 모든 셀을 그리도록는 `ContactName` 사용 하 여 열 여 <xref:System.Windows.Forms.DataGridView> 컨트롤의 색 구성표입니다. 각 셀의 텍스트 내용에 그려질 때 <xref:System.Drawing.Color.Crimson%2A>, 동일한 색으로에서 삽입 사각형이 그려집니다 및는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성입니다.  
  
## <a name="example"></a>예  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   A <xref:System.Windows.Forms.DataGridView> 라는 컨트롤 `dataGridView1` 와 `ContactName` Northwind 샘플 데이터베이스의 Customers 테이블에 같은 열입니다.  
  
-   System, System.Windows.Forms 및 System.Drawing 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellPainting>  
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
