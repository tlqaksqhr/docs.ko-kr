---
title: "DataGrid 컨트롤의 크기 조정 옵션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "자동으로 DataGrid 크기 지정"
  - "DataGrid 컨트롤[WPF], 크기 조정"
  - "크기[WPF], DataGrid"
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# DataGrid 컨트롤의 크기 조정 옵션
<xref:System.Windows.Controls.DataGrid>의 크기가 조정되는 방식을 제어할 수 있는 다양한 옵션이 있습니다.  <xref:System.Windows.Controls.DataGrid> 및 <xref:System.Windows.Controls.DataGrid>의 개별 행과 열을 내용에 따라 자동으로 크기가 조정되도록 설정하거나 특정 값으로 설정할 수 있습니다.  기본적으로 <xref:System.Windows.Controls.DataGrid>는 해당 내용의 크기에 맞게 늘어나거나 줄어듭니다.  
  
## DataGrid 크기 조정  
  
### 자동 크기 조정 사용 시 주의 사항  
 기본적으로 <xref:System.Windows.Controls.DataGrid>의 <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Width%2A> 속성은 <xref:System.Double.NaN?displayProperty=fullName>\(XAML에서 "`Auto`"\)으로 설정되고 <xref:System.Windows.Controls.DataGrid>는 해당 내용의 크기에 맞게 조정됩니다.  
  
 <xref:System.Windows.Controls.Canvas> 또는 <xref:System.Windows.Controls.StackPanel>과 같이 자식 요소의 크기를 제한하지 않는 컨테이너 안에 배치되면 <xref:System.Windows.Controls.DataGrid>가 컨테이너의 보이는 영역을 넘어 확장되고 스크롤 막대는 표시되지 않습니다.  이런 상황은 사용 편이성과 성능 모두에 영향을 줍니다.  
  
 데이터 집합에 바인딩된 경우 <xref:System.Windows.Controls.DataGrid>의 <xref:System.Windows.FrameworkElement.Height%2A>가 제한되지 않으면 바인딩된 데이터 집합의 각 데이터 항목에 대해 한 행씩 계속 추가됩니다.  이처럼 행이 추가되면 <xref:System.Windows.Controls.DataGrid>가 응용 프로그램의 보이는 영역을 넘어 확장될 수 있습니다.  <xref:System.Windows.Controls.DataGrid>는 이런 경우 스크롤 막대를 표시하지 않습니다. 새 행이 들어갈 수 있도록 <xref:System.Windows.FrameworkElement.Height%2A>가 계속 늘어나기 때문입니다.  
  
 <xref:System.Windows.Controls.DataGrid>의 각 행에 대해 개체가 만들어집니다.  대용량 데이터 집합으로 작업하면서 <xref:System.Windows.Controls.DataGrid>가 자동으로 크기 조정되도록 허용한 경우 많은 개체를 만들면 응용 프로그램 성능에 영향을 줄 수 있습니다.  
  
 대용량 데이터 집합으로 작업할 경우 이런 문제를 피하려면 <xref:System.Windows.Controls.DataGrid>의 <xref:System.Windows.FrameworkElement.Height%2A>를 명시적으로 설정하거나 <xref:System.Windows.Controls.Grid>와 같이 <xref:System.Windows.FrameworkElement.Height%2A>를 제한하는 컨테이너에 배치하는 것이 좋습니다.  <xref:System.Windows.FrameworkElement.Height%2A>가 제한되면 <xref:System.Windows.Controls.DataGrid>는 지정된 <xref:System.Windows.FrameworkElement.Height%2A> 안에 들어갈 수 있는 행만 만들며 새 데이터를 표시해야 할 경우에는 이 행을 재활용합니다.  
  
### DataGrid 크기 설정  
 <xref:System.Windows.Controls.DataGrid>를 지정된 경계 안에서 자동 크기 조정되도록 설정하거나 <xref:System.Windows.Controls.DataGrid>를 특정 크기로 설정할 수 있습니다.  다음 표에서는 <xref:System.Windows.Controls.DataGrid> 크기를 제어하기 위해 설정할 수 있는 속성을 보여 줍니다.  
  
|Property|설명|  
|--------------|--------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|<xref:System.Windows.Controls.DataGrid>에 대한 특정 높이를 설정합니다.|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|<xref:System.Windows.Controls.DataGrid>의 높이에 대한 상한을 설정합니다.  <xref:System.Windows.Controls.DataGrid>는 이 높이에 도달할 때까지 세로로 늘어납니다.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|<xref:System.Windows.Controls.DataGrid>의 높이에 대한 하한을 설정합니다.  <xref:System.Windows.Controls.DataGrid>는 이 높이에 도달할 때까지 세로로 줄어듭니다.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|<xref:System.Windows.Controls.DataGrid>에 대한 특정 너비를 설정합니다.|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|<xref:System.Windows.Controls.DataGrid>의 너비에 대한 상한을 설정합니다.  <xref:System.Windows.Controls.DataGrid>는 이 너비에 도달할 때까지 가로로 늘어납니다.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|<xref:System.Windows.Controls.DataGrid>의 너비에 대한 하한을 설정합니다.  <xref:System.Windows.Controls.DataGrid>는 이 너비에 도달할 때까지 가로로 줄어듭니다.|  
  
## 행 및 행 머리글 크기 조정  
  
### DataGrid 행  
 기본적으로 <xref:System.Windows.Controls.DataGrid> 행의 <xref:System.Windows.FrameworkElement.Height%2A> 속성은 <xref:System.Double.NaN?displayProperty=fullName>\(XAML에서 "`Auto`"\)으로 설정되며 행 높이는 해당 내용의 크기에 따라 늘어납니다.  <xref:System.Windows.Controls.DataGrid>의 모든 행 높이는 <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=fullName> 속성을 설정하여 지정할 수 있습니다.  사용자는 행 머리글 구분선을 끌어 행 높이를 변경할 수 있습니다.  
  
### DataGrid 행 머리글  
 행 머리글을 표시하려면 <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> 속성을 <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName> 또는 <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName>로 설정해야 합니다.  기본적으로 행 머리글이 표시되고 내용에 맞게 자동으로 크기가 조정됩니다.  <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=fullName> 속성을 설정하여 행 머리글에 특정 너비를 지정할 수 있습니다.  
  
## 열 및 열 머리글 크기 조정  
  
### DataGrid 열  
 <xref:System.Windows.Controls.DataGrid>는 <xref:System.Windows.Controls.DataGridLength> 및 <xref:System.Windows.Controls.DataGridLengthUnitType> 구조체의 값을 사용하여 절대적 또는 자동 크기 조정 모드를 지정합니다.  
  
 다음 표에서는 <xref:System.Windows.Controls.DataGridLengthUnitType> 구조체에서 제공하는 값을 보여 줍니다.  
  
|Name|설명|  
|----------|--------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|기본 자동 크기 조정 모드에서는 셀 및 열 머리글의 내용에 따라 <xref:System.Windows.Controls.DataGrid> 열의 크기가 조정됩니다.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|셀 기반 자동 크기 조정 모드에서는 열 머리글을 제외한 열의 셀 내용에 따라 <xref:System.Windows.Controls.DataGrid> 열의 크기가 조정됩니다.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|머리글 기반 자동 크기 조정 모드에서는 열 머리글의 내용만을 기준으로 <xref:System.Windows.Controls.DataGrid> 열의 크기가 조정됩니다.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|픽셀 기반 크기 조정 모드에서는 제공된 숫자 값에 따라 <xref:System.Windows.Controls.DataGrid> 열의 크기가 조정됩니다.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|배율 크기 조정 모드는 사용 가능한 공간을 가중치에 따라 배분하는 데 사용합니다.<br /><br /> XAML에서 배율 값은 n\*로 표현됩니다. 여기서 n은 숫자 값을 나타냅니다.  1\*는 \*에 해당합니다.  예를 들어 <xref:System.Windows.Controls.DataGrid>에 있는 두 열의 너비가 \* 및 2\*인 경우 첫 번째 열은 사용 가능한 공간의 한 부분을 받고 두 번째 열은 사용 가능한 공간의 두 부분을 받게 됩니다.|  
  
 <xref:System.Windows.Controls.DataGridLengthConverter> 클래스를 사용하여 숫자 또는 문자열 값과 <xref:System.Windows.Controls.DataGridLength> 값 간에 데이터를 변환할 수 있습니다.  
  
 기본적으로 <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName> 속성은 <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A>로 설정되며 <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=fullName> 속성은 <xref:System.Windows.Controls.DataGridLength.Auto%2A>로 설정됩니다.  크기 조정 모드를 <xref:System.Windows.Controls.DataGridLength.Auto%2A> 또는 <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A>로 설정하면 열이 전체 내용이 다 보이는 너비까지 늘어납니다.  스크롤할 때 현재 열 크기보다 큰 내용이 스크롤될 경우 이러한 크기 조정 모드에 따라 열이 늘어납니다.  내용이 스크롤되어 보이지 않게 되어도 열은 다시 줄어들지 않습니다.  
  
 <xref:System.Windows.Controls.DataGrid>의 열이 지정된 경계 내에서만 자동으로 크기 조정되도록 설정하거나 열을 특정 크기로 설정할 수 있습니다.  다음 표에서는 열 크기를 제어하기 위해 설정할 수 있는 속성을 보여 줍니다.  
  
|Property|설명|  
|--------------|--------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=fullName>|<xref:System.Windows.Controls.DataGrid>의 모든 열에 대해 상한을 설정합니다.|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=fullName>|개별 열에 대해 상한을 설정합니다.  <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=fullName>를 재정의합니다.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=fullName>|<xref:System.Windows.Controls.DataGrid>의 모든 열에 대해 하한을 설정합니다.|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=fullName>|개별 열에 대해 하한을 설정합니다.  <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=fullName>를 재정의합니다.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName>|<xref:System.Windows.Controls.DataGrid>의 모든 열에 대해 특정 너비를 설정합니다.|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=fullName>|개별 열에 대해 특정 너비를 설정합니다.  <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName>를 재정의합니다.|  
  
### DataGrid 열 머리글  
 기본적으로 <xref:System.Windows.Controls.DataGrid> 열 머리글은 표시됩니다.  열 머리글을 숨기려면 <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> 속성을 <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName> 또는 <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName>으로 설정해야 합니다.  기본적으로, 열 머리글은 표시될 경우 내용에 맞게 자동으로 크기가 조정됩니다.  <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=fullName> 속성을 설정하여 열 머리글에 특정 높이를 지정할 수 있습니다.  
  
### 마우스로 크기 조정  
 사용자는 행 또는 열 머리글 구분선을 끌어 <xref:System.Windows.Controls.DataGrid> 행 및 열의 크기를 조정할 수 있습니다.  <xref:System.Windows.Controls.DataGrid>는 행 또는 열 머리글 구분선을 두 번 클릭하여 열의 크기를 자동으로 조정하는 기능도 지원합니다.  사용자가 특정 열의 크기를 조정하지 못하도록 하려면 개별 열에 대해 <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=fullName> 속성을 `false`로 설정하십시오.  사용자가 모든 열의 크기를 조정하지 못하도록 하려면 <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=fullName> 속성을 `false`로 설정하십시오.  사용자가 모든 행의 크기를 조정하지 못하도록 하려면 <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=fullName> 속성을 `false`로 설정하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Controls.DataGrid>   
 <xref:System.Windows.Controls.DataGridColumn>   
 <xref:System.Windows.Controls.DataGridLength>   
 <xref:System.Windows.Controls.DataGridLengthConverter>