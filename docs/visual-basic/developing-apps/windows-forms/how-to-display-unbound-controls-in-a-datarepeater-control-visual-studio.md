---
title: "How to: Display Unbound Controls in a DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, adding unbound controls"
  - "DataRepeater"
  - "displaying unbound data"
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# How to: Display Unbound Controls in a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

바인딩된 컨트롤 이외에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 각 항목에 반복되는 정적 레이블 또는 이미지와 같은 기타 컨트롤도 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>에 추가할 수 있습니다.  
  
> [!NOTE]
>  또한 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>에 바인딩된 컨트롤이 하나 이상 있어야 합니다. 그렇지 않으면 런타임에 아무것도 표시되지 않습니다.  
  
### DataRepeater에 바인딩되지 않은 컨트롤을 추가하려면  
  
1.  **도구 상자**의 **Visual Basic PowerPacks** 탭에서 폼 또는 컨테이너 컨트롤로 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 끌어 옵니다.  
  
2.  크기 조정 핸들을 끌어 배치하여 컨트롤의 크기를 조정하고 컨트롤을 배치합니다.  
  
     또한 속성 창에서 **Size** 및 **Position** 속성을 변경하여 컨트롤의 크기를 조정하고 컨트롤을 배치할 수 있습니다.  
  
3.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에 데이터 바인딩된 컨트롤을 하나 이상 추가합니다.  자세한 내용은 [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)를 참조하십시오.  
  
4.  **도구 상자**에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 항목 템플릿 영역으로 컨트롤을 끌어 옵니다.  
  
     컨트롤에는 두 개의 사각형 영역이 있습니다.  내부 영역은 *항목 템플릿*입니다. 템플릿에 추가된 컨트롤은 런타임에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 각 항목에 반복됩니다.  외부 영역은 항목이 표시되는 *뷰포트*입니다. 이 영역에 추가되는 컨트롤은 런타임에 표시되지 않습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [How to: Create a Master\/Detail Form by Using Two DataRepeater Controls](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)