---
title: "스키마 컴파일을 위한 XmlSchemaSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 55c4b175-3170-4071-9d60-dd5a42f79b54
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 193a9980bba423292921beff6c4c3172ce02fd92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xmlschemaset-for-schema-compilation"></a><span data-ttu-id="a3f19-102">스키마 컴파일을 위한 XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="a3f19-102">XmlSchemaSet for Schema Compilation</span></span>
<span data-ttu-id="a3f19-103">XSD(XML 스키마 정의 언어) 스키마를 저장하고 유효성을 검사할 수 있는 캐시인 <xref:System.Xml.Schema.XmlSchemaSet>에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-103">Describes the <xref:System.Xml.Schema.XmlSchemaSet>, a cache where XML Schema definition language (XSD) schemas can be stored and validated.</span></span>  
  
## <a name="the-xmlschemaset-class"></a><span data-ttu-id="a3f19-104">XmlSchemaSet 클래스</span><span class="sxs-lookup"><span data-stu-id="a3f19-104">The XmlSchemaSet Class</span></span>  
 <span data-ttu-id="a3f19-105"><xref:System.Xml.Schema.XmlSchemaSet>은 XSD(XML 스키마 정의 언어) 스키마를 저장하고 유효성을 검사할 수 있는 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-105">The <xref:System.Xml.Schema.XmlSchemaSet> is a cache where XML Schema definition language (XSD) schemas can be stored and validated.</span></span>  
  
 <span data-ttu-id="a3f19-106"><xref:System.Xml?displayProperty=nameWithType> 버전 1.0에서는 스키마 라이브러리로서 <xref:System.Xml.Schema.XmlSchemaCollection> 클래스에 XML 스키마가 로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-106">In <xref:System.Xml?displayProperty=nameWithType> version 1.0, XML schemas were loaded into an <xref:System.Xml.Schema.XmlSchemaCollection> class as a library of schemas.</span></span> <span data-ttu-id="a3f19-107"><xref:System.Xml?displayProperty=nameWithType> 버전 2.0에서는 <xref:System.Xml.XmlValidatingReader> 및 <xref:System.Xml.Schema.XmlSchemaCollection> 클래스는 사용되지 않으며 각각 <xref:System.Xml.XmlReader.Create%2A> 메서드와 <xref:System.Xml.Schema.XmlSchemaSet> 클래스로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-107">In <xref:System.Xml?displayProperty=nameWithType> version 2.0, the <xref:System.Xml.XmlValidatingReader> and the <xref:System.Xml.Schema.XmlSchemaCollection> classes are obsolete, and have been replaced by the <xref:System.Xml.XmlReader.Create%2A> methods, and the <xref:System.Xml.Schema.XmlSchemaSet> class respectively.</span></span>  
  
 <span data-ttu-id="a3f19-108"><xref:System.Xml.Schema.XmlSchemaSet>이 추가되어 표준 호환성, 성능, 사용되지 않는 Microsoft XDR(XML-Data Reduced) 스키마 형식 등 많은 문제가 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-108">The <xref:System.Xml.Schema.XmlSchemaSet> has been introduced to fix a number of issues including standards compatibility, performance, and the obsolete Microsoft XML-Data Reduced (XDR) schema format.</span></span>  
  
 <span data-ttu-id="a3f19-109">다음은 <xref:System.Xml.Schema.XmlSchemaCollection> 클래스와 <xref:System.Xml.Schema.XmlSchemaSet> 클래스를 비교한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-109">The following is a comparison between the <xref:System.Xml.Schema.XmlSchemaCollection> class and the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span>  
  
|<span data-ttu-id="a3f19-110">XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="a3f19-110">XmlSchemaCollection</span></span>|<span data-ttu-id="a3f19-111">XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="a3f19-111">XmlSchemaSet</span></span>|  
|-------------------------|------------------|  
|<span data-ttu-id="a3f19-112">Microsoft XDR 및 W3C XML 스키마를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-112">Supports Microsoft XDR and W3C XML schemas.</span></span>|<span data-ttu-id="a3f19-113">W3C XML 스키마만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-113">Only supports W3C XML schemas.</span></span>|  
|<span data-ttu-id="a3f19-114"><xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> 메서드를 호출하면 스키마가 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-114">Schemas are compiled when the <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> method is called.</span></span>|<span data-ttu-id="a3f19-115"><xref:System.Xml.Schema.XmlSchemaSet.Add%2A> 메서드를 호출해도 스키마가 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-115">Schemas are not compiled when the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method is called.</span></span> <span data-ttu-id="a3f19-116">스키마 라이브러리를 만드는 동안의 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-116">This provides a performance improvement during creation of the schema library.</span></span>|  
|<span data-ttu-id="a3f19-117">각 스키마는 컴파일된 개별 버전을 생성하며 이는 &quot;스키마 고립 영역&quot;이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-117">Each schema generates an individual compiled version that can result in "schema islands."</span></span> <span data-ttu-id="a3f19-118">결과적으로 모든 포함 및 가져오기 작업의 범위는 해당 스키마 내로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-118">As a result, all includes and imports are scoped only within that schema.</span></span>|<span data-ttu-id="a3f19-119">컴파일된 스키마는 스키마 &quot;집합&quot;인 단일 논리 스키마를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-119">Compiled schemas generate a single logical schema, a "set" of schemas.</span></span> <span data-ttu-id="a3f19-120">이 집합에 추가한 스키마 내에 가져온 스키마는 이 집합 자체에 직접 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-120">Any imported schemas within a schema that are added to the set are directly added to the set themselves.</span></span> <span data-ttu-id="a3f19-121">그러므로 모든 스키마에 모든 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-121">This means that all types are available to all schemas.</span></span>|  
|<span data-ttu-id="a3f19-122">컬렉션 내에는 특정 대상 네임스페이스에 대한 스키마가 한 개만 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-122">Only one schema for a particular target namespace can exist in the collection.</span></span>|<span data-ttu-id="a3f19-123">형식 충돌이 없으면 같은 대상 네임스페이스에 대한 여러 스키마를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-123">Multiple schemas for the same target namespace can be added as long as there are no type conflicts.</span></span>|  
  
## <a name="migrating-to-the-xmlschemaset"></a><span data-ttu-id="a3f19-124">XmlSchemaSet으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="a3f19-124">Migrating to the XmlSchemaSet</span></span>  
 <span data-ttu-id="a3f19-125">다음 코드 예제에서는 사용되지 않는 <xref:System.Xml.Schema.XmlSchemaSet> 클래스에서 새 <xref:System.Xml.Schema.XmlSchemaCollection> 클래스로 마이그레이션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-125">The following code example provides a guide to migrating to the new <xref:System.Xml.Schema.XmlSchemaSet> class from the obsolete <xref:System.Xml.Schema.XmlSchemaCollection> class.</span></span> <span data-ttu-id="a3f19-126">또한 두 클래스 간에 다음과 같은 주요 차이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-126">The code example illustrates the following major differences between the two classes.</span></span>  
  
-   <span data-ttu-id="a3f19-127"><xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> 클래스의 <xref:System.Xml.Schema.XmlSchemaCollection> 메서드와 달리 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 메서드를 호출할 때 스키마가 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-127">Unlike the <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaCollection> class, schemas are not compiled when calling the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="a3f19-128">예제 코드에서는 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 메서드를 명시적으로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-128">The <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is explicitly called in the example code.</span></span>  
  
-   <span data-ttu-id="a3f19-129"><xref:System.Xml.Schema.XmlSchemaSet>을 반복하려면 <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 속성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-129">To iterate over an <xref:System.Xml.Schema.XmlSchemaSet>, you must use the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="a3f19-130">다음은 사용되지 않는 <xref:System.Xml.Schema.XmlSchemaCollection> 코드 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-130">The following is the obsolete <xref:System.Xml.Schema.XmlSchemaCollection> code example.</span></span>  
  
```vb  
Dim schemaCollection As XmlSchemaCollection = New XmlSchemaCollection()  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema in schemaCollection  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaCollection schemaCollection = new XmlSchemaCollection();  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
  
foreach(XmlSchema schema in schemaCollection)  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
 <span data-ttu-id="a3f19-131">다음은 이에 해당하는 <xref:System.Xml.Schema.XmlSchemaSet> 코드 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-131">The following is the equivalent <xref:System.Xml.Schema.XmlSchemaSet> code example.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim schema As XmlSchema  
  
For Each schema in schemaSet.Schemas()  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
foreach(XmlSchema schema in schemaSet.Schemas())  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
## <a name="adding-and-retrieving-schemas"></a><span data-ttu-id="a3f19-132">스키마 추가 및 검색</span><span class="sxs-lookup"><span data-stu-id="a3f19-132">Adding and Retrieving Schemas</span></span>  
 <span data-ttu-id="a3f19-133"><xref:System.Xml.Schema.XmlSchemaSet>의 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> 메서드를 사용하여 <xref:System.Xml.Schema.XmlSchemaSet>에 스키마를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-133">Schemas are added to an <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="a3f19-134">스키마가 <xref:System.Xml.Schema.XmlSchemaSet>에 추가되면 대상 네임스페이스 URI에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-134">When a schema is added to an <xref:System.Xml.Schema.XmlSchemaSet>, it is associated with a target namespace URI.</span></span> <span data-ttu-id="a3f19-135">매개 변수로 대상 네임스페이스 URI를 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> 메서드에 지정할 수 있으며 대상 네임스페이스를 지정하지 않은 경우 <xref:System.Xml.Schema.XmlSchemaSet>은 스키마에 정의된 대상 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-135">The target namespace URI can either be specified as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method or if no target namespace is specified, the <xref:System.Xml.Schema.XmlSchemaSet> uses the target namespace defined in the schema.</span></span>  
  
 <span data-ttu-id="a3f19-136"><xref:System.Xml.Schema.XmlSchemaSet>의 <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> 속성을 사용하여 <xref:System.Xml.Schema.XmlSchemaSet>에서 스키마를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-136">Schemas are retrieved from an <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="a3f19-137"><xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 속성을 사용하여 <xref:System.Xml.Schema.XmlSchema>에 포함된 <xref:System.Xml.Schema.XmlSchemaSet> 개체를 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-137">The <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> allows you to iterate over the <xref:System.Xml.Schema.XmlSchema> objects contained in the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="a3f19-138"><xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> 속성은 <xref:System.Xml.Schema.XmlSchema>에 포함된 모든 <xref:System.Xml.Schema.XmlSchemaSet> 개체를 반환합니다. 또는 대상 네임스페이스 매개 변수를 지정한 경우 대상 네임스페이스에 속한 모든 <xref:System.Xml.Schema.XmlSchema> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-138">The <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property either returns all the <xref:System.Xml.Schema.XmlSchema> objects contained in the <xref:System.Xml.Schema.XmlSchemaSet>, or, given a target namespace parameter, returns all the <xref:System.Xml.Schema.XmlSchema> objects that belong to the target namespace.</span></span> <span data-ttu-id="a3f19-139">대상 네임스페이스 매개 변수로 `null`을 지정한 경우 <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> 속성은 네임스페이스가 없는 모든 스키마를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-139">If `null` is specified as the target namespace parameter, the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property returns all schemas without a namespace.</span></span>  
  
 <span data-ttu-id="a3f19-140">다음 예제에서는 `books.xsd` 네임스페이스의 `http://www.contoso.com/books` 스키마를 <xref:System.Xml.Schema.XmlSchemaSet>에 추가하고 `http://www.contoso.com/books`에서 <xref:System.Xml.Schema.XmlSchemaSet> 네임스페이스에 속한 모든 스키마를 검색한 다음 이 스키마를 <xref:System.Console>에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-140">The following example adds the `books.xsd` schema in the `http://www.contoso.com/books` namespace to an <xref:System.Xml.Schema.XmlSchemaSet>, retrieves all schemas that belong to the `http://www.contoso.com/books` namespace from the <xref:System.Xml.Schema.XmlSchemaSet>, and then writes those schemas to the <xref:System.Console>.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas("http://www.contoso.com/books")  
  
   schema.Write(Console.Out)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas("http://www.contoso.com/books"))  
{  
   schema.Write(Console.Out);  
}  
```  
  
 <span data-ttu-id="a3f19-141"><xref:System.Xml.Schema.XmlSchemaSet> 개체에서 스키마를 추가하고 검색하는 방법은 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> 메서드 및 <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> 속성 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3f19-141">For more information about adding and retrieving schemas from an <xref:System.Xml.Schema.XmlSchemaSet> object, see the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method and the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property reference documentation.</span></span>  
  
## <a name="compiling-schemas"></a><span data-ttu-id="a3f19-142">스키마 컴파일</span><span class="sxs-lookup"><span data-stu-id="a3f19-142">Compiling Schemas</span></span>  
 <span data-ttu-id="a3f19-143"><xref:System.Xml.Schema.XmlSchemaSet>의 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> 메서드를 사용하면 <xref:System.Xml.Schema.XmlSchemaSet>에 있는 스키마가 논리 스키마 한 개로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-143">Schemas in an <xref:System.Xml.Schema.XmlSchemaSet> are compiled into one logical schema by the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3f19-144">사용되지 않는 <xref:System.Xml.Schema.XmlSchemaCollection> 클래스와 달리 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> 메서드를 호출할 때 스키마가 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-144">Unlike the obsolete <xref:System.Xml.Schema.XmlSchemaCollection> class, schemas are not compiled when the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method is called.</span></span>  
  
 <span data-ttu-id="a3f19-145"><xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> 메서드를 성공적으로 실행한 경우 <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 속성은 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-145">If the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method executes successfully, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> is set to `true`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3f19-146"><xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>에 있는 동안 스키마를 편집해도 <xref:System.Xml.Schema.XmlSchemaSet> 속성에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-146">The <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property is not affected if schemas are edited while in the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="a3f19-147"><xref:System.Xml.Schema.XmlSchemaSet>에서 개별 스키마를 업데이트한 내용은 추적되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-147">Updates of the individual schemas in the <xref:System.Xml.Schema.XmlSchemaSet> are not tracked.</span></span> <span data-ttu-id="a3f19-148">결과적으로 <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>에 포함된 스키마 중 하나를 변경해도 `true`에서 스키마를 추가하거나 제거하지 않으면 <xref:System.Xml.Schema.XmlSchemaSet> 속성은 <xref:System.Xml.Schema.XmlSchemaSet>일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-148">As a result, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property can be `true` even though one of the schemas contained in the <xref:System.Xml.Schema.XmlSchemaSet> has been altered, as long as no schemas were added or removed from the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="a3f19-149">다음 예제에서는 `books.xsd` 파일을 <xref:System.Xml.Schema.XmlSchemaSet>에 추가하고 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-149">The following example adds the `books.xsd` file to the <xref:System.Xml.Schema.XmlSchemaSet> and then calls the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
schemaSet.Compile()  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
schemaSet.Compile();  
```  
  
 <span data-ttu-id="a3f19-150"><xref:System.Xml.Schema.XmlSchemaSet>의 스키마를 컴파일하는 방법은 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> 메서드 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3f19-150">For more information about compiling schemas in an <xref:System.Xml.Schema.XmlSchemaSet>, see the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method reference documentation.</span></span>  
  
## <a name="reprocessing-schemas"></a><span data-ttu-id="a3f19-151">스키마 다시 처리</span><span class="sxs-lookup"><span data-stu-id="a3f19-151">Reprocessing Schemas</span></span>  
 <span data-ttu-id="a3f19-152"><xref:System.Xml.Schema.XmlSchemaSet>에서 스키마를 다시 처리하면 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 메서드를 호출할 때 스키마에서 수행된 모든 전처리 단계가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-152">Reprocessing a schema in an <xref:System.Xml.Schema.XmlSchemaSet> performs all the preprocessing steps performed on a schema when the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is called.</span></span> <span data-ttu-id="a3f19-153"><xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> 메서드를 성공적으로 호출한 경우 <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 속성은 `false`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-153">If the call to the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method is successful, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> is set to `false`.</span></span>  
  
 <span data-ttu-id="a3f19-154"><xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>에서 컴파일을 수행한 후 <xref:System.Xml.Schema.XmlSchemaSet>의 스키마를 수정한 경우 <xref:System.Xml.Schema.XmlSchemaSet> 메서드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-154">The <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method should be used when a schema in the <xref:System.Xml.Schema.XmlSchemaSet> has been modified after the <xref:System.Xml.Schema.XmlSchemaSet> has performed compilation.</span></span>  
  
 <span data-ttu-id="a3f19-155">다음 예제에서는 <xref:System.Xml.Schema.XmlSchemaSet> 메서드를 사용하여 <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>에 추가한 스키마를 다시 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-155">The following example illustrates reprocessing a schema added to the <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method.</span></span> <span data-ttu-id="a3f19-156"><xref:System.Xml.Schema.XmlSchemaSet> 메서드를 사용하여 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>을 컴파일하고 <xref:System.Xml.Schema.XmlSchemaSet>에 추가된 스키마를 수정한 후에는 <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A>의 스키마를 수정했더라도 `true` 속성은 <xref:System.Xml.Schema.XmlSchemaSet>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-156">After the <xref:System.Xml.Schema.XmlSchemaSet> is compiled using the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method, and the schema added to the <xref:System.Xml.Schema.XmlSchemaSet> is modified, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property is set to `true` even though a schema in the <xref:System.Xml.Schema.XmlSchemaSet> has been modified.</span></span> <span data-ttu-id="a3f19-157"><xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> 메서드를 호출하면 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> 메서드에 의해 수행된 모든 전처리가 수행되며 <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> 속성이 `false`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-157">Calling the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method performs all the preprocessing performed by the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method, and sets the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property to `false`.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
Dim schema As XmlSchema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim element As XmlSchemaElement = New XmlSchemaElement()  
schema.Items.Add(element)  
element.Name = "book"  
element.SchemaTypeName = New XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema")  
  
schemaSet.Reprocess(schema)  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
XmlSchema schema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
XmlSchemaElement element = new XmlSchemaElement();  
schema.Items.Add(element);  
element.Name = "book";  
element.SchemaTypeName = new XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema");  
  
schemaSet.Reprocess(schema);  
```  
  
 <span data-ttu-id="a3f19-158"><xref:System.Xml.Schema.XmlSchemaSet>의 스키마를 다시 처리하는 방법은 <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> 메서드 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3f19-158">For more information about reprocessing a schema in an <xref:System.Xml.Schema.XmlSchemaSet>, see the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method reference documentation.</span></span>  
  
## <a name="checking-for-a-schema"></a><span data-ttu-id="a3f19-159">스키마 검사</span><span class="sxs-lookup"><span data-stu-id="a3f19-159">Checking for a Schema</span></span>  
 <span data-ttu-id="a3f19-160"><xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 메서드를 사용하여 스키마가 <xref:System.Xml.Schema.XmlSchemaSet>에 포함되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-160">You can use the <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> to check if a schema is contained within an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="a3f19-161"><xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> 메서드는 검사할 대상 네임스페이스 또는 <xref:System.Xml.Schema.XmlSchema> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-161">The <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method takes either a target namespace or an <xref:System.Xml.Schema.XmlSchema> object to check for.</span></span> <span data-ttu-id="a3f19-162">두 경우 모두 스키마가 <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> 내에 포함된 경우 `true` 메서드는 <xref:System.Xml.Schema.XmlSchemaSet>를 반환하며 그렇지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-162">In either case, the <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method returns `true` if the schema is contained within the <xref:System.Xml.Schema.XmlSchemaSet>; otherwise, it returns `false`.</span></span>  
  
 <span data-ttu-id="a3f19-163">스키마 검사에 대한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> 메서드 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3f19-163">For more information about checking for a schema, see the <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method reference documentation.</span></span>  
  
## <a name="removing-schemas"></a><span data-ttu-id="a3f19-164">스키마 제거</span><span class="sxs-lookup"><span data-stu-id="a3f19-164">Removing Schemas</span></span>  
 <span data-ttu-id="a3f19-165"><xref:System.Xml.Schema.XmlSchemaSet>의 <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> 및 <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> 메서드를 사용하여 <xref:System.Xml.Schema.XmlSchemaSet>에서 스키마를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-165">Schemas are removed from an <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> and <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="a3f19-166"><xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> 메서드는 <xref:System.Xml.Schema.XmlSchemaSet>에서 지정된 스키마를 제거하며 <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> 메서드는 지정된 스키마 및 이 스키마가 가져오는 모든 스키마를 <xref:System.Xml.Schema.XmlSchemaSet>에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-166">The <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> method removes the specified schema from the <xref:System.Xml.Schema.XmlSchemaSet>, while the <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> method removes the specified schema and all the schemas it imports from the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="a3f19-167">다음 예제에서는 <xref:System.Xml.Schema.XmlSchemaSet>에 여러 스키마를 추가하고 <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> 메서드를 사용하여 스키마 중 하나와 이 스키마가 가져오는 모든 스키마를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-167">The following example illustrates adding multiple schemas to an <xref:System.Xml.Schema.XmlSchemaSet>, then using the <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> method to remove one of the schemas and all the schemas it imports.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas()  
  
   If schema.TargetNamespace = "http://www.contoso.com/music" Then  
      schemaSet.RemoveRecursive(schema)  
   End If  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas())  
{  
   if (schema.TargetNamespace == "http://www.contoso.com/music")  
   {  
      schemaSet.RemoveRecursive(schema);  
   }  
}  
```  
  
 <span data-ttu-id="a3f19-168"><xref:System.Xml.Schema.XmlSchemaSet>에서 스키마를 제거하는 방법은 <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> 및 <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> 메서드 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3f19-168">For more information about removing schemas from an <xref:System.Xml.Schema.XmlSchemaSet>, see the <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> and <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> methods reference documentation.</span></span>  
  
## <a name="schema-resolution-and-xsimport"></a><span data-ttu-id="a3f19-169">스키마 확인 및 xs:import</span><span class="sxs-lookup"><span data-stu-id="a3f19-169">Schema Resolution and xs:import</span></span>  
 <span data-ttu-id="a3f19-170">다음 예제에서는 지정된 네임스페이스에 대한 여러 스키마가 <xref:System.Xml.Schema.XmlSchemaSet>에 있을 경우 스키마를 가져오는 <xref:System.Xml.Schema.XmlSchemaSet> 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-170">The following examples describe the <xref:System.Xml.Schema.XmlSchemaSet> behavior for importing schemas when multiple schemas for a given namespace exist in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="a3f19-171">예를 들어, <xref:System.Xml.Schema.XmlSchemaSet> 네임스페이스에 대한 여러 스키마가 포함된 `http://www.contoso.com`을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-171">For example, consider an <xref:System.Xml.Schema.XmlSchemaSet> that contains multiple schemas for the `http://www.contoso.com` namespace.</span></span> <span data-ttu-id="a3f19-172">다음 `xs:import` 지시문이 있는 스키마가 <xref:System.Xml.Schema.XmlSchemaSet>에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-172">A schema with the following `xs:import` directive is added to the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
```xml  
<xs:import namespace="http://www.contoso.com" schemaLocation="http://www.contoso.com/schema.xsd" />  
```  
  
 <span data-ttu-id="a3f19-173"><xref:System.Xml.Schema.XmlSchemaSet>은 `http://www.contoso.com` URL에서 `http://www.contoso.com/schema.xsd` 네임스페이스에 대한 스키마를 로드하여 가져오려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-173">The <xref:System.Xml.Schema.XmlSchemaSet> attempts to import a schema for the `http://www.contoso.com` namespace by loading it from the `http://www.contoso.com/schema.xsd` URL.</span></span> <span data-ttu-id="a3f19-174">`http://www.contoso.com`에 <xref:System.Xml.Schema.XmlSchemaSet> 네임스페이스에 대한 다른 스키마 문서가 있더라도 가져오는 스키마에서는 스키마 선언 및 스키마 문서에서 선언된 형식만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-174">Only the schema declaration and types declared in the schema document are available in the importing schema, even though there are other schema documents for the `http://www.contoso.com` namespace in the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="a3f19-175">`schema.xsd` 파일을 `http://www.contoso.com/schema.xsd` URL에서 찾을 수 없으면 가져오는 스키마로 `http://www.contoso.com` 네임스페이스에 대한 스키마를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-175">If the `schema.xsd` file cannot be located at the `http://www.contoso.com/schema.xsd` URL, no schema for the `http://www.contoso.com` namespace is imported into the importing schema.</span></span>  
  
## <a name="validating-xml-documents"></a><span data-ttu-id="a3f19-176">XML 문서 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a3f19-176">Validating XML Documents</span></span>  
 <span data-ttu-id="a3f19-177"><xref:System.Xml.Schema.XmlSchemaSet>의 스키마에 대해 XML 문서의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-177">XML documents can be validated against schemas in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="a3f19-178"><xref:System.Xml.Schema.XmlSchemaSet> 개체의 <xref:System.Xml.XmlReaderSettings.Schemas%2A><xref:System.Xml.XmlReaderSettings> 속성에 스키마를 추가하거나 <xref:System.Xml.Schema.XmlSchemaSet> 개체의 <xref:System.Xml.XmlReaderSettings.Schemas%2A> 속성에 <xref:System.Xml.XmlReaderSettings>을 추가하여 XML 문서의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-178">You validate an XML document by adding a schema to the <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> property of an <xref:System.Xml.XmlReaderSettings> object, or by adding an <xref:System.Xml.Schema.XmlSchemaSet> to the <xref:System.Xml.XmlReaderSettings.Schemas%2A> property of an <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="a3f19-179">그런 다음 <xref:System.Xml.XmlReaderSettings> 클래스의 <xref:System.Xml.XmlReader.Create%2A> 메서드에서 <xref:System.Xml.XmlReader> 개체를 사용하여 <xref:System.Xml.XmlReader> 개체를 만들고 XML 문서의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-179">The <xref:System.Xml.XmlReaderSettings> object is then used by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class to create an <xref:System.Xml.XmlReader> object and validate the XML document.</span></span>  
  
 <span data-ttu-id="a3f19-180">XML 유효성을 검사 하는 방법에 대 한 자세한 내용은 사용 하 여 문서는 <xref:System.Xml.Schema.XmlSchemaSet>, 참조 [XmlSchemaSet 사용 하 여 XSD (XML 스키마) 유효성](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemaset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f19-180">For more information about validating XML documents using an <xref:System.Xml.Schema.XmlSchemaSet>, see [XML Schema (XSD) Validation with XmlSchemaSet](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemaset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f19-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3f19-181">See Also</span></span>  
 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>  
 <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>  
 <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>  
 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>  
 <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>  
 <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>  
 <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>  
 [<span data-ttu-id="a3f19-182">XmlSchemaSet으로 스키마 캐시</span><span class="sxs-lookup"><span data-stu-id="a3f19-182">XmlSchemaSet as a Schema Cache</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [<span data-ttu-id="a3f19-183">XmlSchemaSet는 XML 스키마 (XSD) 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a3f19-183">XML Schema (XSD) Validation with XmlSchemaSet</span></span>](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemaset.md)
