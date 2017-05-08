---
title: "DataGrid 컨트롤에서의 기본 키보드 및 마우스 동작 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DataGrid[WPF], 키보드 동작"
  - "DataGrid[WPF], 마우스 동작"
  - "키보드 동작[WPF], DataGrid"
  - "마우스 동작[WPF], DataGrid"
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# DataGrid 컨트롤에서의 기본 키보드 및 마우스 동작
이 항목에서는 사용자가 키보드 및 마우스를 사용하여 <xref:System.Windows.Controls.DataGrid> 컨트롤과 상호 작용하는 방법에 대해 설명합니다.  
  
 <xref:System.Windows.Controls.DataGrid>와의 일반적 상호 작용에는 탐색, 선택 및 편집이 있습니다.  선택 동작은 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 및 <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> 속성에 의해 영향을 받습니다.  이 항목에서 설명하는 동작의 원인이 되는 기본값은 <xref:System.Windows.Controls.DataGridSelectionMode?displayProperty=fullName> 및 <xref:System.Windows.Controls.DataGridSelectionUnit?displayProperty=fullName>입니다.  이러한 값을 변경하면 설명과 다른 동작이 발생할 수도 있습니다.  셀이 편집 모드인 경우 편집 컨트롤에서 <xref:System.Windows.Controls.DataGrid>의 표준 키보드 동작을 재정의할 수 있습니다.  
  
## 기본 키보드 동작  
 다음 표에서는 <xref:System.Windows.Controls.DataGrid>에 대한 기본 키보드 동작을 보여 줍니다.  
  
|키 또는 키 조합|설명|  
|---------------|--------|  
|아래쪽 화살표|포커스를 현재 셀의 바로 아래 셀로 이동합니다.  포커스가 마지막 행에 있으면 아래쪽 화살표를 눌러도 아무런 동작도 수행되지 않습니다.|  
|위쪽 화살표|포커스를 현재 셀의 바로 위 셀로 이동합니다.  포커스가 첫 번째 행에 있으면 위쪽 화살표를 눌러도 아무런 동작도 수행되지 않습니다.|  
|왼쪽 화살표|포커스를 행의 이전 셀로 이동합니다.  포커스가 행의 첫 번째 셀에 있는 경우 왼쪽 화살표를 눌러도 아무런 동작도 수행되지 않습니다.|  
|오른쪽 화살표|포커스를 행의 다음 셀로 이동합니다.  포커스가 행의 마지막 셀에 있는 경우 오른쪽 화살표를 눌러도 아무런 동작도 수행되지 않습니다.|  
|Home|포커스를 현재 행의 첫 번째 셀로 이동합니다.|  
|End|포커스를 현재 행의 마지막 셀로 이동합니다.|  
|Page Down|행이 그룹화되어 있지 않으면 완전하게 표시되는 행 수만큼 컨트롤을 아래로 스크롤합니다.  열을 변경하지 않고 포커스를 마지막으로 완전하게 표시되는 행으로 이동합니다.<br /><br /> 행이 그룹화되어 있으면 열을 변경하지 않고 <xref:System.Windows.Controls.DataGrid>에서 마지막 행으로 포커스를 이동합니다.|  
|Page Up|행이 그룹화되어 있지 않으면 완전하게 표시되는 행 수만큼 컨트롤을 위로 스크롤합니다.  열을 변경하지 않고 포커스를 처음 표시되는 행으로 이동합니다.<br /><br /> 행이 그룹화되어 있으면 열을 변경하지 않고 <xref:System.Windows.Controls.DataGrid>에서 첫 번째 행으로 포커스를 이동합니다.|  
|TAB|포커스를 현재 행의 다음 셀로 이동합니다.  포커스가 행의 마지막 셀에 있으면 다음 행의 첫 번째 셀로 포커스를 이동합니다.  포커스가 컨트롤의 마지막 셀에 있으면 부모 컨테이너의 탭 순서에서 다음 컨트롤로 포커스를 이동합니다.<br /><br /> 현재 셀이 편집 모드에 있으며 TAB을 누르면 포커스가 현재 행 밖으로 이동하는 경우 행에 대해 변경한 모든 내용은 포커스를 변경 하기 전에 커밋됩니다.|  
|Shift\+Tab|포커스를 현재 행의 이전 셀로 이동합니다.  포커스가 행의 첫 번째 셀에 이미 있으면 이전 행의 마지막 셀로 포커스를 이동합니다.  포커스가 컨트롤의 첫 번째 셀에 있으면 부모 컨테이너의 탭 순서에서 이전 컨트롤로 포커스를 이동합니다.<br /><br /> 현재 셀이 편집 모드에 있으며 TAB을 누르면 포커스가 현재 행 밖으로 이동하는 경우 행에 대해 변경한 모든 내용은 포커스를 변경 하기 전에 커밋됩니다.|  
|\<Ctrl\+아래쪽 화살표\>|포커스를 현재 열의 마지막 셀로 이동합니다.|  
|Ctrl\+위쪽 화살표|포커스를 현재 열의 첫 번째 셀로 이동합니다.|  
|Ctrl\+오른쪽 화살표|포커스를 현재 행의 마지막 셀로 이동합니다.|  
|Ctrl\+왼쪽 화살표|포커스를 현재 행의 첫 번째 셀로 이동합니다.|  
|Ctrl\+Home|포커스를 컨트롤의 첫 번째 셀로 이동합니다.|  
|Ctrl\+End|포커스를 컨트롤의 마지막 셀로 이동합니다.|  
|Ctrl\+Page Down|Page Down과 같습니다.|  
|Ctrl\+Page Up|Page Up과 같습니다.|  
|F2|<xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=fullName> 속성이 `false`이고 현재 열의 <xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=fullName> 속성이 `false`이면 현재 셀이 셀 편집 모드가 됩니다.|  
|Enter|현재 셀과 행에 대한 변경 내용을 커밋하고 포커스를 현재 셀의 바로 아래 셀로 이동합니다.  포커스가 마지막 행에 있으면 변경 내용을 모두 커밋하고 포커스는 이동하지 않습니다.|  
|Esc|컨트롤이 편집 모드에 있으면 편집을 취소하고 해당 컨트롤의 모든 변경 내용을 되돌립니다.  내부 데이터 소스가 <xref:System.ComponentModel.IEditableObject>를 구현하는 경우 Esc를 두 번째 누르면 전체 행에 대해 편집 모드가 취소됩니다.|  
|백스페이스|셀을 편집할 때 커서 앞에 있는 문자를 삭제합니다.|  
|DELETE|셀을 편집할 때 커서 뒤에 있는 문자를 삭제합니다.|  
|Ctrl\+Enter|현재 셀의 변경 내용을 모두 커밋하고 포커스는 이동하지 않습니다.|  
|Ctrl\+A|<xref:System.Windows.Controls.DataGrid.SelectionMode%2A>가 <xref:System.Windows.Controls.DataGridSelectionMode>로 설정된 경우 <xref:System.Windows.Controls.DataGrid>의 모든 행이 선택됩니다.|  
  
## 선택 키  
 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 속성이 <xref:System.Windows.Controls.DataGridSelectionMode>로 설정되면 탐색 동작이 변경되지는 않지만 Ctrl\+Shift 또는 Shift 키를 누른 채 키보드를 사용하여 탐색하면 여러 행 선택 영역이 수정됩니다.  탐색을 시작하기 전에 컨트롤은 현재 행을 앵커 행으로 표시합니다.  Shift 키를 누른 채 탐색하면 앵커 행과 현재 행 사이의 모든 행이 선택 영역에 포함됩니다.  
  
 다음 선택 키를 사용하면 여러 행 선택 영역이 수정됩니다.  
  
-   Shift\+아래쪽 화살표  
  
-   Shift\+위쪽 화살표  
  
-   Shift\+Page Down  
  
-   Shift\+Page Up  
  
-   Ctrl\+Shift\+아래쪽 화살표  
  
-   Ctrl\+Shift\+위쪽 화살표  
  
-   Ctrl\+Shift\+Home  
  
-   Ctrl\+Shift\+End  
  
## 기본 마우스 동작  
 다음 표에서는 <xref:System.Windows.Controls.DataGrid>에 대한 기본 마우스 동작을 보여 줍니다.  
  
|마우스 동작|설명|  
|------------|--------|  
|선택되지 않은 행 클릭|클릭한 행을 현재 행으로 만들고 클릭한 셀을 현재 셀로 만듭니다.|  
|현재 셀을 클릭합니다.|현재 셀을 편집 모드로 전환합니다.|  
|열 머리글 셀 끌기|<xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=fullName> 속성이 `true`이고 현재 열의 <xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=fullName> 속성이 `true`이면 열이 새로운 위치에 놓여질 수 있도록 열을 이동합니다.|  
|열 머리글 구분 기호 끌기|<xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=fullName> 속성이 `true`이고 현재 열의 <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=fullName> 속성이 `true`이면 열의 크기가 조정됩니다.|  
|열 머리글 구분선 두 번 클릭|<xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=fullName> 속성이 `true`이고 <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=fullName> 속성이 현재 열에 대해 `true`인 경우 <xref:System.Windows.Controls.DataGridLength.Auto%2A> 크기 조정 모드를 사용하여 열의 크기를 자동으로 조정합니다.|  
|열 머리글 셀 클릭|<xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=fullName> 속성이 `true`이고 현재 열의 <xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=fullName> 속성이 `true`이면 열을 정렬합니다.<br /><br /> 이미 정렬된 열의 머리글을 클릭하면 해당 열의 정렬 방향이 바뀝니다.<br /><br /> Shift 키를 누른 채로 여러 열 머리글을 클릭하면 클릭한 순서대로 여러 열이 정렬됩니다.|  
|Ctrl\+행 클릭|<xref:System.Windows.Controls.DataGrid.SelectionMode%2A>가 <xref:System.Windows.Controls.DataGridSelectionMode>로 설정되어 있으면 연속되지 않은 여러 행 선택 영역이 수정됩니다.<br /><br /> 행이 이미 선택되어 있으면 해당 행의 선택을 취소합니다.|  
|Shift\+행 클릭|<xref:System.Windows.Controls.DataGrid.SelectionMode%2A>가 <xref:System.Windows.Controls.DataGridSelectionMode>로 설정되어 있으면 연속된 여러 행 선택 영역이 수정됩니다.|  
|행 그룹 머리글을 클릭합니다.|그룹을 확장하거나 축소합니다.|  
|<xref:System.Windows.Controls.DataGrid>의 왼쪽 위 모퉁이에 나타나는 모두 선택 단추를 클릭합니다.|<xref:System.Windows.Controls.DataGrid.SelectionMode%2A>가 <xref:System.Windows.Controls.DataGridSelectionMode>로 설정된 경우 <xref:System.Windows.Controls.DataGrid>의 모든 행이 선택됩니다.|  
  
## 마우스 선택  
 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 속성이 <xref:System.Windows.Controls.DataGridSelectionMode>로 설정되어 있는 경우, Ctrl 키 또는 Shift 키를 누른 채 행을 클릭하면 여러 행 선택 영역이 수정됩니다.  
  
 Ctrl 키를 누른 채 행을 클릭하면 해당 행의 선택 상태가 변경되며 다른 모든 행은 현재 선택 상태로 유지됩니다.  인접하지 않은 행의 범위를 선택하려면 이와 같이 수행하십시오.  
  
 Shift 키를 누른 채 행을 클릭하면 클릭하기 전의 현재 행 위치에 있는 앵커 행과 현재 행 사이의 모든 행이 선택 영역에 포함됩니다.  이후에 Shift 키를 누른 채 클릭하면 앵커 행이 아닌 현재 행이 변경됩니다.  인접 행의 범위를 선택하려면 이와 같이 수행하십시오.  
  
 인접 행의 인접하지 않은 범위를 선택하기 위해 CTRL \+ SHIFT를 결합할 수 있습니다.  이렇게 하려면 앞에 설명된 대로 SHIFT\+클릭을 사용하여 첫 번째 범위를 선택합니다.  행의 첫 번째 범위가 선택된 후에 CTRL\+클릭을 사용하여 다음 범위의 첫 번째 행을 선택한 다음, 다음 범위의 마지막 행을 클릭하면서 CTRL\+SHIFT를 누릅니다.  
  
## 참고 항목  
 <xref:System.Windows.Controls.DataGrid>   
 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>