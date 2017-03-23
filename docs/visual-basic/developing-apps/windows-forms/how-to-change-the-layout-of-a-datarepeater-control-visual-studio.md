---
title: "How to: Change the Layout of a DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, changing layout style"
  - "DataRepeater, changing orientation"
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# How to: Change the Layout of a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤은 세로 방향\(항목을 세로로 스크롤\) 또는 가로 방향\(항목을 가로로 스크롤\)으로 표시할 수 있습니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성을 변경하여 디자인 타임 또는 런타임에 방향을 변경할 수 있습니다.  런타임에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성을 변경하는 경우 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>의 크기를 조정하고 자식 컨트롤의 위치를 변경하려고 할 수도 있습니다.  
  
> [!NOTE]
>  런타임에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>에서 컨트롤의 위치를 변경하는 경우 컨트롤의 위치를 변경하는 코드 블록의 시작 및 끝에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> 및 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> 메서드를 호출할 필요가 있습니다.  
  
### 디자인 타임에 레이아웃을 변경하려면  
  
1.  Windows Forms 디자이너에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 선택합니다.  
  
    > [!NOTE]
    >  컨트롤의 위쪽 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 영역이 아닌 아래쪽 영역을 클릭하여 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 바깥쪽 테두리를 선택해야 합니다.  
  
2.  속성 창에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles> 또는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles>로 설정합니다.  
  
### 런타임에 레이아웃을 변경하려면  
  
1.  단추 또는 메뉴 `Click` 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-cs[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  대부분의 경우 예제 단원에 표시된 코드와 유사한 코드를 추가하여 새 방향에 맞게 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>의 크기를 조정하고 컨트롤을 다시 정렬하려고 합니다.  
  
## 예제  
 다음 예제에서는 이벤트 처리기에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> 이벤트에 응답하는 방법을 보여 줍니다.  이 예제를 실행하려면 폼에 `DataRepeater1`이라는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤이 있고 해당 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>에 `TextBox1` 및 `TextBox2`라는 두 개의 <xref:System.Windows.Forms.TextBox> 컨트롤이 있어야 합니다.  
  
 [!code-cs[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)