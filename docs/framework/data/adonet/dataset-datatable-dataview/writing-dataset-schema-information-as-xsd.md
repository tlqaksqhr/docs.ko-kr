---
title: "DataSet 스키마 정보를 XSD로 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSet 스키마 정보를 XSD로 작성
<xref:System.Data.DataSet>의 스키마를 XSD\(XML 스키마 정의 언어\) 스키마로 작성하여, 작성한 스키마를 관련된 데이터와 함께 또는 데이터 없이 XML 문서에서 전송할 수 있습니다.  XML 스키마는 파일, 스트림, <xref:System.Xml.XmlWriter> 또는 문자열로 작성될 수 있으며 강력한 형식의 **DataSet**을 생성하는 데 유용합니다.  강력한 형식의 **DataSet** 개체에 대한 자세한 내용은 [형식화된 DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)을 참조하세요.  
  
 <xref:System.Data.DataColumn> 개체의 **ColumnMapping** 속성을 사용하여 XML 스키마에서 테이블의 열을 표현하는 방법을 지정할 수 있습니다.  자세한 내용은 [DataSet 내용을 XML 데이터로 쓰기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)의 "열을 XML 요소, 특성 및 텍스트에 매핑"을 참조하세요.  
  
 **DataSet**의 스키마를 파일, 스트림 또는 **XmlWriter**로 된 XML 스키마로 작성하려면 **DataSet**의 **WriteXmlSchema** 메서드를 사용합니다.  **WriteXmlSchema**는 결과로 나타나는 XML 스키마의 대상을 지정하는 하나의 매개 변수를 사용합니다.  다음 코드 예제에서는 파일 이름이 포함된 문자열과 <xref:System.IO.StreamWriter> 개체를 전달하여 **DataSet**의 XML 스키마를 파일로 작성하는 방법을 보여 줍니다.  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 **DataSet**의 스키마를 가져와서 XML 스키마 문자열로 작성하려면 다음 예제에서와 같이 **GetXmlSchema** 메서드를 사용합니다.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## 참고 항목  
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSet 내용을 XML 데이터로 쓰기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)   
 [형식화된 DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)