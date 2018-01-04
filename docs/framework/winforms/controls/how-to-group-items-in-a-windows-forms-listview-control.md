---
title: "방법: Windows Forms ListView 컨트롤에서 항목 그룹화"
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
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b12b7126e03f6a6c8363c69a607f4961f13120ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>방법: Windows Forms ListView 컨트롤에서 항목 그룹화
그룹화 기능을 통해는 <xref:System.Windows.Forms.ListView> 컨트롤을 그룹에 관련된 항목 집합을 표시할 수 있습니다. 이러한 그룹은 화면에서 그룹 제목을 포함 하는 가로 그룹 머리글에 의해 분리 됩니다. 사용할 수 있습니다 <xref:System.Windows.Forms.ListView> 날짜, 또는 다른 논리적 그룹화 하 여 항목을 사전순으로 그룹화 하 여 큰 목록 보다 쉽게 탐색 하기 위해 그룹입니다. 다음 그림에서는 일부 그룹화 된 항목을 보여 줍니다.  
  
 ![ListView 그룹](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
ListView 그룹화 된 항목  
  
 그룹화를 사용 하려면 먼저 디자이너에서 또는 프로그래밍 방식으로 그룹 하나 이상 만들어야 합니다. 그룹을 정의한 후 할당할 수 있습니다 <xref:System.Windows.Forms.ListView> 항목 그룹입니다. 이동할 수도 있습니다 항목 그룹에서 다른 프로그래밍 방식으로 합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView>그룹에 대해서만 사용할 수 있는 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] 응용 프로그램 호출 하는 경우는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드. 이전 버전의 운영 체제 그룹과 관련 된 코드가 아무 효과도 없습니다 및 그룹이 표시 되지 않습니다. 자세한 내용은 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>을 참조하세요.  
  
### <a name="to-add-groups"></a>그룹을 추가 하려면  
  
1.  <xref:System.Windows.Forms.ListView.Groups%2A> 컬렉션의 <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 메서드를 사용합니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>그룹을 제거 하려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 또는 <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 의 메서드는 <xref:System.Windows.Forms.ListView.Groups%2A> 컬렉션입니다.  
  
     <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 단일 그룹을 제거 하는 메서드, <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 메서드 목록에서 모든 그룹을 제거 합니다.  
  
    > [!NOTE]
    >  그룹을 제거 해도 해당 그룹 내의 항목은 제거 되지 않습니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>항목 그룹을 할당 하거나 그룹 간에 항목을 이동 하려면  
  
1.  설정의 <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> 개별 항목의 속성입니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Windows XP 기능 및 Windows Forms 컨트롤](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
