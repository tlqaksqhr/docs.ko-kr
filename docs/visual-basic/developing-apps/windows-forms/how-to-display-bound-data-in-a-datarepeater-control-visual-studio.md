---
title: "How to: Display Bound Data in a DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "DataRepeater, data-binding"
  - "DataRepeater, displaying bound controls"
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Display Bound Data in a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 가장 일반적인 사용 예는 데이터베이스 또는 기타 데이터 소스에서 바인딩된 데이터를 표시하는 것입니다.  
  
 바인딩된 컨트롤 이외에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 각 항목에 반복되는 정적 레이블 또는 이미지와 같은 다른 컨트롤도 추가할 수 있습니다.  자세한 내용은 [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)를 참조하십시오.  
  
 또한 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 속성을 `True`로 설정하고 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> 속성에 데이터 소스를 할당하여 런타임에 데이터 소스에 바인딩할 수 있습니다.  이 경우 데이터 소스와의 모든 상호 작용을 관리해야 합니다.  자세한 내용은 [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md)를 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### 데이터 바인딩된 DataRepeater를 만들려면  
  
1.  **도구 상자**의 **Visual Basic PowerPacks** 탭에서 폼 또는 컨테이너 컨트롤로 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 끌어 옵니다.  
  
2.  크기 조정 핸들을 끌어 배치하여 컨트롤의 크기를 조정하고 컨트롤을 배치합니다.  
  
     컨트롤에는 두 개의 사각형 영역이 있습니다.  위쪽 영역은 *항목 템플릿*입니다. 템플릿에 추가된 컨트롤은 런타임에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 각 항목에 반복됩니다.  아래쪽 영역은 항목이 표시되는 *뷰포트*입니다.  
  
     또한 속성 창에서 **Size** 및 **Position** 속성을 변경하여 컨트롤 또는 항목 템플릿의 크기를 지정하고 컨트롤 또는 항목 템플릿을 배치할 수 있습니다.  
  
3.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
    > [!NOTE]
    >  **데이터 소스** 창이 비어 있으면 데이터 소스를 추가합니다.  자세한 내용은 [데이터 소스 개요](/visual-studio/data-tools/add-new-data-sources)를 참조하십시오.  
  
4.  **데이터 소스** 창에서 바인딩할 데이터가 포함되어 있는 테이블에 대한 최상위 노드를 선택합니다.  
  
5.  테이블 노드의 드롭다운 목록에서 `Details`를 클릭하여 테이블의 놓기 형식을 `Details`로 변경합니다.  
  
6.  테이블 노드를 선택하고 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 항목 템플릿 영역으로 끌어 옵니다.  
  
     각 필드에 대해 표시되는 컨트롤 형식을 지정할 수 있습니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](/visual-studio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [How to: Create a Master\/Detail Form by Using Two DataRepeater Controls](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)