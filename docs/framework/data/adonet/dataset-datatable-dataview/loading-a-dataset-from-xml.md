---
title: XML에서 데이터 집합 로드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 0b74480209c8d06f38ea39e7a89741fc5a89512b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759766"
---
# <a name="loading-a-dataset-from-xml"></a>XML에서 데이터 집합 로드
ADO.NET <xref:System.Data.DataSet>의 내용은 XML 스트림이나 문서로부터 만들 수 있습니다. 또한, .NET Framework를 사용하면 XML로부터 로드할 정보와 <xref:System.Data.DataSet>의 스키마나 관계형 구조를 만드는 방법을 매우 융통성 있게 선택할 수 있습니다.  
  
 채우는 한 <xref:System.Data.DataSet> XML에서 데이터를 사용 하 여는 **ReadXml** 의 메서드는 <xref:System.Data.DataSet> 개체입니다. **ReadXml** 메서드는 파일, 스트림, 읽습니다 또는 **XmlReader**, 소스 XML와 선택적 인수로 사용 **XmlReadMode** 인수입니다. (에 대 한 자세한 내용은 **XmlReader**, 참조 [NIB: XmlTextReader 사용 하 여 XML 데이터 읽기](http://msdn.microsoft.com/library/762c069b-b50c-41b8-936e-39eacfb0d540).) **ReadXml** 메서드를 XML 스트림 또는 문서와 부하의 내용을 읽습니다는 <xref:System.Data.DataSet> 데이터를 사용 합니다. 관계형 스키마 생성는 <xref:System.Data.DataSet> 에 따라는 **XmlReadMode** 관계형 스키마가 있는지 여부 및 지정 합니다.  
  
 다음 표에서 설명에 대 한 옵션은 **XmlReadMode** 인수입니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**자동**|이 값이 기본값입니다. XML을 검사하고 다음 순서에 따라 가장 적합한 옵션을 선택합니다.<br /><br /> -XML이 DiffGram 이면 경우 **DiffGram** 사용 됩니다.<br />If는 <xref:System.Data.DataSet> 스키마가 포함 된 XML에 인라인 스키마 또는 **ReadSchema** 사용 됩니다.<br />If는 <xref:System.Data.DataSet> 스키마는 XML에 인라인 스키마가 포함 되어 있지 않습니다 **InferSchema** 사용 됩니다.<br /><br /> 읽는 중인 XML의 형식을 알고 있는 경우 최상의 성능을 것이 좋습니다 명시적으로 설정 하는 **XmlReadMode**않고 하기 보다는 **자동** 기본값입니다.|  
|**ReadSchema**|모든 인라인 스키마를 읽은 다음 데이터와 스키마를 로드합니다.<br /><br /> <xref:System.Data.DataSet>에 이미 스키마가 있으면 인라인 스키마의 새 테이블이 <xref:System.Data.DataSet>에 있는 기존 스키마에 추가됩니다. 인라인 스키마의 모든 테이블이 <xref:System.Data.DataSet>에 이미 있으면 예외가 throw됩니다. 사용 하 여 기존 테이블의 스키마를 수정할 수 없습니다 **XmlReadMode.ReadSchema**합니다.<br /><br /> <xref:System.Data.DataSet>에 스키마도 없고 인라인 스키마도 없으면 데이터를 읽지 않습니다.<br /><br /> 인라인 스키마는 XSD(XML 스키마 정의 언어) 스키마를 사용하여 정의할 수 있습니다. XML 스키마로 인라인 스키마를 작성 하는 방법에 대 한 세부 정보를 참조 하십시오. [파생 된 데이터 집합 관계형 구조에서 XSD (XML 스키마)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)합니다.|  
|**IgnoreSchema**|모든 인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 로드합니다. 기존 스키마와 일치하지 않는 모든 데이터는 삭제됩니다. <xref:System.Data.DataSet>에 스키마가 없으면 데이터를 로드하지 않습니다.<br /><br /> 데이터가 DiffGram 이면 경우 **IgnoreSchema** 동일한 기능이 **DiffGram** *합니다.*|  
|**InferSchema**|모든 인라인 스키마를 무시하며 XML 데이터의 구조마다 스키마를 유추한 다음 데이터를 로드합니다.<br /><br /> <xref:System.Data.DataSet>에 이미 스키마가 있으면 기존 테이블에 열을 추가하여 현재 스키마를 확장합니다. 기존 테이블이 없으면 테이블이 추가되지 않습니다. 유추된 테이블이 다른 네임스페이스로 이미 존재하거나 유추된 열이 기존 열과 충돌하면 예외가 throw됩니다.<br /><br /> 자세한 방법에 대 한 내용은 **ReadXmlSchema** 스키마를 유추는 XML 문서에서 참조 [유추 데이터 집합 관계형 구조 XML에서](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)합니다.|  
|**DiffGram**|DiffGram을 읽은 다음 해당 데이터를 현재 스키마에 추가합니다. **DiffGram** 은 새 행의 고유 식별자 값과 일치 하는 기존 행을 병합 합니다. 이 항목의 맨 뒤에 나오는 "XML로부터 데이터 병합"을 참조하세요. Diffgram에 대 한 자세한 내용은 참조 [Diffgram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)합니다.|  
|**조각**|스트림의 끝에 도달할 때까지 여러 개의 XML 조각을 계속 읽습니다. <xref:System.Data.DataSet> 스키마에 일치하는 조각이 해당 테이블의 뒤에 추가됩니다. <xref:System.Data.DataSet> 스키마에 일치하지 않는 조각은 삭제됩니다.|  
  
> [!NOTE]
>  전달 하는 경우는 **XmlReader** 를 **ReadXml** 즉 현재 위치를 일부 XML 문서로 **ReadXml** 는 다음 요소 노드를 읽고 루트로 취급 합니다 요소 노드의 끝까지 읽는 요소입니다. 지정 하는 경우 적용 되지 않습니다 **XmlReadMode.Fragment**합니다.  
  
## <a name="dtd-entities"></a>DTD 엔터티  
 로드 하려고 하면 예외가 throw 될 XML에는 문서 형식 정의 (DTD) 스키마에 정의 된 엔터티를 있으면는 <xref:System.Data.DataSet> 파일을 전달 하 여 이름, 스트림 또는 유효성 검사 없는 **XmlReader** 를  **ReadXml**합니다. 대신, 만들어야는 **XmlValidatingReader**와 **EntityHandling** 로 설정 **EntityHandling.ExpandEntities**, 전달 프로그램  **XmlValidatingReader** 를 **ReadXml**합니다. **XmlValidatingReader** 에서 읽기 전에 엔터티를 확장 하 고 <xref:System.Data.DataSet>합니다.  
  
 다음 코드 예제에서는 XML 스트림으로부터 <xref:System.Data.DataSet>을 로드하는 방법을 보여 줍니다. 첫 번째 예제에 전달 되는 파일 이름에서 **ReadXml** 메서드. 두 번째 예제에서는 <xref:System.IO.StringReader>를 사용하여 로드될 XML이 포함된 문자열을 보여 줍니다.  
  
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
>  호출 하는 경우 **ReadXml** 매우 큰 파일을 로드 하려면 성능 저하를 발생할 수 있습니다. 에 대 한 최상의 성능을 위해 **ReadXml**, 큰 파일을 호출 하는 <xref:System.Data.DataTable.BeginLoadData%2A> 의 각 테이블에 대 한 메서드는 <xref:System.Data.DataSet>, 한 다음 호출 **ReadXml**합니다. 마지막으로 다음 예제와 같이 <xref:System.Data.DataTable.EndLoadData%2A>의 각 테이블에 대해 <xref:System.Data.DataSet>를 호출합니다.  
  
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
>  경우에 대 한 XSD 스키마 프로그램 <xref:System.Data.DataSet> 포함 한 **targetNamespace**, 데이터를 읽을 수 있습니다, 그리고 및를 호출할 때 예외가 발생할 수 있습니다 **ReadXml** 로드 하는 <xref:System.Data.DataSet> 포함 된 xml을 정규화 네임 스페이스가 없는 요소입니다. 이 경우 비 정규화 된 요소를 읽을 수 설정 **elementFormDefault** XSD 스키마에 같은를 "qualified"입니다. 예를 들어:  
  
```xml  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a>XML로부터 데이터 병합  
 <xref:System.Data.DataSet>에 데이터가 이미 있으면 XML의 새 데이터는 <xref:System.Data.DataSet>에 이미 있는 데이터에 추가됩니다. **ReadXml** 에 XML에서 병합 하지 않습니다는 <xref:System.Data.DataSet> 행 일치 하는 기본 키 정보입니다. 사용 하 여 기존 행 정보를 XML에서 새 정보로 덮어쓰려면 **ReadXml** 새로 만들려면 <xref:System.Data.DataSet>, 차례로 <xref:System.Data.DataSet.Merge%2A> 새 <xref:System.Data.DataSet> 기존 <xref:System.Data.DataSet>합니다. 사용 하 여 DiffGram을 로드 **ReadXML** 와 **XmlReadMode** 의 **DiffGram** 동일한 고유 식별자가 있는 행이 병합 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>  
 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [XML에서 데이터 집합 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
