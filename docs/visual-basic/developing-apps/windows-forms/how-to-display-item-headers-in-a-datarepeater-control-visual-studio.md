---
title: "How to: Display Item Headers in a DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, item headers"
  - "DataRepeater, selection indicators"
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Display Item Headers in a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 항목 머리글은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>을 선택할 때 시각적 표시기를 제공합니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles>\(기본값\)로 설정되면 각 항목의 왼쪽에 항목 머리글이 표시됩니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles>로 설정되면 각 항목의 위쪽에 항목 머리글이 표시됩니다.  
  
 항목 머리글을 처음 선택하면 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 속성에 의해 지정된 색으로 항목 머리글이 표시되고 흰색 화살표 아이콘이 표시됩니다.  
  
> [!NOTE]
>  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>를 <xref:System.Drawing.Color.White%2A>로 설정한 경우 항목을 처음 선택하면 선택 기호가 표시되지 않습니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>의 필드에 포커스가 있으면 항목 머리글의 색이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 배경색으로 변경되고 화살표 아이콘이 검정으로 변경됩니다.  데이터를 변경하면 항목 머리글에 연필 기호가 표시됩니다.  
  
 항목 머리글의 기본 너비 또는 높이\(<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles>로 설정된 경우\)는 15픽셀입니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성을 설정하여 너비를 변경할 수 있습니다.  
  
> [!NOTE]
>  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성을 11 미만의 값으로 설정하면 항목 머리글에 표시기 기호가 표시되지 않습니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> 속성을 **False**로 설정하여 항목 머리글을 숨길 수 있습니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A>이 **False**로 설정되어 있으면 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 주위의 점선을 통해서만 항목이 선택되었음을 표시할 수 있습니다.  
  
> [!NOTE]
>  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> 속성을 모니터링하여 사용자 고유의 선택 표시기를 제공할 수도 있습니다.  자세한 내용은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>를 참조하십시오.  
  
### 항목 머리글의 모양을 변경하려면  
  
1.  Windows Forms 디자이너에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 아래쪽 영역을 선택합니다.  
  
    > [!NOTE]
    >  컨트롤의 아래쪽 영역을 선택해야 합니다.  항목 템플릿 섹션을 선택하면 다른 속성 집합이 속성 창에 표시됩니다.  
  
2.  속성 창에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 속성을 사용하여 항목 머리글의 색을 변경합니다.  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>를 <xref:System.Drawing.Color.White%2A>로 설정한 경우 항목을 처음 선택하면 선택 기호가 표시되지 않습니다.  
  
3.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성을 사용하여 항목 머리글의 너비 또는 높이를 변경합니다.  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성을 11 미만의 값으로 설정하면 항목 머리글에 표시기 기호가 표시되지 않습니다.  
  
### 항목 머리글을 숨기려면  
  
1.  Windows Forms 디자이너에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 아래쪽 영역을 선택합니다.  
  
    > [!NOTE]
    >  컨트롤의 아래쪽 영역을 선택해야 합니다.  항목 템플릿 섹션을 선택하면 다른 속성 집합이 속성 창에 표시됩니다.  
  
2.  속성 창에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> 속성을 **False**로 설정합니다.  
  
     <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>의 항목이 선택되면 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 주위의 점선을 통해서만 항목이 선택되었음을 표시할 수 있습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [How to: Change the Layout of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)