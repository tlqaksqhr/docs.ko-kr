---
title: "방법: 행 템플릿을 사용하여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정"
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
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4898ed7ddff6ca1800ba9380707ad989cbec1125
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>방법: 행 템플릿을 사용하여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정
<xref:System.Windows.Forms.DataGridView> 컨트롤 사용 하 여 행 템플릿을 기반으로 데이터 바인딩을 통해 또는 호출 하는 경우 컨트롤에 추가 하는 모든 행에 대 한는 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> 기존 행을 지정 하지 않고 메서드.  
  
 행 템플릿을 사용 모양 및 동작 보다는 행에 대 한 제어 강화는 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 속성을 제공 합니다. 행 템플릿을 사용 하 여 설정할 수 있습니다 <xref:System.Windows.Forms.DataGridViewRow> 속성을 포함 하 여 <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>합니다.  
  
 특정 결과를 얻을 행 템플릿을 사용 해야 하는 경우가 있습니다. 예를 들어에 행 높이 정보를 저장할 수 없습니다는 <xref:System.Windows.Forms.DataGridViewCellStyle>, 하므로 모든 행에서 사용 하는 기본 높이 변경 하려면 행 템플릿을 사용 해야 합니다. 행 템플릿을도 유용에서 파생 된 사용자 고유의 클래스를 만들 때 <xref:System.Windows.Forms.DataGridViewRow> 컨트롤에 새 행을 추가할 때 사용 되는 사용자 지정 형식 중이 고 합니다.  
  
> [!NOTE]
>  행 템플릿은 행을 추가 하는 경우에 사용 됩니다. 행 템플릿을 변경 하 여 기존 행을 변경할 수 없습니다.  
  
### <a name="to-use-the-row-template"></a>행 템플릿을 사용 하려면  
  
-   검색 된 개체의 속성을 설정는 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> 속성입니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>  
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
