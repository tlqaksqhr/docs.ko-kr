---
title: "방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩 | Microsoft Docs"
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
  - "바인딩 컨트롤"
  - "바인딩 컨트롤, DataGrid 컨트롤"
  - "데이터 바인딩, DataGrid 컨트롤"
  - "데이터 바인딩 컨트롤, DataGrid"
  - "DataGrid 컨트롤[Windows Forms], 데이터 바인딩"
  - "데이터 집합[Windows Forms], DataGrid 컨트롤에 바인딩"
  - "Windows Forms 컨트롤, 데이터 바인딩"
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤은 데이터 소스의 정보를 표시하도록 특별히 디자인된 컨트롤입니다.  런타임에 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 호출하여 컨트롤을 바인딩합니다.  다양한 데이터 소스의 데이터를 표시할 수 있지만 가장 일반적인 소스는 데이터 집합과 데이터 뷰입니다.  
  
### 프로그래밍 방식으로 DataGrid 컨트롤을 데이터 바인딩하려면  
  
1.  데이터 집합을 채우는 코드를 작성합니다.  
  
     데이터 소스가 데이터 집합이거나 데이터 집합 테이블에 기반하는 데이터 뷰인 경우에는 데이터 집합을 채우는 코드를 폼에 추가합니다.  
  
     이때 사용할 올바른 코드는 데이터 집합이 데이터를 가져오는 위치에 따라 다릅니다.  데이터베이스에서 직접 데이터 집합을 채우는 경우에는 아래 예제에서 볼 수 있는 것과 같이 일반적으로 `DsCategories1`이라는 데이터 집합을 채우는 데이터 어댑터의 `Fill`  메서드를 호출합니다.  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     XML Web services에서 데이터 집합을 채우는 경우에는 일반적으로 코드에서 서비스의 인스턴스를 만든 다음 메서드 중 하나를 호출하여 데이터 집합을 반환합니다.  그런 다음 XML Web services의 데이터 집합을 로컬 데이터 집합에 병합합니다.  다음 예제에서는 `CategoriesService`라는 XML Web services의 인스턴스를 만들고 이 인스턴스의 `GetCategories` 메서드를 호출한 다음 반환되는 데이터 집합을 `DsCategories1`이라는 로컬 데이터 집합에 병합하는 방법을 보여 줍니다.  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2.  <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 호출하여 데이터 소스와 데이터 멤버를 전달합니다.  데이터 멤버를 명시적으로 전달할 필요가 없는 경우에는 빈 문자열을 전달합니다.  
  
    > [!NOTE]
    >  데이터 표를 처음 바인딩하는 경우에는 컨트롤의 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 설정할 수 있습니다.  그러나 이 속성은 한 번 설정하면 다시 설정할 수 없습니다.  따라서 항상 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 사용하는 것이 좋습니다.  
  
     다음 예제에서는 `DsCustomers1`이라는 데이터 집합에 있는 Customers 테이블에 프로그래밍 방식으로 바인딩하는 방법을 보여 줍니다.  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     데이터 집합에 Customers 테이블만 있는 경우에는 다음과 같은 방법으로 데이터 표를 바인딩할 수도 있습니다.  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  선택적으로, 데이터 표에 적절한 테이블 스타일과 열 스타일을 추가합니다.  테이블 스타일이 없는 상태에서 테이블을 보면 최소한의 형식이 지정된 상태로 모든 열이 표시되는 것을 볼 수 있습니다.  
  
## 참고 항목  
 [DataGrid 컨트롤 개요](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Windows Forms 데이터 바인딩](../../../../docs/framework/winforms/windows-forms-data-binding.md)