---
title: "Windows Forms DataGridView 컨트롤의 선택 모드 | Microsoft Docs"
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
  - "DataGridView 컨트롤[Windows Forms], 선택 모드"
  - "선택, DataGridView 컨트롤의 모드"
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Windows Forms DataGridView 컨트롤의 선택 모드
응용 프로그램에서 <xref:System.Windows.Forms.DataGridView> 컨트롤 내의 사용자 선택에 따라 작업을 수행해야 하는 경우도 있습니다.  작업에 따라 사용할 수 있는 선택의 종류를 제한할 수 있습니다.  예를 들어, 응용 프로그램에서 현재 선택된 레코드에 대한 보고서를 인쇄할 수 있는 경우  행의 어느 부분을 클릭해도 항상 전체 행이 선택되고 한 번에 한 개의 행만 선택할 수 있도록 <xref:System.Windows.Forms.DataGridView> 컨트롤을 구성할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> 속성을 다음 <xref:System.Windows.Forms.DataGridViewSelectionMode> 열거형 값 중 하나로 설정하여 허용되는 선택을 지정할 수 있습니다.  
  
|DataGridViewSelectionMode 값|설명|  
|---------------------------------|--------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|셀을 클릭하여 해당 셀을 선택합니다.  행 및 열 머리글은 선택에 사용할 수 없습니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|셀을 클릭하여 해당 셀을 선택합니다.  열 머리글을 클릭하여 전체 열을 선택합니다.  열 머리글은 정렬에 사용할 수 없습니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|셀이나 열 머리글을 클릭하여 전체 열을 선택합니다.  열 머리글은 정렬에 사용할 수 없습니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|셀이나 행 머리글을 클릭하여 전체 행을 선택합니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|기본 선택 모드입니다.  셀을 클릭하여 해당 셀을 선택합니다.  행 머리글을 클릭하여 전체 행을 선택합니다.|  
  
> [!NOTE]
>  런타임에 선택 모드를 변경하면 현재 선택이 자동으로 지워집니다.  
  
 기본적으로 사용자는 마우스를 끌거나, Ctrl 키나 또는 Shift 키를 누른 채로 선택 영역을 확장 또는 수정하거나, 왼쪽 위 머리글을 클릭하여 컨트롤의 모든 셀을 선택하여 여러 행, 열 또는 셀을 선택할 수 있습니다.  이 동작이 실행되지 않게 하려면 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 속성을 `false`로 설정합니다.  
  
 <xref:System.Windows.Forms.DataGridViewSelectionMode> 및 <xref:System.Windows.Forms.DataGridViewSelectionMode> 모드에서 사용자는 행을 선택한 다음 Delete 키를 눌러 행을 삭제할 수 있습니다.  사용자는 현재 셀이 편집 모드에 있지 않고, <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> 속성이 `true`로 설정되어 있으며, 내부 데이터 소스에서 사용자 기반 행 삭제를 지원하는 경우에만 행을 삭제할 수 있습니다.  이러한 설정은 프로그래밍 방식의 행 삭제에 영향을 주지 않습니다.  
  
## 프로그래밍 방식 선택  
 현재 선택 모드는 사용자 선택뿐만 아니라 프로그래밍 방식 선택의 동작도 제한합니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤에 있는 셀, 행 또는 열의 `Selected` 속성을 설정하여 현재 선택을 프로그래밍 방식으로 변경할 수 있습니다.  또한 선택 모드에 따라 <xref:System.Windows.Forms.DataGridView.SelectAll%2A> 메서드를 통해 컨트롤의 모든 셀을 선택할 수 있습니다.  선택을 취소하려면 <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> 메서드를 사용합니다.  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 속성이 `true`로 설정된 경우에는 <xref:System.Windows.Forms.DataGridView> 요소의 `Selected` 속성을 변경하여 이 요소를 선택에 추가하거나 제거할 수 있습니다.  그렇지 않은 경우, 한 요소의 `Selected` 속성을 `true`로 설정하면 다른 요소가 선택에서 자동으로 제거됩니다.  
  
 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 속성 값을 변경하더라도 현재 선택은 바뀌지 않습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 및 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 속성을 통해 현재 선택된 셀, 행 또는 열의 컬렉션을 검색할 수 있습니다.  컨트롤의 모든 셀이 선택된 경우 이러한 속성에 액세스하는 것은 비효율적입니다.  이 경우 성능 저하를 방지하려면 먼저 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 메서드를 사용합니다.  또한 선택된 셀, 행 또는 열의 수를 확인하기 위해 이러한 컬렉션에 액세스하는 것도 비효율적일 수 있습니다.  대신 <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A> 또는 <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> 메서드를 사용하여 <xref:System.Windows.Forms.DataGridViewElementStates> 값을 전달하는 것이 좋습니다.  
  
> [!TIP]
>  선택한 셀을 프로그래밍 방식으로 사용하는 방법을 보여 주는 예제 코드는 <xref:System.Windows.Forms.DataGridView> 클래스 개요에서 찾을 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>   
 <xref:System.Windows.Forms.DataGridViewSelectionMode>   
 [Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)