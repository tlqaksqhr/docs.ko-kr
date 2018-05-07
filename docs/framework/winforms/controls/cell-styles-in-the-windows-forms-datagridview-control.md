---
title: Windows Forms DataGridView 컨트롤의 셀 스타일
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: 463fbbffe1e88991934f08fbe7e7445b2e233081
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 셀 스타일
내에 있는 각 셀은 <xref:System.Windows.Forms.DataGridView> 컨트롤 텍스트 형식, 배경색, 전경색 및 글꼴 등의 고유 스타일 있을 수 있습니다. 하지만 일반적으로 여러 셀 공유 합니다 특정 한 스타일 특성.  
  
 스타일을 공유 하는 셀의 그룹 컨트롤에 특정 행 이나 열, 특정 값을 포함 하는 모든 셀 또는 모든 셀 내에 있는 모든 셀을 포함할 수 있습니다. 이러한 그룹은 겹칠, 하기 때문에 각 셀 둘 이상의 위치에서 스타일링 정보를 얻을 수 있습니다. 예를 들어 모든 셀에 만한는 <xref:System.Windows.Forms.DataGridView> 및 사용 하는 같은 글꼴을 하지만 통화 통화 형식을 사용 하는 열의 셀에에서 통화 셀만 음수 빨간 전경 색을 사용 하는 컨트롤입니다.  
  
## <a name="the-datagridviewcellstyle-class"></a>DataGridViewCellStyle 클래스  
 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스 비주얼 스타일 관련 된 다음 속성이 포함 되어 있습니다.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 이 클래스에는 또한 서식에 관련 된 다음 속성이 포함 되어 있습니다.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 이러한 속성 및 다른 셀 스타일 속성에 대 한 자세한 내용은 참조는 <xref:System.Windows.Forms.DataGridViewCellStyle> 아래 참고 항목 섹션에 나열 된 항목과 참조 설명서입니다.  
  
## <a name="using-datagridviewcellstyle-objects"></a>DataGridViewCellStyle 개체를 사용 하 여  
 검색할 수 있습니다 <xref:System.Windows.Forms.DataGridViewCellStyle> 의 다양 한 속성에서 개체는 <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, 및 <xref:System.Windows.Forms.DataGridViewCell> 클래스 및 파생된 된 클래스입니다. 이러한 속성 중 하나에 아직 설정 되지 값을 검색 만들어집니다 새 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체입니다. 또한 인스턴스화할 수 있습니다 직접 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체 및 이러한 속성에 할당 합니다.  
  
 공유 하 여 스타일 정보가 불필요 한 중복을 방지할 수 <xref:System.Windows.Forms.DataGridViewCellStyle> 여러 개체 <xref:System.Windows.Forms.DataGridView> 요소입니다. 스타일을 컨트롤, 열 및 행 수준 필터 아래로 통해 셀 수준에 각 수준에서 설정 때문에 위의 수준과 다른 각 수준에서 해당 스타일 속성을 설정 하 여도 스타일 중복을 방지할 수 있습니다. 이 스타일 상속 다음 섹션에서 자세히 설명 되어 있습니다.  
  
 다음 표에서 기본 속성을 가져오거나 설정 하는 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체입니다.  
  
|속성|클래스|설명|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView><xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, 및 파생 클래스|전체 컨트롤 (머리글 셀을 포함), 열 또는 행에 있는 모든 셀에서 사용 하는 기본 스타일을 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|컨트롤의 모든 행에서 사용 하는 기본 셀 스타일을 가져오거나 설정 합니다. 머리글 셀을 포함 하지 않습니다.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|교대로 반복 되는 컨트롤의 행에서 사용 하는 기본 셀 스타일을 가져오거나 설정 합니다. 장부와 비슷한 효과 만드는 데 사용 합니다.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|컨트롤의 행 머리글에 의해 사용 되는 기본 셀 스타일을 가져오거나 설정 합니다. 비주얼 스타일을 사용 하는 경우 현재 테마를 기반으로 재정의 합니다.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|컨트롤의 열 머리글에 의해 사용 되는 기본 셀 스타일을 가져오거나 설정 합니다. 비주얼 스타일을 사용 하는 경우 현재 테마를 기반으로 재정의 합니다.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> 클래스와 파생된 클래스|셀 수준에서 지정 된 스타일을 가져오거나 설정 합니다. 이러한 스타일의 상위 수준에서 상속을 재정의 합니다.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell><xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn>, 및 파생 클래스|현재 셀, 행 또는 열을 포함 하는 상위 수준에서 상속 하는 스타일에 적용 된 모든 스타일을 가져옵니다.|  
  
 위에서 설명한 대로 새 인스턴스화합니다 스타일 속성의 값을 자동으로 가져오는 <xref:System.Windows.Forms.DataGridViewCellStyle> 경우 속성이 설정 되지 않았습니다 이전에 개체입니다. 행 및 열 클래스에는 이러한 개체를 불필요 하 게 만드는 방지 하려면는 <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> 속성을 확인 하려면 확인할 수 있습니다 여부는 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> 속성이 설정 되어 있습니다. 마찬가지로, 셀 클래스에는 <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> 나타내는 속성을 여부는 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성이 설정 되어 있습니다.  
  
 각 스타일 속성에 해당 *PropertyName* `Changed` 이벤트에는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 행, 열 및 셀 속성, 이벤트의 이름으로 시작 "`Row`","`Column`", 또는 "`Cell`" (예를 들어 <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). 해당 스타일 속성을 다른 설정 되었을 때 발생 하는 이러한 각 이벤트 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체입니다. 검색 하는 경우에 이러한 이벤트가 발생 하지 않습니다는 <xref:System.Windows.Forms.DataGridViewCellStyle> style 속성 개체와 해당 속성 값을 수정 합니다. 셀 스타일 개체 자체에 대 한 변경에 응답 하려면 처리는 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> 이벤트입니다.  
  
## <a name="style-inheritance"></a>스타일 상속  
 각 <xref:System.Windows.Forms.DataGridViewCell> 에서 모양을 가져옵니다 해당 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 속성입니다. <xref:System.Windows.Forms.DataGridViewCellStyle> 이 속성에서 반환 된 개체 유형 속성의 계층 구조에서 값을 상속 <xref:System.Windows.Forms.DataGridViewCellStyle>합니다. 이러한 속성은 되는 순서에 아래 나열 된 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 비 머리글 셀에 대 한 값을 가져오는 합니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (홀수 인덱스 번호가 있는 행의 셀)에  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 행 및 열 머리글 셀에는 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 속성은 지정 된 순서로 원본 속성의 다음 목록에서 값으로 채워집니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 다음 다이어그램에서는이 프로세스를 보여 줍니다.  
  
 ![DataGridViewCellStyle 형식의 속성](../../../../docs/framework/winforms/controls/media/datagridviewcells1.gif "DataGridViewCells1")  
  
 특정 행과 열에 상속 된 스타일에 액세스할 수도 있습니다. 열 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> 속성은 다음 속성에서 값을 상속 합니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 행 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> 속성은 다음 속성에서 값을 상속 합니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (홀수 인덱스 번호가 있는 행의 셀)에  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 각 속성에 대 한 <xref:System.Windows.Forms.DataGridViewCellStyle> 에서 반환 된 개체는 `InheritedStyle` 속성 값 이외의 값으로 설정 하 고 해당 속성을 가진 적절 한 목록에서 첫 번째 셀 스타일에서 가져온 속성을는 <xref:System.Windows.Forms.DataGridViewCellStyle> 기본값 클래스입니다.  
  
 다음 표에서 설명 방법을 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 예제 셀 속성 값은 포함 된 열에서 상속 됩니다.  
  
|형식의 속성 `DataGridViewCellStyle`|예제 `ForeColor` 검색 된 개체에 대 한 값|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 이 경우에 <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> 셀의 행에서 값은 목록에 첫 번째 실제 값입니다. 이 속성은 됩니다는 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 셀의 속성 값 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>합니다.  
  
 다음 다이어그램에서는 서로 어떻게 다른 지 <xref:System.Windows.Forms.DataGridViewCellStyle> 속성 다른 위치에서 해당 값을 상속할 수 있습니다.  
  
 ![DataGridView 속성&#45;값이 상속](../../../../docs/framework/winforms/controls/media/datagridviewcells2.gif "DataGridViewCells2")  
  
 스타일 상속을 활용 하 여 여러 위치에서 동일한 정보를 지정 하지 않고 전체 컨트롤에 대 한 적절 한 스타일을 제공할 수 있습니다.  
  
 하지만 설명 된 대로 머리글 셀 스타일 상속에 참여 하 여 반환 되는 개체는 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 의 속성은 <xref:System.Windows.Forms.DataGridView> 컨트롤이 반환 되는 개체의 속성 값을 재정의 하는 초기 속성 값 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 속성입니다. 속성이 반환 되는 개체에 대 한 설정 하려는 경우는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 행 및 열 머리글에 적용할 속성에서 반환 된 개체의 해당 속성을 설정 해야 합니다는 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성을 기본값으로 표시 에 대 한는 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스입니다.  
  
> [!NOTE]
>  비주얼 스타일을 사용 하는 경우 행 및 열 머리글 (제외 하 고는 <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>)는 자동으로 이러한 속성에 지정 된 스타일을 재정의 하는 현재 테마에서 스타일이 지정 합니다.  
  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn>, 및 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> 형식 열에 의해 반환 되는 개체의 일부 값을도 초기화 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성입니다. 자세한 내용은 이러한 형식에 대 한 참조 설명서를 참조 합니다.  
  
## <a name="setting-styles-dynamically"></a>스타일을 동적으로 설정  
 특정 값이 포함 된 셀 스타일을 사용자 지정 하려면 구현에 대 한 처리기는 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 이벤트입니다. 이 이벤트에 대 한 처리기 수신의 인수는 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> 유형입니다. 이 개체에서의 위치와 함께 서식이 지정 되는 셀의 값을 확인할 수 있는 속성이 포함 되어는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이 개체도 포함 되어는 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> 속성의 값으로 초기화 되는 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 서식을 지정할 셀의 속성입니다. 셀 값과 위치에 해당 하는 스타일 정보를 지정 하려면 셀 스타일 속성을 수정할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView.RowPrePaint> 및 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 이벤트 발생 하기도 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체 이벤트 데이터를 이지만 경우에는 행의 복사본이 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> 읽기 전용 목적 및 변경 하려면 속성 컨트롤 영향을 주지 않습니다.  
  
 이벤트에 대 한 응답에서 각 셀의 스타일을와 같은 수정 동적으로 수는 <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DataGridView.CellMouseLeave> 이벤트입니다. 에 대 한 처리기에서 예를 들어는 <xref:System.Windows.Forms.DataGridView.CellMouseEnter> 이벤트 셀 배경색의 현재 값을 저장할 수 있습니다 (셀의을 통해 검색 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성), 다음 마우스로 가리킬 때 셀 강조 표시 하는 새로운 색으로 설정 합니다. 에 대 한 처리기에는 <xref:System.Windows.Forms.DataGridView.CellMouseLeave> 이벤트를 원래 값으로 명령 프롬프트 창의 배경색 복원할 수 있습니다.  
  
> [!NOTE]
>  셀의에 저장 된 값을 캐시 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성은 특정 스타일 값이 설정 되어 있는지 여부에 관계 없이 중요 합니다. 스타일 설정의 임시로 대체 하는 경우 셀 스타일 설정을 상위 수준에서 상속 하는 상태로 되돌려집니다 되도록 원래 "설정 안 함" 상태로 복원 합니다. 사용 하 여 셀의 스타일의 상속 여부에 관계 없이 셀에 적용 실제 스타일을 결정 해야 할 경우 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 속성입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>  
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
