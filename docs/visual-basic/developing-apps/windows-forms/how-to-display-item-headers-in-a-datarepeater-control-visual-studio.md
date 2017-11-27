---
title: "방법: DataRepeater 컨트롤의 항목 머리글 표시(Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, item headers
- DataRepeater, selection indicators
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: da02f9374471a581a58131e26d618f91d7cbb7af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a>방법: DataRepeater 컨트롤의 항목 머리글 표시(Visual Studio)
항목 헤더에는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 시각적 표시기를 제공 하는 컨트롤 때는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 을 선택 합니다. 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (기본값) 이면 항목 머리글이 각 항목의 왼쪽에 표시 됩니다. 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, 항목 머리글이 각 항목의 위쪽에 표시 됩니다.  
  
 처음 선택 항목 헤더에 지정 된 색으로 표시 됩니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 속성과 흰색 화살표가 표시 됩니다.  
  
> [!NOTE]
>  설정 하는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 를 <xref:System.Drawing.Color.White%2A>, 항목을 먼저 선택 선택 기호가 표시 되지 것입니다.  
  
 필드에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 에 포커스가 항목 헤더 변경 내용에 색은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 배경 색 및 화살표 아이콘 검정색으로 변경 합니다. 데이터가 변경 되 면 연필 기호 항목 헤더에 표시 됩니다.  
  
 기본 너비 (또는 높이 때는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) 항목의 머리글은 15 픽셀입니다. 설정 하 여 너비를 변경할 수는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성입니다.  
  
> [!NOTE]
>  경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성이 11 보다 작은 값으로 설정 되 면 표시기 기호 항목 머리글에서 표시 되지 것입니다.  
  
 항목 헤더를 설정 하 여 숨길 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> 속성을 **False**합니다. 때 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> 로 설정 된 **False**, 항목을 선택 하는 유일한 표시는 주위에 점선은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>합니다.  
  
> [!NOTE]
>  모니터링 하 여 사용자 고유의 선택 표시기를 제공할 수도 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> 속성은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 의 이벤트는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다. 자세한 내용은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>을 참조하십시오.  
  
### <a name="to-change-the-appearance-of-item-headers"></a>항목 헤더의 모양을 변경 하려면  
  
1.  Windows Forms 디자이너에서의 낮은 영역을 선택는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.  
  
    > [!NOTE]
    >  컨트롤의 아래쪽 영역을 선택 해야 합니다. 항목 템플릿 섹션을 선택 하면 속성 창에서 다른 속성 집합이 표시 됩니다.  
  
2.  속성 창에서 사용 하 여는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 속성 항목 헤더의 색을 변경 합니다.  
  
    > [!NOTE]
    >  설정 하는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 를 <xref:System.Drawing.Color.White%2A>, 항목을 먼저 선택 선택 기호가 표시 되지 것입니다.  
  
3.  사용 하 여는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 항목 머리글의 너비 (또는 높이)을 변경할 속성입니다.  
  
    > [!NOTE]
    >  경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성이 11 보다 작은 값으로 설정 되 면 표시기 기호 항목 머리글에서 표시 되지 것입니다.  
  
### <a name="to-hide-item-headers"></a>항목 머리글을 숨기려면  
  
1.  Windows Forms 디자이너에서의 낮은 영역을 선택는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.  
  
    > [!NOTE]
    >  컨트롤의 아래쪽 영역을 선택 해야 합니다. 항목 템플릿 섹션을 선택 하면 속성 창에서 다른 속성 집합이 표시 됩니다.  
  
2.  속성 창에서 설정 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> 속성을 **False**합니다.  
  
     항목이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 은 선택 하면 유일한 표시 될 주위에 점선은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [DataRepeater 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 모양 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 레이아웃 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [DataRepeater 컨트롤 문제 해결](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
