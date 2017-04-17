---
title: "Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "데이터 표, 마우스 처리"
  - "DataGridView 컨트롤[Windows Forms], 키보드 처리"
  - "DataGridView 컨트롤[Windows Forms], 마우스 처리"
  - "DataGridView 컨트롤[Windows Forms], 탐색 키"
  - "키보드, DataGridView 컨트롤의 기본 처리"
  - "마우스, DataGridView 컨트롤의 기본 처리"
  - "탐색 키, DataGridView 컨트롤"
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리
다음 표에서는 사용자가 키보드나 마우스를 사용하여 <xref:System.Windows.Forms.DataGridView> 컨트롤과 상호 작용하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  키보드 동작을 사용자 지정하려면 <xref:System.Windows.Forms.Control.KeyDown>과 같은 표준 키보드 이벤트를 처리합니다.  그러나 편집 모드에서는 호스팅된 편집 컨트롤이 키보드 입력을 받고 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 키보드 이벤트는 발생하지 않습니다.  편집 컨트롤 이벤트를 처리하려면 <xref:System.Windows.Forms.DataGridView.EditingControlShowing> 이벤트 처리기에서 편집 컨트롤에 처리기를 연결합니다.  <xref:System.Windows.Forms.DataGridView> 서브클래스에서 <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> 및 <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> 메서드를 재정의하여 키보드 동작을 사용자 지정할 수도 있습니다.  
  
## 기본 키보드 처리  
  
### 기본 탐색 및 입력 키  
  
|키 또는 키 조합|설명|  
|---------------|--------|  
|아래쪽 화살표|포커스를 현재 셀의 바로 아래 셀로 이동합니다.  포커스가 마지막 행에 있으면 아무 작업도 수행하지 않습니다.|  
|왼쪽 화살표|포커스를 행의 이전 셀로 이동합니다.  포커스가 행의 첫 번째 셀에 있으면 아무 작업도 수행하지 않습니다.|  
|오른쪽 화살표|포커스를 행의 다음 셀로 이동합니다.  포커스가 행의 마지막 셀에 있으면 아무 작업도 수행하지 않습니다.|  
|위쪽 화살표|포커스를 현재 셀의 바로 위 셀로 이동합니다.  포커스가 첫 번째 행에 있으면 아무 작업도 수행하지 않습니다.|  
|Home|포커스를 현재 행의 첫 번째 셀로 이동합니다.|  
|End|포커스를 현재 행의 마지막 셀로 이동합니다.|  
|Page Down|완전하게 표시되는 행 수만큼 컨트롤을 아래로 스크롤합니다.  열을 변경하지 않고 포커스를 마지막으로 완전하게 표시되는 행으로 이동합니다.|  
|Page Up|완전하게 표시되는 행 수만큼 컨트롤을 위로 스크롤합니다.  열을 변경하지 않고 포커스를 처음 표시되는 행으로 이동합니다.|  
|TAB|<xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값이 `false`이면 포커스를 현재 행의 다음 셀로 이동합니다.  포커스가 행의 마지막 셀에 이미 있으면 다음 행의 첫 번째 셀로 포커스를 이동합니다.  포커스가 컨트롤의 마지막 셀에 있으면 부모 컨테이너의 탭 순서에서 다음 컨트롤로 포커스를 이동합니다.<br /><br /> <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값이 `true`이면 포커스를 부모 컨테이너의 탭 순서에서 다음 컨트롤로 이동합니다.|  
|Shift\+Tab|<xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값이 `false`이면 포커스를 현재 행의 이전 셀로 이동합니다.  포커스가 행의 첫 번째 셀에 이미 있으면 이전 행의 마지막 셀로 포커스를 이동합니다.  포커스가 컨트롤의 첫 번째 셀에 있으면 부모 컨테이너의 탭 순서에서 이전 컨트롤로 포커스를 이동합니다.<br /><br /> <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값이 `true`이면 포커스를 부모 컨테이너의 탭 순서에서 이전 컨트롤로 이동합니다.|  
|Ctrl\+Tab|<xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값이 `false`이면 포커스를 부모 컨테이너의 탭 순서에서 다음 컨트롤로 이동합니다.<br /><br /> <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값이 `true`이면 포커스를 현재 행의 다음 셀로 이동합니다.  포커스가 행의 마지막 셀에 이미 있으면 다음 행의 첫 번째 셀로 포커스를 이동합니다.  포커스가 컨트롤의 마지막 셀에 있으면 부모 컨테이너의 탭 순서에서 다음 컨트롤로 포커스를 이동합니다.|  
|Ctrl\+Shift\+Tab|<xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값이 `false`이면 포커스를 부모 컨테이너의 탭 순서에서 이전 컨트롤로 이동합니다.<br /><br /> <xref:System.Windows.Forms.DataGridView.StandardTab%2A> 속성 값이 `true`이면 포커스를 현재 행의 이전 셀로 이동합니다.  포커스가 행의 첫 번째 셀에 이미 있으면 이전 행의 마지막 셀로 포커스를 이동합니다.  포커스가 컨트롤의 첫 번째 셀에 있으면 부모 컨테이너의 탭 순서에서 이전 컨트롤로 포커스를 이동합니다.|  
|Ctrl\+화살표|포커스를 화살표 방향으로 가장 멀리 있는 셀로 이동합니다.|  
|Ctrl\+Home|포커스를 컨트롤의 첫 번째 셀로 이동합니다.|  
|Ctrl\+End|포커스를 컨트롤의 마지막 셀로 이동합니다.|  
|Ctrl\+Page Down\/Up|Page Down이나 Page Up과 같습니다.|  
|F2|<xref:System.Windows.Forms.DataGridView.EditMode%2A> 속성 값이 <xref:System.Windows.Forms.DataGridViewEditMode> 또는 <xref:System.Windows.Forms.DataGridViewEditMode>일 경우 현재 셀을 셀 편집 모드에 둡니다.|  
|F4|현재 셀이 <xref:System.Windows.Forms.DataGridViewComboBoxCell>일 경우 셀을 편집 모드에 두고 드롭다운 목록을 표시합니다.|  
|Alt\+위쪽\/아래쪽 화살표|현재 셀이 <xref:System.Windows.Forms.DataGridViewComboBoxCell>일 경우 셀을 편집 모드에 두고 드롭다운 목록을 표시합니다.|  
|Space|현재 셀이 <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell> 또는 <xref:System.Windows.Forms.DataGridViewCheckBoxCell>일 경우 <xref:System.Windows.Forms.DataGridView.CellClick> 및 <xref:System.Windows.Forms.DataGridView.CellContentClick> 이벤트를 발생시킵니다.  현재 셀이 <xref:System.Windows.Forms.DataGridViewButtonCell>이면 단추도 누르고,  현재 셀이 <xref:System.Windows.Forms.DataGridViewCheckBoxCell>이면 선택 상태도 변경합니다.|  
|Enter|현재 셀과 행에 대한 변경 내용을 커밋하고 포커스를 현재 셀의 바로 아래 셀로 이동합니다.  포커스가 마지막 행에 있으면 변경 내용을 모두 커밋하고 포커스는 이동하지 않습니다.|  
|Esc|컨트롤이 편집 모드에 있을 경우 편집 내용을 취소합니다.  컨트롤이 편집 모드에 있지 않은 경우 편집 모드를 지원하는 데이터 소스에 컨트롤이 바인딩되어 있거나 가상 모드가 행 수준 커밋 범위를 사용하여 구현되었으면 현재 행에 대한 모든 변경 내용을 되돌립니다.|  
|백스페이스|셀을 편집할 때 삽입 지점 앞에 있는 문자를 삭제합니다.|  
|DELETE|셀을 편집할 때 삽입 지점 뒤에 있는 문자를 삭제합니다.|  
|Ctrl\+Enter|현재 셀의 변경 내용을 모두 커밋하고 포커스는 이동하지 않습니다.  또한 편집 모드를 지원하는 데이터 소스에 컨트롤이 바인딩되어 있거나 가상 모드가 행 수준 커밋 범위를 사용하여 구현된 경우 현재 행에 대한 모든 변경 내용을 커밋합니다.|  
|CTRL\+0|셀이 편집 가능하면 현재 셀에 <xref:System.DBNull.Value?displayProperty=fullName> 값을 입력합니다.  기본적으로 <xref:System.DBNull> 셀 값에 대해 표시되는 값은 현재 셀에 적용된 <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 속성 값입니다.|  
  
### 선택 키  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 속성이 `false`로 설정되어 있고 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성이 <xref:System.Windows.Forms.DataGridViewSelectionMode>로 설정되어 있을 경우, 탐색 키를 사용하여 현재 셀을 변경하면 선택 영역이 새로운 셀로 변경됩니다.  Shift, Ctrl 및 Alt 키는 이 동작에 영향을 주지 않습니다.  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>가 <xref:System.Windows.Forms.DataGridViewSelectionMode> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode>로 설정되어 있으면 같은 동작이 발생하지만 다음 사항이 추가됩니다.  
  
|키 또는 키 조합|설명|  
|---------------|--------|  
|Shift\+스페이스바|전체 행 또는 열을 선택합니다. 행 또는 열 머리글을 클릭하는 것과 결과가 같습니다.|  
|탐색 키\(화살표 키, Page Up\/Page Down, Home, End\)|전체 행 또는 열을 선택한 경우, 현재 셀을 새 행이나 열로 변경하면 선택 모드에 따라 선택 영역이 전체 새 행이나 열로 이동합니다.|  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>가 `false`로 설정되어 있고 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>가 <xref:System.Windows.Forms.DataGridViewSelectionMode> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode>로 설정되어 있는 경우, 키보드를 사용하여 현재 셀을 새 행이나 열로 변경하면 선택 영역이 전체 새 행이나 열로 이동합니다.  Shift, Ctrl 및 Alt 키는 이 동작에 영향을 주지 않습니다.  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>가 `true`로 설정되어 있으면 탐색 동작이 변경되지 않지만 Ctrl\+Shift 또는 Shift 키를 누른 채 키보드를 사용하여 탐색하면 여러 셀 선택 영역이 수정됩니다.  탐색을 시작하기 전에 컨트롤은 현재 셀을 앵커 셀로 표시합니다.  Shift 키를 누른 채 탐색하면 선택 영역에 앵커 셀과 현재 셀 사이의 모든 셀이 포함됩니다.  컨트롤의 다른 셀은 이미 선택된 경우 선택된 상태로 남아 있지만, 키보드로 탐색할 때 이 셀을 임시로 앵커 셀과 현재 셀 사이에 둘 경우 선택 취소될 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>가 `true`로 설정되어 있고 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>가 <xref:System.Windows.Forms.DataGridViewSelectionMode> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode>로 설정되어 있으면 앵커 셀과 현재 셀의 동작은 같지만 전체 행이나 열만 선택되거나 선택 취소됩니다.  
  
## 기본 마우스 처리  
  
### 기본 마우스 처리  
  
> [!NOTE]
>  마우스 왼쪽 단추로 셀을 클릭하면 항상 현재 셀이 변경됩니다.  마우스 오른쪽 단추로 셀을 클릭하면 사용 가능한 상태일 경우 바로 가기 메뉴가 열립니다.  
  
|마우스 동작|설명|  
|------------|--------|  
|마우스 왼쪽 단추 누르기|클릭한 셀을 현재 셀로 만들고 <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=fullName> 이벤트를 발생시킵니다.|  
|마우스 왼쪽 단추 놓기|<xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=fullName> 이벤트를 발생시킵니다.|  
|마우스 왼쪽 단추 클릭|<xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName> 및 <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=fullName> 이벤트를 발생시킵니다.|  
|열 머리글 셀에서 마우스 왼쪽 단추를 눌러 끌기|<xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName> 속성이 `true`이면 새 위치에 놓을 수 있도록 열이 이동합니다.|  
  
### 마우스 선택  
 마우스 가운데 단추 또는 마우스 휠과 연결된 선택 동작이 없습니다.  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 속성이 `false`로 설정되어 있고 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성이 <xref:System.Windows.Forms.DataGridViewSelectionMode>로 설정되어 있으면 다음 동작이 발생합니다.  
  
|마우스 동작|설명|  
|------------|--------|  
|마우스 왼쪽 단추 클릭|사용자가 셀을 클릭하면 현재 셀만 선택됩니다.  사용자가 행 또는 열 머리글을 클릭하면 선택 동작이 발생하지 않습니다.|  
|마우스 오른쪽 단추 클릭|사용 가능한 바로 가기 메뉴가 있으면 표시됩니다.|  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>가 <xref:System.Windows.Forms.DataGridViewSelectionMode> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode>로 설정되어 있으면 같은 동작이 발생합니다. 선택 모드에 따라 행 또는 열 머리글을 클릭할 경우 전체 행 또는 열이 선택되고 현재 셀이 행이나 열의 첫 번째 셀로 설정된다는 점만 다릅니다.  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>가 <xref:System.Windows.Forms.DataGridViewSelectionMode> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode>로 설정되어 있는 경우, 행이나 열의 셀을 클릭하면 전체 행이나 열이 선택됩니다.  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>가 `true`로 설정되어 있는 경우, Ctrl 키 또는 Shift 키를 누른 채 셀을 클릭하면 여러 셀 선택 영역이 수정됩니다.  
  
 Ctrl 키를 누른 채 셀을 클릭하면 해당 셀의 선택 상태가 변경되며 다른 모든 셀은 현재 선택 상태로 유지됩니다.  
  
 Shift 키를 누른 채 하나의 셀이나 여러 셀을 클릭하면 첫 번째 클릭하기 전의 현재 셀 위치에 있는 앵커 셀과 현재 셀 사이의 모든 셀이 선택 영역에 포함됩니다.  셀 하나를 클릭한 다음 여러 셀을 대상으로 포인터를 끌 경우 끌기 작업을 시작할 때 클릭한 셀이 앵커 셀이 됩니다.  이후에 Shift 키를 누른 채 클릭하면 앵커 셀이 아닌 현재 셀이 변경됩니다.  컨트롤의 다른 셀은 이미 선택된 경우 선택된 상태로 남아 있지만, 마우스로 탐색할 때 이 셀을 임시로 앵커 셀과 현재 셀 사이에 둘 경우 선택 취소될 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>가 `true`로 설정되어 있고  <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>가 <xref:System.Windows.Forms.DataGridViewSelectionMode> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode>로 설정되어 있을 때 Shift 키를 누른 채 선택 모드에 따라 행 또는 열 머리글을 클릭할 경우 전체 행이나 전체 열이 선택되어 있으면 그 선택 영역이 수정됩니다.  그렇지 않으면 선택 영역이 지워지고 전체 행이나 열의 새로운 선택 영역이 시작됩니다.  그러나 Ctrl 키를 누른 채 행 또는 열 머리글을 클릭하면 현재 선택 영역이 수정되지 않고 현재 선택 영역에서 클릭한 행이나 열이 제거되거나 추가됩니다.  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>가 `true`로 설정되어 있고 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>가 <xref:System.Windows.Forms.DataGridViewSelectionMode> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode>로 설정되어 있을 때 Shift 키 또는 Ctrl 키를 누른 채 셀을 클릭하면 전체 행과 열만 영향을 받는다는 점을 제외하고는 같은 방식으로 동작합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)