---
title: "연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사 | Microsoft Docs"
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
  - "데이터[Windows Forms], 유효성 검사"
  - "데이터 표, 데이터 유효성 검사"
  - "데이터 유효성 검사, Windows Forms"
  - "DataGridView 컨트롤[Windows Forms], 데이터 유효성 검사"
  - "데이터 유효성 검사, Windows Forms"
  - "연습[Windows Forms], DataGridView 컨트롤"
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# 연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사
데이터 입력 기능을 사용자에게 표시할 때 폼에 입력되는 데이터의 유효성을 검사해야 하는 경우가 많습니다.  <xref:System.Windows.Forms.DataGridView> 클래스는 데이터가 데이터 저장소에 커밋되기 전에 유효성 검사를 수행할 수 있는 편리한 방법을 제공합니다.  <xref:System.Windows.Forms.DataGridView.CellValidating> 이벤트를 처리하여 데이터의 유효성을 검사할 수 있으며, 이 이벤트는 현재 셀이 바뀔 때 <xref:System.Windows.Forms.DataGridView>에 의해 발생됩니다.  
  
 이 연습에서는 Northwind 샘플 데이터베이스의 `Customers` 테이블에서 행을 검색한 후 검색된 행을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시합니다.  사용자가 `CompanyName` 열의 셀을 편집한 후 셀을 벗어나려고 할 때 <xref:System.Windows.Forms.DataGridView.CellValidating> 이벤트 처리기는 새 회사 이름 문자열이 빈 문자열이 아닌지 확인합니다. 그런 다음 새 값이 빈 문자열이면 <xref:System.Windows.Forms.DataGridView>는 비어 있지 않은 문자열이 입력될 때까지 사용자의 커서를 해당 셀에 유지합니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)를 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   Northwind SQL Server 샘플 데이터베이스가 있는 서버에 액세스할 수 있어야 합니다.  
  
## 폼 만들기  
  
#### DataGridView에 입력한 데이터의 유효성을 검사하려면  
  
1.  <xref:System.Windows.Forms.Form>에서 파생되고 <xref:System.Windows.Forms.DataGridView> 컨트롤 및 <xref:System.Windows.Forms.BindingSource> 구성 요소를 포함하는 클래스를 만듭니다.  
  
     다음 코드 예제에서는 기본적인 초기화를 제공하고 `Main` 메서드를 포함합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  데이터베이스에 연결하는 데 필요한 세부 사항을 처리하는 메서드를 폼의 클래스 정의에 구현합니다.  
  
     이 코드 예제에서는 채워진 <xref:System.Data.DataTable> 개체를 반환하는 `GetData` 메서드를 사용합니다.  `connectionString` 변수를 데이터베이스에 해당하는 값으로 설정해야 합니다.  
  
    > [!IMPORTANT]
    >  연결 문자열에 중요한 정보\(예: 암호\)를 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.  데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.  자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)을 참조하십시오.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  <xref:System.Windows.Forms.DataGridView> 및 <xref:System.Windows.Forms.BindingSource>를 초기화하고 데이터 바인딩을 설정하도록 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트에 대한 처리기를 구현합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellValidating> 및 <xref:System.Windows.Forms.DataGridView.CellEndEdit> 이벤트 처리기를 구현합니다.  
  
     <xref:System.Windows.Forms.DataGridView.CellValidating> 이벤트 처리기에서는 `CompanyName` 열의 셀 값이 비어 있는지 여부를 확인합니다.  셀 값의 유효성 검사가 실패한 경우 <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=fullName> 클래스의 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 `true`로 설정합니다.  이렇게 하면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 커서가 셀을 벗어나지 않도록 합니다.  행의 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 속성을 설명 문자열로 설정합니다.  이렇게 하면 오류 텍스트가 포함된 도구 설명과 함께 오류 아이콘이 표시됩니다.  <xref:System.Windows.Forms.DataGridView.CellEndEdit> 이벤트 처리기에서 행의 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 속성을 빈 문자열로 설정합니다.  <xref:System.Windows.Forms.DataGridView.CellEndEdit> 이벤트는 유효성 검사가 실패하여 편집 모드를 종료할 수 없는 셀이 편집 모드를 종료하는 경우에만 발생합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## 응용 프로그램 테스트  
 이제 폼을 테스트하여 예상한 대로 동작하는지 확인할 수 있습니다.  
  
#### 폼을 테스트하려면  
  
-   응용 프로그램을 컴파일하여 실행합니다.  
  
     `Customers` 테이블의 데이터로 채워진 <xref:System.Windows.Forms.DataGridView>가 표시됩니다.  `CompanyName` 열의 셀을 두 번 클릭하면 셀의 값을 편집할 수 있습니다.  모든 문자를 삭제하고 Tab 키를 눌러 셀을 종료하면 <xref:System.Windows.Forms.DataGridView>는 셀이 종료되지 않도록 합니다.  비어 있지 않은 문자열을 셀에 입력하면 <xref:System.Windows.Forms.DataGridView> 컨트롤은 셀 종료를 허용합니다.  
  
## 다음 단계  
 이 응용 프로그램은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능에 대한 기본적인 이해를 제공합니다.  다음과 같은 여러 가지 방법으로 <xref:System.Windows.Forms.DataGridView> 컨트롤의 모양과 동작을 사용자 지정할 수 있습니다.  
  
-   테두리와 머리글 스타일을 변경합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤의 테두리 및 모눈선 스타일 변경](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)을 참조하십시오.  
  
-   <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 사용자 입력을 활성화하거나 제한합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) 및 [방법: Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
-   사용자 입력에 데이터베이스 관련 오류가 있는지 확인합니다.  자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)를 참조하십시오.  
  
-   가상 모드를 사용하여 대용량 데이터 집합을 처리합니다.  자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)을 참조하십시오.  
  
-   셀의 모양을 사용자 지정합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) 및 [방법: Windows Forms DataGridView 컨트롤의 글꼴 및 색 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Windows Forms DataGridView 컨트롤의 데이터 입력](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)   
 [연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)   
 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)