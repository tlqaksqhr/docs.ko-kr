---
title: "XML 스키마 편집"
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
ms.assetid: fa09c8e5-c2b9-49d2-bb0d-40330cd13e4d
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b9505f60b2000ef227463404dab051ecb7fa3cc5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="editing-xml-schemas"></a><span data-ttu-id="2da84-102">XML 스키마 편집</span><span class="sxs-lookup"><span data-stu-id="2da84-102">Editing XML Schemas</span></span>
<span data-ttu-id="2da84-103">XML 스키마 편집 기능은 SOM(스키마 개체 모델)의 중요한 기능 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-103">Editing an XML schema is one of the most important features of the Schema Object Model (SOM).</span></span> <span data-ttu-id="2da84-104">SOM의 모든 pre-schema-compilation 속성을 사용하여 XML 스키마에서 기존 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-104">All of the pre-schema-compilation properties of the SOM can be used to change the existing values in an XML schema.</span></span> <span data-ttu-id="2da84-105">그런 다음 XML 스키마를 다시 컴파일하여 변경 내용을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-105">The XML schema can then be recompiled to reflect the changes.</span></span>  
  
 <span data-ttu-id="2da84-106">SOM에 로드된 스키마를 편집하는 첫 번째 단계는 스키마를 통과하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-106">The first step in editing a schema loaded into the SOM is to traverse the schema.</span></span> <span data-ttu-id="2da84-107">스키마를 편집하기 전에 SOM API를 사용하여 스키마를 통과하는 방법을 잘 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-107">You should be familiar with traversing a schema using the SOM API before you attempt to edit a schema.</span></span> <span data-ttu-id="2da84-108">또한 PSCI(Post-Schema-Compilation-Infoset)의 pre-schema-compilation 속성과 post-schema-compilation 속성에 대해 잘 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-108">You should also be familiar with the pre- and post-schema-compilation properties of the Post-Schema-Compilation-Infoset (PSCI).</span></span>  
  
## <a name="editing-an-xml-schema"></a><span data-ttu-id="2da84-109">XML 스키마 편집</span><span class="sxs-lookup"><span data-stu-id="2da84-109">Editing an XML Schema</span></span>  
 <span data-ttu-id="2da84-110">이 섹션에서는 두 가지 코드 예제가 제공 된 경우에서 생성 하는 고객 스키마를 편집 하 고 [XML 스키마 빌드](../../../../docs/standard/data/xml/building-xml-schemas.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-110">In this section, two code examples are provided, both of which edit the customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic.</span></span> <span data-ttu-id="2da84-111">첫 번째 코드 예제는 새 `PhoneNumber` 요소를 `Customer` 요소에 추가하며 두 번째 코드 예제는 새 `Title` 특성을 `FirstName` 요소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-111">The first code example adds a new `PhoneNumber` element to the `Customer` element and the second code example adds a new `Title` attribute to the `FirstName` element.</span></span> <span data-ttu-id="2da84-112">또한 첫 번째 샘플에서는 post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> 컬렉션을 사용하여 고객 스키마를 통과하며 두 번째 코드 예제에서는 pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> 컬렉션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-112">The first sample also uses the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection as the means of traversing the customer schema while the second code example uses the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>  
  
### <a name="phonenumber-element-example"></a><span data-ttu-id="2da84-113">PhoneNumber 요소 예제</span><span class="sxs-lookup"><span data-stu-id="2da84-113">PhoneNumber Element Example</span></span>  
 <span data-ttu-id="2da84-114">이 첫 번째 코드 예제에서는 새 `PhoneNumber` 요소를 고객 스키마의 `Customer` 요소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-114">This first code example adds a new `PhoneNumber` element to the `Customer` element of the customer schema.</span></span> <span data-ttu-id="2da84-115">이 코드 예제는 다음과 같은 단계로 고객 스키마를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-115">The code example edits the customer schema in the following steps.</span></span>  
  
1.  <span data-ttu-id="2da84-116">고객 스키마를 새 <xref:System.Xml.Schema.XmlSchemaSet> 개체에 추가한 다음 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-116">Adds the customer schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles it.</span></span> <span data-ttu-id="2da84-117">스키마를 읽거나 컴파일할 때 발생하는 모든 스키마 유효성 검사 경고 및 오류는 <xref:System.Xml.Schema.ValidationEventHandler> 대리자에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-117">Any schema validation warnings and errors encountered reading or compiling the schema are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>  
  
2.  <span data-ttu-id="2da84-118"><xref:System.Xml.Schema.XmlSchema> 속성을 반복하여 <xref:System.Xml.Schema.XmlSchemaSet>에서 컴파일된 <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-118">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> object from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="2da84-119">스키마가 컴파일되므로 PSCI(Post-Schema-Compilation-Infoset) 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-119">Because the schema is compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>  
  
3.  <span data-ttu-id="2da84-120">`PhoneNumber` 클래스를 사용하여 <xref:System.Xml.Schema.XmlSchemaElement> 요소를 만들고, `xs:string` 및 <xref:System.Xml.Schema.XmlSchemaSimpleType> 클래스를 사용하여 <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> 단순 형식 제한을 만들고, 이 제한의 <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A> 속성에 패턴 패싯을 추가하고 이 제한을 단순 형식의 <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A> 속성에 추가하고 단순 형식을 <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> 요소의 `PhoneNumber`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-120">Creates the `PhoneNumber` element using the <xref:System.Xml.Schema.XmlSchemaElement> class, the `xs:string` simple type restriction using the <xref:System.Xml.Schema.XmlSchemaSimpleType> and <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> classes, adds a pattern facet to the <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A> property of the restriction, and adds the restriction to the <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A> property of the simple type and the simple type to the <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> of the `PhoneNumber` element.</span></span>  
  
4.  <span data-ttu-id="2da84-121">post-schema-compilation <xref:System.Xml.Schema.XmlSchemaElement> 컬렉션의 <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> 컬렉션에서 각 <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-121">Iterates over each <xref:System.Xml.Schema.XmlSchemaElement> in the <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> collection of the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection.</span></span>  
  
5.  <span data-ttu-id="2da84-122">요소의 <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A>이 `"Customer"`인 경우 `Customer` 클래스를 사용하여 <xref:System.Xml.Schema.XmlSchemaComplexType> 요소의 복합 형식을 얻고 <xref:System.Xml.Schema.XmlSchemaSequence> 클래스를 사용하여 복합 형식의 sequence 파티클을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-122">If the <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> of the element is `"Customer"`, gets the complex type of the `Customer` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class and the sequence particle of the complex type using the <xref:System.Xml.Schema.XmlSchemaSequence> class.</span></span>  
  
6.  <span data-ttu-id="2da84-123">기존 `PhoneNumber` 및 `FirstName` 요소가 포함된 시퀀스의 pre-schema-compilation `LastName` 컬렉션을 사용하여 이 시퀀스에 새 <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A> 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-123">Adds the new `PhoneNumber` element to the sequence containing the existing `FirstName` and `LastName` elements using the pre-schema-compilation <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A> collection of the sequence.</span></span>  
  
7.  <span data-ttu-id="2da84-124">마지막으로, <xref:System.Xml.Schema.XmlSchema> 클래스의 <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> 및 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> 메서드를 사용하여 수정된 <xref:System.Xml.Schema.XmlSchemaSet> 개체를 다시 처리하고 컴파일하여 콘솔에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-124">Finally, reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>  
  
 <span data-ttu-id="2da84-125">다음은 전체 코드 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-125">The following is the complete code example.</span></span>  
  
 [!code-cpp[XmlSchemaEditExample1#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample1/CPP/XmlSchemaEditExample1.cpp#1)]
 [!code-csharp[XmlSchemaEditExample1#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample1/CS/XmlSchemaEditExample1.cs#1)]
 [!code-vb[XmlSchemaEditExample1#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample1/VB/XmlSchemaEditExample1.vb#1)]  
  
 <span data-ttu-id="2da84-126">다음은에서 만든 수정 된 고객 스키마의 [XML 스키마 빌드](../../../../docs/standard/data/xml/building-xml-schemas.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-126">The following is the modified customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="Customer">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="FirstName" type="xs:string" />  
        <xs:element name="LastName" type="tns:LastNameType" />  
        <xs:element name="PhoneNumber">           <xs:simpleType>             <xs:restriction base="xs:string">               <xs:pattern value="\d{3}-\d{3}-\d(4)" />             </xs:restriction>           </xs:simpleType>         </xs:element>  
      </xs:sequence>  
      <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" /  
>  
    </xs:complexType>  
  </xs:element>  
  <xs:simpleType name="LastNameType">  
    <xs:restriction base="xs:string">  
      <xs:maxLength value="20" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
### <a name="title-attribute-example"></a><span data-ttu-id="2da84-127">Title 특성 예제</span><span class="sxs-lookup"><span data-stu-id="2da84-127">Title Attribute Example</span></span>  
 <span data-ttu-id="2da84-128">이 두 번째 코드 예제에서는 새 `Title` 특성을 고객 스키마의 `FirstName` 요소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-128">This second code example, adds a new `Title` attribute to the `FirstName` element of the customer schema.</span></span> <span data-ttu-id="2da84-129">첫 번째 코드 예제에서 `FirstName` 요소의 형식은 `xs:string`입니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-129">In the first code example, the type of the `FirstName` element is `xs:string`.</span></span> <span data-ttu-id="2da84-130">`FirstName` 요소가 문자열 내용과 함께 특성을 가지려면 그 형식을 단순 내용 확장 내용 모델이 있는 복합 형식으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-130">For the `FirstName` element to have an attribute along with string content, its type must be changed to a complex type with a simple content extension content model.</span></span>  
  
 <span data-ttu-id="2da84-131">이 코드 예제는 다음과 같은 단계로 고객 스키마를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-131">The code example edits the customer schema in the following steps.</span></span>  
  
1.  <span data-ttu-id="2da84-132">고객 스키마를 새 <xref:System.Xml.Schema.XmlSchemaSet> 개체에 추가한 다음 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-132">Adds the customer schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles it.</span></span> <span data-ttu-id="2da84-133">스키마를 읽거나 컴파일할 때 발생하는 모든 스키마 유효성 검사 경고 및 오류는 <xref:System.Xml.Schema.ValidationEventHandler> 대리자에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-133">Any schema validation warnings and errors encountered reading or compiling the schema are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>  
  
2.  <span data-ttu-id="2da84-134"><xref:System.Xml.Schema.XmlSchema> 속성을 반복하여 <xref:System.Xml.Schema.XmlSchemaSet>에서 컴파일된 <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-134">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> object from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="2da84-135">스키마가 컴파일되므로 PSCI(Post-Schema-Compilation-Infoset) 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-135">Because the schema is compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>  
  
3.  <span data-ttu-id="2da84-136">`FirstName` 클래스를 사용하여 <xref:System.Xml.Schema.XmlSchemaComplexType> 요소에 대한 새 복합 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-136">Creates a new complex type for the `FirstName` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class.</span></span>  
  
4.  <span data-ttu-id="2da84-137">`xs:string` 및 <xref:System.Xml.Schema.XmlSchemaSimpleContent> 클래스를 사용하여 <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension>의 기본 형식으로 새 단순 내용 확장을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-137">Creates a new simple content extension, with a base type of `xs:string`, using the <xref:System.Xml.Schema.XmlSchemaSimpleContent> and <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension> classes.</span></span>  
  
5.  <span data-ttu-id="2da84-138">`Title` 클래스를 사용하여 <xref:System.Xml.Schema.XmlSchemaAttribute>의 <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A>으로 새 `xs:string` 특성을 만들고 이 특성을 단순 내용 확장에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-138">Creates the new `Title` attribute using the <xref:System.Xml.Schema.XmlSchemaAttribute> class, with a <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> of `xs:string` and adds the attribute to the simple content extension.</span></span>  
  
6.  <span data-ttu-id="2da84-139">단순 내용의 내용 모델을 단순 내용 확장으로 설정하고 복합 형식의 내용 모델을 단순 내용으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-139">Sets the content model of the simple content to the simple content extension and the content model of the complex type to the simple content.</span></span>  
  
7.  <span data-ttu-id="2da84-140">새 복합 형식을 pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-140">Adds the new complex type to the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>  
  
8.  <span data-ttu-id="2da84-141">스키마 사전 컴파일 <xref:System.Xml.Schema.XmlSchemaObject> 컬렉션의 각 <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-141">Iterates over each <xref:System.Xml.Schema.XmlSchemaObject> in the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2da84-142">`FirstName` 요소는 스키마에서 전역 요소가 아니므로 <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> 또는 <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> 컬렉션에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-142">Because the `FirstName` element is not a global element in the schema, it is not available in the <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> or <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collections.</span></span> <span data-ttu-id="2da84-143">이 코드 예제에서는 먼저 `FirstName` 요소를 찾아서 `Customer` 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-143">The code example locates the `FirstName` element by first locating the `Customer` element.</span></span>  
>   
>  <span data-ttu-id="2da84-144">첫 번째 코드 예제에서는 post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> 컬렉션을 사용하여 스키마를 통과했습니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-144">The first code example traversed the schema using the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="2da84-145">이 샘플에서는 pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> 컬렉션을 사용하여 스키마를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-145">In this sample, the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection is used to traverse the schema.</span></span> <span data-ttu-id="2da84-146">두 컬렉션은 모두 스키마에서 전역 요소에 대한 액세스를 제공하지만 <xref:System.Xml.Schema.XmlSchema.Items%2A> 컬렉션을 반복하면 스키마에서 모든 전역 요소를 반복해야 하므로 시간이 더 많이 걸리며 PSCI 속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-146">While both collections provide access to the global elements in the schema, iterating through the <xref:System.Xml.Schema.XmlSchema.Items%2A> collection is more time consuming because you must iterate over all global elements in the schema and it does not have any PSCI properties.</span></span> <span data-ttu-id="2da84-147"><xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType> 등의 PSCI 컬렉션에서는 전역 요소, 특성 및 형식과 해당 PSCI 속성에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-147">The PSCI collections (<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType>, and so on) provide direct access to their global elements, attributes, and types and their PSCI properties.</span></span>  
  
1.  <span data-ttu-id="2da84-148"><xref:System.Xml.Schema.XmlSchemaObject>가 <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A>이 `"Customer"`인 요소일 경우 `Customer` 클래스를 사용하여 <xref:System.Xml.Schema.XmlSchemaComplexType> 요소의 복합 형식을 얻고 <xref:System.Xml.Schema.XmlSchemaSequence> 클래스를 사용하여 복합 형식의 sequence 파티클을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-148">If the <xref:System.Xml.Schema.XmlSchemaObject> is an element, whose <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> is `"Customer"`, gets the complex type of the `Customer` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class and the sequence particle of the complex type using the <xref:System.Xml.Schema.XmlSchemaSequence> class.</span></span>  
  
2.  <span data-ttu-id="2da84-149">스키마 사전 컴파일 <xref:System.Xml.Schema.XmlSchemaParticle> 컬렉션의 각 <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType>를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-149">Iterates over each <xref:System.Xml.Schema.XmlSchemaParticle> in the pre-schema-compilation <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="2da84-150"><xref:System.Xml.Schema.XmlSchemaParticle>이 <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A>이 `"FirstName"`인 요소일 경우 <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> 요소의 `FirstName`을 새 `FirstName` 복합 형식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-150">If the <xref:System.Xml.Schema.XmlSchemaParticle> is an element, who's <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> is `"FirstName"`, sets the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> of the `FirstName` element to the new `FirstName` complex type.</span></span>  
  
4.  <span data-ttu-id="2da84-151">마지막으로, <xref:System.Xml.Schema.XmlSchema> 클래스의 <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> 및 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> 메서드를 사용하여 수정된 <xref:System.Xml.Schema.XmlSchemaSet> 개체를 다시 처리하고 컴파일하여 콘솔에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-151">Finally, reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>  
  
 <span data-ttu-id="2da84-152">다음은 전체 코드 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-152">The following is the complete code example.</span></span>  
  
 [!code-cpp[XmlSchemaEditExample2#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample2/CPP/XmlSchemaEditExample2.cpp#1)]
 [!code-csharp[XmlSchemaEditExample2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample2/CS/XmlSchemaEditExample2.cs#1)]
 [!code-vb[XmlSchemaEditExample2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample2/VB/XmlSchemaEditExample2.vb#1)]  
  
 <span data-ttu-id="2da84-153">다음은에서 만든 수정 된 고객 스키마의 [XML 스키마 빌드](../../../../docs/standard/data/xml/building-xml-schemas.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="2da84-153">The following is the modified customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic.</span></span>  
  
```xml  
<?xml version="1.0" encoding=" utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="Customer">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="FirstName" type="tns:FirstNameComplexType" />  
        <xs:element name="LastName" type="tns:LastNameType" />  
      </xs:sequence>  
      <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" /  
>  
    </xs:complexType>  
  </xs:element>  
  <xs:simpleType name="LastNameType">  
    <xs:restriction base="xs:string">  
      <xs:maxLength value="20" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:complexType name="FirstNameComplexType">     <xs:simpleContent>       <xs:extension base="xs:string">         <xs:attribute name="Title" type="xs:string" />       </xs:extension>     </xs:simpleContent>   </xs:complexType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2da84-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2da84-154">See Also</span></span>  
 [<span data-ttu-id="2da84-155">XML 스키마 개체 모델 개요</span><span class="sxs-lookup"><span data-stu-id="2da84-155">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)  
 [<span data-ttu-id="2da84-156">XML 스키마 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="2da84-156">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)  
 [<span data-ttu-id="2da84-157">XML 스키마 빌드</span><span class="sxs-lookup"><span data-stu-id="2da84-157">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)  
 [<span data-ttu-id="2da84-158">XML 스키마 통과</span><span class="sxs-lookup"><span data-stu-id="2da84-158">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)  
 [<span data-ttu-id="2da84-159">포함 하 여 XML 스키마 또는 가져오기</span><span class="sxs-lookup"><span data-stu-id="2da84-159">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)  
 [<span data-ttu-id="2da84-160">스키마 컴파일 위한 XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="2da84-160">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [<span data-ttu-id="2da84-161">Post-schema Compilation Infoset</span><span class="sxs-lookup"><span data-stu-id="2da84-161">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
