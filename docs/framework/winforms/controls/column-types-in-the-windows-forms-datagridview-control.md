---
title: Windows Forms DataGridView 컨트롤의 열 형식
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: 6630323b66265f478151ec80ab8b225c0b653917
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530005"
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 열 형식
<xref:System.Windows.Forms.DataGridView> 컨트롤 형식을 사용 하 여 여러 열 해당 정보를 표시 하 고 사용자가 정보를 수정 하거나 추가할 수 있도록 합니다.  
  
 바인딩하는 경우는 <xref:System.Windows.Forms.DataGridView> 제어 하 고 설정의 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> 속성을 `true`, 열에 바인딩된 데이터 소스가 포함 된 데이터 형식에 적합 한 기본 열 형식을 사용 하 여 자동으로 생성 됩니다.  
  
 모든 열 클래스의 인스턴스를 직접 만들 수 있고에서 반환 된 컬렉션에 추가 하면는 <xref:System.Windows.Forms.DataGridView.Columns%2A> 속성입니다. 바인딩되지 않은 열으로 사용 하기 위해 이러한 인스턴스를 만들거나 수동으로 바인딩할 수 있습니다. 직접 바인딩한 열은 다른 형식의 열이 있는 한 종류의 자동으로 생성 되는 열을 바꿀 때 예를 들어 유용 합니다.  
  
 다음 표에서 설명에서 사용 하기 위해 사용할 수 있는 다양 한 열 클래스는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
|클래스|설명|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|텍스트 기반 값과 함께 사용 합니다. 숫자와 문자열에 바인딩할 때 자동으로 생성 합니다.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|함께 사용할 <xref:System.Boolean> 및 <xref:System.Windows.Forms.CheckState> 값입니다. 이러한 형식의 값에 바인딩할 때 자동으로 생성 합니다.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|이미지를 표시 하는 데 사용 합니다. 바이트 배열에 바인딩할 때 자동으로 생성 <xref:System.Drawing.Image> 개체 또는 <xref:System.Drawing.Icon> 개체입니다.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|셀의 단추를 표시 하는 데 사용 합니다. 바인딩할 때 자동으로 생성 합니다. 일반적으로 바인딩되지 않은 열으로 사용 합니다.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|셀에서 드롭 다운 목록을 표시 하는 데 사용 합니다. 바인딩할 때 자동으로 생성 합니다. 일반적으로 데이터 바인딩된 수동으로 합니다.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|셀에 대 한 링크를 표시 하는 데 사용 합니다. 바인딩할 때 자동으로 생성 합니다. 일반적으로 데이터 바인딩된 수동으로 합니다.|  
|사용자 지정 열 형식|상속 하 여 고유한 열 클래스를 만들 수는 <xref:System.Windows.Forms.DataGridViewColumn> 클래스 또는 사용자 지정 모양, 동작 또는 호스트 된 컨트롤을 제공 하는 해당 파생된 클래스 중 하나입니다. 자세한 내용은 참조 [하는 방법: 확장 해당 동작과 모양은 하 여 Windows Forms DataGridView 컨트롤에서 사용자 지정 셀 및 열](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 이러한 열 유형에 다음 섹션에서 자세히 설명 되어 있습니다.  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn> 숫자와 문자열 같은 텍스트 기반 값으로 사용 하기 위해 범용 열 형식입니다. 편집 모드에는 <xref:System.Windows.Forms.TextBox> 컨트롤 사용자가 셀 값을 수정할 수 있도록 현재 셀에 표시 됩니다.  
  
 셀 값이 자동으로 표시할 문자열로 변환 됩니다. 입력 하거나 사용자가 수정할 값 적절 한 데이터 형식의 셀 값을 만드는 구문 분석 자동으로 됩니다. 이러한 변환을 처리 하 여 사용자 지정할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CellFormatting> 및 <xref:System.Windows.Forms.DataGridView.CellParsing> 의 이벤트는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
 셀 값 데이터 형식의 열에 지정 된는 <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> 열의 속성입니다.  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> 와 함께 사용 되 <xref:System.Boolean> 및 <xref:System.Windows.Forms.CheckState> 값입니다. <xref:System.Boolean> 2 단계 또는 3 상 확인란으로, 값에 따라 값이 표시는 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> 속성입니다. 열에 바인딩된 경우 <xref:System.Windows.Forms.CheckState> 값의 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> 속성 값은 `true` 기본적으로 합니다.  
  
 일반적으로 확인란 셀 값은 다른 데이터를 저장 하거나 대량 작업을 수행 하기 위한 용도로 사용 합니다. 처리할 수 사용자가 확인란 셀을 클릭 하면 바로 대응 하려는 경우는 <xref:System.Windows.Forms.DataGridView.CellClick> 이벤트, 하지만이 이벤트는 셀 값이 업데이트 되기 전에 발생 합니다. 한 가지 옵션은 됩니다 예상 값을 계산 하 고 클릭 시 새 값이 필요한 경우 현재 값을 기반으로 합니다. 또 다른 방법은 즉시 변경 내용을 커밋하고 처리 하는 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 에 응답 하려면 이벤트입니다. 셀을 클릭할 때의 변경 내용을 커밋하지를 처리 해야 합니다는 <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> 이벤트입니다. 처리기에서 확인란 셀 현재 셀을 사용 하는 경우 호출 된 <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> 메서드와 전달은 <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit> 값.  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 <xref:System.Windows.Forms.DataGridViewImageColumn> 이미지를 표시 하는 데 사용 됩니다. Image 열 데이터 원본에서 자동으로 채워지므로, 바인딩되지 않은 열에 대 한 수동으로 배치 하거나에 대 한 처리기에서 동적으로 채울 수는 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트입니다.  
  
 다양 한 이미지 형식에서 지 원하는 모든 형식을 포함 하 여 바이트 배열에서 작동 하는 데이터 원본에서 image 열의 자동 채우기를 <xref:System.Drawing.Image> 클래스 및 Microsoft® Access 및 Northwind 샘플 데이터베이스에서 사용 되는 OLE 그림 형식입니다.  
  
 이미지 열을 수동으로 채우기는의 기능을 제공 하려는 경우 유용는 <xref:System.Windows.Forms.DataGridViewButtonColumn>, 하면서도 사용자 지정 된 모양입니다. 처리할 수는 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 이미지 셀 내에서 클릭에 응답 하는 이벤트입니다.  
  
 이미지 열에 대 한 처리기에 셀을 채우는 방법은 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트는 계산 된 값 또는 이미지가 아닌 형식의 값에 대 한 이미지를 제공 하려는 경우에 유용 합니다. 예를 들어 할 수 있습니다 "위험" 문자열 값이 열을와 같은 `"high"`, `"middle"`, 및 `"low"` 를 아이콘으로 표시 합니다. 또는 이미지의 이진 콘텐츠 아니라 로드 해야 하는 이미지의 위치를 포함 하는 "이미지" 열을 할 수 있습니다.  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 와 <xref:System.Windows.Forms.DataGridViewButtonColumn>, 단추가 포함 된 셀의 열을 표시할 수 있습니다. 사용자는 주문 또는 별도 창에 자식 레코드 표시와 같은 특정 레코드에서 작업을 수행할 수 있는 간편한 방법을 제공 하는 경우에 유용 합니다.  
  
 데이터 바인딩할 때 단추 열 자동으로 생성 되지 않습니다는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 단추 열을 사용 하려면 수동으로 만들 및에서 반환 된 컬렉션에 추가 해야 합니다는 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType> 속성입니다.  
  
 처리 하 여 사용자가 클릭 단추 셀에서에 응답할 수는 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 이벤트입니다.  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 와 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, 드롭 다운 목록 상자를 포함 하는 셀의 열을 표시할 수 있습니다. Northwind 샘플 데이터베이스의 Products 테이블의 범주 열 등의 특정 값만 포함할 수 있는 필드에 데이터를 입력할 때 유용 합니다.  
  
 채우는 같은 방식으로 모든 셀에 대해 사용 되는 드롭다운 목록을 채울 수는 <xref:System.Windows.Forms.ComboBox> 드롭 다운 목록에서 반환 된 컬렉션을 통해 수동으로 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> 속성을 통해 데이터 소스에 바인딩하는 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>, 및 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 속성입니다. 자세한 내용은 참조 [ComboBox 컨트롤](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)합니다.  
  
 사용 하는 데이터 원본에는 실제 셀 값을 바인딩할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 설정 하 여 컨트롤의 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> 속성은 <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>합니다.  
  
 데이터 바인딩할 때 콤보 상자 열 자동으로 생성 되지 않습니다는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 콤보 상자 열을 사용 하려면 수동으로 만들 및에서 반환 된 컬렉션에 추가 해야 합니다는 <xref:System.Windows.Forms.DataGridView.Columns%2A> 속성입니다.  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 와 <xref:System.Windows.Forms.DataGridViewLinkColumn>, 하이퍼링크가 들어 있는 셀의 열을 표시할 수 있습니다. 데이터 원본 또는 자식 레코드와 창을 여는 것 처럼 특별 한 동작에 대 한 단추 열 하는 대신 URL 값에 대 한 유용 합니다.  
  
 데이터 바인딩할 때 링크 열 자동으로 생성 되지 않습니다는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 링크 열을 사용 하려면 수동으로 만들 및에서 반환 된 컬렉션에 추가 해야 합니다는 <xref:System.Windows.Forms.DataGridView.Columns%2A> 속성입니다.  
  
 처리 하 여 사용자가 링크 클릭 시에 응답할 수는 <xref:System.Windows.Forms.DataGridView.CellContentClick> 이벤트입니다. 이 이벤트는 구별는 <xref:System.Windows.Forms.DataGridView.CellClick> 및 <xref:System.Windows.Forms.DataGridView.CellMouseClick> 셀에는 사용자가 클릭할 때 발생 하는 이벤트입니다.  
  
 <xref:System.Windows.Forms.DataGridViewLinkColumn> 하기 전에, 전후 또는 배포 시 링크의 모양 수정에 대 한 여러 속성을 제공 하는 클래스 클릭할 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewImageColumn>  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewLinkColumn>  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [방법: Windows Forms DataGridView 컨트롤의 셀에 이미지 표시](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤에서 이미지 열 작업](../../../../docs/framework/winforms/controls/how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
