---
title: "Windows Forms DataGridView 컨트롤의 선택 모드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0d605b7ee7e48ad0ed2e693f0e71e5f1c25e022
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 선택 모드
응용 프로그램 내의 사용자 선택에 따라 작업을 수행 하려는 경우에 따라 한 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 작업에 따라 가능한 선택 항목의 종류를 제한 하는 것이 좋습니다. 예를 들어, 응용 프로그램에서 현재 선택 된 레코드에 대 한 보고서를 인쇄할 수 있습니다. 이 경우 구성 해야 할 수는 <xref:System.Windows.Forms.DataGridView> 컨트롤 항상 행 내에서 아무 곳 이나 클릭 하 여 전체 행을 선택한 한 번에 해당 행을 하나만 선택할 수 있습니다.  
  
 허용을 설정 하 여 선택 항목을 지정할 수는 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 속성을 다음 중 하나로 <xref:System.Windows.Forms.DataGridViewSelectionMode> 열거형 값입니다.  
  
|DataGridViewSelectionMode 값|설명|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|셀을 클릭 하 고 선택 합니다. 행 및 열 머리글 선택에 사용할 수 없습니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|셀을 클릭 하 고 선택 합니다. 열 머리글을 클릭 하면 전체 열을 선택 합니다. 정렬에 열 머리글을 사용할 수 없습니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|셀 또는 열 머리글을 클릭 하면 전체 열을 선택 합니다. 정렬에 열 머리글을 사용할 수 없습니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|셀 또는 행 머리글을 클릭 하면 전체 행을 선택 합니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|기본 선택 모드입니다. 셀을 클릭 하 고 선택 합니다. 행 머리글을 클릭 하 여 전체 행을 선택 합니다.|  
  
> [!NOTE]
>  현재 선택을 해제 런타임 시 자동으로 선택 모드를 변경 합니다.  
  
 기본적으로 사용자가 선택할 수 여러 행, 열 또는 셀의 마우스을 확장 하거나 수정 선택 항목을 선택 하거나 컨트롤의 모든 셀을 선택 하려면 왼쪽 위 머리글 셀을 클릭 하는 동안 CTRL 또는 shift 키를 누르면. 이 문제를 방지 하려면 설정는 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 속성을 `false`합니다.  
  
 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 및 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> 모드 선택 하 고 DELETE 키를 눌러 행을 삭제 하려면 사용자가 허용 합니다. 현재 셀이 편집 모드에 있는 경우에 사용자가 행을 삭제할 수는 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> 속성이로 설정 되어 `true`, 데이터 원본 사용자 기반 행 삭제 작업을 지원 하 고 있습니다. 이러한 설정을 프로그래밍 방식으로 행을 삭제 해도 참고 합니다.  
  
## <a name="programmatic-selection"></a>프로그래밍 방식 선택  
 현재 선택 모드도 프로그래밍 방식 선택 사용자 선택 동작을 제한합니다. 현재 선택 영역을 설정 하 여 프로그래밍 방식으로 변경할 수 있습니다는 `Selected` 속성의 모든 셀, 행 또는 열에는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 통해 컨트롤에 모든 셀을 선택할 수도 있습니다는 <xref:System.Windows.Forms.DataGridView.SelectAll%2A> 선택 모드에 따라 메서드. 사용 하 여 선택을 <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> 메서드.  
  
 경우는 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 속성이로 설정 되어 `true`를 추가할 수 있습니다 <xref:System.Windows.Forms.DataGridView> 요소를 하거나 변경 하 여 선택 영역에서 제거는 `Selected` 요소의 속성입니다. 그렇지 않은 경우 설정의 `Selected` 속성을 `true` 요소가 두 개 선택에서 다른 요소를 자동으로 제거에 대 한 합니다.  
  
 값을 변경는 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 속성은 현재 선택 영역을 변경 하지 않습니다.  
  
 현재 선택 된 셀, 행 또는 열을 통해의 컬렉션을 검색할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, 및 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 의 속성은 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이러한 속성에 액세스지 않습니다 효율적인 컨트롤의 모든 셀을 선택 합니다. 이 경우, 성능 저하를 방지 하려면 사용 된 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 메서드 첫 번째입니다. 또한 선택 된 셀의 수를 확인 하려면 이러한 컬렉션에 대 한 액세스, 행 또는 열 수 있습니다 수. 있습니다 를 대신 사용 해야는 <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, 또는 <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> 전달 하는 메서드는 <xref:System.Windows.Forms.DataGridViewElementStates.Selected> 값입니다.  
  
> [!TIP]
>  선택 된 셀의 프로그래밍 방식으로 사용 하는 예제 코드에서 확인할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 클래스 개요입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridViewSelectionMode>  
 [Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
