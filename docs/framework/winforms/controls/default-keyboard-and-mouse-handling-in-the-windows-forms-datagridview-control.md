---
title: "Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], mouse handling
- DataGridView control [Windows Forms], navigation keys
- keyboards [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], keyboard handling
- mouse [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], mouse handling
- navigation keys [Windows Forms], DataGridView control
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 627784f3d68ddf03f1f6c94975405dded3163c06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리
다음 표에서 사용자 수와 상호 작용 하는 방법을 설명는 <xref:System.Windows.Forms.DataGridView> 키보드와 마우스를 통해 제어 합니다.  
  
> [!NOTE]
>  키보드 동작을 사용자 지정 하려면 이벤트를 처리 표준 키보드와 같은 <xref:System.Windows.Forms.Control.KeyDown>합니다. 그러나 편집 모드에 편집 받을 키보드 입력 하 고 키보드 이벤트에 대 한 발생 하지 않습니다는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 편집 컨트롤 이벤트를 처리 하려면에 편집 컨트롤에 처리기를 연결 된 <xref:System.Windows.Forms.DataGridView.EditingControlShowing> 이벤트 처리기입니다. 키보드 동작을 사용자 지정할 수 또는 <xref:System.Windows.Forms.DataGridView> 재정의 하 여 하위 클래스는 <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> 및 <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> 메서드.  
  
## <a name="default-keyboard-handling"></a>기본 키보드 처리  
  
### <a name="basic-navigation-and-entry-keys"></a>기본 항목 및 탐색 키  
  
|키 또는 키 조합|설명|  
|----------------------------|-----------------|  
|아래쪽 화살표|현재 셀의 바로 아래 셀으로 포커스를 이동합니다. 마지막 행에 포커스가 있으면 아무 작업도 수행 하지 않습니다.|  
|왼쪽 화살표|이전 행의 셀으로 포커스를 이동합니다. 포커스가 행의 첫 번째 셀에 있는 경우 아무 작업도 수행 하지 않습니다.|  
|오른쪽 화살표|행의 다음 셀으로 포커스를 이동합니다. 포커스가 행의 마지막 셀에 있는 경우 아무 작업도 수행 하지 않습니다.|  
|위쪽 화살표|현재 셀 바로 위 셀에 포커스를 이동합니다. 포커스가 첫 번째 행에 있는 경우 아무 작업도 수행 하지 않습니다.|  
|홈|현재 행의 첫 번째 셀으로 포커스를 이동합니다.|  
|End |현재 행의 마지막 셀으로 포커스를 이동합니다.|  
|Page Down|완벽 하 게 표시 되는 행의 개수로 컨트롤을 아래로 스크롤합니다. 열을 변경 하지 않고 마지막 완벽 하 게 표시 되는 행에서 포커스를 이동 합니다.|  
|Page Up|컨트롤을 완벽 하 게 표시 되는 행 수 만큼 위로 스크롤합니다. 열을 변경 하지 않고 표시 되는 첫 번째 행에 포커스를 이동 합니다.|  
|Tab|경우는 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값은 `false`, 현재 행에서 다음 셀으로 포커스를 이동 합니다. 포커스가 행의 마지막 셀에 이미 있으면 다음 행의 첫 번째 셀으로 포커스를 이동 합니다. 컨트롤의 마지막 셀에 포커스가 있으면 부모 컨테이너의 탭 순서의 다음 컨트롤로 포커스를 이동 합니다.<br /><br /> 경우는 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값은 `true`, 부모 컨테이너의 탭 순서의 다음 컨트롤로 포커스를 이동 합니다.|  
|Shift+Tab|경우는 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값은 `false`, 현재 행의 이전 셀으로 포커스를 이동 합니다. 포커스가 행의 첫 번째 셀에 이미 있으면 이전 행의 마지막 셀으로 포커스를 이동 합니다. 컨트롤의 첫 번째 셀에 포커스가 있으면 포커스가 부모 컨테이너의 탭 순서에서 이전 컨트롤로 이동 합니다.<br /><br /> 경우는 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값은 `true`, 부모 컨테이너의 탭 순서에서 이전 컨트롤로 포커스를 이동 합니다.|  
|Ctrl+Tab|경우는 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값은 `false`, 부모 컨테이너의 탭 순서의 다음 컨트롤로 포커스를 이동 합니다.<br /><br /> 경우는 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값은 `true`, 현재 행에서 다음 셀으로 포커스를 이동 합니다. 포커스가 행의 마지막 셀에 이미 있으면 다음 행의 첫 번째 셀으로 포커스를 이동 합니다. 컨트롤의 마지막 셀에 포커스가 있으면 부모 컨테이너의 탭 순서의 다음 컨트롤로 포커스를 이동 합니다.|  
|Ctrl+Shift+Tab|경우는 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값은 `false`, 부모 컨테이너의 탭 순서에서 이전 컨트롤로 포커스를 이동 합니다.<br /><br /> 경우는 <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값은 `true`, 현재 행의 이전 셀으로 포커스를 이동 합니다. 포커스가 행의 첫 번째 셀에 이미 있으면 이전 행의 마지막 셀으로 포커스를 이동 합니다. 컨트롤의 첫 번째 셀에 포커스가 있으면 포커스가 부모 컨테이너의 탭 순서에서 이전 컨트롤로 이동 합니다.|  
|CTRL + 화살표|화살표 방향에서 가장 멀리 있는 셀으로 포커스를 이동합니다.|  
|CTRL + HOME|컨트롤의 첫 번째 셀으로 포커스를 이동합니다.|  
|CTRL + END|컨트롤의 마지막 셀으로 포커스를 이동합니다.|  
|CTRL + PAGE DOWN/위로|PAGE UP 또는 PAGE DOWN와 동일 합니다.|  
|F2|하는 경우 현재 셀을 셀 편집 모드로 전환 된 <xref:System.Windows.Forms.DataGridView.EditMode%2A> 속성 값은 <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> 또는 <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>합니다.|  
|F4|현재 셀이 있으면는 <xref:System.Windows.Forms.DataGridViewComboBoxCell>셀을 편집 모드로 전환 하 고 드롭다운 목록을 표시 합니다.|  
|ALT + 위쪽/아래쪽 화살표|현재 셀이 있으면는 <xref:System.Windows.Forms.DataGridViewComboBoxCell>셀을 편집 모드로 전환 하 고 드롭다운 목록을 표시 합니다.|  
|스페이스바|현재 셀이 있으면는 <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>, 또는 <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, 발생는 <xref:System.Windows.Forms.DataGridView.CellClick> 및 <xref:System.Windows.Forms.DataGridView.CellContentClick> 이벤트입니다. 현재 셀이 있으면는 <xref:System.Windows.Forms.DataGridViewButtonCell>, 단추를 누를 수도 있습니다. 현재 셀이 있으면는 <xref:System.Windows.Forms.DataGridViewCheckBoxCell>도 선택 상태를 변경 합니다.|  
|Enter 키|현재 셀 및 행에 모든 변경 내용을 커밋합니다 하 고 현재 셀의 바로 아래 셀으로 포커스를 이동 합니다. 마지막 행에 포커스가 있으면 포커스가 이동 하지 않고 변경을 내용을 커밋합니다.|  
|Esc 키|컨트롤 편집 모드에 있으면 편집을 취소 합니다. 컨트롤 편집 모드에 없는 경우 현재 행에 컨트롤이 편집을 지 원하는 데이터 소스에 바인딩된 경우 적용 된 모든 변경 내용이 되돌립니다 또는 행 수준 커밋 범위를 갖는 가상 모드 구현 되었습니다.|  
|백스페이스|셀을 편집할 때에 삽입 지점 앞에 있는 문자를 삭제 합니다.|  
|Delete|셀을 편집할 때에 삽입 지점 뒤의 문자를 삭제 합니다.|  
|Ctrl+Enter|포커스를 이동 하지 않고 현재 셀의 모든 변경 사항을 커밋합니다. 또한 커밋으로 컨트롤이 편집 또는 가상 모드를 지 원하는 데이터 소스에 바인딩된 경우 현재 행에 변경 내용을 구현 된 행 수준의 커밋 범위.|  
|Ctrl+0|가 입력 한 <xref:System.DBNull.Value?displayProperty=nameWithType> 값이 현재 셀에 셀을 편집할 수 있습니다. 기본적으로 표시에 대 한 값을 <xref:System.DBNull> 셀 값의 값이는 <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 속성은 <xref:System.Windows.Forms.DataGridViewCellStyle> 현재 셀에 적용 합니다.|  
  
### <a name="selection-keys"></a>선택 키  
 경우는 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 속성이 `false` 및 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성이로 설정 되어 <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, 새로운 셀을 선택 항목을 바꿀 탐색 키를 사용 하 여 현재 셀을 변경 합니다. SHIFT, CTRL 및 ALT 키가이 동작에 영향을 주지 않습니다.  
  
 경우는 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 로 설정 된 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, 동일한 동작이 수행 되지만 다음과 같은 추가 합니다.  
  
|키 또는 키 조합|설명|  
|----------------------------|-----------------|  
|SHIFT + 스페이스바|전체 행 또는 열 (동일 행 또는 열 머리글을 클릭 하면)를 선택 합니다.|  
|탐색 키 (화살표 키, PAGE up/down, HOME, 끝)|전체 행 또는 열을 선택 하는 경우 새 행 또는 열에 현재 셀 변경으로 이동 합니다 전체 새 행 또는 열 (에 따라 선택 모드).|  
  
 경우 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 로 설정 된 `false` 및 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 로 설정 된 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, 전체 새 행 또는 열에는 선택 영역을 이동 키보드를 사용 하 여 현재 셀에 새로운 행 또는 열을 변경 합니다. SHIFT, CTRL 및 ALT 키가이 동작에 영향을 주지 않습니다.  
  
 경우 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 로 설정 된 `true`, 탐색 동작을 변경 되지 않지만 다중 셀 선택 영역을 수정 합니다 (CTRL + SHIFT 포함) SHIFT를 누른 채 키보드를 사용 하 여 탐색 합니다. 탐색이 시작 되기 전에 컨트롤을 앵커 셀으로 현재 셀을 표시 합니다. Shift 키를 누른 채 탐색 선택 영역 앵커 셀과 현재 셀 사이의 모든 셀을 포함 합니다. 컨트롤의 다른 셀 키보드 탐색 때이 셀을 임시로 앵커 셀과 현재 셀 사이 둘 경우 선택 취소 될 수 있습니다 하지만 이미 선택 된 경우 선택 된 상태로 유지 됩니다.  
  
 경우 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 로 설정 된 `true` 및 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 로 설정 된 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, 앵커 셀과 현재 셀의 동작은 동일 하지만 전체 행 또는 열만 선택 하거나 선택 합니다.  
  
## <a name="default-mouse-handling"></a>기본 마우스 처리  
  
### <a name="basic-mouse-handling"></a>기본 마우스 처리  
  
> [!NOTE]
>  현재 셀이 변경 항상 마우스 왼쪽된 단추를 사용 하 여 셀을 클릭 합니다. 마우스 오른쪽 단추를 사용 하 여 셀을 클릭 하면 가능한 경우 바로 가기 메뉴에서 열립니다.  
  
|마우스 작업|설명|  
|------------------|-----------------|  
|마우스 왼쪽된 단추 누름|현재 셀을 클릭 한 셀을 사용 하면 고 시킵니다는 <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> 이벤트입니다.|  
|마우스 왼쪽된 단추를|<xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType> 이벤트를 발생시킵니다.|  
|마우스 왼쪽된 단추 클릭|발생 된 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> 이벤트|  
|열 머리글 셀에 끌어다 마우스 왼쪽된 단추, 누름|경우는 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 속성은 `true`, 새로운 위치에 놓을 수 있도록 열을 이동 합니다.|  
  
### <a name="mouse-selection"></a>마우스 선택  
 선택 동작이 없습니다 마우스 가운데 단추 또는 마우스 휠을와 관련이 있습니다.  
  
 경우는 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 속성이 `false` 및 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성이로 설정 되어 <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, 다음과 같은 동작이 발생 합니다.  
  
|마우스 작업|설명|  
|------------------|-----------------|  
|마우스 왼쪽된 단추를 클릭 합니다.|사용자가 셀을 클릭 하는 경우 현재 셀만 선택 합니다. 행 또는 열 머리글을 클릭할 경우 없음 선택 동작 합니다.|  
|마우스 오른쪽 단추를 클릭 합니다.|사용 가능한 경우 바로 가기 메뉴를 표시 합니다.|  
  
 동일한 동작이 수행 때는 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 로 설정 된 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>제외 하 고, 선택 모드에 따라 행 또는 열 머리글을 클릭 하는 전체 행 또는 열을 선택 하 고 현재 셀의 행 이나 열에 첫 번째 셀으로 설정 합니다.  
  
 경우 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 로 설정 된 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, 전체 행 또는 열을 선택 합니다 행 이나 열에 셀을 클릭 합니다.  
  
 경우 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 로 설정 된 `true`, CTRL 또는 shift 키를 누른 채 셀을 클릭 하면 다중 셀 선택 영역을 수정 합니다.  
  
 Ctrl 셀을 클릭 하면 다른 모든 셀의 현재 선택 영역 상태를 유지 하는 동안 셀의 선택 상태가 변경 됩니다.  
  
 Shift 키를 누른 채 셀 또는 일련의 셀을 클릭할 때 현재 셀과 첫 번째 클릭 하기 전에 현재 셀의 위치에 있는 앵커 셀 사이의 모든 셀 선택 영역에 포함 되어 있습니다. 클릭 하 고 여러 셀 포인터를 끌어 앵커 셀은 끌기 작업의 시작 부분에 클릭 한 셀입니다. 이후에 shift 키를 누른 채 클릭 앵커 셀이 아니라 현재 셀이 변경 됩니다. 컨트롤의 다른 셀 마우스 탐색할 때이 셀을 일시적으로 앵커 셀과 현재 셀 사이 둘 경우 선택 취소 될 수 있습니다 하지만 이미 선택 된 경우 선택 된 상태로 유지 됩니다.  
  
 경우 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 로 설정 된 `true` 및 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 로 설정 된 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, SHIFT를 누른 채 (선택 모드)에 따라 행 또는 열 머리글을 클릭 하는 기존 선택 영역이 수정 됩니다 전체 행 또는 열을 이러한 경우는 선택이 있습니다. 그렇지 않은 경우 선택을 취소 되며 전체 행 또는 열을 새 선택을 시작 합니다. Ctrl 행 또는 열 머리글을 클릭 하면 있지만 됩니다를 추가 하거나 그렇지 않은 경우 현재 선택 영역을 수정 하지 않고 현재 선택 영역에서 클릭 한 행 또는 열을 제거 합니다.  
  
 경우 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 로 설정 된 `true` 및 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 로 설정 된 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, 해당 경우에 전체 행을 제외 하 고 동일한 방식으로 작동 하며 SHIFT 또는 ctrl 키를 누른 채 셀을 클릭 하면 입력 한 열에 영향을 받습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
