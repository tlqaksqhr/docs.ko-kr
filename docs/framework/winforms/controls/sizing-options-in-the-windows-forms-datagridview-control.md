---
title: Windows Forms DataGridView 컨트롤의 크기 조정 옵션
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sizing
- data grids [Windows Forms], column sizing
- DataGridView control [Windows Forms], column sizing
- DataGridView control [Windows Forms], sizing options
- data grids [Windows Forms], row sizing
- data grids [Windows Forms], sizing options
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
ms.openlocfilehash: 6e3a7786970ef536da4ef7628cd33ae067ba90be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541756"
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 크기 조정 옵션
<xref:System.Windows.Forms.DataGridView> 행, 열 및 헤더에 여러 가지 동작의 결과로 크기를 변경할 수 있습니다. 다음 표에서 이러한 경우를 보여 줍니다.  
  
|항목|설명|  
|----------------|-----------------|  
|사용자 크기 조정|사용자가 끌거나 행, 열 또는 머리글 구분선을 두 번 클릭 하 여 크기를 조정할 수 있습니다.|  
|컨트롤 크기 조정|열 채우기 모드 열 너비가 변경 컨트롤 너비 바뀌면; 예를 들어 컨트롤은 부모 폼 및 사용자에 고정 된 경우 폼 크기가 조정 됩니다.|  
|셀 값 변경|크기는 콘텐츠 기반 자동 크기 조정 모드에서 새로운 표시 값에 맞게 변경 합니다.|  
|메서드 호출|프로그래밍 방식의 콘텐츠 기반 크기 조정 메서드 호출의 시간에 셀 값에 따라 편의적 크기를 조정할 수 있습니다.|  
|속성 설정|또한 특정 높이 및 너비 값을 설정할 수 있습니다.|  
  
 기본적으로 자동 크기 조정 하지 않는 경우, 사용자가 크기를 조정할 및 열 보다 큰 않은 셀 값은 잘립니다.  
  
 다음 표에서 기본 동작을 조정 하거나 특정 효과를 얻기 위해 특정 크기 조정 옵션을 사용 하려면 사용할 수 있는 시나리오를 보여 줍니다.  
  
|시나리오|구현|  
|--------------|--------------------|  
|비슷한 크기의 비교적 적은 수의 가로 스크롤 막대를 표시 하지 않고 컨트롤의 전체 너비를 차지 하는 열에는 데이터를 표시 하기 위한 열 채우기 모드를 사용 합니다.|<xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>으로 설정합니다.|  
|열 채우기 모드 사용 다양 한 크기의 값을 표시 합니다.|<xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>으로 설정합니다. 상대 열 너비 열을 설정 하 여 초기화 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 속성 컨트롤을 호출 하 여 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> 컨트롤을 데이터로 채운 후 메서드.|  
|다양 한 중요도 값을 가진 열 채우기 모드를 사용 합니다.|<xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>으로 설정합니다. 큰 설정 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> 값은 항상 데이터의 일부를 표시 하거나 이외의 크기 조정 옵션을 사용 해야 하는 열 채우기 모드 특정 열에 대 한 합니다.|  
|열 채우기 모드를 사용 하 여 컨트롤 배경을 표시 되지 않도록 합니다.|설정의 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 속성을 마지막으로 열의 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> 다른 크기 조정 옵션을 사용 하 여 다른 열에 대 한 합니다. 다른 열 너무 많은 사용 가능한 공간을 사용 하는 경우 설정의 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> 마지막 열의 속성입니다.|  
|예: 아이콘 또는 ID 열 고정 너비 열을 표시 합니다.|설정 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 를 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> 및 <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> 를 <xref:System.Windows.Forms.DataGridViewTriState.False> 열에 대 한 합니다. 너비를 설정 하 여 초기화 된 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> 속성 컨트롤을 호출 하 여 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> 컨트롤을 데이터로 채운 후 메서드.|  
|셀 내용이 잘리는 것을 방지 하 고 공간 사용을 최적화할 수 변경 될 때마다 자동으로 크기를 조정 합니다.|콘텐츠 기반 크기 조정 모드를 나타내는 값으로 자동 크기 조정 속성을 설정 합니다. 많은 양의 데이터를 작업할 때 성능 저하를 방지 하려면 표시 된 행을 계산 하는 크기 조정 모드를 사용 합니다.|  
|많은 행을 작업할 때 성능 저하를 방지 하려면 표시 된 행의 값에 맞게 크기 조정 합니다.|자동 또는 프로그래밍 방식의 크기 조정 된 적절 한 크기 조정 모드 열거형 값을 사용 합니다. 스크롤 하는 동안 새로 표시 된 행의 값에 맞게 크기를 조정 하려면 크기 조정 메서드를 호출할는 <xref:System.Windows.Forms.DataGridView.Scroll> 이벤트 처리기입니다. 사용자를 두 번 클릭에 맞게 크기 조정 값만 표시 된 행의 새로운 크기를 확인할 수 있도록 크기 조정의 메서드를 호출는 <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> 또는 <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> 이벤트 처리기입니다.|  
|성능 저하를 방지 하거나 사용자 크기 조정을 사용할 수 있도록 특정 시간에만 셀 내용에 맞게 크기 조정 합니다.|이벤트 처리기의 콘텐츠 기반 크기 조정 메서드를 호출 합니다. 예를 들어 사용는 <xref:System.Windows.Forms.DataGridView.DataBindingComplete> 바인딩 후 크기를 초기화 하 고 처리 하는 이벤트는 <xref:System.Windows.Forms.DataGridView.CellValidated> 또는 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 사용자 편집 또는 변경에 대 한 보정 하는 크기를 조정 하는 이벤트 바인딩된 데이터 소스에 합니다.|  
|여러 줄 셀 내용에 대 한 행 높이 조정 합니다.|열 너비 텍스트 단락을 표시 하는 것에 대 한 적합 한지 확인 하 고 콘텐츠 기반 자동 또는 프로그래밍 방식의 행 크기를 사용 하 여 높이를 조정 합니다. 또한 사용 하 여 콘텐츠가 여러 줄이 포함 된 셀은 표시를 확인 한 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 셀의 스타일 값 <xref:System.Windows.Forms.DataGridViewTriState.True>합니다.<br /><br /> 일반적으로 열 너비를 유지 관리 또는 행 높이 조정 하기 전에 특정 너비로 설정 하려면 열 자동 크기 조정 모드를 사용 합니다.|  
  
## <a name="resizing-with-the-mouse"></a>마우스로 크기 조정  
 기본적으로 행, 열 및 머리글 셀 값을 기반으로 하는 자동 크기 조정 모드를 사용 하지 않는 사용자를 조정할 수 있습니다. 열 채우기 모드와 같은 다른 모드와 크기를 조정 하지 못하게 하려면 다음 중 하나 이상을 설정 <xref:System.Windows.Forms.DataGridView> 속성:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 개별 행 이나 열을 설정 하 여 크기 조정에서 사용자가 방지할 수 있습니다 자신의 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성입니다. 기본적으로는 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성 값은 기반는 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> 열에 대 한 속성 값 및 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> 행에 대 한 속성 값입니다. 명시적으로 설정 하면 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 를 <xref:System.Windows.Forms.DataGridViewTriState.True> 또는 <xref:System.Windows.Forms.DataGridViewTriState.False>하지만 해당 행 이나 열에 대 한 컨트롤 값이 지정 된 값이 재정의 합니다. 설정 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 를 <xref:System.Windows.Forms.DataGridViewTriState.NotSet> 여 상속을 복원 합니다.  
  
 때문에 <xref:System.Windows.Forms.DataGridViewTriState.NotSet> 값 상속을 복원는 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성을 반환 하지 것입니다는 <xref:System.Windows.Forms.DataGridViewTriState.NotSet> 행 또는 열이 추가 되지 않는에 값을 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 확인 해야 하는 경우 여부는 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 행 또는 열 속성 값이 상속을 검사 해당 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성입니다. 경우는 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 값에 포함 됩니다는 <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> 플래그는 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성 값 상속 되지 않습니다.  
  
## <a name="automatic-sizing"></a>자동 크기 조정  
 자동 크기 조정의 두 종류가 <xref:System.Windows.Forms.DataGridView> 제어: 열 채우기 모드 및 콘텐츠 기반 자동 크기 조정 합니다.  
  
 열 채우기 모드를 컨트롤의 표시 영역 너비 채우기 컨트롤에서 표시 되는 열을 발생 합니다. 이 모드에 대 한 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 열 채우기 모드](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)합니다.  
  
 행, 열 및 머리글 셀 내용에 맞게 크기를 자동으로 조정 하도록 구성할 수 있습니다. 이 경우 크기 조정을 셀 내용이 변경 될 때마다 발생 합니다.  
  
> [!NOTE]
>  가상 모드를 사용 하 여 사용자 지정 데이터 캐시에 셀 값을 유지 하는 경우 자동 크기 조정 하면 사용자 편집 셀 값 외부의 캐시 된 값을 변경할 때 발생 하지 않습니다는 <xref:System.Windows.Forms.DataGridView.CellValuePushed> 이벤트 처리기입니다. 이 경우 호출 된 <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> 컨트롤을 셀 표시를 업데이트 하 고 현재 자동 크기 조정 모드를 적용 하려면 메서드.  
  
 콘텐츠 기반 자동 크기 조정 중 한 방향 으로만 사용할 수 있는 경우-하는 열 또는 열을이 아니라 행이 있고-및 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 설정 되 면 크기 조정에도 다른 차원의 변경 될 때마다 발생 이기도 합니다. 예를 들어 열이 아니라 행 자동 크기 조정에 대해 구성 된 경우 및 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 가 사용할 사용자의 열 너비를 변경 하려면 열 구분선을 끌 수 있으며 셀 내용을 모두 표시 되도록 행 높이 자동으로 조정 됩니다.  
  
 행과 콘텐츠 기반 자동 크기 조정에 대 한 열을 모두 구성 하는 경우 및 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 사용 되는 <xref:System.Windows.Forms.DataGridView> 셀 내용 변경 및 새 크기를 계산 하는 경우에 이상적인 셀 높이 너비의 비율을 사용 합니다 때마다 컨트롤 크기를 조정 합니다.  
  
 머리글 및 행에 대 한 및 컨트롤 값을 재정의 하지 않는 열에 대 한 크기 조정 모드를 구성 하려면 다음 중 하나 이상을 설정 <xref:System.Windows.Forms.DataGridView> 속성:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 을 재정의 하려면 개별 열에 대 한 컨트롤의 열 크기 조정 모드 설정 해당 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 속성 이외의 값을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>합니다. 열에 대 한 크기 조정 모드 실제로 따라 사용자가 해당 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> 속성입니다. 이 속성의 값은 열에 기반 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 속성 값이 값은 하지 않는 한 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>있으며이 경우 컨트롤의 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 값이 상속 합니다.  
  
 콘텐츠 기반 자동 크기 조정 주의 해 서 많은 양의 데이터를 작업할 때 사용 합니다. 성능 저하를 방지 하려면 컨트롤의 모든 행을 분석 하는 대신 표시 된 행에 따라서만 크기를 계산 하는 자동 크기 조정 모드를 사용 합니다. 최상의 성능을 위해 사용 하 여 프로그래밍 방식으로 크기 조정을 수 크기를 조정할 수 있도록 특정 시간에 같은 새 데이터 직후 로드 됩니다.  
  
 콘텐츠 기반 자동 크기 조정 모드 행, 열 또는 행 이나 열을 설정 하 여 숨겨진 헤더에 영향을 주지 않습니다 <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> 속성이 나 컨트롤 <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> 또는 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> 속성을 `false`합니다. 예를 들어 열 크기가 큰 셀 값에 맞게 자동으로 조정 후를 숨길 경우 숨겨진된 열 크기로 바뀌지 않습니다 큰 셀 값이 포함 된 행을 삭제 합니다. 표시 유형 변경 될 때 자동 크기 조정 발생 하지 않습니다는 열을 변경 하는 것 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 속성을 다시 `true` 는 현재 내용에 따라 크기 다시 계산 하도록 요구 하지 않습니다.  
  
 프로그래밍 방식의 콘텐츠 기반 크기 조정 행, 열 및 머리글 표시 여부에 관계 없이 영향을 줍니다.  
  
## <a name="programmatic-resizing"></a>프로그래밍 방식의 크기 조정  
 자동 크기 조정 비활성화 되 면 정확한 너비 또는 높이 행, 열 또는 헤더는 다음과 같은 속성의 프로그래밍 방식으로 설정할 수 있습니다.  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 또한 프로그래밍 방식으로 행, 열 및 헤더 다음 방법을 사용 하 여 내용에 맞게 조정할 수 있습니다.  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 이러한 메서드는 행, 열 또는 헤더를 한 번 구성 하지 않고 연속 크기 조정에 대 한 크기가 조정 됩니다. 새 크기 클리핑 없이 모든 셀 내용을 표시 하도록 자동으로 계산 됩니다. 그러나 가진 열을 프로그래밍 방식으로 조정 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> 속성 값이 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>, 콘텐츠 기반 계산된 된 너비는 그에 따라 열을 조정 사용 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 속성 값 및 너비는 실제로 열 모든 열은 컨트롤의 사용 가능한 표시 영역을 채울 수 있도록 이러한 새 비율에 따라 계산 합니다.  
  
 프로그래밍 방식의 크기 조정은 연속 크기 조정 된 성능 저하를 방지 하는 데 유용 합니다. 또한 열 채우기 모드와 사용자를 크기 조정 가능한 행, 열 및 헤더에 대 한 초기 크기를 제공 하는 것이 유용 합니다.  
  
 일반적으로 특정 시간에 프로그래밍 방식으로 크기 조정 메서드를 호출 합니다. 예를 들어 데이터를 로드 한 직후 모든 열을 프로그래밍 방식으로 조정 될 수 있습니다 또는 특정 셀 값이 수정 된 후 특정 행을 프로그래밍 방식으로 조정 될 수 있습니다.  
  
## <a name="customizing-content-based-sizing-behavior"></a>콘텐츠 기반 크기 조정 동작을 사용자 지정  
 파생을 작업할 때 크기 조정 동작을 사용자 지정할 수 있습니다 <xref:System.Windows.Forms.DataGridView> 재정의 하 여 셀, 행 및 열 형식은 <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>, 또는 <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> 메서드를 호출 하 여 파생 된 크기 조정 메서드 오버 로드 보호 되는 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다. 보호 되는 크기 조정 메서드 오버 로드는 이상적인 셀 높이 너비 비율을 이룹니다 셀을 만들기 위해 쌍으로 실행 되도록 디자인 되었습니다. 예를 들어, 호출 하는 경우는 `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` 오버 로드는 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> 메서드 및 값이 전달 `false` 에 대 한는 <xref:System.Boolean> 매개 변수는 행 높이 조정 하지만 이상적인 높이 너비는 행의 셀에 대 한 오버 로드를 계산 합니다 만 합니다. 다음 호출 해야 합니다는 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> 열 너비를 계산된 된 이상적인을 조정 하는 메서드.  
  
## <a name="content-based-sizing-options"></a>콘텐츠 기반 크기 조정 옵션  
 콘텐츠 기반 크기 조정에 대 한 유사한 값을 포함 하는 크기 조정 속성 및 메서드를 사용 하는 열거형입니다. 값이 있는 셀은 기본 설정된 크기를 계산 하는 데 사용 됩니다 제한할 수 있습니다. 모든 크기 조정 열거형에 대 한 이름이 표시 된 셀을 참조 하는 값을 표시 된 행의 셀에는 계산을 제한 합니다. 행은 제외 하는 것은 많은 행을 사용 하 여 작업할 때 성능 저하를 방지 하는 데 유용 합니다. 또한 헤더 또는 머리글이 아닌 셀의 셀 값으로 계산을 제한할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>  
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>  
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>  
 [Windows Forms DataGridView 컨트롤의 열 및 행 크기 조정](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 열 채우기 모드](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤의 크기 조정 모드 설정](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
