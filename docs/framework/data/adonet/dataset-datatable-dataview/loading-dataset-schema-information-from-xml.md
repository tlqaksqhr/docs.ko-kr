---
title: "XML로부터 DataSet 스키마 정보 로드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# XML로부터 DataSet 스키마 정보 로드
<xref:System.Data.DataSet>의 스키마\(테이블, 열, 관계 및 제약 조건\)는 프로그래밍 방식으로 정의할 수도 있고, <xref:System.Data.Common.DataAdapter>의 **Fill** 또는 **FillSchema** 메서드를 사용하여 만들거나 XML 문서에서 로드할 수도 있습니다.  XML 문서로부터 **DataSet** 스키마 정보를 로드하기 위해 **DataSet**의 **ReadXmlSchema** 또는 **InferXmlSchema** 메서드를 사용할 수 있습니다.  **ReadXmlSchema**를 사용하면 XSD\(XML 스키마 정의 언어\) 스키마가 있는 문서나 인라인 XML 스키마가 있는 XML 문서로부터 **DataSet** 스키마 정보를 로드하거나 유추할 수 있습니다.  **InferXmlSchema**를 사용하면 지정한 특정 XML 네임스페이스는 무시하고 XML 문서로부터 스키마를 유추할 수 있습니다.  
  
> [!NOTE]
>  XSD 생성자를 사용하여 메모리 내에 생성된 **DataSet**\(예: 중첩 관계\)을 웹 서비스나 XML serialization을 통해 전송할 때는 **DataSet**의 테이블 순서가 유지되지 않을 수도 있습니다.  따라서 이와 같은 경우에는 **DataSet**을 받는 사용자가 테이블 순서를 신뢰하지 않아야 합니다.  하지만 메모리 내에 생성하는 대신 전송하는 **DataSet**의 스키마를 XSD 파일에서 읽는 경우에는 항상 테이블 순서가 유지됩니다.  
  
## ReadXmlSchema  
 데이터는 로드하지 않고 **DataSet**의 스키마만 XML 문서로부터 로드하려면 **DataSet**의 **ReadXmlSchema** 메서드를 사용합니다.  **ReadXmlSchema** 메서드는 XSD\(XML 스키마 정의 언어\) 스키마를 사용하여 정의한 **DataSet** 스키마를 만듭니다.  
  
 **ReadXmlSchema** 메서드는 로드할 XML 문서가 포함된 파일 이름, 스트림 또는 **XmlReader**를 단일 인수로 사용합니다.  XML 문서에는 스키마만 있을 수도 있고 데이터가 포함된 XML 요소를 가진 스키마 인라인이 있을 수도 있습니다.  인라인 스키마를 XML 스키마로 작성하는 방법에 대한 자세한 내용은 [XSD\(XML 스키마\)에서 DataSet 관계형 구조 파생](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)을 참조하세요.  
  
 **ReadXmlSchema**로 전달된 XML 문서에 인라인 스키마 정보가 없으면 **ReadXmlSchema**에서 XML 문서 내의 요소로부터 스키마를 유추합니다.  **DataSet**에 이미 스키마가 있으면 새 테이블을 추가하여\(없는 경우\) 현재 스키마를 확장합니다.  새 열은 기존 테이블에 추가되지 않습니다.  추가되는 열이 **DataSet**에 이미 있지만 XML에 있는 열과 형식이 호환되지 않으면 예외가 throw됩니다.  **ReadXmlSchema**가 XML 문서로부터 스키마를 유추하는 방법에 대한 자세한 내용은 [XML에서 DataSet 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)를 참조하세요.  
  
 **ReadXmlSchema**가 **DataSet**의 스키마만 로드하거나 유추하는 반면, **DataSet**의 **ReadXml** 메서드는 XML 문서에 있는 스키마와 데이터를 모두 로드하거나 유추합니다.  자세한 내용은 [XML로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)을 참조하세요.  
  
 다음 코드 예제에서는 XML 문서나 스트림으로부터 **DataSet** 스키마를 로드하는 방법을 보여 줍니다.  첫 번째 예제에서는 **ReadXmlSchema** 메서드로 전달될 XML 스키마 파일 이름을 보여 줍니다.  두 번째 예제에서는 **System.IO.StreamReader**를 보여 줍니다.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema(xmlStream)  
xmlStream.Close()  
```  
  
```csharp  
System.IO.StreamReader xmlStream = new System.IO.StreamReader("schema.xsd");  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema(xmlStream);  
xmlStream.Close();  
```  
  
## InferXmlSchema  
 **DataSet**의 **InferXmlSchema** 메서드를 사용하여 XML 문서로부터 해당 스키마를 유추하도록 **DataSet**을 지정할 수도 있습니다.  **InferXmlSchema**는 읽을 문서에 인라인 스키마가 없는 경우 **InferSchema**가 **XmlReadMode**로 설정된 **ReadXml**\(데이터 로드 및 스키마 유추\) 및 **ReadXmlSchema**와 동일하게 작동합니다.  그러나 **InferXmlSchema**의 추가 기능을 사용하면 스키마를 유추할 때 무시할 특정 XML 네임스페이스를 지정할 수 있습니다.  **InferXmlSchema**는 두 개의 필수 인수를 사용하는데, 하나는 파일 이름, 스트림 또는 **XmlReader**로 지정하는 XML 문서의 위치이고 다른 하나는 처리 중 무시될 XML 네임스페이스의 문자열 배열입니다.  
  
 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```  
<NewDataSet xmlns:od="urn:schemas-microsoft-com:officedata">  
<Categories>  
  <CategoryID od:adotype="3">1</CategoryID>   
  <CategoryName od:maxLength="15" od:adotype="130">Beverages</CategoryName>   
  <Description od:adotype="203">Soft drinks and teas</Description>   
</Categories>  
<Products>  
  <ProductID od:adotype="20">1</ProductID>   
  <ReorderLevel od:adotype="3">10</ReorderLevel>   
  <Discontinued od:adotype="11">0</Discontinued>   
</Products>  
</NewDataSet>  
```  
  
 이전 XML 문서의 요소에 대해 지정된 특성으로 인해, **InferSchema**가 **XmlReadMode**로 설정된 **ReadXml** 메서드와 **ReadXmlSchema** 메서드는 모두 문서의 모든 요소\(**Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel** 및 **Discontinued**\)에 대해 테이블을 만듭니다.  자세한 내용은 [XML에서 DataSet 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)을 참조하세요. 그러나, 보다 적합한 구조는 **Categories** 및 **Products** 테이블만 만든 다음, **Categories** 테이블에 **CategoryID**, **CategoryName** 및 **Description** 열을 만들고 **Products** 테이블에 **ProductID**, **ReorderLevel** 및 **Discontinued** 열을 만드는 것입니다.  유추된 스키마에서 XML 요소에 지정된 특성을 무시하도록 하려면 다음 예제와 같이 **InferXmlSchema** 메서드를 사용하고 무시할 **officedata**에 대한 XML 네임스페이스를 지정합니다.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## 참고 항목  
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [XSD\(XML 스키마\)에서 DataSet 관계형 구조 파생](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)   
 [XML에서 DataSet 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [XML로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)