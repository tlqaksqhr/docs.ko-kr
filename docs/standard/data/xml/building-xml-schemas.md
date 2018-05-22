---
title: XML 스키마 빌드
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 8a5ea56c-0140-4b51-8997-875ae6a8e0cb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ed02680831302880e2bfc02b21ea61303b92a3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="building-xml-schemas"></a><span data-ttu-id="8f9ea-102">XML 스키마 빌드</span><span class="sxs-lookup"><span data-stu-id="8f9ea-102">Building XML Schemas</span></span>
<span data-ttu-id="8f9ea-103"><xref:System.Xml.Schema?displayProperty=nameWithType> 네임스페이스의 클래스는 W3C(World Wide Web 컨소시엄) XML 스키마 권장 사항에 정의된 구조에 매핑되며 이 클래스를 사용하여 메모리 내 XML 스키마를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-103">The classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation and can be used to build XML schemas in-memory.</span></span>  
  
## <a name="building-an-xml-schema"></a><span data-ttu-id="8f9ea-104">XML 스키마 빌드</span><span class="sxs-lookup"><span data-stu-id="8f9ea-104">Building an XML Schema</span></span>  
 <span data-ttu-id="8f9ea-105">다음 코드 예제에서는 SOM API를 사용하여 메모리 내 고객 XML 스키마를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-105">In the code examples that follow, the SOM API is used to build a customer XML schema in-memory.</span></span>  
  
### <a name="creating-element-and-attributes"></a><span data-ttu-id="8f9ea-106">요소 및 특성 만들기</span><span class="sxs-lookup"><span data-stu-id="8f9ea-106">Creating Element and Attributes</span></span>  
 <span data-ttu-id="8f9ea-107">이 코드 예제에서는 자식 요소, 특성 및 해당 형식을 먼저 만든 후 최상위 요소를 만들어 상향식으로 고객 스키마를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-107">The code examples build the customer schema from the bottom up, creating the child elements, attributes, and their corresponding types first, and then the top-level elements.</span></span>  
  
 <span data-ttu-id="8f9ea-108">다음 코드 예제에서는 SOM의 `FirstName` 및 `LastName` 클래스를 사용하여 고객 스키마의 `CustomerId` 특성 외에도 <xref:System.Xml.Schema.XmlSchemaElement> 및 <xref:System.Xml.Schema.XmlSchemaAttribute> 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-108">In the following code example, the `FirstName` and `LastName` elements, as well as the `CustomerId` attribute of the customer schema are created using the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes of the SOM.</span></span> <span data-ttu-id="8f9ea-109">XML 스키마에서 <xref:System.Xml.Schema.XmlSchemaElement.Name%2A> 및 <xref:System.Xml.Schema.XmlSchemaElement> 요소의 "name" 특성에 해당하는 <xref:System.Xml.Schema.XmlSchemaAttribute> 및 `<xs:element />` 클래스의 `<xs:attribute />` 속성과는 별도로 `defaultValue`, `fixedValue`, `form` 등의 스키마가 허용하는 다른 모든 특성은 <xref:System.Xml.Schema.XmlSchemaElement> 및 <xref:System.Xml.Schema.XmlSchemaAttribute> 클래스에 해당 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-109">Apart from the <xref:System.Xml.Schema.XmlSchemaElement.Name%2A> properties of the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes, which correspond to the "name" attribute of the `<xs:element />` and `<xs:attribute />` elements in an XML schema, all other attributes allowed by the schema (`defaultValue`, `fixedValue`, `form`, and so on) have corresponding properties in the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#2)]
 [!code-csharp[XmlSchemaCreateExample#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#2)]
 [!code-vb[XmlSchemaCreateExample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#2)]  
  
### <a name="creating-schema-types"></a><span data-ttu-id="8f9ea-110">스키마 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="8f9ea-110">Creating Schema Types</span></span>  
 <span data-ttu-id="8f9ea-111">요소 및 특성 내용은 해당 형식에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-111">The content of elements and attributes is defined by their types.</span></span> <span data-ttu-id="8f9ea-112">기본 제공 스키마 형식 중 하나가 있는 요소 및 특성을 만들려면 <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> 클래스를 사용하는 기본 제공 형식의 정규화된 해당 이름으로 <xref:System.Xml.Schema.XmlSchemaElement> 또는 <xref:System.Xml.Schema.XmlSchemaAttribute> 클래스의 <xref:System.Xml.XmlQualifiedName> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-112">To create elements and attributes whose types are one of the built-in schema types, the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes are set with the corresponding qualified name of the built-in type using the <xref:System.Xml.XmlQualifiedName> class.</span></span> <span data-ttu-id="8f9ea-113">요소 및 특성에 대한 사용자 정의 형식을 만들려면 <xref:System.Xml.Schema.XmlSchemaSimpleType> 또는 <xref:System.Xml.Schema.XmlSchemaComplexType> 클래스를 사용하여 새 단순 형식 또는 복합 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-113">To create a user-defined type for elements and attributes, a new simple or complex type is created using the <xref:System.Xml.Schema.XmlSchemaSimpleType> or <xref:System.Xml.Schema.XmlSchemaComplexType> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f9ea-114">요소 또는 특성의 익명 자식으로서 이름이 지정되지 않은 단순 형식 또는 복합 형식을 만들려면(특성에는 단순 형식만 적용됨) <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> 또는 <xref:System.Xml.Schema.XmlSchemaElement> 클래스의 <xref:System.Xml.Schema.XmlSchemaAttribute> 속성 대신 <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> 또는 <xref:System.Xml.Schema.XmlSchemaElement> 클래스의 <xref:System.Xml.Schema.XmlSchemaAttribute> 속성을 이름이 지정되지 않은 단순 형식 또는 복합 형식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-114">To create unnamed simple or complex types that are anonymous children of an element or attribute (only simple types apply for attributes), set the <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes to the unnamed simple or complex type, instead of the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes.</span></span>  
  
 <span data-ttu-id="8f9ea-115">XML 스키마는 다른 단순 형식(기본 제공 또는 사용자 정의)에서 제한에 의해 익명 단순 형식 및 이름이 지정된 단순 형식이 파생되거나 다른 단순 형식의 목록 또는 통합으로 구성되도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-115">XML schemas allow both anonymous and named simple types to be derived by restriction from other simple types (built-in or user-defined) or constructed as a list or union of other simple types.</span></span> <span data-ttu-id="8f9ea-116"><xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> 클래스로 기본 제공 `xs:string` 형식을 제한하여 단순 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-116">The <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> class is used to create a simple type by restricting the built-in `xs:string` type.</span></span> <span data-ttu-id="8f9ea-117">또한 <xref:System.Xml.Schema.XmlSchemaSimpleTypeList> 또는 <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion> 클래스를 사용하여 list 또는 union 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-117">You can also use the <xref:System.Xml.Schema.XmlSchemaSimpleTypeList> or <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion> classes to create list or union types.</span></span> <span data-ttu-id="8f9ea-118"><xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType> 속성은 단순 형식 제한인지 또는 list나 union 형식 제한인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-118">The <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType> property denotes whether it is a simple type restriction, list, or union.</span></span>  
  
 <span data-ttu-id="8f9ea-119">다음 코드 예제에서 `FirstName` 요소 형식은 기본 제공 형식 `xs:string`이고, `LastName` 요소 형식은 기본 제공 형식 `xs:string`의 제한인 명명된 단순 형식으로, `MaxLength` 패싯 값이 20이며, `CustomerId` 특성 형식은 기본 제공 형식 `xs:positiveInteger`입니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-119">In the following code example, the `FirstName` element's type is the built-in type `xs:string`, the `LastName` element's type is a named simple type that is a restriction of the built-in type `xs:string`, with a `MaxLength` facet value of 20, and the `CustomerId` attribute's type is the built-in type `xs:positiveInteger`.</span></span> <span data-ttu-id="8f9ea-120">`Customer` 요소는 파티클이 `FirstName` 및 `LastName` 요소의 시퀀스이고 특성에 `CustomerId` 특성이 포함된 익명 복합 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-120">The `Customer` element is an anonymous complex type whose particle is the sequence of the `FirstName` and `LastName` elements and whose attributes contains the `CustomerId` attribute.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f9ea-121"><xref:System.Xml.Schema.XmlSchemaChoice> 또는 <xref:System.Xml.Schema.XmlSchemaAll> 클래스를 복합 형식의 파티클로 사용하여 `<xs:choice />` 또는 `<xs:all />` 의미 체계를 복제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-121">You can also use the <xref:System.Xml.Schema.XmlSchemaChoice> or <xref:System.Xml.Schema.XmlSchemaAll> classes as the particle of the complex type to replicate `<xs:choice />` or `<xs:all />` semantics.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#3](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#3)]
 [!code-csharp[XmlSchemaCreateExample#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#3)]
 [!code-vb[XmlSchemaCreateExample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#3)]  
  
### <a name="creating-and-compiling-schemas"></a><span data-ttu-id="8f9ea-122">스키마 만들기 및 컴파일</span><span class="sxs-lookup"><span data-stu-id="8f9ea-122">Creating and Compiling Schemas</span></span>  
 <span data-ttu-id="8f9ea-123">이때 SOM API를 사용하여 자식 요소와 특성, 해당 형식 및 최상위 `Customer` 요소가 메모리 내에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-123">At this point, the child elements and attributes, their corresponding types, and the top-level `Customer` element have been created in-memory using the SOM API.</span></span> <span data-ttu-id="8f9ea-124">다음 코드 예제에서는 <xref:System.Xml.Schema.XmlSchema> 클래스를 사용하여 스키마 요소를 만들고 <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> 속성을 사용하여 최상위 요소 및 형식을 이 스키마 요소에 추가한 다음 <xref:System.Xml.Schema.XmlSchemaSet> 클래스를 사용하여 전체 스키마를 컴파일하고 콘솔에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-124">In the following code example, the schema element is created using the <xref:System.Xml.Schema.XmlSchema> class, the top-level elements and types are added to it using the <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> property and the complete schema is compiled using the <xref:System.Xml.Schema.XmlSchemaSet> class and written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#4)]
 [!code-csharp[XmlSchemaCreateExample#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#4)]
 [!code-vb[XmlSchemaCreateExample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#4)]  
  
 <span data-ttu-id="8f9ea-125"><xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType> 메서드는 XML 스키마의 규칙에 대해 고객 스키마의 유효성을 검사하고 post-schema-compilation 속성을 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-125">The <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType> method validates the customer schema against the rules for an XML schema and makes post-schema-compilation properties available.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f9ea-126">SOM API의 모든 post-schema-compilation 속성은 Post-Schema-Validation-Infoset과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-126">All post-schema-compilation properties in the SOM API differ from the Post-Schema-Validation-Infoset.</span></span>  
  
 <span data-ttu-id="8f9ea-127"><xref:System.Xml.Schema.ValidationEventHandler>에 추가된 <xref:System.Xml.Schema.XmlSchemaSet>는 콜백 메서드 `ValidationCallback`을 호출하여 스키마 유효성 검사 경고 및 오류를 처리하는 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-127">The <xref:System.Xml.Schema.ValidationEventHandler> added to the <xref:System.Xml.Schema.XmlSchemaSet> is a delegate that calls the callback method `ValidationCallback` to handle schema validation warnings and errors.</span></span>  
  
 <span data-ttu-id="8f9ea-128">다음은 전체 코드 예제 및 콘솔에 작성된 고객 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="8f9ea-128">The following is the complete code example, and the customer schema written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#1)]
 [!code-csharp[XmlSchemaCreateExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#1)]
 [!code-vb[XmlSchemaCreateExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name="Customer">  
      <xs:complexType>  
         <xs:sequence>  
            <xs:element name="FirstName" type="xs:string" />  
            <xs:element name="LastName" type="tns:LastNameType" />  
         </xs:sequence>  
         <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" />  
      </xs:complexType>  
   </xs:element>  
   <xs:simpleType name="LastNameType">  
      <xs:restriction base="xs:string">  
         <xs:maxLength value="20" />  
      </xs:restriction>  
   </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f9ea-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f9ea-129">See Also</span></span>  
 [<span data-ttu-id="8f9ea-130">XML 스키마 개체 모델 개요</span><span class="sxs-lookup"><span data-stu-id="8f9ea-130">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)  
 [<span data-ttu-id="8f9ea-131">XML 스키마 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="8f9ea-131">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)  
 [<span data-ttu-id="8f9ea-132">XML 스키마 통과</span><span class="sxs-lookup"><span data-stu-id="8f9ea-132">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)  
 [<span data-ttu-id="8f9ea-133">XML 스키마 편집</span><span class="sxs-lookup"><span data-stu-id="8f9ea-133">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)  
 [<span data-ttu-id="8f9ea-134">XML 스키마 포함하기 또는 가져오기</span><span class="sxs-lookup"><span data-stu-id="8f9ea-134">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)  
 [<span data-ttu-id="8f9ea-135">스키마 컴파일을 위한 XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="8f9ea-135">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [<span data-ttu-id="8f9ea-136">Post-Schema Compilation Infoset</span><span class="sxs-lookup"><span data-stu-id="8f9ea-136">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
