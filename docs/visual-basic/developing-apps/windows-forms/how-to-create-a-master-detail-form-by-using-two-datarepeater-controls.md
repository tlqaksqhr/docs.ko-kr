---
title: "How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, master/detail tables"
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

마스터\/세부 폼을 만드는 두 개 이상의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 사용하여 관련 데이터를 표시할 수 있습니다.  예를 들어 한 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>에서 고객 목록을 표시하고, 사용자가 고객을 선택할 때 두 번째 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>에서 해당 고객의 주문 목록을 표시하려고 할 수 있습니다.  
  
 동일한 마스터 테이블 노드를 공유하는 세부 항목을 **데이터 소스** 창에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤로 끌어 관련 데이터를 표시할 수 있습니다.  예를 들어 Customers 테이블 및 관련 Orders 테이블을 포함하는 데이터 소스가 있는 경우 두 테이블이 **데이터 소스** 창의 트리 뷰에서 최상위 노드로 표시됩니다.  열을 볼 수 있도록 Customers 노드를 확장합니다.  목록의 마지막 열은 Orders 테이블을 나타내는 확장 가능한 노드입니다.  이 노드는 고객과 관련된 주문을 나타냅니다.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### 두 DataRepeater 컨트롤에서 관련 데이터를 표시하려면  
  
1.  **도구 상자**의 **Visual Basic PowerPacks** 탭에서 폼 또는 컨테이너 컨트롤로 두 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 끌어 옵니다.  
  
2.  크기 조정 핸들을 끌어 배치하여 컨트롤의 크기를 조정하고 컨트롤을 나란히 배치합니다.  
  
3.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
    > [!NOTE]
    >  **데이터 소스** 창이 비어 있으면 데이터 소스를 추가합니다.  자세한 내용은 [데이터 소스 개요](/visual-studio/data-tools/add-new-data-sources)를 참조하십시오.  
  
4.  **데이터 소스** 창에서 마스터 테이블의 최상위 노드를 선택합니다.  
  
5.  테이블 노드의 드롭다운 목록에서 **자세히**를 클릭하여 마스터 테이블의 놓기 형식을 자세히로 변경합니다.  
  
6.  마스터 테이블 노드를 첫 번째 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 항목 템플릿 영역으로 끌어 옵니다.  
  
7.  마스터 테이블 노드를 확장하고 관련 테이블의 세부 노드를 선택합니다.  
  
8.  테이블 노드의 드롭다운 목록에서 **자세히**를 클릭하여 세부 테이블의 놓기 형식을 자세히로 변경합니다.  
  
9. 이 테이블 노드를 선택하고 두 번째 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 항목 템플릿 영역으로 끌어 옵니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)