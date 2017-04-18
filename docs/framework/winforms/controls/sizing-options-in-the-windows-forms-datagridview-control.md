---
title: "Windows Forms DataGridView 컨트롤의 크기 조정 옵션 | Microsoft Docs"
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
  - "데이터 표, 열 크기 조정"
  - "데이터 표, 행 크기 조정"
  - "데이터 표, 크기 조정 옵션"
  - "DataGridView 컨트롤[Windows Forms], 열 크기 조정"
  - "DataGridView 컨트롤[Windows Forms], 행 크기 조정"
  - "DataGridView 컨트롤[Windows Forms], 크기 조정 옵션"
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Windows Forms DataGridView 컨트롤의 크기 조정 옵션
<xref:System.Windows.Forms.DataGridView> 행, 열 및 머리글의 크기는 여러 가지 동작으로 인해 변경될 수 있습니다.  다음 표에서는 이러한 동작을 보여 줍니다.  
  
|동작|설명|  
|--------|--------|  
|사용자 크기 조정|사용자는 행, 열 또는 머리글 구분선을 끌거나 두 번 클릭하여 크기를 조정할 수 있습니다.|  
|컨트롤 크기 조정|열 채우기 모드에서 컨트롤 너비가 바뀌면 열 너비도 바뀝니다. 예를 들어, 컨트롤이 부모 폼에 도킹되어 있고 사용자가 폼의 크기를 변경하면 컨트롤 너비가 바뀌면서 열 너비도 바뀝니다.|  
|셀 값 변경|내용 기반 자동 크기 조정 모드에서 새로운 표시 값에 맞게 크기가 바뀝니다.|  
|메서드 호출|프로그래밍 방식의 내용 기반 크기 조정을 사용하면 메서드가 호출될 때 셀 값에 따라 크기를 조정할 수 있습니다.|  
|속성 설정|특정 높이와 너비 값도 설정할 수 있습니다.|  
  
 기본적으로 사용자 크기 조정은 활성화되고 자동 크기 조정은 비활성화되며, 열보다 큰 셀 값은 잘립니다.  
  
 다음 표에서는 기본 동작을 조정하거나 특정 크기 조정 옵션을 사용하여 특정 효과를 적용하는 데 사용할 수 있는 시나리오를 보여 줍니다.  
  
|시나리오|구현|  
|----------|--------|  
|가로 스크롤 막대를 표시하지 않은 채로 컨트롤의 전체 너비를 차지하는 비교적 적은 수의 열에 비슷한 크기의 데이터를 표시하려면 열 채우기 모드를 사용합니다.|<xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>으로 설정합니다.|  
|다양한 크기의 표시 값과 함께 열 채우기 모드를 사용합니다.|<xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>으로 설정합니다.  열의 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 속성을 설정하거나 컨트롤에 데이터를 채운 후 컨트롤의 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> 메서드를 호출하여 상대 열 너비를 초기화합니다.|  
|다양한 중요도 값과 함께 열 채우기 모드를 사용합니다.|<xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>으로 설정합니다.  데이터의 일부를 항상 표시해야 하는 열에 대해 큰 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> 값을 설정하거나 특정 열에 채우기 모드 이외의 크기 조정 옵션을 사용합니다.|  
|컨트롤 배경을 표시하지 않으려면 열 채우기 모드를 사용합니다.|마지막 열의 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>로 설정하고 다른 열에는 다른 크기 조정 옵션을 사용합니다.  사용할 수 있는 공간을 다른 열에서 너무 많이 사용하고 있다면 마지막 열의 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> 속성을 설정합니다.|  
|아이콘 또는 ID 열과 같은 고정 너비 열을 표시합니다.|해당 열의 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>를 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>으로 설정하고 <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A>을 <xref:System.Windows.Forms.DataGridViewTriState>로 설정합니다.  <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> 속성을 설정하거나 컨트롤에 데이터를 채운 후 컨트롤의 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> 메서드를 호출하여 너비를 초기화합니다.|  
|내용이 잘리는 것을 방지하고 사용 공간을 최적화하려면 셀 내용이 바뀔 때마다 크기를 자동으로 조정합니다.|자동 크기 조정 속성을 내용 기반 크기 조정 모드를 나타내는 값으로 설정합니다.  대용량 데이터 작업을 수행할 때 성능 저하를 방지하려면 표시된 행만 계산하는 크기 조정 모드를 사용합니다.|  
|행 수가 많은 경우 성능 저하를 방지하려면 표시된 행에 있는 값에 맞게 크기를 조정합니다.|적절한 크기 조정 모드 열거형 값과 자동 또는 프로그래밍 방식의 크기 조정을 사용합니다.  스크롤하는 동안 새로 표시되는 행의 값에 맞게 크기를 조정하려면 <xref:System.Windows.Forms.DataGridView.Scroll> 이벤트 처리기의 크기 조정 메서드를 호출합니다.  표시된 행의 값만 새 크기를 결정하도록 사용자의 두 번 클릭 크기 조정을 사용자 지정하려면 <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> 또는 <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> 이벤트 처리기의 크기 조정 메서드를 호출합니다.|  
|성능 저하를 방지하거나 사용자 크기 조정을 활성화하려면 특정 시간에만 셀 내용에 맞게 크기를 조정합니다.|이벤트 처리기의 내용 기반 크기 조정 메서드를 호출합니다.  예를 들어, 바인딩 후 <xref:System.Windows.Forms.DataGridView.DataBindingComplete> 이벤트를 사용하여 크기를 초기화하고 <xref:System.Windows.Forms.DataGridView.CellValidated> 또는 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 이벤트를 처리하여 바인딩된 데이터 소스의 사용자 편집 또는 변경 내용이 보완되도록 크기를 조정합니다.|  
|여러 줄로 이루어진 셀 내용의 행 높이를 조정합니다.|열 너비가 텍스트 단락을 표시하기에 적합한지 확인하고 자동 또는 프로그래밍 방식의 내용 기반 행 크기 조정을 사용하여 높이를 조정합니다.  또한 <xref:System.Windows.Forms.DataGridViewTriState>의 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 셀 스타일 값을 사용하여 여러 줄 내용을 가진 셀이 표시되도록 합니다.<br /><br /> 일반적으로 자동 열 크기 조정 모드를 사용하여 열 너비를 유지하거나 행 높이를 조정하기 전에 열 너비를 특정 너비로 설정합니다.|  
  
## 마우스로 크기 조정  
 기본적으로 사용자는 셀 값을 기준으로 자동 크기 조정 모드를 사용하지 않는 행, 열 및 머리글의 크기를 조정할 수 있습니다.  사용자가 열 채우기 모드와 같은 그 밖의 모드를 사용하여 크기를 조정하지 못하도록 하려면 다음 <xref:System.Windows.Forms.DataGridView> 속성 중 하나 이상을 설정합니다.  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 행이나 열의 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성을 설정하여 개별 행이나 열의 크기를 조정하지 못하도록 할 수도 있습니다.  기본적으로 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성 값은 열의 경우 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> 속성 값을 기반으로 하고 행의 경우 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> 속성 값을 기반으로 합니다.  그러나 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>을 <xref:System.Windows.Forms.DataGridViewTriState> 또는 <xref:System.Windows.Forms.DataGridViewTriState>로 명시적으로 설정한 경우 지정된 값은 해당 행 또는 열에 대한 컨트롤 값을 재정의합니다.  <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A>을 <xref:System.Windows.Forms.DataGridViewTriState>으로 설정하여 상속을 복원합니다.  
  
 <xref:System.Windows.Forms.DataGridViewTriState>은 값 상속을 복원하기 때문에 행이나 열이 <xref:System.Windows.Forms.DataGridView> 컨트롤에 추가되지 않는 한 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성은 <xref:System.Windows.Forms.DataGridViewTriState> 값을 반환하지 않습니다.  행 또는 열의 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성 값이 상속되었는지 확인하려면 해당 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성을 확인합니다.  <xref:System.Windows.Forms.DataGridViewElement.State%2A> 값에 <xref:System.Windows.Forms.DataGridViewElementStates> 플래그가 들어 있으면 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성 값은 상속되지 않은 것입니다.  
  
## 자동 크기 조정  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에는 열 채우기 모드 및 내용 기반 자동 크기 조정이라는 두 종류의 자동 크기 조정이 있습니다.  
  
 열 채우기 모드를 사용하면 컨트롤에 표시되는 열이 컨트롤의 표시 영역의 너비를 채웁니다.  이 모드에 대한 자세한 내용은 [Windows Forms DataGridView 컨트롤의 열 채우기 모드](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)를 참조하십시오.  
  
 또한 셀 내용에 맞게 자동으로 크기가 조정되도록 행, 열 및 머리글을 구성할 수 있습니다.  이 경우 셀 내용이 바뀔 때마다 크기가 조정됩니다.  
  
> [!NOTE]
>  가상 모드를 사용하여 셀 값을 사용자 지정 데이터 캐시에 유지하는 경우에는 사용자가 셀 값을 편집할 때 자동 크기 조정이 발생하지만 <xref:System.Windows.Forms.DataGridView.CellValuePushed> 이벤트 처리기 외부에서 캐시된 값을 변경할 때는 자동 크기 조정이 발생하지 않습니다.  이 경우 <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> 메서드를 호출하여 컨트롤에서 셀 표시를 업데이트하고 현재 자동 크기 조정 모드를 적용합니다.  
  
 내용 기반 자동 크기 조정이 1차원에 대해서만 활성화되어 있고\(즉, 열과 행 중 하나에만 활성화되어 있고\) <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>도 활성화된 경우에는 다른 차원이 바뀔 때도 항상 크기 조정이 발생합니다.  예를 들어, 열은 제외하고 행에 대해서만 자동 크기 조정을 구성하고 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>를 활성화한 경우 사용자는 열 구분선을 끌어서 열 너비를 변경할 수 있으며, 이 경우 행 높이는 셀 내용이 모두 표시되도록 자동으로 조정됩니다.  
  
 행과 열 모두에 대해 내용 기반 자동 크기 조정을 구성하고 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>를 활성화한 경우 <xref:System.Windows.Forms.DataGridView> 컨트롤은 셀 내용이 바뀔 때마다 크기를 조정하고 이상적인 셀 높이\/너비 비율을 사용하여 새 크기를 계산합니다.  
  
 머리글과 행에 대한 크기 조정 모드와 컨트롤 값을 재정의하지 않는 열에 대한 크기 조정 모드를 구성하려면 다음 <xref:System.Windows.Forms.DataGridView> 속성 중 하나 이상을 설정합니다.  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 개별 열에 대해 컨트롤의 열 크기 조정 모드를 재정의하려면 열의 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> 이외의 값으로 설정합니다.  열의 크기 조정 모드는 실제로 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> 속성에 의해 결정됩니다.  이 속성 값은 컨트롤의 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 값이 상속된 경우 해당 값이 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>이 아니면 열의 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 속성 값을 기반으로 합니다.  
  
 대용량 데이터 작업을 수행할 경우에는 내용 기반 자동 크기 조정을 주의해서 사용합니다.  성능 저하를 방지하려면 컨트롤의 모든 행을 분석하기보다는 표시된 행만 기준으로 크기를 계산하는 자동 크기 조정 모드를 사용합니다.  최대의 성능을 위해서는 프로그래밍 방식의 크기 조정을 통해 새 데이터가 로드된 직후와 같은 특정 시간에 크기를 조정합니다.  
  
 내용 기반 자동 크기 조정 모드는 행이나 열의 <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> 속성 또는 컨트롤의 <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> 또는 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> 속성을 `false`로 설정하여 숨겨진 행, 열 또는 머리글에 영향을 주지 않습니다.  예를 들어, 큰 셀 값에 맞게 자동으로 크기가 조정된 후 숨겨진 열의 크기는 큰 셀 값을 가진 행이 삭제되더라도 바뀌지 않습니다.  자동 크기 조정은 표시가 변경될 때 발생하지 않기 때문에 열의 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 속성을 `true`로 다시 변경할 경우 현재 내용에 따라 열의 크기가 다시 계산되지 않습니다.  
  
 프로그래밍 방식의 내용 기반 크기 조정은 표시와 관계없이 행, 열 및 머리글에 영향을 미칩니다.  
  
## 프로그래밍 방식의 크기 조정  
 자동 크기 조정을 비활성화한 경우 다음과 같은 속성을 통해 행, 열 또는 머리글의 너비나 높이를 프로그래밍 방식으로 정확하게 설정할 수 있습니다.  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=fullName>  
  
 또한 다음과 같은 메서드를 사용하여 행, 열 및 머리글의 크기를 내용에 맞게 프로그래밍 방식으로 조정할 수 있습니다.  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 이러한 메서드는 행, 열 또는 머리글의 크기를 계속적으로 조정하도록 구성하지 않고 한 번만 조정합니다.  모든 셀 내용이 잘리지 않고 표시되도록 새 크기가 자동으로 계산됩니다.  그러나 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>의 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> 속성 값을 가진 열의 크기를 프로그래밍 방식으로 조정할 경우 계산된 내용 기반 너비를 기준으로 열의 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 속성 값이 비례적으로 조정되며 그런 다음 모든 열이 컨트롤의 사용 가능한 표시 영역을 채울 수 있도록 실제 열 너비가 이러한 새 비율에 따라 계산됩니다.  
  
 프로그래밍 방식의 크기 조정은 계속적인 크기 조정으로 인한 성능 저하를 방지하려는 경우에 유용합니다.  또한 사용자가 크기를 조정할 수 있는 행, 열 및 머리글의 초기 크기와 열 채우기 모드의 초기 크기를 제공하는 경우에 유용합니다.  
  
 일반적으로 프로그래밍 방식의 크기 조정 메서드는 특정한 때에 호출하게 됩니다.  예를 들어, 데이터를 로드한 직후 모든 열의 크기를 프로그래밍 방식으로 조정하거나 특정 셀 값을 수정한 후 특정 행의 크기를 프로그래밍 방식으로 조정할 수 있습니다.  
  
## 내용 기반 크기 조정 동작 사용자 지정  
 <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=fullName>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=fullName> 또는 <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=fullName> 메서드를 재정의하거나 파생된 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 protected 형식의 크기 조정 메서드 오버로드를 호출하여 파생된 <xref:System.Windows.Forms.DataGridView> 셀, 행 및 열 형식 작업을 수행할 경우 크기 조정 동작을 사용자 지정할 수 있습니다.  protected 형식의 크기 조정 메서드 오버로드는 균형 잡힌 셀을 만들기 위해 쌍으로 작동하여 이상적인 셀 높이\/너비 비율을 이룹니다.  예를 들어, <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> 메서드의 `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` 오버로드를 호출하고 <xref:System.Boolean> 매개 변수의 값으로 `false`를 전달하는 경우 이 오버로드는 행의 셀에 대한 이상적인 높이와 너비를 계산하지만 행 높이만 조정됩니다.  그런 다음 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> 메서드를 호출하여 열 너비를 계산된 이상적인 값으로 조정해야 합니다.  
  
## 내용 기반 크기 조정 옵션  
 크기 조정 속성 및 메서드에서 사용하는 열거형에는 내용 기반 크기 조정에 대해 비슷한 값이 있습니다.  이러한 값을 사용하여 기본 설정 크기를 계산하는 데 사용되는 셀을 제한할 수 있습니다.  모든 크기 조정 열거형에 대해 표시된 셀을 참조하는 이름을 가진 값은 표시된 행의 셀에 대해서만 계산을 수행합니다.  작업에 많은 행이 사용할 때는 행을 제외하여 성능 저하를 방지할 수 있습니다.  또한 머리글 셀 또는 머리글이 아닌 셀의 셀 값으로 계산을 제한할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>   
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>   
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>   
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>   
 [Windows Forms DataGridView 컨트롤의 열 및 행 크기 조정](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 열 채우기 모드](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤의 크기 조정 모드 설정](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)