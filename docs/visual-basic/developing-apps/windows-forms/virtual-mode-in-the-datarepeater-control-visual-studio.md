---
title: "Virtual Mode in the DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "virtual data binding"
  - "DataRepeater"
  - "DataRepeater, virtual mode"
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Virtual Mode in the DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

표 형식의 대용량 데이터를 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에 표시하려는 경우 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 속성을 `True`로 설정하고 컨트롤과 해당 데이터 소스의 상호 작용을 명시적으로 관리하여 성능을 향상시킬 수 있습니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤은 런타임에 필요한 경우 데이터 소스와 상호 작용하고 데이터를 표시하기 위해 처리할 수 있는 여러 가지 이벤트를 제공합니다.  
  
## 가상 모드 작동 방식  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에 대한 가장 일반적인 시나리오는 디자인 타임에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>의 자식 컨트롤을 데이터 소스에 바인딩하고 <xref:System.Windows.Forms.BindingSource>에서 필요한 경우 데이터를 앞뒤로 전달할 수 있도록 하는 것입니다.  가상 모드를 사용하는 경우 컨트롤이 데이터 소스에 바인딩되지 않으며 런타임에 데이터가 기본 데이터 소스에 앞뒤로 전달됩니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 속성이 `True`로 설정되면 **데이터 소스** 창에서 바인딩된 컨트롤을 추가하는 대신 **도구 상자**에서 컨트롤을 추가하여 사용자 인터페이스를 만듭니다.  
  
 이벤트는 컨트롤별로 발생하며 사용자는 데이터 표시를 처리하는 코드를 추가해야 합니다.  새 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>이 뷰로 스크롤되면 각 컨트롤에 대해 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> 이벤트가 한 번 발생하며 사용자는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> 이벤트 처리기에서 각 컨트롤에 대한 값을 제공해야 합니다.  
  
 컨트롤 중 하나의 데이터가 사용자에 의해 변경되면 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> 이벤트가 발생하며 사용자는 데이터의 유효성을 검사하고 데이터를 데이터 소스에 저장해야 합니다.  
  
 사용자가 새 항목을 추가하면 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> 이벤트가 발생합니다.  이 이벤트 처리기를 사용하여 데이터 소스에 새 레코드를 만들 수 있습니다.  원하지 않는 변경 작업이 수행되지 않게 하려면 각 컨트롤에 대한 <xref:System.Windows.Forms.Control.KeyDown> 이벤트를 모니터링하고 사용자가 Esc 키를 누를 때 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>를 호출해야 합니다.  
  
 데이터 소스가 변경되면 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetTemplateItem%2A> 및 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetTemplateItem%2A> 메서드를 호출하여 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 새로 고칠 수 있습니다.  두 메서드는 반드시 순서대로 호출해야 합니다.  
  
 마지막으로 항목이 삭제될 때 발생하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> 이벤트와 사용자가 Delete 키를 눌러 항목을 삭제할 때마다 발생하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> 및 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> 이벤트\(옵션\)에 대한 이벤트 처리기를 구현해야 합니다.  
  
## 가상 모드 구현  
 가상 모드를 구현하는 데 필요한 단계는 다음과 같습니다.  
  
#### 가상 모드를 구현하려면  
  
1.  **도구 상자**의 **Visual Basic PowerPacks** 탭에서 폼 또는 컨테이너 컨트롤로 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 끌어 옵니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 속성을 `True`으로 설정합니다.  
  
2.  **도구 상자**에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 항목 템플릿 영역\(위쪽 영역\)으로 컨트롤을 끌어 옵니다.  표시할 데이터 소스의 각 필드에 대해 하나의 컨트롤이 필요합니다.  
  
3.  각 컨트롤에 대한 값을 제공하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> 이벤트에 대한 처리기를 구현합니다.  새 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>이 뷰로 스크롤될 때 이 이벤트가 발생합니다.  코드는 `Employees`라는 데이터 소스에 대한 다음 예제와 유사합니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksDataRepeaterVirtualMode/VbPowerPacksDataRepeaterVirtualMode.vb#1)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksDataRepeaterVirtualModeCS/VbPowerPacksDataRepeaterVirtualMode.cs#1)]  
  
4.  데이터를 저장하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> 이벤트 처리기를 구현합니다.  사용자가 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>의 자식 컨트롤에 대한 변경 내용을 커밋할 때 이 이벤트가 발생합니다.  코드는 `Employees`라는 데이터 소스에 대한 다음 예제와 유사합니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksDataRepeaterVirtualMode/VbPowerPacksDataRepeaterVirtualMode.vb#2)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksDataRepeaterVirtualModeCS/VbPowerPacksDataRepeaterVirtualMode.cs#2)]  
  
5.  각 자식 컨트롤의 <xref:System.Windows.Forms.Control.KeyDown> 이벤트 처리기를 구현하고 Esc 키를 모니터링합니다.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> 이벤트가 발생하지 않도록 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> 메서드를 호출합니다.  코드는 다음 예제와 같습니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksDataRepeaterVirtualMode/VbPowerPacksDataRepeaterVirtualMode.vb#3)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksDataRepeaterVirtualModeCS/VbPowerPacksDataRepeaterVirtualMode.cs#3)]  
  
6.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> 이벤트 처리기를 구현합니다.  사용자가 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에 새 항목을 추가하면 이 이벤트가 발생합니다.  코드는 `Employees`라는 데이터 소스에 대한 다음 예제와 유사합니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksDataRepeaterVirtualMode/VbPowerPacksDataRepeaterVirtualMode.vb#4)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksDataRepeaterVirtualModeCS/VbPowerPacksDataRepeaterVirtualMode.cs#4)]  
  
7.  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> 이벤트 처리기를 구현합니다.  이 이벤트는 사용자가 기존 항목을 삭제할 때 발생합니다.  코드는 `Employees`라는 데이터 소스에 대한 다음 예제와 유사합니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksDataRepeaterVirtualMode/VbPowerPacksDataRepeaterVirtualMode.vb#5)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksDataRepeaterVirtualModeCS/VbPowerPacksDataRepeaterVirtualMode.cs#5)]  
  
8.  컨트롤 수준 유효성 검사의 경우 자식 컨트롤의 <xref:System.Windows.Forms.Control.Validating> 이벤트에 대한 처리기를 구현할 수 있습니다.  코드는 다음 예제와 같습니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksDataRepeaterVirtualMode/VbPowerPacksDataRepeaterVirtualMode.vb#6)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksDataRepeaterVirtualModeCS/VbPowerPacksDataRepeaterVirtualMode.cs#6)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)