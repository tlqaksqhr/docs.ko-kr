---
title: "Introduction to the DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "repeating data"
  - "DataRepeater, overview"
  - "DataRepeater"
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Introduction to the DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic Power Packs <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤은 데이터베이스 테이블의 행과 같이 반복되는 데이터를 표시하는 컨트롤을 위한 스크롤 가능한 컨테이너입니다.  데이터의 레이아웃을 보다 세부적으로 제어해야 할 때 <xref:System.Windows.Forms.DataGridView> 컨트롤 대신 사용할 수 있습니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>는 스크롤 뷰에서 많은 인스턴스를 만들어 관련 컨트롤 그룹을 "반복합니다".  이를 통해 사용자는 여러 레코드를 동시에 볼 수 있습니다.  
  
## 개요  
 디자인 타임에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤은 두 섹션으로 구성됩니다.  외부 섹션은 런타임에 스크롤 데이터가 표시되는 *뷰포트*입니다.  *항목 템플릿*이라고 하는 내부\(위쪽\) 섹션은 런타임에 반복되는 컨트롤을 배치합니다. 일반적으로 데이터 소스의 각 필드에 대해 한 컨트롤씩 배치됩니다.  항목 템플릿의 속성 및 컨트롤은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 속성에 캡슐화됩니다.  
  
 런타임에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>은 각 레코드가 뷰로 스크롤될 때 데이터를 표시하는 데 사용되는 가상 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 개체로 복사됩니다.  필드에 포함되어 있는 값을 기준으로 필드를 강조 표시하는 작업과 같이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트에서의 개별 레코드 표시를 사용자 지정할 수 있습니다.  자세한 내용은 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)을 참조하십시오.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 가장 일반적인 사용 예는 데이터베이스 테이블 또는 기타 바인딩된 데이터 소스의 데이터를 표시하는 것입니다.  [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)] 데이터 개체 이외에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤은 <xref:System.Collections.IList> 인터페이스\(배열 포함\)을 구현하는 클래스, <xref:System.ComponentModel.IListSource> 인터페이스를 구현하는 클래스, <xref:System.ComponentModel.IBindingList> 인터페이스를 구현하는 클래스 또는 <xref:System.ComponentModel.IBindingListView> 인터페이스를 구현하는 클래스로 바인딩할 수 있습니다.  
  
### 데이터 바인딩  
 일반적으로 **데이터 소스** 창에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤로 필드를 끌어 와 데이터 바인딩을 수행합니다.  자세한 내용은 [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)를 참조하십시오.  
  
 데이터 양이 큰 경우 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 속성을 `True`로 설정하면 사용 가능한 데이터의 하위 집합을 표시할 수 있습니다.  가상 모드의 경우 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>가 채워지는 데이터 캐시를 구현해야 하므로 런타임에 데이터 캐시와의 모든 상호 작용을 제어해야 합니다.  자세한 내용은 [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md)를 참조하십시오.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에 바인딩되지 않은 컨트롤을 표시할 수도 있습니다.  예를 들어 각 항목에 반복되는 이미지를 표시할 수 있습니다.  자세한 내용은 [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)를 참조하십시오.  
  
### 이벤트  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에 대한 가장 중요한 이벤트는 새 항목이 뷰로 스크롤될 때 발생하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트 및 항목이 선택될 때 발생하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> 이벤트입니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트를 사용하여 항목의 모양을 변경할 수 있습니다.  예를 들어 음수 값을 강조 표시할 수 있습니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> 이벤트를 사용하면 항목이 선택될 때 컨트롤 값에 액세스할 수 있습니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤은 코드 편집기의 모든 표준 컨트롤 이벤트를 노출합니다.  그러나 일부 이벤트는 사용해서는 안 됩니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 자체에는 포커스가 없으므로 `KeyDown`, `Click` 및 `MouseDown`과 같은 키보드 및 마우스 이벤트는 런타임에 발생하지 않습니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>은 런타임에만 만들어지므로 디자인 타임에 이벤트를 노출하지 않습니다.  키보드 및 마우스 이벤트를 처리하려는 경우 디자인 타임에 <xref:System.Windows.Forms.Panel> 컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>에 추가한 다음 <xref:System.Windows.Forms.Panel>에 대한 이벤트를 처리할 수 있습니다.  자세한 내용은 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)을 참조하십시오.  
  
### 사용자 지정  
 런타임과 디자인 타임 모두에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 모양 및 동작을 여러 방법으로 사용자 지정할 수 있습니다.  색을 변경하고, 항목 머리글을 숨기거나 수정하고, 세로 방향에서 가로 방향으로 변경하도록 속성을 설정할 수 있습니다.  자세한 내용은 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [How to: Display Item Headers in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) 및 [How to: Change the Layout of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)을 참조하십시오.  
  
 일부 속성은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 자체에 적용되는 반면 다른 속성은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>에만 적용됩니다.  속성을 설정하기 전에 컨트롤의 올바른 섹션을 선택했는지 확인하십시오.  자세한 내용은 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)을 참조하십시오.  
  
 기타 사용자 지정에는 레코드를 추가 또는 삭제하는 기능 제어, 검색 기능 추가, 관련 데이터를 마스터 및 세부 형식으로 표시하는 작업이 포함되어 있습니다.  자세한 내용은 [How to: Disable Adding and Deleting DataRepeater Items](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [How to: Search Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) 및 [How to: Create a Master\/Detail Form by Using Two DataRepeater Controls](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)를 참조하십시오.  
  
## 참고 항목  
 [DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)   
 [연습: DataRepeater 컨트롤의 데이터 표시](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)