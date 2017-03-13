---
title: "How to: Search Data in a DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, implementing search"
  - "DataRepeater, searching data"
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Search Data in a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

많은 레코드를 포함하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 사용하는 경우 사용자가 특정 레코드를 검색할 수 있도록 지정할 수 있습니다.  컨트롤 자체의 데이터를 검색하는 대신 기본 <xref:System.Windows.Forms.BindingSource>를 쿼리하여 검색을 구현할 수 있습니다.  항목을 찾으면 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> 속성을 사용하여 항목을 선택하고 뷰로 스크롤할 수 있습니다.  
  
### 검색을 구현하려면  
  
1.  **도구 상자**에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤이 포함된 폼으로 <xref:System.Windows.Forms.TextBox> 컨트롤을 끌어 옵니다.  
  
2.  속성 창에서 **Name** 속성을 SearchTextBox로 변경합니다.  
  
3.  **도구 상자**에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤이 포함된 폼으로 <xref:System.Windows.Forms.Button> 컨트롤을 끌어 옵니다.  
  
4.  속성 창에서 **Name** 속성을 SearchButton으로 변경합니다.  **Text** 속성을 Search로 변경합니다.  
  
5.  <xref:System.Windows.Forms.Button> 컨트롤을 두 번 클릭하여 코드 편집기를 열고 `SearchButton_Click` 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-cs[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     *ProductsBindingSource*를 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>에 대한 <xref:System.Windows.Forms.BindingSource> 이름으로 바꾸고 *ProductID*를 검색할 필드 이름으로 바꿉니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)