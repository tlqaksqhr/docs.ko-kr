---
title: "방법: DataGrid 컨트롤을 사용하여 유효성 검사 구현 | Microsoft Docs"
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
  - "DataGrid[WPF], 유효성 검사"
  - "유효성 검사[WPF], DataGrid"
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: DataGrid 컨트롤을 사용하여 유효성 검사 구현
<xref:System.Windows.Controls.DataGrid> 컨트롤을 사용하여 셀 수준과 행 수준 모두에서 유효성 검사를 수행할 수 있습니다.  셀 수준 유효성 검사에서는 사용자가 값을 업데이트할 때 바인딩된 데이터 개체에 대한 개별 속성의 유효성을 검사합니다.  행 수준 유효성 검사에서는 사용자가 행에 대한 변경 내용을 커밋할 때 전체 데이터 개체의 유효성을 검사합니다.  유효성 검사 오류에 대한 사용자 지정 시각적 피드백을 제공하거나, <xref:System.Windows.Controls.DataGrid> 컨트롤에서 제공하는 기본 시각적 피드백을 사용할 수 있습니다.  
  
 다음 절차에서는 <xref:System.Windows.Controls.DataGrid> 바인딩에 유효성 검사 규칙을 적용하고 시각적 피드백을 사용자 지정하는 방법에 대해 설명합니다.  
  
### 개별 셀 값의 유효성을 검사하려면  
  
-   열과 함께 사용되는 바인딩에 하나 이상의 유효성 검사 규칙을 지정합니다.  이 방법은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)에 설명된 대로 간단한 컨트롤에서 데이터의 유효성을 검사하는 방법과 비슷합니다.  
  
     다음 예제에서는 네 개의 열이 비즈니스 개체의 각기 다른 속성에 바인딩된 <xref:System.Windows.Controls.DataGrid> 컨트롤을 보여 줍니다.  이 중 세 개의 열에서는 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 속성을 `true`로 설정하여 <xref:System.Windows.Controls.ExceptionValidationRule>을 지정합니다.  
  
     [!code-xml[DataGrid_Validation#BasicXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     사용자가 Course ID 열에 정수가 아닌 값을 입력하는 등 올바르지 않은 값을 입력하면 셀 주위에 빨간색 테두리가 나타납니다.  다음 절차에 설명된 대로 이 기본 유효성 검사 피드백을 변경할 수 있습니다.  
  
### 셀 유효성 검사 피드백을 사용자 지정하려면  
  
-   열의 <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> 속성을 열의 편집 컨트롤에 적절한 스타일로 설정합니다.  편집 컨트롤은 런타임에 만들어지므로 간단한 컨트롤에서처럼 연결된 속성 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=fullName>을 사용할 수 없습니다.  
  
     다음 예제에서는 유효성 검사 규칙이 설정된 세 개의 열에서 공유하는 오류 스타일을 추가하여 이전 예제를 업데이트합니다.  사용자가 올바르지 않은 값을 입력하면 이 스타일을 통해 셀 배경색이 바뀌고 도구 설명이 추가됩니다.  또한 유효성 검사 오류가 있는지 여부를 확인하기 위해 트리거를 사용합니다.  현재 셀에 대한 전용 오류 템플릿이 없으므로 이 작업은 필수적입니다.  
  
     [!code-xml[DataGrid_Validation#CellValidationXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     열에 사용된 <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A>을 바꿔 보다 광범위한 사용자 지정을 구현할 수 있습니다.  
  
### 단일 행에 있는 여러 값의 유효성을 검사하려면  
  
1.  바인딩된 데이터 개체의 여러 속성을 검사하는 <xref:System.Windows.Controls.ValidationRule> 서브클래스를 구현합니다.  <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드 구현에서 `value` 매개 변수 값을 <xref:System.Windows.Data.BindingGroup> 인스턴스로 캐스팅합니다.  그런 다음 <xref:System.Windows.Data.BindingGroup.Items%2A> 속성을 통해 데이터 개체에 액세스할 수 있습니다.  
  
     다음 예제에서는 `Course` 개체에 대한 `StartDate` 속성 값이 `EndDate` 속성 값보다 이전인지 확인하는 프로세스를 보여 줍니다.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=fullName> 컬렉션에 유효성 검사 규칙을 추가합니다.  <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> 속성은 해당 컨트롤에 사용된 모든 바인딩을 그룹화하는 <xref:System.Windows.Data.BindingGroup> 인스턴스의 <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> 속성에 대한 직접 액세스를 제공합니다.  
  
     다음 예제에서는 XAML에서 <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> 속성을 설정합니다.  바인딩된 데이터 개체가 업데이트된 후에만 유효성이 검사되도록 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 속성은 <xref:System.Windows.Controls.ValidationStep>로 설정됩니다.  
  
     [!code-xml[DataGrid_Validation#RowValidationRulesXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     사용자가 종료 날짜를 시작 날짜보다 이전의 날짜로 지정하면 행 머리글에 빨간색 느낌표\(\!\)가 나타납니다.  다음 절차에 설명된 대로 이 기본 유효성 검사 피드백을 변경할 수 있습니다.  
  
### 행 유효성 검사 피드백을 사용자 지정하려면  
  
-   <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=fullName> 속성을 설정합니다.  이 속성은 개별 <xref:System.Windows.Controls.DataGrid> 컨트롤에 대한 행 유효성 검사 피드백을 사용자 지정할 수 있게 해 줍니다.  암시적 행 스타일을 사용하여 <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=fullName> 속성을 설정하는 방법으로 여러 컨트롤에 영향을 줄 수도 있습니다.  
  
     다음 예제에서는 기본 행 유효성 검사 피드백을 보다 시각적인 표시기로 바꿉니다.  사용자가 올바르지 않은 값을 입력하면 행 머리글에 흰색 느낌표가 있는 빨간색 원이 나타납니다.  이 피드백은 행 유효성 검사 오류와 셀 유효성 검사 오류 모두에 대해 발생합니다.  도구 설명에는 연결된 오류 메시지가 표시됩니다.  
  
     [!code-xml[DataGrid_Validation#RowValidationFeedbackXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## 예제  
 다음 예제에서는 셀 및 행 유효성 검사의 전체 데모를 제공합니다.  `Course` 클래스는 <xref:System.ComponentModel.IEditableObject>를 구현하여 트랜잭션을 지원하는 샘플 데이터 개체를 제공합니다.  <xref:System.Windows.Controls.DataGrid> 컨트롤은 <xref:System.ComponentModel.IEditableObject>와 상호 작용하여 사용자가 Esc 키를 눌러 변경 내용을 되돌릴 수 있도록 합니다.  
  
> [!NOTE]
>  Visual Basic을 사용하는 경우에는 MainWindow.xaml의 첫 번째 줄에서 `x:Class="DataGridValidation.MainWindow"`를 `x:Class="MainWindow"`로 바꿉니다.  
  
 유효성 검사를 테스트하려면 다음을 시도합니다.  
  
-   Course ID 열에서 정수가 아닌 값을 입력합니다.  
  
-   End Date 열에서 시작 날짜보다 이전인 날짜를 입력합니다.  
  
-   Course ID, Start Date 또는 End Date에서 값을 삭제합니다.  
  
-   올바르지 않은 셀 값을 취소하려면 커서를 다시 셀에 놓고 Esc 키를 누릅니다.  
  
-   현재 셀이 편집 모드에 있을 때 전체 행의 변경 내용을 취소하려면 Esc 키를 두 번 누릅니다.  
  
-   유효성 검사 오류가 발생하면 마우스 포인터를 행 머리글의 표시기 위로 이동하여 연결된 오류 메시지를 확인합니다.  
  
 [!code-csharp[DataGrid_Validation#FullCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xml[DataGrid_Validation#FullXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.DataGrid>   
 [DataGrid](../../../../docs/framework/wpf/controls/datagrid.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/data/data-binding-wpf.md)   
 [바인딩 유효성 검사 구현](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [사용자 지정 개체의 유효성 검사 논리 구현](../../../../docs/framework/wpf/data/how-to-implement-validation-logic-on-custom-objects.md)