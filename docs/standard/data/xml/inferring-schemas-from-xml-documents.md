---
title: "XML 문서에서 스키마 유추"
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
- cpp
ms.assetid: f3d97d53-614d-4a04-a174-87965b7405f6
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8085ecb86018460f14a2532b55907472988b67b2
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="inferring-schemas-from-xml-documents"></a><span data-ttu-id="8362f-102">XML 문서에서 스키마 유추</span><span class="sxs-lookup"><span data-stu-id="8362f-102">Inferring Schemas from XML Documents</span></span>
<span data-ttu-id="8362f-103">이 항목에서는 <xref:System.Xml.Schema.XmlSchemaInference> 클래스를 사용하여 XML 문서 구조에서 XSD(XML 스키마 정의 언어) 스키마를 유추하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-103">This topic describes how to use the <xref:System.Xml.Schema.XmlSchemaInference> class to infer an XML Schema definition language (XSD) schema from the structure of an XML document.</span></span>  
  
## <a name="the-schema-inference-process"></a><span data-ttu-id="8362f-104">스키마 유추 과정</span><span class="sxs-lookup"><span data-stu-id="8362f-104">The Schema Inference Process</span></span>  
 <span data-ttu-id="8362f-105"><xref:System.Xml.Schema.XmlSchemaInference> 네임스페이스의 <xref:System.Xml.Schema?displayProperty=nameWithType> 클래스는 XML 문서 구조에서 XSD(XML 스키마 정의 언어) 스키마를 하나 이상 생성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-105">The <xref:System.Xml.Schema.XmlSchemaInference> class of the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace is used to generate one or more XML Schema definition language (XSD) schemas from the structure of an XML document.</span></span> <span data-ttu-id="8362f-106">생성된 스키마는 원래 XML 문서의 유효성을 검사하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-106">The generated schemas may be used to validate the original XML document.</span></span>  
  
 <span data-ttu-id="8362f-107"><xref:System.Xml.Schema.XmlSchemaInference> 클래스에서 XML 문서를 처리할 때 <xref:System.Xml.Schema.XmlSchemaInference> 클래스는 XML 문서의 요소와 특성을 설명하는 스키마 구성 요소에 대해 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-107">As an XML document is processed by the <xref:System.Xml.Schema.XmlSchemaInference> class, the <xref:System.Xml.Schema.XmlSchemaInference> class makes assumptions about the schema components that describe the elements and attributes in the XML document.</span></span> <span data-ttu-id="8362f-108">또한 <xref:System.Xml.Schema.XmlSchemaInference> 클래스는 특정 요소 또는 특성에 대해 가장 제한적인 형식을 유추함으로써 제약된 방식으로 스키마 구성 요소를 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-108">The <xref:System.Xml.Schema.XmlSchemaInference> class also infers schema components in a constrained way by inferring the most restrictive type for a particular element or attribute.</span></span> <span data-ttu-id="8362f-109">XML 문서에 대한 상세한 정보가 수집되면 이 제약 조건은 덜 제한적인 형식을 유추하여 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-109">As more information about the XML document is gathered, these constraints are loosened by inferring less restrictive types.</span></span> <span data-ttu-id="8362f-110">유추되는 형식 중 가장 제한이 적은 형식은 `xs:string`입니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-110">The least restrictive type that can be inferred is `xs:string`.</span></span>  
  
 <span data-ttu-id="8362f-111">다음 XML 문서의 일부를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-111">Take, for example, the following piece of an XML document.</span></span>  
  
```xml  
<parent attribute1="6">  
    <child>One</child>  
    <child>Two</child>  
</parent>  
<parent attribute1="A">  
```  
  
 <span data-ttu-id="8362f-112">위의 예제에서 `attribute1` 특성이 `6` 프로세스에 의해 값 <xref:System.Xml.Schema.XmlSchemaInference>을 발견하면 `xs:unsignedByte` 형식으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-112">In the example above, when the `attribute1` attribute is encountered with a value of `6` by the <xref:System.Xml.Schema.XmlSchemaInference> process, it is assumed to be of type `xs:unsignedByte`.</span></span> <span data-ttu-id="8362f-113">`parent` 프로세스가 두 번째 <xref:System.Xml.Schema.XmlSchemaInference> 요소를 발견하면 해당 `xs:string` 특성 값이 `attribute1`이므로 `A` 형식으로 수정하여 제약 조건을 완화합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-113">When the second `parent` element is encountered by the <xref:System.Xml.Schema.XmlSchemaInference> process, the constraint is loosened by modifying the type to `xs:string` because the value of the `attribute1` attribute is now `A`.</span></span> <span data-ttu-id="8362f-114">마찬가지로 스키마에서 유추되는 모든 `minOccurs` 요소의 `child` 특성은 두 번째 부모 요소에 자식 요소가 없기 때문에 `minOccurs="0"`으로 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-114">Similarly, the `minOccurs` attribute for all the `child` elements inferred in the schema are loosened to `minOccurs="0"` because the second parent element has no child elements.</span></span>  
  
## <a name="inferring-schemas-from-xml-documents"></a><span data-ttu-id="8362f-115">XML 문서에서 스키마 유추</span><span class="sxs-lookup"><span data-stu-id="8362f-115">Inferring Schemas from XML Documents</span></span>  
 <span data-ttu-id="8362f-116"><xref:System.Xml.Schema.XmlSchemaInference> 클래스는 오버로드된 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드 두 개를 사용하여 XML 문서에서 스키마를 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-116">The <xref:System.Xml.Schema.XmlSchemaInference> class uses two overloaded <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> methods to infer a schema from an XML document.</span></span>  
  
 <span data-ttu-id="8362f-117">첫 번째 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> 메서드는 XML 문서를 기반으로 스키마를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-117">The first <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> method is used to create a schema based on an XML document.</span></span> <span data-ttu-id="8362f-118">두 번째 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> 메서드는 여러 XML 문서를 설명하는 스키마를 유추하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-118">The second <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> method is used to infer a schema that describes multiple XML documents.</span></span> <span data-ttu-id="8362f-119">예를 들어, 여러 XML 문서를 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> 메서드에 한 번에 하나씩 공급하여 전체 XML 문서 집합을 설명하는 스키마를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-119">For example, you can feed multiple XML documents to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> method one at a time to produce a schema that describes the entire set of XML documents.</span></span>  
  
 <span data-ttu-id="8362f-120">첫 번째 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> 메서드는 <xref:System.Xml.XmlReader> 개체에 들어 있는 XML 문서에서 스키마를 유추하고 유추된 스키마가 들어 있는 <xref:System.Xml.Schema.XmlSchemaSet> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-120">The first <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> method infers a schema from an XML document contained in an <xref:System.Xml.XmlReader> object, and returns an <xref:System.Xml.Schema.XmlSchemaSet> object containing the inferred schema.</span></span> <span data-ttu-id="8362f-121">두 번째 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> 메서드는 <xref:System.Xml.Schema.XmlSchemaSet> 개체를 검색하여 <xref:System.Xml.XmlReader> 개체에 들어 있는 XML 문서와 같은 대상 네임스페이스를 가진 스키마를 찾고 기존 스키마를 구체화한 다음 유추된 스키마가 들어 있는 <xref:System.Xml.Schema.XmlSchemaSet> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-121">The second <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> method searches an <xref:System.Xml.Schema.XmlSchemaSet> object for a schema with the same target namespace as the XML document contained in the <xref:System.Xml.XmlReader> object, refines the existing schema, and returns an <xref:System.Xml.Schema.XmlSchemaSet> object containing the inferred schema.</span></span>  
  
 <span data-ttu-id="8362f-122">구체화된 스키마에 대한 변경 내용은 XML 문서에 나타나는 새로운 구조를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-122">The changes made to the refined schema are based on new structure found in the XML document.</span></span> <span data-ttu-id="8362f-123">예를 들어, XML 문서를 살펴볼 때 발견한 데이터 형식에 대해 가정하고 이 가정을 기반으로 스키마를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-123">For example, as an XML document is traversed, assumptions are made about the data types found, and the schema is created based on those assumptions.</span></span> <span data-ttu-id="8362f-124">하지만 원래 가정과 다른 두 번째 유추 과정에서 데이터가 발견되면 스키마는 구체화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-124">However, if data is encountered on a second inference pass that differs from the original assumption, the schema is refined.</span></span> <span data-ttu-id="8362f-125">다음 예제에서는 구체화 과정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-125">The following example illustrates the refinement process.</span></span>  
  
 [!code-cpp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaInferenceExamples/CPP/XmlSchemaInferenceExamples.cpp#4)]
 [!code-csharp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaInferenceExamples/CS/XmlSchemaInferenceExamples.cs#4)]
 [!code-vb[XmlSchemaInferenceExamples#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaInferenceExamples/VB/XmlSchemaInferenceExamples.vb#4)]  
  
 <span data-ttu-id="8362f-126">이 예제에서는 다음 `item1.xml` 파일을 첫 번째 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-126">The example takes the following file, `item1.xml`, as its first input.</span></span>  
  
 [!code-xml[XmlSchemaInferenceExamples#13](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item1.xml#13)]  
  
 <span data-ttu-id="8362f-127">그런 다음 `item2.xml` 파일을 두 번째 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-127">The example then takes the `item2.xml` file as its second input:</span></span>  
  
 [!code-xml[XmlSchemaInferenceExamples#14](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item2.xml#14)]  
  
 <span data-ttu-id="8362f-128">첫 번째 XML 문서에서 `productID` 특성이 발견되면 `123456789` 값은 `xs:unsignedInt` 형식으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-128">When the `productID` attribute is encountered in the first XML document, the value of `123456789` is assumed to be an `xs:unsignedInt` type.</span></span> <span data-ttu-id="8362f-129">하지만 두 번째 XML 문서를 읽고 `A53-246` 값이 있으면 더 이상 `xs:unsignedInt` 형식으로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-129">However, when the second XML document is read and the value of `A53-246` is found, the `xs:unsignedInt` type can no longer be assumed.</span></span> <span data-ttu-id="8362f-130">스키마가 구체화되고 `productID`의 형식이 `xs:string`으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-130">The schema is refined and the type of `productID` is changed to `xs:string`.</span></span> <span data-ttu-id="8362f-131">또한 두 번째 XML 문서에 `minOccurs` 요소가 없기 때문에 `supplierID` 요소에 대한 `0` 특성이 `supplierID`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-131">In addition, the `minOccurs` attribute for the `supplierID` element is set to `0`, because the second XML document contains no `supplierID` element.</span></span>  
  
 <span data-ttu-id="8362f-132">다음은 첫 번째 XML 문서에서 유추된 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-132">The following is the schema inferred from the first XML document.</span></span>  
  
 [!code-xml[XmlSchemaInferenceExamples#15](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema1.xml#15)]  
  
 <span data-ttu-id="8362f-133">다음은 첫 번째 XML 문서에서 유추되고 두 번째 XML 문서에서 구체화된 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-133">The following is the schema inferred from the first XML document, refined by the second XML document.</span></span>  
  
 [!code-xml[XmlSchemaInferenceExamples#16](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema2.xml#16)]  
  
## <a name="inline-schemas"></a><span data-ttu-id="8362f-134">인라인 스키마</span><span class="sxs-lookup"><span data-stu-id="8362f-134">Inline Schemas</span></span>  
 <span data-ttu-id="8362f-135"><xref:System.Xml.Schema.XmlSchemaInference> 프로세스에서 인라인 XSD(XML 스키마 정의 언어) 스키마가 발견되면 <xref:System.Xml.Schema.XmlSchemaInferenceException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-135">If an inline XML Schema definition language (XSD) schema is encountered during the <xref:System.Xml.Schema.XmlSchemaInference> process, an <xref:System.Xml.Schema.XmlSchemaInferenceException> is thrown.</span></span> <span data-ttu-id="8362f-136">예를 들어, 다음 인라인 스키마는 <xref:System.Xml.Schema.XmlSchemaInferenceException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-136">For example, the following inline schema throws an <xref:System.Xml.Schema.XmlSchemaInferenceException>.</span></span>  
  
```xml  
<root xmlns:ex="http://www.contoso.com" xmlns="http://www.tempuri.org">  
    <xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://www.contoso.com">  
        <xs:element name="Contoso" type="xs:normalizedString" />  
    </xs:schema>  
    <ex:Contoso>Test</ex:Contoso>  
</root>  
```  
  
## <a name="schemas-that-cannot-be-refined"></a><span data-ttu-id="8362f-137">구체화할 수 없는 스키마</span><span class="sxs-lookup"><span data-stu-id="8362f-137">Schemas that Cannot be Refined</span></span>  
 <span data-ttu-id="8362f-138">구체화하고 예외를 throw할 형식이 지정될 경우 XSD(XML 스키마 정의 언어) 스키마 <xref:System.Xml.Schema.XmlSchemaInference> 프로세스에서 처리할 수 없는 W3C XML 스키마 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-138">There are W3C XML Schema constructs that the XML Schema definition language (XSD) schema <xref:System.Xml.Schema.XmlSchemaInference> process cannot handle if given a type to refine and cause an exception to be thrown.</span></span> <span data-ttu-id="8362f-139">최상위 compositor가 시퀀스가 아닌 복합 형식 등이 이에 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-139">Such as a complex type whose top-level compositor is anything other than a sequence.</span></span> <span data-ttu-id="8362f-140">SOM(스키마 개체 모델)에서 이 스키마는 <xref:System.Xml.Schema.XmlSchemaComplexType> 속성이 <xref:System.Xml.Schema.XmlSchemaComplexType.Particle%2A>의 인스턴스가 아닌 <xref:System.Xml.Schema.XmlSchemaSequence>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8362f-140">In the Schema Object Model (SOM), this corresponds to an <xref:System.Xml.Schema.XmlSchemaComplexType> whose <xref:System.Xml.Schema.XmlSchemaComplexType.Particle%2A> property is not an instance of <xref:System.Xml.Schema.XmlSchemaSequence>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8362f-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8362f-141">See Also</span></span>  
 <xref:System.Xml.Schema.XmlSchemaInference>  
 [<span data-ttu-id="8362f-142">XML SOM(스키마 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="8362f-142">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 [<span data-ttu-id="8362f-143">XML 스키마 유추</span><span class="sxs-lookup"><span data-stu-id="8362f-143">Inferring an XML Schema</span></span>](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 [<span data-ttu-id="8362f-144">스키마 노드 형식 및 구조 유추 규칙</span><span class="sxs-lookup"><span data-stu-id="8362f-144">Rules for Inferring Schema Node Types and Structure</span></span>](../../../../docs/standard/data/xml/rules-for-inferring-schema-node-types-and-structure.md)  
 [<span data-ttu-id="8362f-145">단순 형식 유추 규칙</span><span class="sxs-lookup"><span data-stu-id="8362f-145">Rules for Inferring Simple Types</span></span>](../../../../docs/standard/data/xml/rules-for-inferring-simple-types.md)
