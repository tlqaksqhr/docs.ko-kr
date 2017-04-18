---
title: "강력한 형식의 DataSets 생성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# 강력한 형식의 DataSets 생성
XSD\(XML 스키마 정의 언어\) 표준과 호환되는 XML 스키마가 있으면 [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)]에 제공된 XSD.exe 도구를 사용하여 강력한 형식의 <xref:System.Data.DataSet>을 생성할 수 있습니다.  
  
 \(데이터베이스 테이블에서 xsd를 만들려면 <xref:System.Data.DataSet.WriteXmlSchema%2A> 또는 [Visual Studio에서 데이터 집합 작업](http://msdn.microsoft.com/library/8bw9ksd6.aspx)을 참조하세요.\)  
  
 다음 코드는 이 도구를 사용하여 **DataSet**을 생성하는 구문을 보여 줍니다.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 이 구문에서 `/d` 지시문은 도구에 **DataSet**을 생성하라는 것을, `/l:`은 사용할 언어\(예: C\# 또는 Visual Basic .NET\)를 지정합니다.  선택적 `/eld` 지시문은 [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)]을 사용하여 생성된 **DataSet**을 쿼리할 수 있음을 지정합니다. 이 옵션은 `/d` 옵션도 함께 지정한 경우에 사용합니다.  자세한 내용은 [형식화된 데이터 집합 쿼리](../../../../../docs/framework/data/adonet/querying-typed-datasets.md)을 참조하세요.  선택적 지시문인 `/n:`은 도구에 **XSDSchema.Namespace**라는 **DataSet**의 네임스페이스를 생성하라는 것을 지정합니다.  이 명령을 실행하면 XSDSchemaFileName.cs가 생성되며, 이 파일을 컴파일하여 ADO.NET 응용 프로그램에서 사용할 수 있습니다.  생성된 코드는 라이브러리나 모듈로 컴파일할 수 있습니다.  
  
 다음 코드는 생성된 코드를 C\# 컴파일러\(csc.exe\)를 사용하여 라이브러리로 컴파일하는 구문을 보여 줍니다.  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 `/t:` 지시문은 도구에 라이브러리로 컴파일하라는 것을, `/r:` 지시문은 컴파일에 필요한 종속 라이브러리를 지정합니다.  이 명령을 실행하면 XSDSchemaFileName.dll이 생성되며, 이 dll은 `/r:` 지시문으로 ADO.NET 응용 프로그램을 컴파일할 때 컴파일러로 전달할 수 있습니다.  
  
 다음 코드는 ADO.NET 응용 프로그램에서 XSD.exe로 전달된 네임스페이스에 액세스하는 구문을 보여 줍니다.  
  
```vb  
Imports XSDSchema.Namespace  
  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 다음 코드 예제에서는 **CustomerDataSet**이라는 형식화된 **DataSet**을 사용하여 **Northwind** 데이터베이스의 고객 목록을 로드합니다.  **Fill** 메서드를 사용하여 데이터를 로드하면 이 예제는 형식화된 **CustomersRow**\(**DataRow**\) 개체를 사용하여 **Customers** 테이블에 있는 각 고객에 대해 루프를 실행합니다.  그러면 **DataColumnCollection**을 통하지 않고 **CustomerID** 열에 직접 액세스할 수 있습니다.  
  
```vb  
Dim customers As CustomerDataSet= New CustomerDataSet()  
Dim adapter As SqlDataAdapter New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers;", _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=Northwind")  
  
adapter.Fill(customers, "Customers")  
  
Dim customerRow As CustomerDataSet.CustomersRow  
For Each customerRow In customers.Customers  
  Console.WriteLine(customerRow.CustomerID)  
Next  
  
```  
  
```csharp  
CustomerDataSet customers = new CustomerDataSet();  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers;",  
  "Data Source=(local);Integrated " +  
  "Security=SSPI;Initial Catalog=Northwind");  
  
adapter.Fill(customers, "Customers");  
  
foreach(CustomerDataSet.CustomersRow customerRow in customers.Customers)  
  Console.WriteLine(customerRow.CustomerID);  
```  
  
 다음은 예제에서 사용한 XML 스키마입니다.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## 참고 항목  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataSet>   
 [형식화된 DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)