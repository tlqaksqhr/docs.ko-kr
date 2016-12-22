---
title: "How to: Change the Appearance of a DataRepeater Control (Visual Studio) | Microsoft Docs"
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
  - "DataRepeater, customizing"
  - "DataRepeater, changing run time appearance"
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Change the Appearance of a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

디자인 타임에 속성을 설정하거나 런타임에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트를 처리하여 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 모양을 변경할 수 있습니다.  
  
 디자인 타임에 컨트롤의 항목 템플릿 섹션을 선택할 때 설정한 속성이 런타임에 각 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>에 대해 반복됩니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 자체의 모양 관련 속성은 <xref:System.Windows.Forms.Control.Padding%2A> 속성이 큰 값으로 설정된 경우와 같이 컨테이너의 일부가 덮여 있지 않은 경우만 런타임에 표시됩니다.  
  
 런타임에 조건에 따라 모양 관련 속성을 설정할 수 있습니다.  예를 들어 일정 응용 프로그램에서 항목이 기한을 넘기면 항목의 배경색을 변경하여 사용자에게 경고할 수 있습니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트 처리기에서 `If...Then`와 같은 조건문에 속성을 설정하는 경우 `Else` 절을 사용하여 조건에 맞지 않을 때의 모양도 지정해야 합니다.  
  
### 디자인 타임에 모양을 변경하려면  
  
1.  Windows Forms 디자이너에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 항목 템플릿\(위쪽\) 영역을 선택합니다.  
  
2.  속성 창에서 속성을 선택하고 값을 변경합니다.  모양에 영향을 주는 공용 속성에는 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A> 및 <xref:System.Windows.Forms.Control.ForeColor%2A>가 있습니다.  
  
### 런타임에 모양을 변경하려면  
  
1.  코드 편집기의 이벤트 드롭다운 목록에서 **DrawItem**을 클릭합니다.  
  
2.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트 처리기에서 속성을 설정하는 다음 코드를 추가합니다.  
  
     [!code-cs[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## 예제  
 일반적으로 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤은 행을 다른 색으로 표시하거나 조건에 따라 필드의 색을 변경하는 등의 방식으로 사용자 지정할 수 있습니다.  다음 예제에서는 사용자 지정 작업을 수행하는 방법을 보여 줍니다.  이 예제에서는 Northwind 데이터베이스의 Products 테이블에 바인딩된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤이 있는 것으로 가정합니다.  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-cs[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 이러한 사용자 지정 작업 모두의 경우 조건의 양쪽에 대한 속성을 설정하는 코드를 제공해야 합니다.  `Else` 조건을 지정하지 않으면 런타임에 예기치 않은 결과가 표시됩니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [How to: Display Item Headers in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)