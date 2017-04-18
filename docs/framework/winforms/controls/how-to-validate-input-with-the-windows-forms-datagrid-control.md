---
title: "방법: Windows Forms DataGrid 컨트롤을 사용하여 입력 유효성 검사 | Microsoft Docs"
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
  - "DataGrid 컨트롤[Windows Forms], 예제"
  - "DataGrid 컨트롤[Windows Forms], 입력 유효성 검사"
  - "예제[Windows Forms], DataGrid 컨트롤"
  - "사용자 입력, 유효성 검사"
  - "유효성 검사, 사용자 입력"
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms DataGrid 컨트롤을 사용하여 입력 유효성 검사
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤에서는 두 가지 유형의 입력 유효성 검사를 수행할 수 있습니다.  정수 형식의 셀에 문자열을 입력하는 경우처럼 사용자가 해당 셀에 적합하지 않은 데이터 형식의 값을 입력하면 잘못된 값이 이전 값으로 대체됩니다.  이 유효성 검사는 자동으로 수행되며 사용자 지정할 수 없습니다.  
  
 또한 1보다 크거나 같은 값을 입력해야 하는 필드에 0을 입력하는 경우처럼 적합하지 않은 데이터나 잘못된 문자열을 입력하지 못하도록 하는 데 사용할 수 있는 유효성 검사도 있습니다.  이 유효성 검사는 데이터 집합에서 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 이벤트에 대한 이벤트 처리기를 작성하여 수행됩니다.  아래 예제에서는 특히 "Product" 열에 허용되는 값을 사용해야 하므로 <xref:System.Data.DataTable.ColumnChanging> 이벤트를 사용하여 입력 유효성을 검사합니다.  <xref:System.Data.DataTable.RowChanging> 이벤트를 사용하여 "End Date" 열의 날짜가 같은 행에 있는 "Start Date" 열의 날짜보다 나중인지 여부를 검사할 수도 있습니다.  
  
### 사용자 입력의 유효성을 검사하려면  
  
1.  해당 테이블의 <xref:System.Data.DataTable.ColumnChanging> 이벤트를 처리하는 코드를 작성합니다.  입력한 내용이 적합하지 않을 경우 <xref:System.Data.DataRow> 개체의 <xref:System.Data.DataRow.SetColumnError%2A> 메서드를 호출합니다.  
  
    ```vb  
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _  
    ByVal e As System.Data.DataColumnChangeEventArgs)  
       ' Only check for errors in the Product column  
       If (e.Column.ColumnName.Equals("Product")) Then  
          ' Do not allow "Automobile" as a product.  
          If CType(e.ProposedValue, String) = "Automobile" Then  
             Dim badValue As Object = e.ProposedValue  
             e.ProposedValue = "Bad Data"  
             e.Row.RowError = "The Product column contians an error"  
             e.Row.SetColumnError(e.Column, "Product cannot be " & _  
             CType(badValue, String))  
          End If  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    //Handle column changing events on the Customers table  
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {  
  
       //Only check for errors in the Product column  
       if (e.Column.ColumnName.Equals("Product")) {  
  
          //Do not allow "Automobile" as a product  
          if (e.ProposedValue.Equals("Automobile")) {  
             object badValue = e.ProposedValue;  
             e.ProposedValue = "Bad Data";  
             e.Row.RowError = "The Product column contains an error";  
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);  
          }  
       }  
    }  
  
    ```  
  
2.  이벤트 처리기를 이벤트에 연결합니다.  
  
     다음 코드를 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 또는 생성자에 배치합니다.  
  
    ```vb  
    ' Assumes the grid is bound to a dataset called customersDataSet1  
    ' with a table called Customers.  
    ' Put this code in the form's Load event or its constructor.  
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging  
  
    ```  
  
    ```csharp  
    // Assumes the grid is bound to a dataset called customersDataSet1  
    // with a table called Customers.  
    // Put this code in the form's Load event or its constructor.  
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGrid>   
 <xref:System.Data.DataTable.ColumnChanging>   
 <xref:System.Data.DataRow.SetColumnError%2A>   
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)