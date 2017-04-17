---
title: "Windows Forms DataGridView 컨트롤의 셀 스타일 | Microsoft Docs"
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
  - "셀, 스타일"
  - "데이터 표, 셀 스타일"
  - "DataGridView 컨트롤[Windows Forms], 셀 스타일"
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Windows Forms DataGridView 컨트롤의 셀 스타일
<xref:System.Windows.Forms.DataGridView> 컨트롤 내의 각 셀은 텍스트 형식, 배경색, 전경색 및 글꼴과 같은 고유한 스타일을 가질 수 있습니다.  그러나 일반적으로는 여러 셀에서 특정한 스타일 특성을 공유합니다.  
  
 스타일을 공유하는 셀 그룹에는 특정 행이나 열 내의 모든 셀, 특정 값을 포함하는 모든 셀 또는 컨트롤 내의 모든 셀이 포함될 수 있습니다.  이러한 그룹이 겹치기 때문에 각 셀에서는 여러 위치에서 스타일링 정보를 가져올 수 있습니다.  예를 들어, <xref:System.Windows.Forms.DataGridView> 컨트롤 내의 모든 셀에 같은 글꼴을 사용하면서 통화 열의 셀에만 통화 형식을 사용하고 음수 값인 통화 셀에만 빨간 전경색을 사용할 수 있습니다.  
  
## DataGridViewCellStyle 클래스  
 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스에는 비주얼 스타일에 관한 다음과 같은 속성이 있습니다.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 이 클래스에는 서식에 관한 다음과 같은 속성도 있습니다.  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 이러한 속성과 기타 셀 스타일 속성에 대한 자세한 내용은 아래 참고 항목 부분에 있는 <xref:System.Windows.Forms.DataGridViewCellStyle> 참조 문서 및 항목을 참조하십시오.  
  
## DataGridViewCellStyle 개체 사용  
 <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow> 및 <xref:System.Windows.Forms.DataGridViewCell> 클래스와 해당 파생 클래스의 여러 속성에서 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 검색할 수 있습니다.  이러한 속성 중 하나를 설정하지 않은 상태에서 해당 값을 검색하면 새 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체가 만들어집니다.  <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 직접 인스턴스화하고 이러한 속성에 할당할 수도 있습니다.  
  
 여러 <xref:System.Windows.Forms.DataGridView> 요소에서 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 공유하여 스타일 정보가 불필요하게 중복되지 않도록 할 수 있습니다.  컨트롤, 열 및 행 수준에서 설정된 스타일은 각 수준 아래로 셀 수준까지 필터링되기 때문에 위의 수준과 다른 각 수준의 해당 스타일 속성만 설정하여 스타일 중복을 막을 수도 있습니다.  자세한 내용은 뒤에 나오는 스타일 상속 단원에 설명되어 있습니다.  
  
 다음 표에서는 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 가져오거나 설정하는 기본 속성에 대해 설명합니다.  
  
|Property|클래스|설명|  
|--------------|---------|--------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow> 및 파생 클래스|전체 컨트롤, 열 또는 행의 머리글 셀을 포함한 모든 셀에 사용되는 기본 스타일을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|컨트롤의 모든 행에 사용되는 기본 셀 스타일을 가져오거나 설정합니다.  머리글 셀은 여기에 포함되지 않습니다.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|컨트롤의 교대로 반복되는 행에 사용되는 기본 셀 스타일을 가져오거나 설정합니다.  장부와 비슷한 효과를 만드는 데 사용됩니다.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|컨트롤의 행 머리글에 사용되는 기본 셀 스타일을 가져오거나 설정합니다.  비주얼 스타일이 활성화되어 있으면 현재 테마로 재정의됩니다.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|컨트롤의 열 머리글에 사용되는 기본 셀 스타일을 가져오거나 설정합니다.  비주얼 스타일이 활성화되어 있으면 현재 테마로 재정의됩니다.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> 및 파생 클래스|셀 수준에서 지정되는 스타일을 가져오거나 설정합니다.  이 스타일은 상위 수준에서 상속되는 스타일을 재정의합니다.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn> 및 파생 클래스|상위 수준에서 상속되는 스타일을 포함하여 셀, 행 또는 열에 현재 적용되어 있는 모든 스타일을 가져옵니다.|  
  
 앞에서 언급한 대로 이전에 속성을 설정하지 않은 경우 스타일 속성 값을 가져오면 새 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체가 자동으로 인스턴스화됩니다.  이러한 개체가 불필요하게 만들어지지 않도록 하기 위해 행 및 열 클래스에는 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> 속성이 설정되었는지 여부를 확인할 수 있는 <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> 속성이 있습니다.  마찬가지로, 셀 클래스에는 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성이 설정되었는지 여부를 나타내는 <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> 속성이 있습니다.  
  
 각 스타일 속성에는 해당하는 *PropertyName*`Changed` 이벤트가 <xref:System.Windows.Forms.DataGridView> 컨트롤에 있습니다.  행, 열 및 셀 속성의 이벤트 이름은 "`Row`", "`Column`" 또는 "`Cell`"로 시작합니다. 예를 들면 <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>와 같습니다.  이러한 이벤트는 각각 해당하는 스타일 속성이 다른 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체로 설정될 경우 발생합니다.  스타일 속성에서 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 검색하고 해당 속성 값을 수정하면 이러한 이벤트가 발생하지 않습니다.  셀 스타일 개체의 변경 내용에 대해서는 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> 이벤트를 처리합니다.  
  
## 스타일 상속  
 각 <xref:System.Windows.Forms.DataGridViewCell>은 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 속성에서 모양을 가져옵니다.  이 속성에서 반환되는 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체는 <xref:System.Windows.Forms.DataGridViewCellStyle> 형식 속성의 계층 구조에서 값을 상속합니다.  이러한 속성은 머리글 셀이 아닌 셀에 대해 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>이 값을 가져오는 순서대로 아래에 나열되어 있습니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>\(홀수 인덱스 번호를 가진 행의 셀에만 해당\)  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 행 및 열 머리글 셀의 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 속성은 다음과 같은 소스 속성 목록의 값으로 지정된 순서대로 채워집니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=fullName> 또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=fullName>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 다음 다이어그램에서는 이 프로세스를 보여 줍니다.  
  
 ![DataGridViewCellStyle 형식의 속성](../../../../docs/framework/winforms/controls/media/datagridviewcells1.png "DataGridViewCells1")  
  
 특정 행과 열에 상속된 스타일에 액세스할 수도 있습니다.  열의 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> 속성은 다음 속성에서 값을 상속합니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 행의 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> 속성은 다음 속성에서 값을 상속합니다.  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>\(홀수 인덱스 번호를 가진 행의 셀에만 해당\)  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>  
  
 `InheritedStyle` 속성에서 반환되는 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체의 각 속성에 대한 값은 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스 기본값 이외의 값으로 설정된 해당 속성이 있는 적절한 목록의 첫 번째 셀 스타일에서 가져옵니다.  
  
 다음 표에서는 포함된 열에서 예제 셀의 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 속성 값이 상속되는 방법을 보여 줍니다.  
  
|`DataGridViewCellStyle` 형식의 속성|검색된 개체에 대한 예제 `ForeColor` 값|  
|------------------------------------|---------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Red%2A?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Empty?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=fullName>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>|<xref:System.Drawing.Color.Black%2A?displayProperty=fullName>|  
  
 이 경우에는 셀 행의 <xref:System.Drawing.Color.Red%2A?displayProperty=fullName> 값이 목록에서 실질적으로 첫 번째 값입니다.  이 값은 셀의 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>에 대한 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 속성 값이 됩니다.  
  
 다음 다이어그램에서는 여러 <xref:System.Windows.Forms.DataGridViewCellStyle> 속성이 서로 다른 위치에서 값을 상속하는 방법을 보여 줍니다.  
  
 ![DataGridView 속성 값 상속](../../../../docs/framework/winforms/controls/media/datagridviewcells2.png "DataGridViewCells2")  
  
 스타일 상속 기능을 사용하면 여러 위치에 같은 정보를 지정할 필요 없이 전체 컨트롤에 적절한 스타일을 제공할 수 있습니다.  
  
 스타일 상속에서 머리글 셀은 위에 설명된 대로 적용되지만 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성에서 반환되는 개체는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 속성에서 반환되는 개체의 속성 값을 재지정하는 초기 속성 값을 갖습니다.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 속성에서 반환되는 개체에 설정된 속성을 행 및 열 머리글에 적용하려면 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성에서 반환되는 개체의 해당 속성을 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스에 대해 표시되는 기본값으로 설정해야 합니다.  
  
> [!NOTE]
>  비주얼 스타일이 활성화되어 있으면 <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>의 경우를 제외하고는 행 및 열 머리글이 현재 테마로 자동 스타일링되어 이러한 속성에서 지정한 모든 스타일이 재정의됩니다.  
  
 또한 <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn> 및 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> 형식은 열의 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성에서 반환되는 개체의 일부 값을 초기화합니다.  자세한 내용은 이러한 형식에 대한 참조 설명서를 참조하십시오.  
  
## 동적으로 스타일 설정  
 셀의 스타일을 특정 값으로 사용자 지정하려면 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName> 이벤트에 대한 처리기를 구현합니다.  이 이벤트에 대한 처리기는 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> 형식의 인수를 받습니다.  이 개체에는 <xref:System.Windows.Forms.DataGridView> 컨트롤에서의 위치와 함께 서식이 지정되는 셀 값을 결정할 수 있는 속성이 있으며,  서식이 지정되는 셀의 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 속성 값으로 초기화되는 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> 속성도 있습니다.  셀 스타일 속성을 수정하여 셀 값과 위치에 적절한 스타일 정보를 지정할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView.RowPrePaint> 및 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 이벤트는 이벤트 데이터의 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체도 받지만 이 경우에는 행의 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> 속성에 대한 읽기 전용 복사본이므로 변경하더라도 컨트롤에 영향을 주지 않습니다.  
  
 <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=fullName> 및 <xref:System.Windows.Forms.DataGridView.CellMouseLeave> 같은 이벤트에 대한 응답으로 개별 셀 스타일을 동적으로 수정할 수도 있습니다.  예를 들어, <xref:System.Windows.Forms.DataGridView.CellMouseEnter> 이벤트에 대한 처리기에서 셀의 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성을 통해 검색된 셀 배경색의 현재 값을 저장한 다음 마우스를 해당 셀 위로 이동할 경우 셀이 강조 표시되도록 새로운 색으로 설정할 수 있습니다.  나중에 <xref:System.Windows.Forms.DataGridView.CellMouseLeave> 이벤트에 대한 처리기에서 배경색을 원래 값으로 복원할 수 있습니다.  
  
> [!NOTE]
>  특정 스타일 값의 설정 여부에 관계없이 셀의 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성에 저장된 값을 캐싱하는 것이 중요합니다.  스타일 설정을 임시로 바꿀 경우 원래의 "설정 안 함" 상태로 복원하면 셀이 다시 상위 수준의 스타일 설정을 상속하도록 돌아갑니다.  스타일의 상속 여부에 관계없이 셀에 적용된 실제 스타일을 확인하려면 셀의 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 속성을 사용해야 합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)