---
title: Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 91153df539871de571375d7bf6d49d712a0c43b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529810"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법
<xref:System.Windows.Forms.DataGridView> 컨트롤은 최대 확장성을 제공 하도록 설계 되었습니다. 많은 양의 데이터를 표시 해야 하는 경우 많은 양의 메모리를 사용 하거나 사용자 인터페이스 (UI)의 응답 속도 저하를 방지 하려면이 항목에 설명 된 지침을 따라야 합니다. 이 항목에서는 다음과 같은 문제를 설명합니다.  
  
-   셀 스타일을 효율적으로 사용  
  
-   바로 가기 메뉴를 효율적으로 사용  
  
-   자동 크기 조정의 효율적인 사용  
  
-   선택한 셀, 행 및 열 컬렉션의 효율적인 사용  
  
-   공유 행을 사용 하 여  
  
-   공유가 해제에서 행을 방지  
  
 특별 한 성능 요구 사항이 있는 경우 가상 모드 구현 하 고 사용자 고유의 데이터 관리 작업을 제공 해야 합니다. 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="using-cell-styles-efficiently"></a>셀 스타일을 효율적으로 사용  
 각 셀, 행 및 열에는 자체 스타일 정보를 가질 수 있습니다. 에 스타일 정보를 저장 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체입니다. 여러 개별 셀 스타일 개체를 만드는 <xref:System.Windows.Forms.DataGridView> 특히 많은 양의 데이터를 사용 하는 경우 요소 비효율적일 수 있습니다. 성능에 영향을 방지 하려면 다음 지침을 따르세요.  
  
-   개인에 대 한 셀 스타일 속성을 설정 하지 마십시오 <xref:System.Windows.Forms.DataGridViewCell> 또는 <xref:System.Windows.Forms.DataGridViewRow> 개체입니다. 여기에 의해 지정 된 row 개체는 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성입니다. 각각의 새 행의 행 템플릿에서 복제 하는 서식 파일의 셀 스타일 개체의 자체 복사본을 받게 됩니다. 최대 확장성을 위해에서 셀 스타일 속성이 설정 된 <xref:System.Windows.Forms.DataGridView> 수준입니다. 예를 들어 설정 된 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 속성 보다는 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> 속성입니다.  
  
-   기본 서식 이외의 서식을 지정 해야 하는 일부 셀을 사용 하 여 동일한 <xref:System.Windows.Forms.DataGridViewCellStyle> 의 셀, 행 또는 열 그룹에 걸쳐 인스턴스. 직접 형식의 속성을 설정 하지 마십시오 <xref:System.Windows.Forms.DataGridViewCellStyle> 개별 셀, 행 및 열에 있습니다. 셀 스타일 공유에 대 한 예제를 보려면 [하는 방법: Windows Forms DataGridView 컨트롤에 대 한 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)합니다. 셀 스타일을 처리 하 여 개별적으로 설정할 경우에 성능 저하를 방지할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트 처리기입니다. 예를 들어 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 사용자 지정 데이터 형식](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)합니다.  
  
-   셀의 스타일을 결정할 때 사용 된 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> 속성 보다는 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> 속성입니다. 에 액세스 하는 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성의 새 인스턴스를 만듭니다.는 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스 속성이 이미 사용 하지 않은 경우. 또한이 개체 일부 스타일 행, 열 또는 컨트롤에서 상속 된 경우 셀에 대 한 전체 스타일 정보를 포함 하지 수도 있습니다. 셀 스타일 상속 하는 방법에 대 한 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="using-shortcut-menus-efficiently"></a>바로 가기 메뉴를 효율적으로 사용  
 각 셀, 행 및 열에 바로 가기 메뉴를 가질 수 있습니다. 바로 가기 메뉴에는 <xref:System.Windows.Forms.DataGridView> 제어 표현 됩니다 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤입니다. 셀 스타일 개체와 마찬가지로 많은 개인에 대 한 바로 가기 메뉴 만들기 <xref:System.Windows.Forms.DataGridView> 요소 성능이 저하 됩니다. 이러한 성능 저하를 방지 하려면 다음 지침을 따르세요.  
  
-   개별 셀 및 행에 대 한 바로 가기 메뉴를 만들지 마십시오. 이 컨트롤에 새 행을 추가할 때 해당 바로 가기 메뉴와 함께 복제 되는 행 템플릿에 포함 됩니다. 최대 확장성을 위해만: 컨트롤을 사용 하 여 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 통해 전체 컨트롤에 대 한 단일 바로 가기 메뉴를 지정 합니다.  
  
-   여러 행 또는 셀에 대 한 여러 바로 가기 메뉴를 필요한 경우 처리는 <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> 또는 <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> 이벤트입니다. 이러한 이벤트를 사용 하면 바로 가기 메뉴 개체를 관리할 수를 직접 성능을 조정할 수 있습니다.  
  
## <a name="using-automatic-resizing-efficiently"></a>자동 크기 조정의 효율적인 사용  
 행, 열 및 헤더 자동으로 크기를 조정할 수 셀 내용 변경으로 셀의 전체 내용을 클리핑 없이 표시 되도록 합니다. 크기 조정 모드를 변경 크기를 조정할 수도 행, 열 및 헤더입니다. 올바른 크기를 결정 하는 <xref:System.Windows.Forms.DataGridView> 컨트롤 수용 해야 하는 각 셀의 값을 검사 해야 합니다. 큰 데이터 집합을 사용이 분석 발생 자동 크기 조정 컨트롤의 성능을 저하 될 수 있습니다. 성능 저하를 방지 하려면 다음 지침을 따르세요.  
  
-   자동 크기 조정에 사용 하지 않도록는 <xref:System.Windows.Forms.DataGridView> 대량의 행 집합으로 제어 합니다. 자동 크기 조정, 표시 된 행에 따라 크기 조정에만 사용 않으면 합니다. 가상 모드에 표시 된 행만을 사용 합니다.  
  
    -   행과 열을 사용 하 여는 `DisplayedCells` 또는 `DisplayedCellsExceptHeaders` 필드는 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>, 및 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> 열거형입니다.  
  
    -   행 머리글에 대 한 사용는 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> 또는 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> 필드는 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> 열거형입니다.  
  
-   최대 확장성을 위해 자동 크기 조정을 해제 하 고 프로그래밍 방식의 크기를 사용 합니다.  
  
 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>선택한 셀, 행 및 열 컬렉션의 효율적인 사용  
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 큰 선택 범위 컬렉션을 효율적으로 수행 하지 않습니다. <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 및 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 컬렉션 수 또한 비효율적일 수 있지만에 일반적인 셀 수보다 적은 행 수 있기 때문에 <xref:System.Windows.Forms.DataGridView> 컨트롤과 행 보다 더 적은 열이 많습니다. 이러한 컬렉션을 사용할 때 성능 저하를 방지 하려면 다음 지침을 따르세요.  
  
-   확인 하려면 있는지 여부를 모든 셀에는 <xref:System.Windows.Forms.DataGridView> 의 내용에 액세스 하기 전에 선택한는 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 컬렉션의 반환 값을 확인는 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 메서드. 그러나 Note,이 메서드가 행이 공유를 발생할 수 있습니다. 자세한 내용은 다음 단원을 참조하세요.  
  
-   사용 하지 않도록는 <xref:System.Collections.ICollection.Count%2A> 의 속성은 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> 선택 된 셀의 수를 결정 합니다. 대신를 사용 하 여는 <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> 메서드와 전달은 <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> 값입니다. 마찬가지로 사용 하 여는 <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> 메서드 선택 된 행 및 열 컬렉션에 액세스 하는 것이 아니라 선택 된 요소 수를 결정 합니다.  
  
-   셀 기반 선택 모드를 하지 마십시오. 대신, 설정 된 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>합니다.  
  
## <a name="using-shared-rows"></a>행 공유 사용  
 효율적인 메모리 사용에 이루어집니다는 <xref:System.Windows.Forms.DataGridView> 공유 행을 통해 제어 합니다. 행의 인스턴스를 공유 하 여 최대한의 모양 및 동작에 대 한 많은 정보를 공유 합니다는 <xref:System.Windows.Forms.DataGridViewRow> 클래스입니다.  
  
 행 인스턴스를 공유 메모리를 저장 하는 동안 행 쉽게 공유 될 수 있습니다. 예를 들어 셀와 직접 사용자 상호 작용, 때마다 해당 행은 공유 해제 됩니다. 이 방지할 수 있으므로 매우 많은 양의 데이터를 사용 하는 경우에와 사용자가 프로그램을 실행할 때마다 데이터의 상대적으로 작은 일부 상호 작용 하는 경우에이 항목의 지침은 유용 합니다.  
  
 행을 공유할 수 없는에 바인딩되지 않은 <xref:System.Windows.Forms.DataGridView> 값을 포함 하는 셀의 있는 경우를 제어 합니다. 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤 외부 데이터 원본에 바인딩되어 있거나 가상 모드를 구현 하 고 사용자 지정 데이터 소스를 제공 하는 경우 셀 값은 행을 공유할 수 있도록 하는 셀 개체가 아닌 컨트롤 외부 저장 됩니다.  
  
 Row 개체 상태의 행 및 셀이 들어 있는 열의 상태에서 모든 셀의 상태를 확인할 수 있습니다 하는 경우에 공유할 수 있습니다. 수 더 이상 해당 행과 열의 상태에서 확인할 수 있도록 셀의 상태를 변경한 경우에 행을 공유할 수 없습니다.  
  
 예를 들어 다음과 같은 상황에 행을 공유할 수 없습니다.  
  
-   행 선택된 된 열에 있지 않은 단일 선택 된 셀을 포함 합니다.  
  
-   행에 있는 셀의 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 또는 <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> 속성 집합입니다.  
  
-   이 행에는 <xref:System.Windows.Forms.DataGridViewComboBoxCell> 와 해당 <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> 속성 집합입니다.  
  
 바인딩된 모드나 가상 모드에 제공할 수 있습니다 도구 설명 및 바로 가기 메뉴 개별 셀에 대 한 처리는 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> 및 <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> 이벤트입니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 행에 추가 될 때마다 공유 행을 사용 하도록 자동으로 시도 <xref:System.Windows.Forms.DataGridViewRowCollection>합니다. 다음 지침을 사용 하 여 행이 공유 되도록 합니다.  
  
-   호출 하지는 `Add(Object[])` 오버 로드는 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 메서드 및 `Insert(Object[])` 오버 로드는 <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> 의 메서드는 <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 컬렉션입니다. 이러한 오버 로드는 자동으로 공유 되지 않는 행을 만듭니다.  
  
-   수 있도록에 지정 된 행은 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> 다음과 같은 경우에 속성을 공유할 수 있습니다.  
  
    -   호출할 때는 `Add()` 또는 `Add(Int32)` 오버 로드는 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 메서드 또는 `Insert(Int32,Int32)` 오버 로드는 <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> 의 메서드는 <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 컬렉션입니다.  
  
    -   값을 변경 하는 경우는 <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> 속성입니다.  
  
    -   설정할 때의 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> 속성입니다.  
  
-   수 있도록 지정 된 행의 `indexSource` 를 호출할 때 매개 변수를 공유할 수 있습니다는 <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>, 및 <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> 의 메서드는 <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 컬렉션입니다.  
  
-   호출할 때 지정 된 행 또는 행 수 공유 해야는 `Add(DataGridViewRow)` 오버 로드는 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 메서드를는 <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> 메서드를는 `Insert(Int32,DataGridViewRow)` 오버 로드는 <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> 메서드, 및 <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> 메서드는 의<xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>컬렉션입니다.  
  
 행을 공유할지 여부를 확인 하려면는 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> 행 개체를 검색 한 다음 개체의 메서드 <xref:System.Windows.Forms.DataGridViewBand.Index%2A> 속성입니다. 공유 행은 항상 한 <xref:System.Windows.Forms.DataGridViewBand.Index%2A> 속성 값이-1입니다.  
  
## <a name="preventing-rows-from-becoming-unshared"></a>공유가 해제에서 행을 방지  
 공유 행을 코드 또는 사용자 작업의 결과로 공유가 해제 될 수 있습니다. 성능에 영향을 방지 하려면 되는 행이 공유 하지 않아야 합니다. 응용 프로그램 개발 중 처리할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.RowUnshared> 행이 공유를 결정 하는 이벤트입니다. 행 공유 문제를 디버깅할 때 유용 합니다.  
  
 행의 공유 해제 되지 않도록 하려면 다음 지침을 따르세요.  
  
-   인덱싱하지 마십시오는 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션 또는을 사용 하 여 반복 하는 `foreach` 루프입니다. 일반적으로 않아도 됩니다 행에 직접 액세스할 수 있습니다. <xref:System.Windows.Forms.DataGridView> 행에서 작동 하는 메서드 행 인스턴스가 아닌 행 인덱스 인수 변수를 사용 합니다. 또한 행 관련 이벤트에 대 한 처리기 공유가 하지 않고 행을 조작 하는 데 사용할 수 있는 행의 속성을 가진 이벤트 인수 개체를 표시 합니다.  
  
-   사용 하 여 행 개체에 액세스 해야 할 경우는 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> 메서드와 행의 실제 인덱스를 전달 합니다. 그러나 Note,이 메서드를 통해 검색 하는 공유 행 개체를 수정 합니다.이 개체를 공유 하는 모든 행 수정 합니다. 하지만 새 레코드에 대 한 행와 공유 되지 않습니다 다른 행 다른 행을 수정 하는 경우 영향 수 있도록 합니다. Note 또한 공유 행으로 표시 하는 행 마다 서로 다른 바로 가기 메뉴를 있을 수 있습니다. 해당 바로 가기 메뉴는 공유 행 인스턴스에서를 검색 하려면 사용 된 <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> 메서드와 행의 실제 인덱스를 전달 합니다. 공유 행의에 액세스 하면 <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> 속성 대신는-1의 공유 행 인덱스를 사용 하 고 해당 바로 가기 메뉴를 검색 하지 것입니다.  
  
-   인덱싱하지 마십시오는 <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> 컬렉션입니다. 이 새 인스턴스화 공유 부모 행의 셀에 직접 액세스 하면 <xref:System.Windows.Forms.DataGridViewRow>합니다. 셀 관련 이벤트에 대 한 처리기는 행이 공유 발생 하지 않고 셀을 조작 하는 데 사용할 수 있는 셀 속성을 가진 이벤트 인수 개체를 받습니다. 사용할 수도 있습니다는 <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> 속성을 셀에 직접 액세스 하지 않고 현재 셀의 행 및 열 인덱스를 검색 합니다.  
  
-   셀 기반 선택 모드를 하지 마십시오. 이러한 모드를 사용 하면 행이 공유 합니다. 대신, 설정 된 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>합니다.  
  
-   처리 하지 않습니다는 <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> 이벤트입니다. 이러한 이벤트로 인해 발생할 행이 공유 합니다. 또한 호출 하지 마십시오는 <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> 이러한 이벤트를 발생 하는 메서드.  
  
-   에 액세스 하지 않는 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> 컬렉션 때는 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 속성 값은 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>, 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>합니다. 이렇게 하면 선택 된 모든 행이 공유 합니다.  
  
-   호출 하지 마십시오는 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> 메서드. 이 메서드는 행이 공유를 발생할 수 있습니다.  
  
-   호출 하지 마십시오는 <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> 메서드 때는 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 속성 값은 <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>합니다. 이 경우 모든 행이 공유 합니다.  
  
-   설정 하지 않으면는 <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> 또는 <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> 셀 속성 `false` 해당 열에서 해당 속성 설정 된 경우 `true`합니다. 이 경우 모든 행이 공유 합니다.  
  
-   에 액세스 하지 않는 <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> 속성입니다. 이 경우 모든 행이 공유 합니다.  
  
-   호출 하지 마십시오는 `Sort(IComparer)` 오버 로드는 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드. 사용자 지정 비교자를 사용 하 여 정렬 하면 모든 행이 공유 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 [Windows Forms DataGridView 컨트롤의 성능 조정](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 가상 모드](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)
