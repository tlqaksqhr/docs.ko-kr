---
title: "방법: Windows Forms DataGrid 컨트롤을 사용하여 마스터/세부 목록 만들기 | Microsoft Docs"
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
  - "DataGrid 컨트롤[Windows Forms], 마스터-세부 목록"
  - "마스터-세부 목록"
  - "관계 테이블, DataGrid 컨트롤에 표시"
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Forms DataGrid 컨트롤을 사용하여 마스터/세부 목록 만들기
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 <xref:System.Data.DataSet>에 일련의 관련된 테이블이 포함된 경우에는 두 개의 <xref:System.Windows.Forms.DataGrid> 컨트롤을 사용하여 데이터를 마스터\/세부 형식으로 표시할 수 있습니다.  <xref:System.Windows.Forms.DataGrid> 하나는 마스터 데이터 표이고 다른 하나는 세부 데이터 표입니다.  마스터 목록에서 항목을 선택하면 관련된 자식 항목이 모두 세부 목록에 표시됩니다.  예를 들어, <xref:System.Data.DataSet>에 Customers 테이블과 이 테이블에 관련된 Orders 테이블이 있는 경우에는 Customers 테이블을 마스터 데이터 표로 지정하고 Orders 테이블을 세부 데이터 표로 지정할 수 있습니다.  마스터 데이터 표에서 고객을 선택하면 해당 고객과 관련된 Order 테이블의 모든 주문이 세부 데이터 표에 표시됩니다.  
  
### 프로그래밍 방식으로 마스터\/세부 관계를 설정하려면  
  
1.  두 개의 새 <xref:System.Windows.Forms.DataGrid> 컨트롤을 만들고 각각의 속성을 설정합니다.  
  
2.  데이터 집합에 테이블을 추가합니다.  
  
3.  만들 관계를 나타내는 <xref:System.Data.DataRelation> 형식의 변수를 선언합니다.  
  
4.  관계에 대한 이름을 지정하고 테이블, 열 및 두 테이블을 연결해 주는 항목을 지정하여 관계를 인스턴스화합니다.  
  
5.  만든 관계를 <xref:System.Data.DataSet> 개체의 <xref:System.Data.DataSet.Relations%2A> 컬렉션에 추가합니다.  
  
6.  <xref:System.Windows.Forms.DataGrid>의 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 사용하여 각 데이터 표를 <xref:System.Data.DataSet>에 바인딩합니다.  
  
     다음 예제에서는 이전에 생성한 <xref:System.Data.DataSet>\(`ds`\)에서 Customers 및 Orders 테이블 사이의 마스터\/세부 관계를 설정하는 방법을 보여 줍니다.  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## 참고 항목  
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [DataGrid 컨트롤 개요](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)