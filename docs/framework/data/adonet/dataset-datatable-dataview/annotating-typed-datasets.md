---
title: "형식화된 DataSets 주석 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# 형식화된 DataSets 주석 지정
주석을 사용하면 원본으로 사용하는 스키마를 수정하지 않고 형식화된 <xref:System.Data.DataSet>의 요소 이름을 수정할 수 있습니다.  원본으로 사용하는 스키마의 요소 이름을 수정하면 형식화된 **DataSet**에서 데이터 소스에 없는 개체를 참조하게 되며 데이터 소스에 실제로 있는 개체에 대한 참조는 손실됩니다.  
  
 주석을 사용하면 원본으로 사용하는 스키마를 변경하지 않고도 형식화된 **DataSet**에 있는 개체의 이름을 보다 의미 있는 이름으로 사용자 지정하고, 코드의 가독성을 높이며 형식화된 **DataSet**을 고객이 더 쉽게 사용하도록 만들 수 있습니다.  예를 들어, **Northwind** 데이터베이스의 **Customers** 테이블에 대한 다음 스키마 요소의 경우 **DataRow** 개체의 이름은 **CustomersRow**가 되고 <xref:System.Data.DataRowCollection>의 이름은 **Customers**가 됩니다.  
  
```  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 **Customers**라는 **DataRowCollection** 이름은 클라이언트 코드에서는 의미가 있지만 **DataRow**의 경우 단일 개체이므로 **CustomersRow**라는 이름이 혼동을 가져올 수 있습니다.  또한 일반적인 시나리오에서 이 개체는 **Row** 식별자 없이 참조될 수 있고, 대신 **Customer** 개체로 간단히 참조될 수 있습니다.  이를 해결하는 방법은 스키마에 주석을 달고 **DataRow** 및 **DataRowCollection** 개체의 새 이름을 식별하는 것입니다.  다음 코드는 이전 스키마에 주석을 단 것입니다.  
  
```  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 **typedName** 값을 **Customer**로 지정하면 **DataRow** 개체 이름이 **Customer**가 됩니다.  **typedPlural** 값을 **Customers**로 지정하면 **DataRowCollection** 이름이 **Customers**로 유지됩니다.  
  
 다음 표에서는 사용할 수 있는 주석을 보여 줍니다.  
  
|주석|설명|  
|--------|--------|  
|**typedName**|개체의 이름입니다.|  
|**typedPlural**|개체 컬렉션의 이름입니다.|  
|**typedParent**|부모 관계에서 참조될 때의 개체 이름입니다.|  
|**typedChildren**|자식 관계에서 개체를 반환하기 위한 메서드의 이름입니다.|  
|**nullValue**|원본으로 사용하는 값이 **DBNull**인 경우의 값입니다.  **nullValue** 주석에 대해서는 다음 표를 참조하세요.  기본값은 **\_throw**입니다.|  
  
 다음 표에서는 **nullValue** 주석에 지정할 수 있는 값을 보여 줍니다.  
  
|nullValue 값|설명|  
|-----------------|--------|  
|*Replacement Value*|반환될 값을 지정합니다.  반환되는 값은 요소의 형식과 일치해야 합니다.  예를 들어, `nullValue="0"`을 사용하여 null 정수 필드에 0을 반환합니다.|  
|**\_throw**|예외를 throw합니다.  이 값이 기본값입니다.|  
|**\_null**|기본 형식이 발견되면 null 참조를 반환하거나 예외를 throw합니다.|  
|**\_empty**|문자열인 경우 **String.Empty**를 반환하고, 그렇지 않으면 빈 생성자에서 만든 개체를 반환합니다.  기본 형식이 발견되면 예외를 throw합니다.|  
  
 다음 표에서는 형식화된 **DataSet**에 있는 개체에 대한 기본값과 사용 가능한 주석을 보여 줍니다.  
  
|개체\/메서드\/이벤트|기본|주석|  
|------------------|--------|--------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**DataTable** Methods|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**DataRow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**속성**|PropertyName|typedName|  
|**Child** Accessor|GetChildTableNameRows|typedChildren|  
|**Parent** 접근자|TableNameRow|typedParent|  
|**DataSet** 이벤트|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 형식화된 **DataSet** 주석을 사용하려면 다음 **xmlns** 참조를 사용자의 XSD\(XML 스키마 정의 언어\) 스키마에 포함시켜야 합니다.  \(데이터베이스 테이블에서 xsd를 만들려면 <xref:System.Data.DataSet.WriteXmlSchema%2A> 또는 [Visual Studio에서 데이터 집합 작업](http://msdn.microsoft.com/library/8bw9ksd6.aspx)을 참조하세요.\)  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 다음은 포함된 **Orders** 테이블에 대한 관계와 함께 **Northwind** 데이터베이스의 **Customers** 테이블을 노출하는, 주석이 있는 샘플 스키마입니다.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"   
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""   
      xmlns:xs="http://www.w3.org/2001/XMLSchema"   
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer"  
codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone"  
codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order"  
codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"  
                 codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"   
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter"  
codegen:nullValue="1980-01-01T00:00:00"   
type="xs:dateTime" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Customers" />  
      <xs:field xpath="CustomerID" />  
    </xs:unique>  
    <xs:keyref name="CustOrders" refer="Constraint1"  
codegen:typedParent="Customer" codegen:typedChildren="GetOrders">  
      <xs:selector xpath=".//Orders" />  
      <xs:field xpath="CustomerID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 다음 코드 예제에서는 샘플 스키마에서 만든 강력한 형식의 **DataSet**을 사용합니다.  이 코드에서는 하나의 <xref:System.Data.SqlClient.SqlDataAdapter>를 사용하여 **Customers** 테이블을 채우고 다른 <xref:System.Data.SqlClient.SqlDataAdapter>를 사용하여 **Orders** 테이블을 채웁니다.  **DataRelations**는 강력한 형식의 **DataSet**에서 정의합니다.  
  
```vb  
' Assumes a valid SqlConnection object named connection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT CustomerID, CompanyName, Phone FROM Customers", &  
    connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders", &  
    connection)  
  
' Populate a strongly typed DataSet.  
connection.Open()  
Dim customers As CustomerDataSet = New CustomerDataSet()  
customerAdapter.Fill(customers, "Customers")  
orderAdapter.Fill(customers, "Orders")  
connection.Close()  
  
' Add a strongly typed event.  
AddHandler customers.Customers.CustomerChanged, &  
    New CustomerDataSet.CustomerChangeEventHandler( _  
    AddressOf OnCustomerChanged)  
  
' Add a strongly typed DataRow.  
Dim newCustomer As CustomerDataSet.Customer = _  
    customers.Customers.NewCustomeromer()  
newCustomer.CustomerID = "NEW01"  
newCustomer.CompanyName = "My New Company"  
customers.Customers.AddCustomer(newCustomer)  
  
' Navigate the child relation.  
Dim customer As CustomerDataSet.Customer  
Dim order As CustomerDataSet.Order  
  
For Each customer In customers.Customers  
  Console.WriteLine(customer.CustomerID)  
  For Each order In customer.GetOrders()  
    Console.WriteLine(vbTab & order.OrderID)  
  Next  
Next  
  
Private Shared Sub OnCustomerChanged( _  
    sender As Object, e As CustomerDataSet.CustomerChangeEvent)  
  
End Sub  
  
```  
  
```csharp  
// Assumes a valid SqlConnection object named connection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
    "SELECT CustomerID, CompanyName, Phone FROM Customers",  
    connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders",   
    connection);  
  
// Populate a strongly typed DataSet.  
connection.Open();  
CustomerDataSet customers = new CustomerDataSet();  
customerAdapter.Fill(customers, "Customers");  
orderAdapter.Fill(customers, "Orders");  
connection.Close();  
  
// Add a strongly typed event.  
customers.Customers.CustomerChanged += new   
  CustomerDataSet.CustomerChangeEventHandler(OnCustomerChanged);  
  
// Add a strongly typed DataRow.  
CustomerDataSet.Customer newCustomer =   
    customers.Customers.NewCustomeromer();  
newCustomer.CustomerID = "NEW01";  
newCustomer.CompanyName = "My New Company";  
customers.Customers.AddCustomer(newCustomer);  
  
// Navigate the child relation.  
foreach(CustomerDataSet.Customer customer in customers.Customers)  
{  
  Console.WriteLine(customer.CustomerID);  
  foreach(CustomerDataSet.Order order in customer.GetOrders())  
    Console.WriteLine("\t" + order.OrderID);  
}  
  
protected static void OnCustomerChanged(object sender, CustomerDataSet.CustomerChangeEvent e)  
    {  
  
    }  
```  
  
## 참고 항목  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataSet>   
 [형식화된 DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)