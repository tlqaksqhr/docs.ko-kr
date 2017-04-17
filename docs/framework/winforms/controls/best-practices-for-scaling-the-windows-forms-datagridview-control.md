---
title: "Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "유용한 정보, DataGridView 컨트롤"
  - "데이터 표, 유용한 정보"
  - "DataGridView 컨트롤[Windows Forms], 유용한 정보"
  - "DataGridView 컨트롤[Windows Forms], 행 공유"
  - "DataGridView 컨트롤[Windows Forms], 배율"
  - "DataGridView 컨트롤[Windows Forms], 공유 행"
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법
<xref:System.Windows.Forms.DataGridView> 컨트롤은 최대의 확장성을 제공하도록 디자인되었습니다.  대용량 데이터를 표시해야 하는 경우 많은 양의 메모리를 낭비하지 않고 UI\(사용자 인터페이스\)의 응답 기능을 저하시키지 않으려면 이 항목에서 설명하는 지침을 따라야 합니다.  이 항목에서는 다음 문제에 대해 설명합니다.  
  
-   셀 스타일의 효율적인 사용  
  
-   바로 가기 메뉴의 효율적인 사용  
  
-   자동 크기 조정의 효율적인 사용  
  
-   선택한 셀, 행 및 열 컬렉션의 효율적인 사용  
  
-   공유 행 사용  
  
-   행의 공유 해제 방지  
  
 성능이 특별히 중요한 경우에는 가상 모드를 구현하여 고유한 데이터 관리 작업을 제공할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)를 참조하십시오.  
  
## 셀 스타일의 효율적인 사용  
 각각의 셀, 행 및 열은 고유한 스타일 정보를 가질 수 있습니다.  스타일 정보는 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체에 저장됩니다.  수많은 개별 <xref:System.Windows.Forms.DataGridView> 요소에 대해 셀 스타일 개체를 만드는 것은 비효율적이며 특히 대용량 데이터 작업을 수행하는 경우에는 더욱 비효율적입니다.  성능에 영향을 미치지 않으려면 다음 지침을 따르십시오.  
  
-   개별 <xref:System.Windows.Forms.DataGridViewCell> 또는 <xref:System.Windows.Forms.DataGridViewRow> 개체에 대해 셀 스타일 속성을 설정하지 마십시오.  여기에는 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성에 지정된 행 개체도 포함됩니다.  행 템플릿에서 복제된 각각의 새 행은 템플릿의 셀 스타일 개체의 고유한 사본을 받습니다.  최대의 확장성을 위해 <xref:System.Windows.Forms.DataGridView> 수준에서 셀 스타일 속성을 설정합니다.  예를 들어, <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName> 속성보다는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> 속성을 설정합니다.  
  
-   일부 셀에 기본 서식 이외의 서식을 지정해야 하는 경우에는 셀, 행 또는 열 그룹 전체에 같은 <xref:System.Windows.Forms.DataGridViewCellStyle> 인스턴스를 사용합니다.  개별 셀, 행 및 열에 <xref:System.Windows.Forms.DataGridViewCellStyle> 형식의 속성을 직접 설정하지 마십시오.  셀 스타일 공유에 대한 예제를 보려면 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)을 참조하십시오.  <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트 처리기를 처리하여 셀 스타일을 개별적으로 설정하는 경우에도 성능 저하를 방지할 수 있습니다.  예제를 보려면 [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
-   셀의 스타일을 결정할 경우에는 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName> 속성보다는 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=fullName> 속성을 사용합니다.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성에 액세스하면 속성이 아직 사용되지 않은 경우 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스의 새 인스턴스가 만들어집니다.  또한 이 개체에는 일부 스타일이 행, 열 또는 컨트롤에서 상속된 경우 셀에 대한 전체 스타일 정보가 포함되지 않을 수 있습니다.  셀 스타일 상속에 대한 자세한 내용은 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 바로 가기 메뉴의 효율적인 사용  
 각각의 셀, 행 및 열은 고유한 바로 가기 메뉴를 가질 수 있습니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤의 바로 가기 메뉴는 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤로 나타냅니다.  셀 스타일 개체와 마찬가지로 많은 개별 <xref:System.Windows.Forms.DataGridView> 요소에 대해 바로 가기 메뉴를 만들면 성능이 저하됩니다.  이러한 성능 저하를 막으려면 다음 지침을 따르십시오.  
  
-   개별 셀 및 행에 대해 바로 가기 메뉴를 만들지 마십시오.  여기에는 새 행을 컨트롤에 추가할 때 바로 가기 메뉴와 함께 복제되는 행 템플릿도 포함됩니다.  최대의 확장성을 위해 컨트롤의 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성만 사용하여 전체 컨트롤에 대해 단일 바로 가기 메뉴를 지정합니다.  
  
-   여러 개의 행 또는 셀에 대해 여러 개의 바로 가기 메뉴가 필요한 경우에는 <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> 또는 <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> 이벤트를 처리합니다.  이러한 이벤트를 사용하면 바로 가기 메뉴 개체를 직접 관리하여 성능을 조정할 수 있습니다.  
  
## 자동 크기 조정의 효율적인 사용  
 행, 열 및 머리글의 크기는 셀 내용이 바뀔 때 셀의 내용이 잘리지 않고 모두 표시되도록 자동으로 조정될 수 있습니다.  또한 크기 조정 모드를 변경하여 행, 열 및 머리글의 크기를 조정할 수 있습니다.  정확한 크기를 결정하기 위해 <xref:System.Windows.Forms.DataGridView> 컨트롤은 조정할 각 셀의 값을 확인해야 합니다.  대용량 데이터 집합을 처리하는 경우 자동 크기 조정이 발생할 때 이 분석으로 인해 컨트롤의 성능이 저하될 수 있습니다.  이러한 성능 저하를 막으려면 다음 지침을 따르십시오.  
  
-   많은 행이 포함된 <xref:System.Windows.Forms.DataGridView> 컨트롤에는 자동 크기 조정을 사용하지 마십시오.  자동 크기 조정을 사용하는 경우에는 표시된 행만 기준으로 크기를 조정합니다.  가상 모드에서도 표시된 행만 사용합니다.  
  
    -   행과 열의 경우 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode> 및 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> 열거형의 `DisplayedCells` 또는 `DisplayedCellsExceptHeaders` 필드를 사용합니다.  
  
    -   열 머리글의 경우 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> 열거형의 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> 또는 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> 필드를 사용합니다.  
  
-   최대의 확장성을 위해 자동 크기 조정을 해제하고 프로그래밍 방식의 크기 조정을 사용합니다.  
  
 자세한 내용은 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 선택한 셀, 행 및 열 컬렉션의 효율적인 사용  
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 컬렉션은 선택 항목이 많은 경우 효율적으로 수행되지 않습니다.  <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 및 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 컬렉션도 일반적인 <xref:System.Windows.Forms.DataGridView> 컨트롤의 셀보다 행의 수가 적고, 행보다 열의 수가 적기 때문에 정도는 덜하지만 역시 효율적으로 수행되지 않을 수 있습니다.  이러한 컬렉션 작업을 수행할 때 성능 저하를 막으려면 다음 지침을 따르십시오.  
  
-   <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 컬렉션의 내용에 액세스하기 전에 <xref:System.Windows.Forms.DataGridView>의 모든 셀이 선택되었는지 확인하려면 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 메서드의 반환 값을 확인합니다.  그러나 이 메서드는 행을 공유되지 않은 상태로 만들 수 있기 때문에 주의해야 합니다.  자세한 내용은 다음 단원을 참조하십시오.  
  
-   <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=fullName>의 <xref:System.Collections.ICollection.Count%2A> 속성을 사용하여 선택된 행 수를 확인하지 마십시오.  대신 <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=fullName> 메서드를 사용하여 <xref:System.Windows.Forms.DataGridViewElementStates?displayProperty=fullName> 값을 전달합니다.  마찬가지로 선택된 행 및 열 컬렉션에 액세스하는 대신 <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=fullName> 및 <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=fullName> 메서드를 사용하여 선택된 요소의 수를 확인합니다.  
  
-   셀 기반 선택 모드를 사용하지 마십시오.  대신 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName>로 설정합니다.  
  
## 공유 행 사용  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에서는 공유 행을 통해 메모리를 효율적으로 사용할 수 있습니다.  행은 <xref:System.Windows.Forms.DataGridViewRow> 클래스의 인스턴스를 공유하여 모양과 동작에 대한 정보를 최대한 공유합니다.  
  
 행 인스턴스를 공유하면 메모리를 절약할 수 있지만 행의 공유는 쉽게 해제될 수 있습니다.  예를 들어, 사용자가 셀과 직접 상호 작용할 때마다 해당 행의 공유는 해제됩니다.  이러한 행의 공유 해제는 피할 수 없으므로, 이 항목의 지침은 매우 많은 양의 데이터 작업을 수행하는 경우 및 프로그램을 실행할 때마다 비교적 적은 부분의 데이터를 대상으로 사용자의 상호 작용이 이루어지는 경우에만 유용합니다.  
  
 바인딩되지 않은 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 셀에 값이 포함된 경우에는 행을 공유할 수 없습니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤이 외부 데이터 소스에 바인딩되었거나 가상 모드를 구현하여 고유한 데이터 소스를 제공하는 경우 셀 값은 셀 개체가 아닌 컨트롤의 외부에 저장되기 때문에 행을 공유할 수 있습니다.  
  
 행 개체는 행의 모든 셀 상태를 셀이 포함된 행의 상태와 열의 상태에서 확인할 수 있는 경우에만 공유할 수 있습니다.  셀의 상태를 변경하면 셀의 상태를 행 및 열의 상태에서 더 이상 확인할 수 없기 때문에 해당 행을 공유할 수 없습니다.  
  
 예를 들어, 다음과 같은 상황에서는 행을 공유할 수 없습니다.  
  
-   선택한 열에 없는 단일 선택 셀이 행에 포함된 경우  
  
-   <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 또는 <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> 속성이 설정된 셀이 행에 포함된 경우  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> 속성이 설정된 <xref:System.Windows.Forms.DataGridViewComboBoxCell>이 행에 포함된 경우  
  
 바인딩된 모드 또는 가상 모드에서 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> 및 <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> 이벤트를 처리하여 개별 셀에 대한 도구 설명 및 바로 가기 메뉴를 제공할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 행이 <xref:System.Windows.Forms.DataGridViewRowCollection>에 추가될 때마다 자동으로 공유 행을 사용하려고 시도합니다.  행이 공유되도록 하려면 다음 지침을 따르십시오.  
  
-   <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName> 컬렉션의 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 메서드의 `Add(Object[])` 오버로드와 <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> 메서드의 `Insert(Object[])` 오버로드를 호출하지 마십시오.  이러한 오버로드는 행의 공유를 자동으로 해제합니다.  
  
-   다음과 같은 경우에 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName> 속성에 지정된 행이 공유될 수 있는지 확인합니다.  
  
    -   <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName> 컬렉션의 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 메서드의 `Add()` 또는 `Add(Int32)` 오버로드 또는 <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> 메서드의 `Insert(Int32,Int32)` 오버로드를 호출하는 경우  
  
    -   <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=fullName> 속성 값을 증가시키는 경우  
  
    -   <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName> 속성을 설정하는 경우  
  
-   `indexSource` 매개 변수로 지정된 행이 <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName> 컬렉션의 <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A> 및 <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> 메서드를 호출할 때 공유될 수 있는지 확인합니다.  
  
-   <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName> 컬렉션의 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 메서드의 `Add(DataGridViewRow)` 오버로드, <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> 메서드, <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> 메서드의 `Insert(Int32,DataGridViewRow)` 오버로드 및 <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> 메서드를 호출할 때 지정된 행을 공유할 수 있는지 확인합니다.  
  
 행이 공유되었는지 확인하려면 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=fullName> 메서드를 사용하여 행 개체를 검색한 다음 개체의 <xref:System.Windows.Forms.DataGridViewBand.Index%2A> 속성을 확인합니다.  공유 행의 <xref:System.Windows.Forms.DataGridViewBand.Index%2A> 속성 값은 항상 –1입니다.  
  
## 행의 공유 해제 방지  
 공유 행은 코드 또는 사용자 작업의 결과로 공유가 해제될 수 있습니다.  성능 저하를 방지하려면 행의 공유가 해제되지 않도록 해야 합니다.  응용 프로그램을 개발하는 동안 <xref:System.Windows.Forms.DataGridView.RowUnshared> 이벤트를 처리하여 행의 공유가 해제되었는지 확인할 수 있습니다.  이 방법은 행 공유 문제를 디버깅할 때 유용합니다.  
  
 행의 공유가 해제되지 않도록 하려면 다음 지침을 따르십시오.  
  
-   <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션을 인덱싱하거나 `foreach` 루프를 사용하여 컬렉션을 반복하지 마십시오.  대개는 행에 직접 액세스할 필요가 없습니다.  행에 대해 실행되는 <xref:System.Windows.Forms.DataGridView> 메서드는 행 인스턴스보다는 행 인덱스 인수를 사용합니다.  또한 행 관련 이벤트 처리기는 행의 공유를 해제하지 않고 행을 조작하는 데 사용할 수 있는 행 속성을 가진 이벤트 인수 개체를 받습니다.  
  
-   행 개체에 액세스해야 하는 경우에는 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=fullName> 메서드를 사용하여 행의 실제 인덱스를 전달합니다.  그러나 이 메서드를 통해 검색된 공유 행 개체를 수정하면 이 개체를 공유하는 모든 행이 수정됩니다.  그러나 새 레코드 행은 다른 행과 공유되지 않기 때문에 다른 행을 수정할 때 이 행은 영향을 받지 않습니다.  공유 행이 나타내는 여러 행은 서로 다른 바로 가기 메뉴를 가질 수 있습니다.  공유 행 인스턴스에서 올바른 바로 가기 메뉴를 검색하려면 <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> 메서드를 사용하여 행의 실제 인덱스를 전달합니다.  대신 공유 행의 <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> 속성에 액세스하는 경우 이 속성은 \-1이라는 공유 행 인덱스를 사용하기 때문에 올바른 바로 가기 메뉴가 검색되지 않습니다.  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=fullName> 컬렉션을 인덱싱하지 마십시오.  셀에 직접 액세스하면 부모 행의 공유가 해제되고 새 <xref:System.Windows.Forms.DataGridViewRow>가 인스턴스화됩니다.  셀 관련 이벤트 처리기는 행의 공유를 해제하지 않고 셀을 조작하는 데 사용할 수 있는 셀 속성을 가진 이벤트 인수 개체를 받습니다.  또한 <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> 속성을 사용하여 셀에 직접 액세스하지 않고도 현재 셀의 행 및 열 인덱스를 검색할 수 있습니다.  
  
-   셀 기반 선택 모드를 사용하지 마십시오.  이러한 모드를 사용하면 행의 공유가 해제됩니다.  대신 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName>로 설정합니다.  
  
-   <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=fullName> 또는 <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=fullName> 이벤트를 처리하지 마십시오.  이러한 이벤트를 처리하면 행의 공유가 해제됩니다.  또한 이러한 이벤트를 발생시키는 <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=fullName> 또는 <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=fullName> 메서드를 호출하지 마십시오.  
  
-   <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> 속성 값이 <xref:System.Windows.Forms.DataGridViewSelectionMode>, <xref:System.Windows.Forms.DataGridViewSelectionMode>, <xref:System.Windows.Forms.DataGridViewSelectionMode> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode>인 경우 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=fullName> 컬렉션에 액세스하지 마십시오.  이 경우 선택된 모든 행의 공유가 해제됩니다.  
  
-   <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=fullName> 메서드를 호출하지 마십시오.  이 메서드를 호출하면 선택된 행의 공유가 해제됩니다.  
  
-   <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> 속성 값이 <xref:System.Windows.Forms.DataGridViewSelectionMode>인 경우 <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=fullName> 메서드를 호출하지 마십시오.  이 경우 모든 행의 공유가 해제됩니다.  
  
-   열의 해당 속성이 `true`로 설정된 경우 셀의 <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> 또는 <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> 속성을 `false`로 설정하지 마십시오.  이 경우 모든 행의 공유가 해제됩니다.  
  
-   <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=fullName> 속성에 액세스하지 마십시오.  이 경우 모든 행의 공유가 해제됩니다.  
  
-   <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드의 `Sort(IComparer)` 오버로드를 호출하지 마십시오.  사용자 지정 비교자를 사용하여 정렬하는 경우 모든 행의 공유가 해제됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 [Windows Forms DataGridView 컨트롤의 성능 조정](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 가상 모드](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)