---
title: "연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기 | Microsoft Docs"
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
  - "데이터[Windows Forms], 데이터 소스에 바인딩하지 않고 표시"
  - "데이터[Windows Forms], 바인딩되지 않은"
  - "DataGridView 컨트롤[Windows Forms], 데이터 소스에 바인딩하지 않고 데이터 표시"
  - "DataGridView 컨트롤[Windows Forms], 바인딩되지 않은 데이터"
  - "연습[Windows Forms], DataGridView 컨트롤"
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기
데이터베이스로부터 만들어지지 않은 표 형식의 데이터를 표시해야 할 경우가 자주 있습니다.  예를 들어, 문자열로 된 2차원 배열의 내용을 보여 주려는 경우  <xref:System.Windows.Forms.DataGridView> 클래스를 사용하면 데이터 소스에 바인딩하지 않고도 데이터가 표시되는 방식을 쉽게 사용자 지정할 수 있습니다.  이 연습에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 채우고 "바인딩되지 않은" 모드에서 행의 추가와 삭제를 관리하는 방법을 보여 줍니다.  기본적으로 사용자는 새 행을 추가할 수 있습니다.  행을 추가하지 못하게 하려면 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성을 `false`로 설정합니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)를 참조하십시오.  
  
## 폼 만들기  
  
#### 바인딩되지 않은 DataGridView 컨트롤을 사용하려면  
  
1.  <xref:System.Windows.Forms.Form>에서 파생되고 다음 변수 선언과 `Main` 메서드가 포함된 클래스를 만듭니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  폼의 클래스 정의에 폼의 레이아웃을 설정하는 `SetupLayout` 메서드를 구현합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  <xref:System.Windows.Forms.DataGridView> 열과 속성을 설정하는 `SetupDataGridView` 메서드를 만듭니다.  
  
     이 메서드는 먼저 <xref:System.Windows.Forms.DataGridView> 컨트롤을 폼의 <xref:System.Windows.Forms.Control.Controls%2A> 컬렉션에 추가합니다.  그런 다음 <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> 속성을 사용하여 표시할 열의 수를 설정합니다.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 속성에서 반환된 <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> 속성을 설정하여 열 머리글의 기본 스타일을 설정할 수 있습니다.  
  
     레이아웃 속성과 모양 속성이 설정된 다음 열 이름이 할당됩니다.  이 메서드가 종료되면 <xref:System.Windows.Forms.DataGridView> 컨트롤을 채울 수 있습니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  행을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 추가하는 `PopulateDataGridView` 메서드를 만듭니다.  
  
     각 행은 노래와 해당 노래에 관련된 정보를 나타냅니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  적절한 유틸리티 메서드를 사용하여 이벤트 처리기를 연결할 수 있습니다.  
  
     **추가** 및 **삭제** 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트, 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 및 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트를 처리합니다.  
  
     **추가** 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생하면 새로운 빈 행이 <xref:System.Windows.Forms.DataGridView>에 추가됩니다.  
  
     **삭제** 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생하면 선택한 행이 삭제됩니다. 단, 해당 행이 사용자가 새 행을 추가하는 데 사용하는 새 레코드를 위한 행이 아니어야 합니다.  이 행은 항상 <xref:System.Windows.Forms.DataGridView> 컨트롤의 마지막 행입니다.  
  
     폼의 <xref:System.Windows.Forms.Form.Load> 이벤트가 발생하면 `SetupLayout`, `SetupDataGridView` 및 `PopulateDataGridView` 유틸리티 메서드가 호출됩니다.  
  
     <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트가 발생하면 `Date` 열의 각 셀은 자세한 날짜 형식으로 지정됩니다. 이 경우 셀 값을 구문 분석할 수 있어야 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## 응용 프로그램 테스트  
 이제 폼을 테스트하여 예상한 대로 동작하는지 확인할 수 있습니다.  
  
#### 폼을 테스트하려면  
  
-   F5 키를 눌러 응용 프로그램을 실행합니다.  
  
     `PopulateDataGridView`에 나열된 노래를 표시하는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 표시됩니다.  **행 추가** 단추를 사용하여 새 행을 추가할 수 있으며 **행 삭제** 단추를 사용하여 선택한 행을 삭제할 수 있습니다.  바인딩되지 않은 <xref:System.Windows.Forms.DataGridView> 컨트롤은 데이터 저장소이며, 이 컨트롤의 데이터는 <xref:System.Data.DataSet> 또는 배열과 같은 외부 소스에 대해 독립적입니다.  
  
## 다음 단계  
 이 응용 프로그램은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능에 대한 기본적인 이해를 제공합니다.  다음과 같은 여러 가지 방법으로 <xref:System.Windows.Forms.DataGridView> 컨트롤의 모양과 동작을 사용자 지정할 수 있습니다.  
  
-   테두리와 머리글 스타일을 변경합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤의 테두리 및 모눈선 스타일 변경](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)을 참조하십시오.  
  
-   <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 사용자 입력을 활성화하거나 제한합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) 및 [방법: Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
-   사용자 입력에 데이터베이스 관련 오류가 있는지 확인합니다.  자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)를 참조하십시오.  
  
-   가상 모드를 사용하여 대용량 데이터 집합을 처리합니다.  자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)을 참조하십시오.  
  
-   셀의 모양을 사용자 지정합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) 및 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)