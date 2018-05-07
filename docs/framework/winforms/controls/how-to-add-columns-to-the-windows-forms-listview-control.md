---
title: '방법: Windows Forms ListView 컨트롤에 열 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 4c284e9d2798a1992e3152a85eca47c8d33bfde8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>방법: Windows Forms ListView 컨트롤에 열 추가
세부 정보 뷰에서 <xref:System.Windows.Forms.ListView> 컨트롤 각 목록 항목에 대 한 여러 열을 표시할 수 있습니다. 여러 유형의 각 목록 항목에 대 한 정보를 사용자에 게 표시 하는 열을 사용할 수 있습니다. 예를 들어 파일 이름, 파일 형식, 크기 및 파일을 마지막으로 수정한 날짜 파일의 목록을 표시할 수 있습니다. 생성 된 후 열을 채우는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Windows Forms ListView 컨트롤에서 열에 하위 항목 표시](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)합니다.  
  
### <a name="to-add-columns-programmatically"></a>프로그래밍 방식으로 열을 추가 하려면  
  
1.  컨트롤의 <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View.Details>합니다.  
  
2.  사용 하 여는 <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> 메서드 목록 보기의 <xref:System.Windows.Forms.ListView.Columns%2A> 속성입니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ListView>  
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
