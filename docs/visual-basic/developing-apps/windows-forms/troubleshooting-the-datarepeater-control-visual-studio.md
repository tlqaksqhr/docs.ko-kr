---
title: "Troubleshooting the DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, troubleshooting"
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Troubleshooting the DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 사용하여 작업할 때 일반적으로 발생할 수 있는 문제에 대해 설명합니다.  
  
## DataRepeater 키보드 및 마우스 이벤트가 발생하지 않는 경우  
 키보드 및 마우스 이벤트와 같은 일부 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 이벤트가 발생하지 않습니다.  이는 의도된 것입니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 자체는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 개체에 대한 컨테이너이며 런타임에 이 컨트롤에 액세스할 수 없습니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>은 디자인 타임에 이벤트를 노출하지 않습니다.  따라서 항목에 포커스가 있을 때 항목을 클릭하거나 키를 누르면 이벤트가 발생하지 않습니다.  
  
 <xref:System.Windows.Forms.Control.Padding%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 가장자리를 노출할 정도로 큰 값으로 설정된 경우는 예외입니다.  이 경우 노출된 여백을 클릭하면 마우스 이벤트가 발생합니다.  
  
 이 문제를 해결하려면 <xref:System.Windows.Forms.Panel> 컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 섹션에 추가한 다음 나머지 컨트롤을 <xref:System.Windows.Forms.Panel>에 추가합니다.  그리고 나서 키보드 및 마우스 이벤트에 대한 <xref:System.Windows.Forms.Panel> 컨트롤의 이벤트 처리기에 코드를 추가할 수 있습니다.  
  
## DataRepeater가 바인딩 탐색기 뒤에 부분적으로 숨겨진 경우  
 처음에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 폼에 추가한 다음 **데이터 소스** 창의 데이터 바인딩된 컨트롤을 추가하면 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 맨 위에 <xref:System.Windows.Forms.BindingNavigator> 컨트롤이 나타날 수 있습니다.  이는 **데이터 소스** 창의 알려진 한계이며 <xref:System.Windows.Forms.DataGridView> 컨트롤과 같은 다른 컨트롤의 동작과 일치합니다.  
  
 디자인 타임에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>를 <xref:System.Windows.Forms.BindingNavigator> 컨트롤 아래로 이동하거나 `Load` 이벤트 처리기에 다음과 같은 코드를 추가할 수 있습니다.  
  
```vb#  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```c#  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## 컨트롤이 런타임에 올바르게 표시되지 않는 경우  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 일부 컨트롤은 런타임에 예상한 대로 표시되지 않을 수 있습니다.  컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>으로 복제하는 데 사용되는 프로세스가 항상 모든 컨트롤의 모든 속성을 확인할 수 있는 것은 아닙니다.  예를 들어 디자인 타임에 바인딩되지 않은 <xref:System.Windows.Forms.ListBox> 컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에 추가하고 해당 <xref:System.Windows.Forms.ListBox.Items%2A> 컬렉션을 문자열 목록으로 채우면 런타임에 <xref:System.Windows.Forms.ListBox>가 비워집니다.  이는 복제 프로세스에서 <xref:System.Windows.Forms.ListBox.Items%2A> 속성을 고려할 수 없기 때문입니다.  
  
 기본 복제가 완료된 후 발생하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> 이벤트에서 누락된 속성을 복원하여 이와 같은 문제를 해결할 수 있습니다.  다음 예제에서는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> 이벤트 처리기에서 <xref:System.Windows.Forms.ListBox> 컨트롤의 <xref:System.Windows.Forms.ListBox.Items%2A> 컬렉션을 복원하는 방법을 보여 줍니다.  
  
 [!code-cs[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/DataRepeaterItemClonedCS/ItemCloned.cs#1)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/DataRepeaterItemCloned/ItemCloned.vb#1)]  
  
## 항목 머리글에 선택 기호가 없는 경우  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에서 항목 머리글의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 속성을 변경할 때 일부 색 선택 사항으로 인해 선택 기호가 표시되지 않을 수 있습니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성을 변경하면 선택 기호가 표시되지 않을 수도 있습니다.  
  
 선택 기호의 색 및 크기를 변경할 수 없습니다.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>를 <xref:System.Drawing.Color.White%2A>로 설정하면 항목이 처음 선택될 때 선택 기호가 표시되지 않습니다.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>를 <xref:System.Drawing.Color.Black%2A>으로 설정하면 컨트롤을 선택할 때 선택 기호가 표시되지 않고 컨트롤이 편집 모드에 있을 때 연필 기호가 표시되지 않습니다.  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성을 11 미만의 값으로 설정하면 항목 머리글에 표시기 기호가 표시되지 않습니다.  
  
 <xref:System.Windows.Forms.PictureBox> 컨트롤을 사용하고 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> 속성을 모니터링하여 사용자의 고유한 항목 머리글 및 선택 기호를 제공할 수 있습니다.  자세한 내용은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>를 참조하십시오.  
  
## 참고 항목  
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [How to: Change the Layout of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [How to: Display Item Headers in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)   
 [How to: Disable Adding and Deleting DataRepeater Items](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)   
 [How to: Search Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)   
 [How to: Create a Master\/Detail Form by Using Two DataRepeater Controls](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)