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
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="d90ac-102">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="d90ac-102">Loading a DataSet from XML</span></span>
<span data-ttu-id="d90ac-103">ADO.NET <xref:System.Data.DataSet>의 내용은 XML 스트림이나 문서로부터 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-103">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="d90ac-104">또한, .NET Framework를 사용하면 XML로부터 로드할 정보와 <xref:System.Data.DataSet>의 스키마나 관계형 구조를 만드는 방법을 매우 융통성 있게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-104">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="d90ac-105">채우는 한 <xref:System.Data.DataSet> XML에서 데이터를 사용 하 여는 **ReadXml** 의 메서드는 <xref:System.Data.DataSet> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-105">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="d90ac-106">**ReadXml** 메서드는 파일, 스트림, 읽습니다 또는 **XmlReader**, 소스 XML와 선택적 인수로 사용 **XmlReadMode** 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-106">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="d90ac-107">(에 대 한 자세한 내용은 **XmlReader**, 참조 [NIB: XmlTextReader 사용 하 여 XML 데이터 읽기](http://msdn.microsoft.com/library/762c069b-b50c-41b8-936e-39eacfb0d540).) **ReadXml** 메서드를 XML 스트림 또는 문서와 부하의 내용을 읽습니다는 <xref:System.Data.DataSet> 데이터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-107">(For more information about the **XmlReader**, see [NIB: Reading XML Data with XmlTextReader](http://msdn.microsoft.com/library/762c069b-b50c-41b8-936e-39eacfb0d540).) The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="d90ac-108">관계형 스키마 생성는 <xref:System.Data.DataSet> 에 따라는 **XmlReadMode** 관계형 스키마가 있는지 여부 및 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-108">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="d90ac-109">다음 표에서 설명에 대 한 옵션은 **XmlReadMode** 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-109">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="d90ac-110">옵션</span><span class="sxs-lookup"><span data-stu-id="d90ac-110">Option</span></span>|<span data-ttu-id="d90ac-111">설명</span><span class="sxs-lookup"><span data-stu-id="d90ac-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d90ac-112">**자동**</span><span class="sxs-lookup"><span data-stu-id="d90ac-112">**Auto**</span></span>|<span data-ttu-id="d90ac-113">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-113">This is the default.</span></span> <span data-ttu-id="d90ac-114">XML을 검사하고 다음 순서에 따라 가장 적합한 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-114">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="d90ac-115">-XML이 DiffGram 이면 경우 **DiffGram** 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-115">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="d90ac-116">If는 <xref:System.Data.DataSet> 스키마가 포함 된 XML에 인라인 스키마 또는 **ReadSchema** 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-116">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="d90ac-117">If는 <xref:System.Data.DataSet> 스키마는 XML에 인라인 스키마가 포함 되어 있지 않습니다 **InferSchema** 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-117">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="d90ac-118">읽는 중인 XML의 형식을 알고 있는 경우 최상의 성능을 것이 좋습니다 명시적으로 설정 하는 **XmlReadMode**않고 하기 보다는 **자동** 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-118">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="d90ac-119">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="d90ac-119">**ReadSchema**</span></span>|<span data-ttu-id="d90ac-120">모든 인라인 스키마를 읽은 다음 데이터와 스키마를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-120">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="d90ac-121"><xref:System.Data.DataSet>에 이미 스키마가 있으면 인라인 스키마의 새 테이블이 <xref:System.Data.DataSet>에 있는 기존 스키마에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-121">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d90ac-122">인라인 스키마의 모든 테이블이 <xref:System.Data.DataSet>에 이미 있으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-122">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="d90ac-123">사용 하 여 기존 테이블의 스키마를 수정할 수 없습니다 **XmlReadMode.ReadSchema**합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-123">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="d90ac-124"><xref:System.Data.DataSet>에 스키마도 없고 인라인 스키마도 없으면 데이터를 읽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-124">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="d90ac-125">인라인 스키마는 XSD(XML 스키마 정의 언어) 스키마를 사용하여 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-125">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="d90ac-126">XML 스키마로 인라인 스키마를 작성 하는 방법에 대 한 세부 정보를 참조 하십시오. [파생 된 데이터 집합 관계형 구조에서 XSD (XML 스키마)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-126">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="d90ac-127">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="d90ac-127">**IgnoreSchema**</span></span>|<span data-ttu-id="d90ac-128">모든 인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-128">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="d90ac-129">기존 스키마와 일치하지 않는 모든 데이터는 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-129">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="d90ac-130"><xref:System.Data.DataSet>에 스키마가 없으면 데이터를 로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-130">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="d90ac-131">데이터가 DiffGram 이면 경우 **IgnoreSchema** 동일한 기능이 **DiffGram** *합니다.*</span><span class="sxs-lookup"><span data-stu-id="d90ac-131">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="d90ac-132">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="d90ac-132">**InferSchema**</span></span>|<span data-ttu-id="d90ac-133">모든 인라인 스키마를 무시하며 XML 데이터의 구조마다 스키마를 유추한 다음 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-133">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="d90ac-134"><xref:System.Data.DataSet>에 이미 스키마가 있으면 기존 테이블에 열을 추가하여 현재 스키마를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-134">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="d90ac-135">기존 테이블이 없으면 테이블이 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-135">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="d90ac-136">유추된 테이블이 다른 네임스페이스로 이미 존재하거나 유추된 열이 기존 열과 충돌하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-136">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="d90ac-137">자세한 방법에 대 한 내용은 **ReadXmlSchema** 스키마를 유추는 XML 문서에서 참조 [유추 데이터 집합 관계형 구조 XML에서](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-137">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="d90ac-138">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="d90ac-138">**DiffGram**</span></span>|<span data-ttu-id="d90ac-139">DiffGram을 읽은 다음 해당 데이터를 현재 스키마에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-139">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="d90ac-140">**DiffGram** 은 새 행의 고유 식별자 값과 일치 하는 기존 행을 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-140">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="d90ac-141">이 항목의 맨 뒤에 나오는 "XML로부터 데이터 병합"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d90ac-141">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="d90ac-142">Diffgram에 대 한 자세한 내용은 참조 [Diffgram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-142">For more information about DiffGrams, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>|  
|<span data-ttu-id="d90ac-143">**조각**</span><span class="sxs-lookup"><span data-stu-id="d90ac-143">**Fragment**</span></span>|<span data-ttu-id="d90ac-144">스트림의 끝에 도달할 때까지 여러 개의 XML 조각을 계속 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-144">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="d90ac-145"><xref:System.Data.DataSet> 스키마에 일치하는 조각이 해당 테이블의 뒤에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-145">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="d90ac-146"><xref:System.Data.DataSet> 스키마에 일치하지 않는 조각은 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-146">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d90ac-147">전달 하는 경우는 **XmlReader** 를 **ReadXml** 즉 현재 위치를 일부 XML 문서로 **ReadXml** 는 다음 요소 노드를 읽고 루트로 취급 합니다 요소 노드의 끝까지 읽는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-147">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="d90ac-148">지정 하는 경우 적용 되지 않습니다 **XmlReadMode.Fragment**합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-148">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="d90ac-149">DTD 엔터티</span><span class="sxs-lookup"><span data-stu-id="d90ac-149">DTD Entities</span></span>  
 <span data-ttu-id="d90ac-150">로드 하려고 하면 예외가 throw 될 XML에는 문서 형식 정의 (DTD) 스키마에 정의 된 엔터티를 있으면는 <xref:System.Data.DataSet> 파일을 전달 하 여 이름, 스트림 또는 유효성 검사 없는 **XmlReader** 를  **ReadXml**합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-150">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="d90ac-151">대신, 만들어야는 **XmlValidatingReader**와 **EntityHandling** 로 설정 **EntityHandling.ExpandEntities**, 전달 프로그램  **XmlValidatingReader** 를 **ReadXml**합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-151">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="d90ac-152">**XmlValidatingReader** 에서 읽기 전에 엔터티를 확장 하 고 <xref:System.Data.DataSet>합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-152">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="d90ac-153">다음 코드 예제에서는 XML 스트림으로부터 <xref:System.Data.DataSet>을 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-153">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="d90ac-154">첫 번째 예제에 전달 되는 파일 이름에서 **ReadXml** 메서드.</span><span class="sxs-lookup"><span data-stu-id="d90ac-154">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="d90ac-155">두 번째 예제에서는 <xref:System.IO.StringReader>를 사용하여 로드될 XML이 포함된 문자열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-155">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
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
>  <span data-ttu-id="d90ac-156">호출 하는 경우 **ReadXml** 매우 큰 파일을 로드 하려면 성능 저하를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-156">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="d90ac-157">에 대 한 최상의 성능을 위해 **ReadXml**, 큰 파일을 호출 하는 <xref:System.Data.DataTable.BeginLoadData%2A> 의 각 테이블에 대 한 메서드는 <xref:System.Data.DataSet>, 한 다음 호출 **ReadXml**합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-157">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="d90ac-158">마지막으로 다음 예제와 같이 <xref:System.Data.DataTable.EndLoadData%2A>의 각 테이블에 대해 <xref:System.Data.DataSet>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-158">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="d90ac-159">경우에 대 한 XSD 스키마 프로그램 <xref:System.Data.DataSet> 포함 한 **targetNamespace**, 데이터를 읽을 수 있습니다, 그리고 및를 호출할 때 예외가 발생할 수 있습니다 **ReadXml** 로드 하는 <xref:System.Data.DataSet> 포함 된 xml을 정규화 네임 스페이스가 없는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-159">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="d90ac-160">이 경우 비 정규화 된 요소를 읽을 수 설정 **elementFormDefault** XSD 스키마에 같은를 "qualified"입니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-160">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="d90ac-161">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="d90ac-161">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="d90ac-162">XML로부터 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="d90ac-162">Merging Data from XML</span></span>  
 <span data-ttu-id="d90ac-163"><xref:System.Data.DataSet>에 데이터가 이미 있으면 XML의 새 데이터는 <xref:System.Data.DataSet>에 이미 있는 데이터에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-163">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d90ac-164">**ReadXml** 에 XML에서 병합 하지 않습니다는 <xref:System.Data.DataSet> 행 일치 하는 기본 키 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-164">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="d90ac-165">사용 하 여 기존 행 정보를 XML에서 새 정보로 덮어쓰려면 **ReadXml** 새로 만들려면 <xref:System.Data.DataSet>, 차례로 <xref:System.Data.DataSet.Merge%2A> 새 <xref:System.Data.DataSet> 기존 <xref:System.Data.DataSet>합니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-165">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d90ac-166">사용 하 여 DiffGram을 로드 **ReadXML** 와 **XmlReadMode** 의 **DiffGram** 동일한 고유 식별자가 있는 행이 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90ac-166">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d90ac-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d90ac-167">See Also</span></span>  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="d90ac-168">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="d90ac-168">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="d90ac-169">DiffGram</span><span class="sxs-lookup"><span data-stu-id="d90ac-169">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [<span data-ttu-id="d90ac-170">XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="d90ac-170">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="d90ac-171">XML에서 데이터 집합 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="d90ac-171">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="d90ac-172">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="d90ac-172">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="d90ac-173">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="d90ac-173">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="d90ac-174">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="d90ac-174">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
