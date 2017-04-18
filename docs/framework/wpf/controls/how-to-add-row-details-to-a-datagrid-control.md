---
title: "방법: DataGrid 컨트롤에 행 세부 정보 추가 | Microsoft Docs"
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
  - "DataGrid[WPF], 행 세부 정보"
  - "DataTemplate[WPF], DataGrid"
  - "행 세부 정보[WPF], DataGrid"
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: DataGrid 컨트롤에 행 세부 정보 추가
<xref:System.Windows.Controls.DataGrid> 컨트롤을 사용하는 경우 행 세부 정보 섹션을 추가하여 데이터 프레젠테이션을 사용자 지정할 수 있습니다.  행 세부 정보 섹션을 추가하여 템플릿에서 선택적으로 표시되거나 축소되는 일부 데이터를 그룹화할 수 있습니다.  예를 들어 <xref:System.Windows.Controls.DataGrid>에 행 세부 정보를 추가하여 <xref:System.Windows.Controls.DataGrid>에서 각 행의 데이터에 대한 요약 정보만 표시하고 사용자가 행을 선택하는 경우 더 많은 데이터 필드를 나타낼 수 있습니다.  <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 속성에 행 세부 정보 섹션에 대한 템플릿을 정의합니다.  다음 그림에서는 행 세부 정보 섹션의 예를 보여 줍니다.  
  
 ![행 세부 정보가 표시된 DataGrid](../../../../docs/framework/wpf/controls/media/ndp-rowdetails.png "NDP\_RowDetails")  
  
 행 세부 정보 템플릿을 인라인 XAML 또는 리소스로 정의합니다.  다음 절차에서는 두 방법을 모두 보여 줍니다.  템플릿을 다시 만들지 않고 리소스로 추가되는 데이터 템플릿을 프로젝트 전체에서 사용할 수 있습니다.  인라인 XAML로 추가되는 데이터 템플릿은 정의된 컨트롤에서만 액세스할 수 있습니다.  
  
### 인라인 XAML을 사용하여 행 세부 정보를 표시하려면  
  
1.  데이터 소스에서 데이터를 표시하는 <xref:System.Windows.Controls.DataGrid>를 만듭니다.  
  
2.  <xref:System.Windows.Controls.DataGrid> 요소에서 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 요소를 추가합니다.  
  
3.  행 세부 정보 섹션의 모양을 정의하는 <xref:System.Windows.DataTemplate>을 만듭니다.  
  
     다음 XAML은 <xref:System.Windows.Controls.DataGrid>를 보여 주고 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>을 인라인으로 정의하는 방법을 보여 줍니다.  <xref:System.Windows.Controls.DataGrid>의 각 행에는 세 개의 값이 표시되고 행을 선택하면 세 개의 값이 더 표시됩니다.  
  
     [!code-xml[DataGrid_RowDetails#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     다음 코드에서는 <xref:System.Windows.Controls.DataGrid>에 표시되는 데이터를 선택하는 데 사용되는 쿼리를 보여 줍니다.  이 예제의 쿼리에서는 고객 정보가 들어 있는 엔터티에서 데이터를 선택합니다.  
  
     [!code-csharp[DataGrid_RowDetails#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### 리소스를 사용하여 행 세부 정보를 표시하려면  
  
1.  데이터 소스에서 데이터를 표시하는 <xref:System.Windows.Controls.DataGrid>를 만듭니다.  
  
2.  <xref:System.Windows.FrameworkElement.Resources%2A> 요소를 루트 요소\(예: <xref:System.Windows.Window> 컨트롤 또는 <xref:System.Windows.Controls.Page> 컨트롤\)에 추가하거나 <xref:System.Windows.Application.Resources%2A> 요소를 App.xaml 또는 Application.xaml 파일의 <xref:System.Windows.Application> 클래스에 추가합니다.  
  
3.  리소스 요소에서 행 세부 정보 섹션의 모양을 정의하는 <xref:System.Windows.DataTemplate>을 만듭니다.  
  
     다음 XAML에서는 <xref:System.Windows.Application> 클래스에 정의된 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>을 보여 줍니다.  
  
     [!code-xml[DataGrid_RowDetails#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4.  <xref:System.Windows.DataTemplate>에서 [x:Key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md)를 데이터 템플릿을 고유하게 식별하는 값으로 설정합니다.  
  
5.  <xref:System.Windows.Controls.DataGrid> 요소에서 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 속성을 이전 단계에서 정의한 리소스로 설정합니다.  리소스를 정적 리소스로 할당합니다.  
  
     다음 XAML에서는 이전 예제에서 리소스로 설정한 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 속성을 보여 줍니다.  
  
     [!code-xml[DataGrid_RowDetails#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### 행 세부 정보에 대한 표시 유형을 설정하고 가로 방향으로 스크롤되지 않도록 하려면  
  
1.  필요한 경우 <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> 속성을 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> 값으로 설정합니다.  
  
     기본적으로 값은 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>로 설정되어 있습니다.  값을 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>로 설정하여 모든 행에 대한 세부 정보를 표시하거나 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>로 설정하여 모든 행에 대한 세부 정보를 숨길 수 있습니다.  
  
2.  필요한 경우 <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> 속성을 `true`로 설정하여 행 세부 정보 섹션이 가로 방향으로 스크롤되지 않도록 할 수 있습니다.