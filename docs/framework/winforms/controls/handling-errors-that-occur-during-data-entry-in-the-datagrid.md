---
title: "연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리 | Microsoft Docs"
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
  - "데이터 입력, 오류 처리"
  - "데이터 표, 오류 처리"
  - "DataGridView 컨트롤[Windows Forms], 오류 처리"
  - "오류 처리, 데이터 입력"
  - "오류 처리, DataGridView 컨트롤"
  - "연습[Windows Forms], DataGridView 컨트롤"
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리
내부 데이터 저장소의 오류 처리 기능은 데이터 입력 응용 프로그램의 필수 기능입니다.  Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하면 데이터 저장소에서 제약 조건 위반 또는 비즈니스 규칙 위반이 감지될 때 발생하는 <xref:System.Windows.Forms.DataGridView.DataError> 이벤트가 노출되기 때문에 이 작업을 쉽게 수행할 수 있습니다.  
  
 이 연습에서는 Northwind 샘플 데이터베이스의 `Customers` 테이블에서 행을 검색한 후 검색된 행을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시합니다.  새 행이나 편집된 기존 행에 중복된 `CustomerID` 값이 있으면 <xref:System.Windows.Forms.DataGridView.DataError> 이벤트가 발생하는데, 이 이벤트는 예외를 설명하는 <xref:System.Windows.Forms.MessageBox>를 표시함으로써 처리됩니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)를 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   Northwind SQL Server 샘플 데이터베이스가 있는 서버에 액세스할 수 있어야 합니다.  
  
## 폼 만들기  
  
#### DataGridView 컨트롤의 데이터 입력 오류를 처리하려면  
  
1.  <xref:System.Windows.Forms.Form>에서 파생되고 <xref:System.Windows.Forms.DataGridView> 컨트롤 및 <xref:System.Windows.Forms.BindingSource> 구성 요소를 포함하는 클래스를 만듭니다.  
  
     다음 코드 예제에서는 기본적인 초기화를 제공하고 `Main` 메서드를 포함합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  데이터베이스에 연결하는 데 필요한 세부 사항을 처리하는 메서드를 폼의 클래스 정의에 구현합니다.  
  
     이 코드 예제에서는 채워진 <xref:System.Data.DataTable> 개체를 반환하는 `GetData` 메서드를 사용합니다.  `connectionString` 변수를 데이터베이스에 해당하는 값으로 설정해야 합니다.  
  
    > [!IMPORTANT]
    >  연결 문자열에 중요한 정보\(예: 암호\)를 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.  데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.  자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)을 참조하십시오.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  <xref:System.Windows.Forms.DataGridView> 및 <xref:System.Windows.Forms.BindingSource>를 초기화하고 데이터 바인딩을 설정하도록 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트에 대한 처리기를 구현합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  <xref:System.Windows.Forms.DataGridView>의 <xref:System.Windows.Forms.DataGridView.DataError> 이벤트를 처리합니다.  
  
     오류 컨텍스트가 커밋 작업인 경우에는 <xref:System.Windows.Forms.MessageBox>에 오류를 표시합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## 응용 프로그램 테스트  
 이제 폼을 테스트하여 예상한 대로 동작하는지 확인할 수 있습니다.  
  
#### 폼을 테스트하려면  
  
-   F5 키를 눌러 응용 프로그램을 실행합니다.  
  
     Customers 테이블의 데이터로 채워진 <xref:System.Windows.Forms.DataGridView> 컨트롤이 표시됩니다.  `CustomerID`에 대해 중복 값을 입력하고 편집 내용을 커밋하면 셀 값이 자동으로 복원되고 데이터 입력 오류를 표시하는 <xref:System.Windows.Forms.MessageBox>가 나타납니다.  
  
## 다음 단계  
 이 응용 프로그램은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능에 대한 기본적인 이해를 제공합니다.  다음과 같은 여러 가지 방법으로 <xref:System.Windows.Forms.DataGridView> 컨트롤의 모양과 동작을 사용자 지정할 수 있습니다.  
  
-   테두리와 머리글 스타일을 변경합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤의 테두리 및 모눈선 스타일 변경](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)을 참조하십시오.  
  
-   <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 사용자 입력을 활성화하거나 제한합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) 및 [방법: Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
-   <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 사용자 입력의 유효성을 검사합니다.  자세한 내용은 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)를 참조하십시오.  
  
-   가상 모드를 사용하여 대용량 데이터 집합을 처리합니다.  자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)을 참조하십시오.  
  
-   셀의 모양을 사용자 지정합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) 및 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Windows Forms DataGridView 컨트롤의 데이터 입력](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)   
 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)   
 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)