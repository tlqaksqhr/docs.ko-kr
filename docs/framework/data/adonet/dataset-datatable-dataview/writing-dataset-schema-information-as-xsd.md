---
title: "데이터 집합 스키마 정보를 XSD로 작성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: dde8a16ee0fbd86dacf6125c9a02209a794a5b74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="111bb-102">데이터 집합 스키마 정보를 XSD로 작성</span><span class="sxs-lookup"><span data-stu-id="111bb-102">Writing DataSet Schema Information as XSD</span></span>
<span data-ttu-id="111bb-103"><xref:System.Data.DataSet>의 스키마를 XSD(XML 스키마 정의 언어) 스키마로 작성하여, 작성한 스키마를 관련된 데이터와 함께 또는 데이터 없이 XML 문서에서 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="111bb-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="111bb-104">XML 스키마 파일, 스트림에 쓸 수는 <xref:System.Xml.XmlWriter>, 문자열 또는 강력한 형식의 생성 하는 데 유용 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="111bb-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="111bb-105">에 대 한 자세한 내용은 강력한 형식의 **DataSet** 개체 참조 [형식화 된 데이터 집합](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="111bb-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 <span data-ttu-id="111bb-106">XML 스키마에서 테이블의 열을 표현 하는 방법을 지정할 수 있습니다를 사용 하 여는 **ColumnMapping** 의 속성은 <xref:System.Data.DataColumn> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="111bb-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="111bb-107">자세한 내용은의 "XML 요소, 특성 및 텍스트에 열 매핑" 참조 [XML 데이터로 작성 데이터 집합 콘텐츠](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="111bb-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="111bb-108">스키마를 작성 하는 **데이터 집합** 파일에 XML 스키마로 스트림 또는 **XmlWriter**를 사용 하 여는 **WriteXmlSchema** 의 메서드는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="111bb-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="111bb-109">**WriteXmlSchema** 결과 XML 스키마의 대상을 지정 하는 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="111bb-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="111bb-110">다음 코드 예의 XML 스키마를 작성 하는 방법을 보여 줍니다는 **DataSet** 파일 이름을 포함 하는 문자열을 전달 하 여 파일에는 및 <xref:System.IO.StreamWriter> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="111bb-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
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
  
 <span data-ttu-id="111bb-111">스키마를 가져올는 **DataSet** 사용, XML 스키마 문자열로 작성 및는 **GetXmlSchema** 메서드를 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="111bb-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="111bb-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="111bb-112">See Also</span></span>  
 [<span data-ttu-id="111bb-113">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="111bb-113">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="111bb-114">데이터 집합 콘텐츠를 XML 데이터로 작성</span><span class="sxs-lookup"><span data-stu-id="111bb-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [<span data-ttu-id="111bb-115">형식화된 데이터 집합</span><span class="sxs-lookup"><span data-stu-id="111bb-115">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="111bb-116">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="111bb-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="111bb-117">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="111bb-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
