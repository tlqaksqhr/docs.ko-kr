---
title: "XML에서 데이터 집합 스키마 정보 로드"
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
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8b814715782710994f18163ccfcd3db342199145
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="2fae0-102">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="2fae0-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="2fae0-103">스키마는 <xref:System.Data.DataSet> (해당 테이블, 열, 관계 및 제약 조건) 정의할 수 있습니다, 프로그래밍 방식으로 개발한는 **채우기** 또는 **FillSchema** 의 메서드는 <xref:System.Data.Common.DataAdapter>, 또는에서 로드 된 프로그램 XML 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="2fae0-104">로드할 **데이터 집합** 스키마 정보는 XML 문서에서 사용할 수 있습니다는 **ReadXmlSchema** 또는 **InferXmlSchema** 의 메서드는 **데이터집합**.</span><span class="sxs-lookup"><span data-stu-id="2fae0-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="2fae0-105">**ReadXmlSchema** 로드 하거나 유추할 수 있습니다 **DataSet** XML 스키마 정의 언어 (XSD) 스키마 또는 인라인 XML 스키마는 XML 문서를 포함 하는 문서에서 스키마 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="2fae0-106">**InferXmlSchema** 지정한 특정 XML 네임 스페이스를 무시 하는 동안 XML 문서에서 스키마를 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2fae0-107">테이블에서 순서는 **DataSet** 전송할 웹 서비스나 XML serialization을 사용할 때 유지 되지 않을 수 있습니다는 **데이터 집합** XSD 구문 (예: 중첩된 관계)을 사용 하 여 메모리에서 만든 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="2fae0-108">따라서 받는 사람은 **데이터 집합** 테이블 순서에 경우에 종속 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="2fae0-109">그러나 순서 지정 테이블은 항상 유지 하는 경우의 스키마는 **데이터 집합** 메모리를 생성 하는 대신 XSD 파일에서 읽은 전송 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="2fae0-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="2fae0-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="2fae0-111">스키마를 로드 한 **데이터 집합** 모든 데이터를 로드 하지 않고 XML 문서에서 사용할 수 있습니다는 **ReadXmlSchema** 의 메서드는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="2fae0-112">**ReadXmlSchema** 만듭니다 **DataSet** XML 스키마 정의 언어 (XSD) 스키마를 사용 하 여 정의 된 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="2fae0-113">**ReadXmlSchema** 파일 이름, 스트림, 단일 인수를 사용 하는 메서드 또는 **XmlReader** 로드할 XML 문서가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="2fae0-114">XML 문서에는 스키마만 있을 수도 있고 데이터가 포함된 XML 요소를 가진 스키마 인라인이 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="2fae0-115">XML 스키마로 인라인 스키마를 작성 하는 방법에 대 한 세부 정보를 참조 하십시오. [파생 된 데이터 집합 관계형 구조에서 XSD (XML 스키마)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="2fae0-116">XML 문서에 전달 하는 경우 **ReadXmlSchema** 인라인 스키마 정보가 없으면 포함 **ReadXmlSchema** XML 문서의 요소에서 스키마를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="2fae0-117">경우는 **DataSet** 이미 스키마가 포함 되어 이미 존재 하지 않는 경우 새 테이블을 추가 하 여 현재 스키마 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="2fae0-118">새 열은 기존 테이블에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="2fae0-119">이미 추가 되는 열에 있는 경우는 **DataSet** 하지만 열과는 호환 되지 않는 형식에서에서 발견 되는 XML, 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="2fae0-120">자세한 방법에 대 한 내용은 **ReadXmlSchema** 스키마를 유추는 XML 문서에서 참조 [유추 데이터 집합 관계형 구조 XML에서](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="2fae0-121">하지만 **ReadXmlSchema** 로드 하거나 유추의 스키마만는 **DataSet**, **ReadXml** 의 메서드는 **데이터 집합** 로드 하거나 유추 둘 다 스키마 및 XML 문서에 포함 된 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="2fae0-122">자세한 내용은 참조 [XML 로부터 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-122">For more information, see [Loading a DataSet from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="2fae0-123">다음 코드 예제는 로드 하는 방법을 보여는 **DataSet** 스키마에서 XML 문서 또는 스트림에 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="2fae0-124">첫 번째 예에 전달 되는 XML 스키마 파일 이름을 보여 줍니다.는 **ReadXmlSchema** 메서드.</span><span class="sxs-lookup"><span data-stu-id="2fae0-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="2fae0-125">두 번째 예에서는 한 **System.IO.StreamReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="2fae0-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="2fae0-126">InferXmlSchema</span></span>  
 <span data-ttu-id="2fae0-127">지시할 수 있습니다는 **DataSet** 사용 하 여 XML 문서에서 해당 스키마를 유추 하는 **InferXmlSchema** 의 메서드는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="2fae0-128">**InferXmlSchema** 둘 다 수행과 동일한 함수가 **ReadXml** 와 **XmlReadMode** 의 **InferSchema** (데이터 로드으로 스키마를 유추) 및  **ReadXmlSchema** 읽는 중인 문서에 인라인 스키마가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="2fae0-129">그러나 **InferXmlSchema** 하면 스키마를 유추할 때 무시할 특정 XML 네임 스페이스를 지정할 수 있도록의 추가 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="2fae0-130">**InferXmlSchema** 는 두 개의 필수 인수: 스트림, 파일 이름으로 지정 된 XML 문서의 위치 또는 **XmlReader**; 및 해당 작업에서 무시 될 XML 네임 스페이스의 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="2fae0-131">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-131">For example, consider the following XML:</span></span>  
  
```xml  
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
  
 <span data-ttu-id="2fae0-132">앞의 XML 문서에 있는 요소에 지정 된 특성으로 인해 둘 다는 **ReadXmlSchema** 메서드 및 **ReadXml** 메서드는 **XmlReadMode** 의 **InferSchema** 문서에서 모든 요소에 대 한 테이블을 만듭니다: **범주**, **CategoryID**, **CategoryName**, **설명**, **제품**, **ProductID**, **ReorderLevel**, 및 **중단**.</span><span class="sxs-lookup"><span data-stu-id="2fae0-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="2fae0-133">(자세한 내용은 참조 [유추 데이터 집합 관계형 구조 XML에서](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) 그러나 더 적절 한 구조에만 만들 수는 **범주** 및 **제품** 테이블을 만든 다음 **CategoryID**, **CategoryName** , 및 **설명** 열에는 **범주** 테이블 및 **ProductID**, **ReorderLevel**, 및 **단종** 열에는 **제품** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-133">(For more information, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="2fae0-134">유추 된 스키마는 XML 요소에 지정 된 특성을 무시 하려면 사용 하 여는 **InferXmlSchema** 메서드 XML 네임 스페이스를 지정 하 고 **officedata** 에서처럼 무시 되어야 하는 다음 예제에서는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fae0-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fae0-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fae0-135">See Also</span></span>  
 [<span data-ttu-id="2fae0-136">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="2fae0-136">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="2fae0-137">XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="2fae0-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="2fae0-138">XML에서 데이터 집합 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="2fae0-138">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="2fae0-139">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="2fae0-139">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="2fae0-140">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="2fae0-140">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="2fae0-141">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="2fae0-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
