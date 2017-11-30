---
title: "연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c602af6799da57fec904c87da7bed77c0040eff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리
내부 데이터 저장소에서 오류를 처리 하는 것은 데이터 입력 응용 프로그램에 대 한 필수 기능입니다. Windows Forms <xref:System.Windows.Forms.DataGridView> 제어 작업을 편리 노출 하 여는 <xref:System.Windows.Forms.DataGridView.DataError> 데이터 저장소는 비즈니스 규칙 또는 제약 조건 위반을 감지할 때 발생 하는 이벤트입니다.  
  
 이 연습에서는 행을 검색 합니다는 `Customers` Northwind 샘플 데이터베이스의 테이블을 표시 한 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 에 중복 된 `CustomerID` 새 행 이나는 편집된 된 기존 행에 값이 검색 되는 <xref:System.Windows.Forms.DataGridView.DataError> 표시 하 여 처리 되는 이벤트가 발생 합니다는 <xref:System.Windows.Forms.MessageBox> 예외를 설명 하는 합니다.  
  
 단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: 처리 오류는 발생 하는 동안 데이터 입력 Windows Forms DataGridView 컨트롤에서](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind SQL Server 예제 데이터베이스에 있는 서버에 액세스 합니다.  
  
## <a name="creating-the-form"></a>폼 만들기  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>DataGridView 컨트롤에서 데이터 입력 오류를 처리 하려면  
  
1.  파생 되는 클래스를 만듭니다 <xref:System.Windows.Forms.Form> 포함 한 <xref:System.Windows.Forms.DataGridView> 제어 및 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.  
  
     다음 코드 예제에서는 기본 초기화를 제공 하 고 포함 된 `Main` 메서드.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  폼의 클래스 정의 처리 하는 데이터베이스에 대 한 연결 정보에는 메서드를 구현 합니다.  
  
     사용 하 여이 코드 예제는 `GetData` 채워진 반환 하는 메서드 <xref:System.Data.DataTable> 개체입니다. 설정 하는 `connectionString` 변수를 사용 중인 데이터베이스에 대 한 적합 한 값입니다.  
  
    > [!IMPORTANT]
    >  암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)를 참조하세요.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  폼의에 대 한 처리기를 구현 <xref:System.Windows.Forms.Form.Load> 초기화 하는 이벤트는 <xref:System.Windows.Forms.DataGridView> 및 <xref:System.Windows.Forms.BindingSource> 데이터 바인딩을 가져오거나 설정 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  처리는 <xref:System.Windows.Forms.DataGridView.DataError> 이벤트에는 <xref:System.Windows.Forms.DataGridView>합니다.  
  
     오류에 대 한 컨텍스트가 커밋 작업에 오류를 표시 한 <xref:System.Windows.Forms.MessageBox>합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이제 예상 대로 동작 되도록 폼을 테스트할 수 있습니다.  
  
#### <a name="to-test-the-form"></a>양식을 테스트 하려면  
  
-   F5 키를 눌러 응용 프로그램을 실행합니다.  
  
     표시 됩니다는 <xref:System.Windows.Forms.DataGridView> Customers 테이블의 데이터로 채워진 제어 합니다. 에 대 한 중복 값을 입력 하면 `CustomerID` 및 편집, 셀 값을 자동으로 되돌아갑니다 커밋하고 표시 됩니다는 <xref:System.Windows.Forms.MessageBox> 데이터 입력 오류를 표시 하는 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 응용 프로그램에서는 기본적으로 이해는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능입니다. 모양 및 동작을 사용자 지정할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 여러 가지 방법으로 제어 합니다.  
  
-   테두리 및 머리글 스타일을 변경 합니다. 자세한 내용은 참조 [하는 방법: 테두리 및 눈금선 스타일 Windows Forms DataGridView 컨트롤에서 변경](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)합니다.  
  
-   사용 하거나 사용자 입력을 제한 된 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 자세한 내용은 참조 [하는 방법: 행 추가 및 삭제 금지 Windows Forms DataGridView 컨트롤에서](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), 및 [하는 방법: 열을 읽기 전용 Windows Forms DataGridView 컨트롤에서](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)합니다.  
  
-   에 대 한 사용자 입력 유효성 검사는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 자세한 내용은 참조 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)합니다.  
  
-   가상 모드를 사용 하 여 매우 큰 데이터 집합을 처리 합니다. 자세한 내용은 참조 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)합니다.  
  
-   셀의 모양을 사용자 지정 합니다. 자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) 및 [하는 방법: Windows Forms DataGridView 컨트롤에 대 한 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Windows Forms DataGridView 컨트롤의 데이터 입력](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)
