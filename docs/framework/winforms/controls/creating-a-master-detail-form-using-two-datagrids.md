---
title: "연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 폼 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
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
  - "DataGridView 컨트롤[Windows Forms], 마스터/세부 폼"
  - "마스터-세부 목록, Windows Forms에 표시"
  - "부모-자식 표, Windows Forms에 표시"
  - "연습[Windows Forms], DataGridView 컨트롤"
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 폼 만들기
<xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하는 가장 일반적인 시나리오 중 하나는 두 데이터베이스 테이블의 부모\/자식 관계가 표시되는 *마스터\/세부* 폼입니다.  마스터 테이블에서 행을 선택하면 세부 테이블이 해당 자식 데이터를 사용하여 업데이트됩니다.  
  
 마스터\/세부 폼은 <xref:System.Windows.Forms.DataGridView> 컨트롤과 <xref:System.Windows.Forms.BindingSource> 구성 요소의 상호 작용을 사용하여 쉽게 구현할 수 있습니다.  이 연습에서는 두 개의 <xref:System.Windows.Forms.DataGridView> 컨트롤과 두 개의 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 폼을 만듭니다.  이 폼에는 Northwind SQL Server 샘플 데이터베이스에 있는 `Customers`와 `Orders`라는 두 개의 관련 테이블이 표시됩니다.  연습을 모두 완료하면 데이터베이스의 모든 고객이 마스터 <xref:System.Windows.Forms.DataGridView>에 표시되고 선택한 고객의 모든 주문이 세부 <xref:System.Windows.Forms.DataGridView>에 표시됩니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터\/세부 폼 만들기](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagrids.md)를 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   Northwind SQL Server 샘플 데이터베이스가 있는 서버에 액세스할 수 있어야 합니다.  
  
## 폼 만들기  
  
#### 마스터\/세부 폼을 만들려면  
  
1.  <xref:System.Windows.Forms.Form>에서 파생되고 두 개의 <xref:System.Windows.Forms.DataGridView> 컨트롤과 두 개의 <xref:System.Windows.Forms.BindingSource> 구성 요소를 포함하는 클래스를 만듭니다.  다음 코드는 기본 폼 초기화를 제공하고 `Main` 메서드를 포함합니다.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 디자이너를 사용하여 폼을 만들 경우 이 코드 대신 디자이너 생성 코드를 사용할 수 있습니다. 그럴 경우에는 이 코드의 변수 선언에 표시된 이름을 사용해야 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  데이터베이스에 연결하는 데 필요한 세부 사항을 처리할 수 있도록 메서드를 폼의 클래스 정의에 구현합니다.  이 예제에서는 `GetData` 메서드를 사용하여 <xref:System.Data.DataSet> 개체를 채우고 <xref:System.Data.DataRelation> 개체를 데이터 집합에 추가한 다음 <xref:System.Windows.Forms.BindingSource> 구성 요소를 바인딩합니다.  `connectionString` 변수를 데이터베이스에 해당하는 값으로 설정해야 합니다.  
  
    > [!IMPORTANT]
    >  연결 문자열에 중요한 정보\(예: 암호\)를 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.  데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.  자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)을 참조하십시오.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  <xref:System.Windows.Forms.DataGridView> 컨트롤을 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩하고 `GetData` 메서드를 호출하도록 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기를 구현합니다.  다음 예제에는 표시된 데이터에 맞게 <xref:System.Windows.Forms.DataGridView> 열의 크기를 조정하는 코드가 들어 있습니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## 응용 프로그램 테스트  
 이제 폼을 테스트하여 예상한 대로 동작하는지 확인할 수 있습니다.  
  
#### 폼을 테스트하려면  
  
-   응용 프로그램을 컴파일하여 실행합니다.  
  
     두 개의 <xref:System.Windows.Forms.DataGridView> 컨트롤이 위아래로 나란히 표시됩니다.  위쪽 컨트롤에는 Northwind `Customers` 테이블에 있는 고객이 표시되고, 아래쪽 컨트롤에는 선택한 고객에 해당하는 `Orders`가 표시됩니다.  위쪽 <xref:System.Windows.Forms.DataGridView>에서 다른 행을 선택하면 그에 따라 아래쪽 <xref:System.Windows.Forms.DataGridView>의 내용이 바뀝니다.  
  
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
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [방법: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터\/세부 폼 만들기](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagrids.md)   
 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)