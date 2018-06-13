---
title: DataGrid 컨트롤에서의 기본 키보드 및 마우스 동작
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid [WPF], keyboard behavior
- DataGrid [WPF], mouse behavior
- keyboard behavior [WPF], DataGrid
- mouse behavior [WPF], DataGrid
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
ms.openlocfilehash: 559b84d3e6b5ece6c71f17e6766cac4ec14824cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557422"
---
# <a name="default-keyboard-and-mouse-behavior-in-the-datagrid-control"></a>DataGrid 컨트롤에서의 기본 키보드 및 마우스 동작
이 항목에서는 사용자 수와 상호 작용 하는 방법을 설명는 <xref:System.Windows.Controls.DataGrid> 키보드 및 마우스를 사용 하 여 제어 합니다.  
  
 와 일반적인 상호 작용은 <xref:System.Windows.Controls.DataGrid> 탐색, 선택 및 편집을 포함 합니다. 선택 동작에 영향을 받는 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 및 <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> 속성입니다. 이 항목에 설명 된 동작의 원인이 되는 기본값은 <xref:System.Windows.Controls.DataGridSelectionMode.Extended?displayProperty=nameWithType> 및 <xref:System.Windows.Controls.DataGridSelectionUnit.FullRow?displayProperty=nameWithType>합니다. 이러한 값을 변경 하는 설명 된 것과 다른 동작을 발생할 수 있습니다. 편집 컨트롤의 표준 키보드의 동작을 재정의할 수 있습니다 셀 편집 모드일 때는 <xref:System.Windows.Controls.DataGrid>합니다.  
  
## <a name="default-keyboard-behavior"></a>기본 키보드 동작  
 다음 표에서 기본 키보드 동작에 대 한는 <xref:System.Windows.Controls.DataGrid>합니다.  
  
|키 또는 키 조합|설명|  
|----------------------------|-----------------|  
|아래쪽 화살표|현재 셀의 바로 아래 셀으로 포커스를 이동합니다. 마지막 행에 포커스가 있으면 아래쪽 화살표를 누르면는 아무 작업도 수행 합니다.|  
|위쪽 화살표|현재 셀 바로 위 셀에 포커스를 이동합니다. 첫 번째 행에 포커스가 있으면 위쪽 화살표 키를 누르면는 아무 작업도 수행 합니다.|  
|왼쪽 화살표|이전 행의 셀으로 포커스를 이동합니다. 포커스가 행의 첫 번째 셀에 있는 경우 왼쪽 화살표 키를 누르면는 아무 작업도 수행 합니다.|  
|오른쪽 화살표|행의 다음 셀으로 포커스를 이동합니다. 포커스가 행의 마지막 셀에 있는 경우 오른쪽 화살표를는 아무 작업도 수행 합니다.|  
|홈|현재 행의 첫 번째 셀으로 포커스를 이동합니다.|  
|End |현재 행의 마지막 셀으로 포커스를 이동합니다.|  
|Page Down|행 그룹화 되어 있지 않으면 완벽 하 게 표시 되는 행의 개수로 컨트롤을 아래로 스크롤합니다. 열을 변경 하지 않고 마지막 완벽 하 게 표시 되는 행에서 포커스를 이동 합니다.<br /><br /> 행을 그룹화 하는 경우의 마지막 행에 포커스를 이동는 <xref:System.Windows.Controls.DataGrid> 열을 변경 하지 않고 있습니다.|  
|Page Up|행 그룹화 되어 있지 않으면 컨트롤을 위로 스크롤합니다 완벽 하 게 표시 되는 행 수입니다. 열을 변경 하지 않고 표시 되는 첫 번째 행에 포커스를 이동 합니다.<br /><br /> 행을 그룹화 하는 경우 첫 번째 행에 포커스를 이동는 <xref:System.Windows.Controls.DataGrid> 열을 변경 하지 않고 있습니다.|  
|Tab|현재 행에서 다음 셀으로 포커스를 이동합니다. 행의 마지막 셀에 포커스가 있으면 포커스가 다음 행의 첫 번째 셀으로 이동 합니다. 컨트롤의 마지막 셀에 포커스가 있으면 부모 컨테이너의 탭 순서의 다음 컨트롤로 포커스를 이동 합니다.<br /><br /> 현재 셀이 편집 모드에 있고 TAB을 누르면 포커스가 현재 행에서 멀리 이동, 모든 변경 된 행에 대 한 내용이 포커스를 변경 하기 전에 하는 경우.|  
|Shift+Tab|현재 행에서 이전 셀으로 포커스를 이동합니다. 포커스가 행의 첫 번째 셀에 이미 있으면 이전 행의 마지막 셀으로 포커스를 이동 합니다. 컨트롤의 첫 번째 셀에 포커스가 있으면 포커스가 부모 컨테이너의 탭 순서에서 이전 컨트롤로 이동 합니다.<br /><br /> 현재 셀이 편집 모드에 있고 TAB을 누르면 포커스가 현재 행에서 멀리 이동, 모든 변경 된 행에 대 한 내용이 포커스를 변경 하기 전에 하는 경우.|  
|Ctrl+아래쪽 화살표|현재 열의 마지막 셀으로 포커스를 이동합니다.|  
|Ctrl+위쪽 화살표|현재 열에서 첫 번째 셀으로 포커스를 이동합니다.|  
|Ctrl+오른쪽 화살표|현재 행의 마지막 셀으로 포커스를 이동합니다.|  
|Ctrl+왼쪽 화살표|현재 행의 첫 번째 셀으로 포커스를 이동합니다.|  
|CTRL + HOME|컨트롤의 첫 번째 셀으로 포커스를 이동합니다.|  
|CTRL + END|컨트롤의 마지막 셀으로 포커스를 이동합니다.|  
|Ctrl+Page Down|PAGE DOWN와 동일 합니다.|  
|Ctrl+Page Up|PAGE UP와 동일 합니다.|  
|F2|경우는 <xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=nameWithType> 속성은 `false` 및 <xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=nameWithType> 속성은 `false` 현재 열에 대 한 현재 셀을 셀 편집 모드로 전환 합니다.|  
|Enter 키|현재 셀 및 행에 모든 변경 내용을 커밋합니다 하 고 현재 셀의 바로 아래 셀으로 포커스를 이동 합니다. 마지막 행에 포커스가 있으면 포커스가 이동 하지 않고 변경을 내용을 커밋합니다.|  
|Esc 키|컨트롤 편집 모드에 있으면 편집을 취소 하 고 컨트롤에 적용 된 모든 변경 내용이 되돌립니다. 기본 데이터 원본 구현 하는 경우 <xref:System.ComponentModel.IEditableObject>, esc 키를 두 번째로 전체 행에 대 한 편집 모드를 취소 합니다.|  
|백스페이스|셀을 편집할 때 커서를 앞에 있는 문자를 삭제 합니다.|  
|Delete|셀을 편집할 때 커서 뒤의 문자를 삭제 합니다.|  
|Ctrl+Enter|포커스를 이동 하지 않고 현재 셀의 모든 변경 사항을 커밋합니다.|  
|Ctrl+A|경우 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 로 설정 된 <xref:System.Windows.Controls.DataGridSelectionMode.Extended>의 모든 행을 선택는 <xref:System.Windows.Controls.DataGrid>합니다.|  
  
## <a name="selection-keys"></a>선택 키  
 경우는 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 속성이 <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, 탐색 동작을 변경 되지 않지만 다중 행 선택 영역을 수정 합니다 (CTRL + SHIFT 포함) SHIFT를 누른 채 키보드를 사용 하 여 탐색 합니다. 탐색 시작 되기 전에 컨트롤을 앵커 행으로 현재 행을 표시 합니다. Shift 키를 누른 채 탐색 하는 경우 앵커 행과 현재 행 사이의 모든 행 선택 영역에 포함 되어 있습니다.  
  
 다음 선택 키를 사용 하는 여러 행 선택 영역이 수정합니다.  
  
-   Shift+아래쪽 화살표  
  
-   Shift+위쪽 화살표  
  
-   Shift+Page Down  
  
-   Shift+Page Up  
  
-   Ctrl+Shift+아래쪽 화살표  
  
-   Ctrl+Shift+위쪽 화살표  
  
-   CTRL + SHIFT + HOME  
  
-   CTRL + SHIFT + END  
  
## <a name="default-mouse-behavior"></a>기본 마우스 동작  
 다음 표에서 기본 마우스 동작에 대 한는 <xref:System.Windows.Controls.DataGrid>합니다.  
  
|마우스 작업|설명|  
|------------------|-----------------|  
|선택 되지 않은 행을 클릭 합니다.|현재 행 및 현재 셀 클릭 한 셀을 클릭 한 행으로 만듭니다.|  
|현재 셀을 클릭 합니다.|현재 셀을 편집 모드로 전환 합니다.|  
|열 머리글 셀을 끌어 옵니다.|경우는 <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=nameWithType> 속성은 `true` 및 <xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=nameWithType> 속성은 `true` 새로운 위치에 놓을 수 있도록 현재 열에 대 한 열을 이동 합니다.|  
|열 머리글 구분 기호를 끌어 옵니다.|경우는 <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> 속성은 `true` 및 <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> 속성은 `true` 현재 열에 대 한 열 크기를 조정 합니다.|  
|열 머리글 구분선을 두 번 클릭|경우는 <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> 속성은 `true` 및 <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> 속성은 `true` 현재 열 자동 크기에 대 한 사용 하 여 열에서 <xref:System.Windows.Controls.DataGridLength.Auto%2A> 크기 조정 모드입니다.|  
|열 머리글 셀을 클릭 합니다.|경우는 <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=nameWithType> 속성은 `true` 및 <xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=nameWithType> 속성은 `true` 현재 열에 대 한 열을 정렬 합니다.<br /><br /> 정렬 된 열의 머리글을 클릭 하는 해당 열의 정렬 방향을 반대로 바꿉니다.<br /><br /> 여러 열 머리글을 클릭 하는 여러 열을 클릭 한 순서로 별로 정렬 하는 동안 SHIFT 키를 누릅니다.|  
|CTRL + 행을 클릭 합니다.|경우 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 로 설정 된 <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, 연속 되지 않은 다중 행 선택 영역이 수정 합니다.<br /><br /> 행은 이미 선택 되어 있으면 행을 선택 취소 합니다.|  
|Shift 키를 한 행을 클릭 합니다.|경우 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 로 설정 된 <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, 연속 다중 행 선택 영역이 수정 합니다.|  
|행 그룹 머리글을 클릭 합니다.|활동이 확장 되거나 그룹을 축소 합니다.|  
|왼쪽된 위 모퉁이에 있는 모든 선택 단추를 클릭 합니다.는 <xref:System.Windows.Controls.DataGrid>|경우 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 로 설정 된 <xref:System.Windows.Controls.DataGridSelectionMode.Extended>의 모든 행을 선택는 <xref:System.Windows.Controls.DataGrid>합니다.|  
  
## <a name="mouse-selection"></a>마우스 선택  
 경우는 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 속성이 <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, CTRL 또는 shift 키를 누른 채 행을 클릭 하면 여러 행 선택 영역이 수정 합니다.  
  
 CTRL 키를 눌러 하는 동안 행을 클릭 하면 다른 모든 행 현재 선택 영역 상태를 유지 하는 동안 행의 선택 상태가 변경 됩니다. 인접 하지 않은 행을 선택 하려면이 작업을 수행 합니다.  
  
 Shift 키를 누른 채 행을 클릭 하면 현재 행과 클릭 하기 전에 현재 행의 위치에 있는 앵커 행 사이의 모든 행 선택 영역에 포함 됩니다. 이후에 shift 키를 누른 채 클릭 앵커 행이 아니라 현재 행이 변경 됩니다. 인접 한 행의 범위를 선택 하려면이 작업을 수행 합니다.  
  
 인접 한 행의 인접 하지 않은 범위를 선택 하려면 CTRL + SHIFT은 결합할 수 있습니다. 이 수행 하려면 shift 키를 사용 하 여 첫 번째 범위를 선택 하에서 앞에서 설명한 대로 클릭 합니다. 첫 번째 범위의 행을 선택한 후 ctrl 키를 사용 + 다음 범위에서 첫 번째 행을 선택 하려면 클릭 한 다음 CTRL + SHIFT를 누른 채 다음 범위에서 마지막 행을 클릭 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.DataGrid>  
 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>
