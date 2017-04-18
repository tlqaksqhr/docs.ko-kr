---
title: "XML로부터 DataSet 로드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# XML로부터 DataSet 로드
ADO.NET <xref:System.Data.DataSet>의 내용은 XML 스트림이나 문서로부터 만들 수 있습니다.  또한, .NET Framework를 사용하면 XML로부터 로드할 정보와 <xref:System.Data.DataSet>의 스키마나 관계형 구조를 만드는 방법을 매우 융통성 있게 선택할 수 있습니다.  
  
 XML의 데이터로 <xref:System.Data.DataSet>을 채우려면 <xref:System.Data.DataSet> 개체의 **ReadXml** 메서드를 사용합니다.  **ReadXml** 메서드는 파일, 스트림 또는 **XmlReader**를 읽은 다음 XML 소스와 선택적 **XmlReadMode** 인수를 인수로 사용합니다.  **XmlReader**에 대한 자세한 내용은 [NIB: Reading XML Data with XmlTextReader](http://msdn.microsoft.com/ko-kr/762c069b-b50c-41b8-936e-39eacfb0d540)를 참조하세요. **ReadXml** 메서드는 XML 스트림이나 문서의 내용을 읽은 다음 데이터와 함께 <xref:System.Data.DataSet>을 로드합니다.  또한 이 메서드는 기존의 관계형 스키마가 있는지 여부에 상관없이 지정된 **XmlReadMode**에 따라 <xref:System.Data.DataSet>의 관계형 스키마를 만듭니다.  
  
 다음 표에서는 **XmlReadMode** 인수에 대한 옵션을 설명합니다.  
  
|옵션|설명|  
|--------|--------|  
|**Auto**|이 값이 기본값입니다.  XML을 검사하고 다음 순서에 따라 가장 적합한 옵션을 선택합니다.<br /><br /> -   XML이 DiffGram이면 **DiffGram**을 사용합니다.<br />-   <xref:System.Data.DataSet>에 스키마가 있거나 XML에 인라인 스키마가 있으면 **ReadSchema**를 사용합니다.<br />-   <xref:System.Data.DataSet>에 스키마가 없거나 XML에 인라인 스키마가 없으면 **InferSchema**를 사용합니다.<br /><br /> 읽고 있는 XML의 형식을 알고 있는 경우 최적의 성능을 구현하려면 기본값인 **Auto**를 사용하는 대신 **XmlReadMode**를 명시적으로 설정하는 것이 좋습니다.|  
|**ReadSchema**|모든 인라인 스키마를 읽은 다음 데이터와 스키마를 로드합니다.<br /><br /> <xref:System.Data.DataSet>에 이미 스키마가 있으면 인라인 스키마의 새 테이블이 <xref:System.Data.DataSet>에 있는 기존 스키마에 추가됩니다.  인라인 스키마의 모든 테이블이 <xref:System.Data.DataSet>에 이미 있으면 예외가 throw됩니다.  **XmlReadMode.ReadSchema**를 사용하여 기존 테이블의 스키마를 수정할 수는 없습니다.<br /><br /> <xref:System.Data.DataSet>에 스키마도 없고 인라인 스키마도 없으면 데이터를 읽지 않습니다.<br /><br /> 인라인 스키마는 XSD\(XML 스키마 정의 언어\) 스키마를 사용하여 정의할 수 있습니다.  인라인 스키마를 XML 스키마로 작성하는 방법에 대한 자세한 내용은 [XSD\(XML 스키마\)에서 DataSet 관계형 구조 파생](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)을 참조하세요.|  
|**IgnoreSchema**|모든 인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 로드합니다.  기존 스키마와 일치하지 않는 모든 데이터는 삭제됩니다.  <xref:System.Data.DataSet>에 스키마가 없으면 데이터를 로드하지 않습니다.<br /><br /> 데이터가 DiffGram이면 **IgnoreSchema**와 **DiffGram**은 동일하게 작동합니다*.*|  
|**InferSchema**|모든 인라인 스키마를 무시하며 XML 데이터의 구조마다 스키마를 유추한 다음 데이터를 로드합니다.<br /><br /> <xref:System.Data.DataSet>에 이미 스키마가 있으면 기존 테이블에 열을 추가하여 현재 스키마를 확장합니다.  기존 테이블이 없으면 테이블이 추가되지 않습니다.  유추된 테이블이 다른 네임스페이스로 이미 존재하거나 유추된 열이 기존 열과 충돌하면 예외가 throw됩니다.<br /><br /> **ReadXmlSchema**가 XML 문서로부터 스키마를 유추하는 방법에 대한 자세한 내용은 [XML에서 DataSet 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)를 참조하세요.|  
|**DiffGram**|DiffGram을 읽은 다음 해당 데이터를 현재 스키마에 추가합니다.  **DiffGram**은 새 행을 고유한 식별자 값이 일치하는 기존 행에 병합시킵니다.  이 항목의 맨 뒤에 나오는 "XML로부터 데이터 병합"을 참조하세요.  DiffGrams에 대한 자세한 내용은 [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)을 참조하세요.|  
|**Fragment**|스트림의 끝에 도달할 때까지 여러 개의 XML 조각을 계속 읽습니다.  <xref:System.Data.DataSet> 스키마에 일치하는 조각이 해당 테이블의 뒤에 추가됩니다.  <xref:System.Data.DataSet> 스키마에 일치하지 않는 조각은 삭제됩니다.|  
  
> [!NOTE]
>  XML 문서로 이동하고 있는 **ReadXml**에 **XmlReader**를 전달하면 **ReadXml**은 요소 노드를 끝까지 읽기만 하여, 다음 요소 노드를 읽고 루트 요소로 취급합니다.  **XmlReadMode.Fragment**를 지정하는 경우에는 이 방식이 적용되지 않습니다.  
  
## DTD 엔터티  
 XML에 DTD\(문서 형식 정의\) 스키마에 정의된 엔터티가 있는 경우 파일 이름, 스트림 또는 비검증 **XmlReader**를 **ReadXml**로 전달하여 <xref:System.Data.DataSet>을 로드하면 예외가 throw됩니다.  대신 **EntityHandling**을 **EntityHandling.ExpandEntities**로 설정한 상태에서 **XmlValidatingReader**를 만든 다음 **XmlValidatingReader**를 **ReadXml**로 전달해야 합니다.  **XmlValidatingReader**는 <xref:System.Data.DataSet>에서 읽기 전에 엔터티를 확장합니다.  
  
 다음 코드 예제에서는 XML 스트림으로부터 <xref:System.Data.DataSet>을 로드하는 방법을 보여 줍니다.  첫 번째 예제에서는 **ReadXml** 메서드로 전달될 파일 이름을 보여 줍니다.  두 번째 예제에서는 <xref:System.IO.StringReader>를 사용하여 로드될 XML이 포함된 문자열을 보여 줍니다.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema);  
```  
  
```vb  
Dim dataSet As DataSet = New DataSet  
Dim dataTable As DataTable = New DataTable("table1")  
dataTable.Columns.Add("col1", Type.GetType("System.String"))  
dataSet.Tables.Add(dataTable)  
  
Dim xmlData As String = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>"  
  
Dim xmlSR As System.IO.StringReader = New System.IO.StringReader(xmlData)  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
DataTable dataTable = new DataTable("table1");  
dataTable.Columns.Add("col1", typeof(string));  
dataSet.Tables.Add(dataTable);  
  
string xmlData = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>";  
  
System.IO.StringReader xmlSR = new System.IO.StringReader(xmlData);  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema);  
```  
  
> [!NOTE]
>  **ReadXml**을 호출하여 매우 큰 파일을 로드할 경우 성능이 느려질 수 있습니다.  큰 파일을 대상으로 **ReadXml**을 사용할 때 최적의 성능을 얻으려면 <xref:System.Data.DataSet>의 각 테이블에 대해 <xref:System.Data.DataTable.BeginLoadData%2A> 메서드를 호출한 다음 **ReadXml**을 호출합니다.  마지막으로 다음 예제와 같이 <xref:System.Data.DataSet>의 각 테이블에 대해 <xref:System.Data.DataTable.EndLoadData%2A>를 호출합니다.  
  
```vb  
Dim dataTable As DataTable  
  
For Each dataTable In dataSet.Tables  
   dataTable.BeginLoadData()  
Next  
  
dataSet.ReadXml("file.xml")  
  
For Each dataTable in dataSet.Tables  
   dataTable.EndLoadData()  
Next  
```  
  
```csharp  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.BeginLoadData();  
  
dataSet.ReadXml("file.xml");   
  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.EndLoadData();  
```  
  
> [!NOTE]
>  <xref:System.Data.DataSet>에 대한 XSD 스키마에 **targetNamespace**가 포함되어 있으면 **ReadXml**을 호출하여 정규화된 네임스페이스가 없는 요소가 포함된 XML이 있는 <xref:System.Data.DataSet>을 로드할 때 데이터를 읽지 못하고 예외가 발생할 수 있습니다.  이 경우 비정규화된 요소를 읽으려면 XSD 스키마에서 **elementFormDefault**를 "qualified"로 설정합니다.  예를 들면 다음과 같습니다.  
  
```  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## XML로부터 데이터 병합  
 <xref:System.Data.DataSet>에 데이터가 이미 있으면 XML의 새 데이터는 <xref:System.Data.DataSet>에 이미 있는 데이터에 추가됩니다.  **ReadXml**은 XML로부터 기본 키가 일치하지 않는 <xref:System.Data.DataSet> 행 정보로 병합되지 않습니다.  기존 행 정보를 XML의 새 정보로 덮어쓰려면 **ReadXml**을 사용하여 새 <xref:System.Data.DataSet>을 만든 다음, 이 새 <xref:System.Data.DataSet>을 기존 <xref:System.Data.DataSet>으로 <xref:System.Data.DataSet.Merge%2A>합니다.  **DiffGram**이 **XmlReadMode**인 **ReadXML**을 사용하여 DiffGram을 로드하면 동일한 고유 식별자가 있는 행이 병합됩니다.  
  
## 참고 항목  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=fullName>   
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)   
 [XSD\(XML 스키마\)에서 DataSet 관계형 구조 파생](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)   
 [XML에서 DataSet 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [XML로부터 DataSet 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)