---
title: '방법: Windows Forms에서 데이터 탐색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: 9572c1234c07c77d5df0c9cd58499faafe460e4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540370"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>방법: Windows Forms에서 데이터 탐색
Windows 응용 프로그램에서 데이터 원본의 레코드를 탐색 하는 가장 쉬운 방법은에 바인딩하는 것을 <xref:System.Windows.Forms.BindingSource> 구성 요소는 데이터 소스를 바인딩한 다음 컨트롤에는 <xref:System.Windows.Forms.BindingSource>합니다. 다음 기본 제공 탐색 메서드를 사용할 수 있습니다는 <xref:System.Windows.Forms.BindingSource> 이러한는 <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> 및 <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>합니다. 이러한 메서드를 사용 하는 조정는 <xref:System.Windows.Forms.BindingSource.Position%2A> 및 <xref:System.Windows.Forms.BindingSource.Current%2A> 의 속성은 <xref:System.Windows.Forms.BindingSource> 적절 하 게 합니다. 항목을 찾을 수 있고 설정 하 여 현재 항목으로 설정 하면는 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성입니다.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>데이터 소스에서 위치를 증가 시키기  
  
1.  설정의 <xref:System.Windows.Forms.BindingSource.Position%2A> 의 속성은 <xref:System.Windows.Forms.BindingSource> 돌아가려면 레코드 위치에 바인딩된 데이터에 대 한 합니다. 다음 예제에서는 사용 하 여는 <xref:System.Windows.Forms.BindingSource.MoveNext%2A> 의 메서드는 <xref:System.Windows.Forms.BindingSource> 증가 하는 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성 때는 `nextButton` 를 클릭 합니다. <xref:System.Windows.Forms.BindingSource> 과 연관 된 `Customers` 데이터 집합의 테이블 `Northwind`합니다.  
  
    > [!NOTE]
    >  설정의 <xref:System.Windows.Forms.BindingSource.Position%2A> 첫 번째 또는 마지막 레코드를 벗어나는 값을 속성으로 하면 오류가 발생 하지 않습니다는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 목록의 범위를 벗어난 값으로 위치를 설정할 수 있습니다를 허용 하지 것입니다. 첫 번째 또는 마지막 레코드를 지난를 벗어났는지 여부를 알아야 응용 프로그램에서 중요 한 경우에 데이터 요소 개수를 초과 되어 있는지 여부를 테스트 논리를 포함 합니다.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>시작 또는 끝 전달한 있는지 여부를 확인 하려면  
  
1.  <xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트에 대한 이벤트 처리기를 만듭니다. 처리기에서 제안 된 위치 값이 실제 데이터 요소 개수를 초과 하는지 여부를 테스트할 수 있습니다.  
  
     다음 예제에서는 마지막 데이터 요소를에 도달 했는지 여부를 테스트 하는 방법을 보여 줍니다. 예제에서는 마지막 요소에 있을 경우에 **다음** 폼의 단추에 사용할 수 없습니다.  
  
    > [!NOTE]
    >  즉, 코드에서 탐색 중인 목록을 변경 하면 다시 사용 해야 유의 **다음** 단추를 사용자가 새 목록의 전체 길이 찾아볼 수 있도록 합니다. 또한는 위의 <xref:System.Windows.Forms.BindingSource.PositionChanged> 특정에 대 한 이벤트 <xref:System.Windows.Forms.BindingSource> 해당 이벤트 처리 메서드에 연결 되도록 요구를 사용 하는 합니다. 다음은 처리에 대 한 방법의 예는 <xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>항목을 찾아 현재 항목으로 설정  
  
1.  현재 항목으로 설정 하려는 레코드를 찾습니다. 사용 하 여 수행할 수 있습니다는 <xref:System.Windows.Forms.BindingSource.Find%2A> 의 메서드는 <xref:System.Windows.Forms.BindingSource>데이터 원본 구현, <xref:System.ComponentModel.IBindingList>합니다. 데이터의 몇 가지 예는 구현 하는 소스 <xref:System.ComponentModel.IBindingList> 는 <xref:System.ComponentModel.BindingList%601> 및 <xref:System.Data.DataView>합니다.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms에서 지원하는 데이터 소스](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [Windows Forms 데이터 바인딩의 변경 알림](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [데이터 바인딩 및 Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)
