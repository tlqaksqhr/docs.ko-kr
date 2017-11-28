---
title: "DataRepeater 컨트롤의 가상 모드(Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- virtual data binding [Visual Basic]
- DataRepeater
- DataRepeater, virtual mode
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4c85ce4541e32991bfa09b1436385281d27ad355
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>DataRepeater 컨트롤의 가상 모드(Visual Studio)
테이블 형식 데이터를 표시 하려는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 설정 하 여 성능을 향상 시킬 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 속성을 `True` 명시적으로 해당 데이터 원본 컨트롤의 상호 작용을 관리 합니다. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤은 데이터 원본과 상호 작용 하 고 런타임 시 필요에 따라 데이터를 표시 하기 위해 처리할 수 있는 여러 이벤트를 제공 합니다.  
  
## <a name="how-virtual-mode-works"></a>가상 모드 작동 방식  
 에 대 한 가장 일반적인 시나리오는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 자식 컨트롤을 바인딩하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 에 대 한 데이터 디자인 타임에 소스 및 허용는 <xref:System.Windows.Forms.BindingSource> 필요에 따라 간에 데이터를 전달 합니다. 가상 모드를 사용 하면 컨트롤이 데이터 원본에 바인딩되지 않은 이며 데이터 전달 됩니다 간에 데이터 원본에 실행 시.  
  
 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 속성이로 설정 되어 `True`, 컨트롤을 추가 하 여 사용자 인터페이스를 만드는 **도구 상자** 바인딩된 컨트롤을 추가 하는 대신는 **데이터 원본** 창.  
  
 컨트롤 단위로 별로 발생 하 고 데이터의 표시를 처리 하는 코드를 추가 해야 합니다. 새 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 스크롤해서 보이면는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> 이벤트는 각 컨트롤에 대해 한 번씩 발생 하 고 각 컨트롤에 대 한 값을 제공 해야는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> 이벤트 처리기입니다.  
  
 사용자가 컨트롤 중 하나에 데이터가 변경 되 면는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> 이벤트가 발생 하 고 데이터의 유효성을 검사 하 고 데이터 원본에 저장 해야 합니다.  
  
 사용자가 새 항목을 추가할 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> 이벤트가 발생 합니다. 이 이벤트의이 처리기를 사용 하 여 데이터 원본에 새 레코드를 만듭니다. 의도 하지 않은 변경 내용을 방지 하려면 모니터링 해야는 <xref:System.Windows.Forms.Control.KeyDown> 각 컨트롤 및 호출에 대 한 이벤트 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> 사용자가 ESC 키를 누르면 됩니다.  
  
 데이터 소스가 변경 하는 경우 새로 고칠 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 호출 하 여 컨트롤의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> 및 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> 메서드. 순서에서 두 메서드를 호출 합니다.  
  
 에 대 한 이벤트 처리기를 구현 해야 하는 마지막으로 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> 항목이 삭제 될 때 및 필요에 따라 발생 하는 이벤트는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> 및 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> 사용자 DELETE 키를 눌러 항목을 삭제할 때마다 발생 하는 이벤트입니다.  
  
## <a name="implementing-virtual-mode"></a>가상 모드 구현  
 다음은 가상 모드 구현 하는 데 필요한 단계입니다.  
  
#### <a name="to-implement-virtual-mode"></a>가상 모드 구현 하려면  
  
1.  끌어서는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 속성을 `True`으로 설정합니다.  
  
2.  컨트롤을 끌어는 **도구 상자** 의 항목 템플릿 영역 (위쪽 영역)으로 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다. 각 필드는 표시 하려는 데이터 원본에 대 한 제어를 해야 합니다.  
  
3.  구현에 대 한 처리기는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> 각 컨트롤에 대 한 값을 제공 하는 이벤트입니다. 이 이벤트는 새 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 스크롤해서 표시 합니다. 라는 데이터 원본에는 다음 예제에서는 코드와 비슷합니다 `Employees`합니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  구현에 대 한 처리기는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> 이벤트 데이터를 저장 합니다. 이 이벤트는 사용자의 자식 컨트롤에 변경 내용이 커밋될 때는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>합니다. 라는 데이터 원본에는 다음 예제에서는 코드와 비슷합니다 `Employees`합니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  각 자식 컨트롤에 대 한 처리기를 구현 <xref:System.Windows.Forms.Control.KeyDown> 이벤트 및 ESC 키를 모니터 합니다. 호출 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> 방지 하기 위해는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> 이벤트가 발생 하지 합니다. 코드는 다음 예제를 비슷합니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  구현에 대 한 처리기는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> 이벤트입니다. 이 이벤트는 사용자를 새 항목 추가 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다. 라는 데이터 원본에는 다음 예제에서는 코드와 비슷합니다 `Employees`합니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  구현에 대 한 처리기는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> 이벤트입니다. 이 이벤트는 사용자는 기존 항목을 삭제할 때 발생 합니다. 라는 데이터 원본에는 다음 예제에서는 코드와 비슷합니다 `Employees`합니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  제어 수준 유효성 검사에 대 한 처리기를 구현할 필요에 따라는 <xref:System.Windows.Forms.Control.Validating> 자식 컨트롤의 이벤트입니다. 코드는 다음 예제를 비슷합니다.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>  
 [DataRepeater 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
