---
title: '연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용 하 여 마스터-세부 폼 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: 38f7c6197fb3ee79119e41ab9620bc3aa2b21900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529443"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 폼 만들기
사용 하기 위한 가장 일반적인 시나리오 중 하나는 <xref:System.Windows.Forms.DataGridView> 컨트롤은는 *마스터/세부* 폼을 두 개의 데이터베이스 테이블 간의 부모/자식 관계 표시 됩니다. 마스터 테이블에서 행을 선택 하면 해당 자식 데이터로 업데이트할 세부 테이블 합니다.  
  
 마스터/세부 폼을 구현 하는 것은 간의 상호 작용을 사용 하 여 쉽게는 <xref:System.Windows.Forms.DataGridView> 제어 및 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. 이 연습에서는 두 개를 사용 하 여 폼 빌드됩니다 <xref:System.Windows.Forms.DataGridView> 컨트롤과 두 개의 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. Northwind SQL Server 예제 데이터베이스의 테이블을 관련 된 두 양식에 표시 됩니다: `Customers` 및 `Orders`합니다. 완료 되 면 master에서 데이터베이스의 모든 고객을 표시 하는 폼 갖습니다 <xref:System.Windows.Forms.DataGridView> 및 세부 정보에 선택한 고객에 대 한 모든 주문 <xref:System.Windows.Forms.DataGridView>합니다.  
  
 단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법:는 마스터/세부 폼을 사용 하 여 두 개의 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind SQL Server 예제 데이터베이스에 있는 서버에 액세스 합니다.  
  
## <a name="creating-the-form"></a>폼 만들기  
  
#### <a name="to-create-a-masterdetail-form"></a>마스터/세부 폼을 만들려면  
  
1.  파생 되는 클래스를 만듭니다 <xref:System.Windows.Forms.Form> 두 개가 포함 및 <xref:System.Windows.Forms.DataGridView> 컨트롤과 두 개의 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. 기본 폼 초기화를 제공 하 고 포함 하는 다음 코드는 `Main` 메서드. 폼을 만드는 데 Visual Studio 디자이너를 사용 하는 경우이 코드 대신 디자이너 생성된 코드를 사용할 수 있지만 변수 선언에 여기에 나열 된 이름을 사용 하십시오.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  데이터베이스에 연결 하는 정보를 처리 하기 위한 폼의 클래스 정의에 메서드를 구현 합니다. 사용 하 여이 예제는 `GetData` 정보를 표시 하는 메서드는 <xref:System.Data.DataSet> 개체를 추가 하는 <xref:System.Data.DataRelation> 데이터 집합 및 바인딩 개체를는 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. `connectionString` 변수를 사용자의 데이터베이스에 적합한 값으로 설정해야 합니다.  
  
    > [!IMPORTANT]
    >  암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)를 참조하세요.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  폼의에 대 한 처리기를 구현 <xref:System.Windows.Forms.Form.Load> 바인딩하는 이벤트는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 <xref:System.Windows.Forms.BindingSource> 구성 요소와 호출 된 `GetData` 메서드. 다음 예제에서는 크기를 조정 하는 코드를 포함 <xref:System.Windows.Forms.DataGridView> 에 표시 된 데이터에 맞게 열 조정 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이제 예상 대로 동작 되도록 폼을 테스트할 수 있습니다.  
  
#### <a name="to-test-the-form"></a>양식을 테스트 하려면  
  
-   응용 프로그램을 컴파일하고 실행합니다.  
  
     두 개의 나타납니다 <xref:System.Windows.Forms.DataGridView> 상하로 제어 합니다. 위에 표시 되는 northwind customers `Customers` 테이블을 마우스는 맨 아래에 `Orders` 선택한 고객에 해당 하 합니다. 위에 있는 다른 행을 선택 하는 대로 <xref:System.Windows.Forms.DataGridView>, 더 작은 값의 내용을 <xref:System.Windows.Forms.DataGridView> 적절 하 게 변경 합니다.  
  
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
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [방법: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 폼 만들기](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md)  
 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)
