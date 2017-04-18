---
title: "Windows Forms DataGridView 컨트롤의 열 정렬 모드 | Microsoft Docs"
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
  - "데이터 표, 정렬 모드"
  - "DataGridView 컨트롤[Windows Forms], 정렬 모드"
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Windows Forms DataGridView 컨트롤의 열 정렬 모드
<xref:System.Windows.Forms.DataGridView> 열에는 세 가지 정렬 모드가 있습니다.  각 열의 정렬 모드는 열의 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성을 통해 지정할 수 있으며 이 속성은 다음 <xref:System.Windows.Forms.DataGridViewColumnSortMode> 열거형 값 중 하나로 설정할 수 있습니다.  
  
|`DataGridViewColumnSortMode` 값|설명|  
|------------------------------------|--------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|텍스트 상자 열의 기본값입니다.  열 머리글을 선택에 사용하지 않는 한 열 머리글을 클릭하면 <xref:System.Windows.Forms.DataGridView>가 이 열을 기준으로 자동 정렬되고 정렬 순서를 나타내는 문자가 표시됩니다.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|텍스트 상자가 아닌 열의 기본값입니다.  이 열을 프로그래밍 방식으로 정렬할 수도 있지만 이 열은 정렬을 위한 열이 아니므로 정렬 문자에 대한 공간이 예약되어 있지 않습니다.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|이 열은 프로그래밍 방식으로 정렬할 수 있으며 정렬 문자에 대한 공간이 예약되어 있습니다.|  
  
 열에 의미에 따라 정렬될 수 있는 값이 포함되어 있는 경우에는 열의 정렬 모드를 기본값인 <xref:System.Windows.Forms.DataGridViewColumnSortMode>에서 다른 값으로 변경할 수 있습니다.  예를 들어, 항목 상태를 나타내는 번호를 포함하는 데이터베이스 열이 있는 경우 이미지 열을 데이터베이스 열에 바인딩하여 이러한 번호를 해당 아이콘으로 표시할 수 있습니다.  그런 다음 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName> 이벤트 처리기에서 숫자 셀 값을 이미지 표시 값으로 변경할 수 있습니다.  이 경우 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewColumnSortMode>으로 설정하면 사용자가 열을 정렬할 수 있습니다.  자동 정렬을 사용하면 번호에 해당하는 상태에 자연 시퀀스가 없더라도 사용자가 상태가 동일한 항목을 그룹화할 수 있습니다.  확인란 열에서 상태가 동일한 항목을 그룹화하는 데에도 자동 정렬이 유용합니다.  
  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 설정에 관계없이 열 값을 기준으로 <xref:System.Windows.Forms.DataGridView>를 프로그래밍 방식으로 정렬할 수 있습니다.  프로그래밍 정렬은 정렬에 대해 사용자 지정 UI\(사용자 인터페이스\)를 제공하거나 사용자 지정 정렬을 구현하려는 경우에 유용합니다.  사용자 정렬 UI는 열 머리글 선택을 사용하도록 <xref:System.Windows.Forms.DataGridView> 선택 모드를 설정하는 경우 등에 유용합니다.  이 경우 열 머리글을 정렬에 사용할 수는 없지만 머리글에 적절한 정렬 문자를 표시하려면 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewColumnSortMode>으로 설정합니다.  
  
 프로그래밍 정렬 모드로 설정된 열에는 정렬 문자가 자동으로 표시되지 않습니다.  이러한 열의 경우 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName> 속성을 설정하여 문자를 직접 표시해야 합니다.  이 기능은 사용자 지정 정렬을 융통적으로 수행하려는 경우에 필요합니다.  예를 들어, <xref:System.Windows.Forms.DataGridView>를 여러 열을 기준으로 정렬하는 경우 여러 정렬 문자를 표시하거나 정렬 문자를 표시하지 않을 수 있습니다.  
  
 모든 열을 기준으로 <xref:System.Windows.Forms.DataGridView>를 프로그래밍 방식으로 정렬할 수 있지만 단추 열처럼 의미에 따라 정렬될 수 있는 값이 없는 열도 있습니다.  이러한 열의 경우 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewColumnSortMode>로 설정하면 해당 열이 정렬에 사용되지 않으며 이로 인해 머리글에 정렬 문자에 대한 공간을 예약할 필요가 없습니다.  
  
 <xref:System.Windows.Forms.DataGridView>를 정렬한 경우 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 및 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 속성 값을 확인하여 정렬 열과 정렬 순서를 확인할 수 있습니다.  사용자 지정 정렬 작업을 수행한 후에는 이러한 값이 의미가 없습니다.  사용자 지정 정렬에 대한 자세한 내용은 이 항목의 뒷부분에 나오는 사용자 지정 정렬 단원을 참조하십시오.  
  
 바인딩된 열과 바인딩되지 않은 열을 모두 포함하는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 정렬하는 경우 바인딩되지 않은 열의 값을 자동으로 유지 관리할 수 없습니다.  이러한 값을 유지 관리하려면 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성을 `true`로 설정하고 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 및 <xref:System.Windows.Forms.DataGridView.CellValuePushed> 이벤트를 처리하여 가상 모드를 구현해야 합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  바인딩된 모드에서 바인딩되지 않은 열별로 정렬할 수는 없습니다.  
  
## 프로그래밍 정렬  
 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드를 호출하여 <xref:System.Windows.Forms.DataGridView>를 프로그래밍 방식으로 정렬할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드의 `Sort(DataGridViewColumn,ListSortDirection)` 오버로드는 <xref:System.Windows.Forms.DataGridViewColumn> 및 <xref:System.ComponentModel.ListSortDirection> 열거형 값을 매개 변수로 사용합니다.  의미에 따라 정렬될 수 있는 값이 있는 열을 기준으로 정렬하려고 하지만 자동 정렬을 구성하지 않으려는 경우에 이 오버로드가 유용합니다.  이 오버로드를 호출하고 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성 값이 <xref:System.Windows.Forms.DataGridViewColumnSortMode?displayProperty=fullName>인 열에 전달하면 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 및 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 속성이 자동으로 설정되고 적절한 정렬 문자가 열 머리글에 나타납니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 설정하여 <xref:System.Windows.Forms.DataGridView> 컨트롤을 외부 데이터 소스에 바인딩하면 `Sort(DataGridViewColumn,ListSortDirection)` 메서드 오버로드가 바인딩되지 않은 열에서 동작하지 않습니다.  또한 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성을 `true`로 설정하면 바인딩된 열에 대해서만 이 오버로드를 호출할 수 있습니다.  열이 데이터 바인딩되었는지 여부를 확인하려면 <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> 속성 값을 확인합니다.  바인딩된 모드에서는 바인딩되지 않은 열을 정렬할 수 없습니다.  
  
## 사용자 지정 정렬  
 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드의 `Sort(IComparer)` 오버로드를 사용하거나 <xref:System.Windows.Forms.DataGridView.SortCompare> 이벤트를 처리하여 <xref:System.Windows.Forms.DataGridView>를 사용자 지정할 수 있습니다.  
  
 `Sort(IComparer)` 메서드 오버로드는 <xref:System.Collections.IComparer> 인터페이스를 매개 변수로 구현하는 클래스 인스턴스를 사용합니다.  이 오버로드는 열 값에 자연 정렬 순서가 없거나 자연 정렬 순서가 부적합한 경우처럼 사용자 지정 정렬을 제공하려는 경우에 유용합니다.  이 경우 자동 정렬을 사용할 수 없지만 사용자가 열 머리글을 클릭하여 정렬하도록 할 수는 있습니다.  열 머리글을 선택에 사용하지 않는 경우 <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> 이벤트 처리기에서 이 오버로드를 호출합니다.  
  
> [!NOTE]
>  `Sort(IComparer)` 메서드 오버로드는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 외부 데이터 소스에 바인딩되어 있지 않고 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성 값이 `false`인 경우에만 동작합니다.  외부 데이터 소스에 바인딩된 열에 대한 정렬을 사용자 지정하려면 해당 데이터 소스에서 제공하는 정렬 작업을 사용해야 합니다.  또한 가상 모드에서 바인딩되지 않은 열에 대한 사용자 정렬 작업을 제공해야 합니다.  
  
 `Sort(IComparer)` 메서드 오버로드를 사용하려면 <xref:System.Collections.IComparer> 인터페이스를 구현하는 사용자 클래스를 만들어야 합니다.  이 인터페이스를 사용하려면 클래스에서 <xref:System.Collections.IComparer.Compare%2A?displayProperty=fullName> 메서드를 구현해야 합니다. 이 때 `Sort(IComparer)` 메서드 오버로드가 호출되면 <xref:System.Windows.Forms.DataGridView>에서 <xref:System.Windows.Forms.DataGridViewRow> 개체를 입력으로 전달합니다.  이렇게 하면 열 값을 기반으로 올바른 행 정렬 순서를 계산할 수 있습니다.  
  
 `Sort(IComparer)` 메서드 오버로드는 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 및 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 속성을 설정하지 않으므로 정렬 문자를 표시하려면 항상 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName> 속성을 직접 설정해야 합니다.  
  
 `Sort(IComparer)` 메서드 오버로드 대신 <xref:System.Windows.Forms.DataGridView.SortCompare> 이벤트에 대한 처리기를 구현하여 사용자 지정 정렬을 제공할 수 있습니다.  자동 정렬이 구성된 열의 머리글을 클릭하거나 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드의 `Sort(DataGridViewColumn,ListSortDirection)` 오버로드를 호출하면 이 이벤트가 발생합니다.  이 이벤트는 컨트롤에 있는 각 쌍의 행에 대해 발생하므로 이러한 행의 올바른 순서를 계산할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성이 설정되어 있거나 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성 값이 `true`인 경우에는 <xref:System.Windows.Forms.DataGridView.SortCompare> 이벤트가 발생하지 않습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 데이터 정렬](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)