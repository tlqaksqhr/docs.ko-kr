---
title: "방법: DataGrid 컨트롤을 사용하여 유효성 검사 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78846e2b6a1d73e011441b0ccb46b8aad365d5dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>방법: DataGrid 컨트롤을 사용하여 유효성 검사 구현
<xref:System.Windows.Controls.DataGrid> 컨트롤 셀 및 행 수준에서 유효성 검사를 수행할 수 있습니다. 셀 수준 유효성 검사는 사용자는 값을 업데이트 하는 경우 바인딩된 데이터 개체의 각 속성에 유효성 검사 합니다. 행 수준 유효성 검사와 행에 변경 내용을 커밋할 때 전체 데이터 개체에 유효성 검사. 유효성 검사 오류에 대 한 사용자 지정된 시각적 피드백을 제공 하거나 기본 시각적 피드백을 사용할 수도 있는 <xref:System.Windows.Controls.DataGrid> 제어를 제공 합니다.  
  
 다음 절차는 유효성 검사 규칙을 적용 하는 방법을 설명 <xref:System.Windows.Controls.DataGrid> 바인딩 및 시각적 피드백을 사용자 지정 합니다.  
  
### <a name="to-validate-individual-cell-values"></a>개별 셀 값의 유효성을 검사 하려면  
  
-   유형의 열에 사용할 바인딩에 하나 이상의 유효성 검사 규칙을 지정 합니다. 에 설명 된 대로이 간단한 컨트롤의 데이터 유효성 검사 비슷합니다 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.  
  
     다음 예제에서는 한 <xref:System.Windows.Controls.DataGrid> 비즈니스 개체의 다른 속성에 바인딩된 4 개의 열이 있는 컨트롤입니다. 지정 하는 열 3 개는 <xref:System.Windows.Controls.ExceptionValidationRule> 설정 하 여는 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 속성을 `true`합니다.  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     잘못 된 값 (예: 정수가 아닌 과정 ID 열에)를 입력 하는 경우 셀 주위에 빨간색 테두리가 나타납니다. 다음 절차에 설명 된 대로이 기본 유효성 검사 피드백을 변경할 수 있습니다.  
  
### <a name="to-customize-cell-validation-feedback"></a>유효성 검사 피드백 셀 사용자 지정 하려면  
  
-   열의 설정 <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> 열 편집 컨트롤에 대 한 스타일을 속성 적절 합니다. 편집 컨트롤이 실행 시 만들어지므로 사용할 수 없습니다는 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> 연결 된 속성 간단한 컨트롤와 동일 하 게 합니다.  
  
     다음 예제에서는 세 개의 열을 유효성 검사 규칙에서 공유 하는 오류 스타일을 추가 하 여 앞의 예제를 업데이트 합니다. 사용자가 잘못 된 값을 입력 스타일 셀 배경색을 변경 하 고 도구 설명을 추가 합니다. Note 유효성 검사 오류가 있는지 여부를 확인 하려면 트리거를 사용 합니다. 현재 셀에 대 한 전용된 오류 템플릿이 있기 때문에 이것이 필요 합니다.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     대체 하 여 가장 광범위 한 사용자 지정을 구현할 수는 <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> 열에서 사용 합니다.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>단일 행에 여러 값의 유효성을 검사 하려면  
  
1.  구현 된 <xref:System.Windows.Controls.ValidationRule> 바인딩된 데이터 개체의 여러 속성을 검사 하는 하위 클래스입니다. 사용자 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드 구현 캐스팅는 `value` 매개 변수 값을 한 <xref:System.Windows.Data.BindingGroup> 인스턴스. 통해 데이터 개체에 액세스할 수 있습니다는 <xref:System.Windows.Data.BindingGroup.Items%2A> 속성입니다.  
  
     다음 예제에서는이 유효성 검사이 프로세스를 여부는 `StartDate` 속성 값에 대 한는 `Course` 개체 보다 빠릅니다. 해당 `EndDate` 속성 값입니다.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  유효성 검사 규칙을 추가 <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> 컬렉션입니다. <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> 속성에 대 한 직접 액세스를 제공는 <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> 속성은 <xref:System.Windows.Data.BindingGroup> 컨트롤에서 사용 되는 모든 바인딩은 그룹화 된 인스턴스.  
  
     다음 예에서는 <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> XAML에서 속성입니다. <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 속성이 <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 바인딩된 데이터 개체를 업데이트 한 후에는 유효성 검사가 수행 되도록 합니다.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     사용자가 종료 날짜는 시작 날짜 보다 이전 인지를 지정 하는 경우 빨간색 느낌표 (!) 행 머리글에 나타납니다. 다음 절차에 설명 된 대로이 기본 유효성 검사 피드백을 변경할 수 있습니다.  
  
### <a name="to-customize-row-validation-feedback"></a>행 유효성 검사 피드백을 사용자 지정 하려면  
  
-   <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> 속성을 설정합니다. 이 속성을 사용 하면 개인에 대 한 행 유효성 검사 피드백을 사용자 지정할 수 있습니다 <xref:System.Windows.Controls.DataGrid> 컨트롤입니다. 암시적 행 스타일 설정 하 여 여러 컨트롤에 영향을 줄 수도 있습니다는 <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> 속성입니다.  
  
     다음 예제에서는 기본 행 유효성 검사 피드백을 더 잘 보이도록 표시기를 바꿉니다. 사용자가 잘못 된 값을 입력 하는 경우 빨간색 원과 흰색 느낌표가 행 머리글에 나타납니다. 이 행 및 셀 모두 유효성 검사 오류를 발생합니다. 도구 설명에 관련 된 오류 메시지가 표시 됩니다.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>예  
 다음 예에서는 셀 및 행 유효성 검사의 전체 데모를 제공합니다. `Course` 클래스를 구현 하는 샘플 데이터 개체를 제공 <xref:System.ComponentModel.IEditableObject> 트랜잭션을 지원 합니다. <xref:System.Windows.Controls.DataGrid> 컨트롤과 간의 상호 작용 <xref:System.ComponentModel.IEditableObject> 사용자가 ESC 키를 눌러 변경 내용이 되돌릴 수 있도록 합니다.  
  
> [!NOTE]
>  Visual Basic에서 MainWindow.xaml의 첫 번째 줄을 사용 하는 경우 대체 `x:Class="DataGridValidation.MainWindow"` 와 `x:Class="MainWindow"`합니다.  
  
 유효성 검사를 테스트 하려면 다음을 시도 합니다.  
  
-   과정 ID 열에 정수가 아닌 값을 입력 합니다.  
  
-   종료 날짜 열에는 시작 날짜 보다 이전 날짜를 입력 합니다.  
  
-   과정 ID, 시작 날짜 또는 종료 날짜의 값을 삭제 합니다.  
  
-   잘못 된 셀 값을 실행 취소 하려면 다시 셀에에서 커서를 놓은 ESC 키를 누릅니다.  
  
-   현재 셀이 편집 모드일 때 전체 행에 대 한 변경을 취소 하려면 ESC 키를 두 번 누릅니다.  
  
-   유효성 검사 오류가 발생 하면 관련 된 오류 메시지를 보려면 행 머리글에 있는 표시기 위로 마우스 포인터를 이동 합니다.  
  
 [!code-csharp[DataGrid_Validation#FullCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.DataGrid>  
 [DataGrid](../../../../docs/framework/wpf/controls/datagrid.md)  
 [데이터 바인딩](../../../../docs/framework/wpf/data/data-binding-wpf.md)  
 [바인딩 유효성 검사 구현](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [사용자 지정 개체의 유효성 검사 논리 구현](../../../../docs/framework/wpf/data/how-to-implement-validation-logic-on-custom-objects.md)
