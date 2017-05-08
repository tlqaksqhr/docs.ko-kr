---
title: "DataGrid | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "컨트롤[WPF], DataGrid"
  - "DataGrid[WPF], 일반 작업"
  - "DataGrid[WPF], 모양 사용자 지정"
  - "DataGrid 열 형식[WPF]"
  - "DataGrid 열[WPF], using"
  - "DataGrid 컨트롤[WPF]"
  - "DataGrid 시나리오[WPF]"
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# DataGrid
<xref:System.Windows.Controls.DataGrid> 컨트롤을 사용하면 SQL 데이터베이스, LINQ 쿼리 및 다른 바인딩 가능한 데이터 소스와 같은 여러 종류의 소스에서 가져온 데이터를 표시하고 편집할 수 있습니다.  자세한 내용은 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)를 참조하십시오.  
  
 열에 텍스트, 컨트롤\(예: <xref:System.Windows.Controls.ComboBox>\) 또는 기타 WPF 콘텐츠\(예: 이미지, 단추, 템플릿에 포함된 콘텐츠\)를 표시할 수 있습니다.  <xref:System.Windows.Controls.DataGridTemplateColumn>을 사용하여 템플릿에 정의된 데이터를 표시할 수 있습니다.  다음 표에서는 기본적으로 제공되는 열 형식을 보여 줍니다.  
  
|생성된 열 형식|데이터 형식|  
|--------------|------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 셀 글꼴, 색, 크기 등의 모양에서 <xref:System.Windows.Controls.DataGrid>를 사용자 지정할 수 있습니다.  <xref:System.Windows.Controls.DataGrid>는 다른 WPF 컨트롤의 모든 스타일 지정 및 템플릿 기능을 지원합니다.  또한 <xref:System.Windows.Controls.DataGrid>는 편집, 정렬, 유효성 검사 등에 대한 기본 동작과 사용자 지정 가능한 동작을 포함합니다.  
  
 다음 표에서는 <xref:System.Windows.Controls.DataGrid>에 대한 몇 가지 일반적인 작업과 작업을 수행하는 방법을 보여 줍니다.  관련 API를 확인하여 자세한 정보와 샘플 코드를 찾아 볼 수 있습니다.  
  
|시나리오|방법|  
|----------|--------|  
|교대로 반복되는 배경색|<xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> 속성을 2 이상으로 설정한 다음 <xref:System.Windows.Media.Brush>를 <xref:System.Windows.Controls.DataGrid.RowBackground%2A> 및 <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> 속성에 할당합니다.|  
|셀 및 행 선택 동작을 정의합니다.|<xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 및 <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> 속성을 설정합니다.|  
|머리글, 셀 및 행의 시각적 모양을 사용자 지정합니다.|새 <xref:System.Windows.Style>을 <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.CellStyle%2A> 또는 <xref:System.Windows.Controls.DataGrid.RowStyle%2A> 속성에 적용합니다.|  
|크기 조정 옵션 설정|<xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A> 또는 <xref:System.Windows.FrameworkElement.MinWidth%2A> 속성을 설정합니다.  자세한 내용은 [DataGrid 컨트롤의 크기 조정 옵션](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md)을 참조하십시오.|  
|선택한 항목에 액세스|<xref:System.Windows.Controls.DataGrid.SelectedCells%2A> 속성을 확인하여 선택한 셀을 가져오고 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> 속성을 확인하여 선택한 행을 가져옵니다.  자세한 내용은 <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>를 참조하십시오.|  
|최종 사용자 상호 작용 사용자 지정|<xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A> 및 <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> 속성을 설정합니다.|  
|자동으로 생성된 열 취소 또는 변경|<xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> 이벤트를 처리합니다.|  
|열 고정|<xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> 속성을 1로 설정하고, <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> 속성을 0으로 설정하여 열을 가장 왼쪽으로 이동합니다.|  
|데이터 소스로 XML 데이터 사용|<xref:System.Windows.Controls.DataGrid>에서 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>를 항목의 컬렉션을 나타내는 XPath 쿼리에 바인딩합니다.  <xref:System.Windows.Controls.DataGrid>에서 각 열을 만듭니다.  항목 소스에 대한 속성을 가져오는 쿼리에 대한 바인딩에서 XPath를 설정하여 각 열을 바인딩합니다.  예제를 보려면 <xref:System.Windows.Controls.DataGridTextColumn>을 참조하십시오.|  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[연습: DataGrid 컨트롤에서 SQL Server 데이터베이스의 데이터 표시](../../../../docs/framework/wpf/controls/walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|새 WPF 프로젝트를 설정하고 Entity Framework 요소를 추가하고 소스를 설정한 다음 <xref:System.Windows.Controls.DataGrid>에 데이터를 표시하는 방법에 대해 설명합니다.|  
|[방법: DataGrid 컨트롤에 행 세부 정보 추가](../../../../docs/framework/wpf/controls/how-to-add-row-details-to-a-datagrid-control.md)|<xref:System.Windows.Controls.DataGrid>에 대한 열 세부 정보를 만드는 방법에 대해 설명합니다.|  
|[방법: DataGrid 컨트롤을 사용하여 유효성 검사 구현](../../../../docs/framework/wpf/controls/how-to-implement-validation-with-the-datagrid-control.md)|<xref:System.Windows.Controls.DataGrid> 셀과 행의 값을 확인하고 유효성 검사 피드백을 표시하는 방법에 대해 설명합니다.|  
|[DataGrid 컨트롤에서의 기본 키보드 및 마우스 동작](../../../../docs/framework/wpf/controls/default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|키보드 및 마우스를 사용하여 <xref:System.Windows.Controls.DataGrid> 컨트롤과 상호 작용하는 방법에 대해 설명합니다.|  
|[방법: DataGrid 컨트롤에서 데이터 그룹화, 정렬 및 필터링](../../../../docs/framework/wpf/controls/how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|<xref:System.Windows.Controls.DataGrid>에서 데이터를 그룹화, 정렬 및 필터링하여 다양한 방식으로 보는 방법에 대해 설명합니다.|  
|[DataGrid 컨트롤의 크기 조정 옵션](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md)|<xref:System.Windows.Controls.DataGrid>에서 절대 크기 및 자동 크기를 조정하는 방법에 대해 설명합니다.|  
  
## 참고 항목  
 <xref:System.Windows.Controls.DataGrid>   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [컨트롤](../../../../docs/framework/wpf/controls/index.md)   
 [WPF 콘텐츠 모델](../../../../docs/framework/wpf/controls/wpf-content-model.md)