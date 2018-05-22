---
title: XML 스키마 포함하기 또는 가져오기
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fe1b4a11-37f4-4e1a-93c9-239f4fe736c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2f83128f47a687e75a7db9bb36c487fa1f5bb6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="including-or-importing-xml-schemas"></a><span data-ttu-id="7d157-102">XML 스키마 포함하기 또는 가져오기</span><span class="sxs-lookup"><span data-stu-id="7d157-102">Including or Importing XML Schemas</span></span>
<span data-ttu-id="7d157-103">XML 스키마에 `<xs:import />`, `<xs:include />` 및 `<xs:redefine />` 요소를 포함시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-103">An XML schema may contain `<xs:import />`, `<xs:include />`, and `<xs:redefine />` elements.</span></span> <span data-ttu-id="7d157-104">이 스키마 요소는 이를 포함하거나 가져오는 스키마의 구조를 보완하는 데 사용할 수 있는 다른 XML 스키마를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-104">These schema elements refer to other XML schemas that can be used to supplement the structure of the schema that includes or imports them.</span></span> <span data-ttu-id="7d157-105">SOM(스키마 개체 모델) API에서 <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> 및 <xref:System.Xml.Schema.XmlSchemaRedefine> 클래스는 이러한 요소에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-105">The <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> and <xref:System.Xml.Schema.XmlSchemaRedefine> classes, map to these elements in the Schema Object Model (SOM) API.</span></span>  
  
## <a name="including-or-importing-an-xml-schema"></a><span data-ttu-id="7d157-106">XML 스키마 포함하기 또는 가져오기</span><span class="sxs-lookup"><span data-stu-id="7d157-106">Including or Importing an XML Schema</span></span>  
 <span data-ttu-id="7d157-107">다음 코드 예제는 주소 스키마를 사용하여 [XML 스키마 빌드](../../../../docs/standard/data/xml/building-xml-schemas.md) 항목에서 만든 고객 스키마를 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-107">The following code example supplements the customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic with the address schema.</span></span> <span data-ttu-id="7d157-108">주소 스키마로 고객 스키마를 보완하면 고객 스키마에서 주소 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-108">Supplementing the customer schema with the address schema makes address types available in the customer schema.</span></span>  
  
 <span data-ttu-id="7d157-109">`<xs:include />` 또는 `<xs:import />` 요소를 사용하여 주소 스키마의 구성 요소를 그대로 사용하거나 `<xs:redefine />` 요소를 사용하여 고객 스키마의 필요에 맞게 구성 요소를 수정함으로써 주소 스키마를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-109">The address schema can be incorporated using either `<xs:include />` or `<xs:import />` elements to use the components of the address schema as-is, or using an `<xs:redefine />` element to modify any of its components to suit the need of the customer schema.</span></span> <span data-ttu-id="7d157-110">주소 스키마에는 고객 스키마에 포함된 것과는 다른 `targetNamespace`가 있기 때문에 `<xs:import />` 요소 및 가져오기 의미 체계가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-110">Because the address schema has a `targetNamespace` that is different from that of the customer schema, the `<xs:import />` element and therefore import semantics is used.</span></span>  
  
 <span data-ttu-id="7d157-111">이 코드 예제에서는 다음과 같은 단계로 주소 스키마를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-111">The code example includes the address schema in the following steps.</span></span>  
  
1.  <span data-ttu-id="7d157-112">고객 스키마 및 주소 스키마를 새 <xref:System.Xml.Schema.XmlSchemaSet> 개체에 추가한 다음 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-112">Adds the customer schema and the address schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles them.</span></span> <span data-ttu-id="7d157-113">스키마를 읽거나 컴파일할 때 발생하는 모든 스키마 유효성 검사 경고 및 오류는 <xref:System.Xml.Schema.ValidationEventHandler> 대리자에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-113">Any schema validation warnings and errors encountered reading or compiling the schemas are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>  
  
2.  <span data-ttu-id="7d157-114"><xref:System.Xml.Schema.XmlSchema> 속성을 반복하여 <xref:System.Xml.Schema.XmlSchemaSet>의 고객 스키마와 주소 스키마에 대해 컴파일된 <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-114">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> objects for both the customer and address schemas from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="7d157-115">스키마가 컴파일되므로 PSCI(Post-Schema-Compilation-Infoset) 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-115">Because the schemas are compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>  
  
3.  <span data-ttu-id="7d157-116"><xref:System.Xml.Schema.XmlSchemaImport> 개체를 만들고, 가져오기의 <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A> 속성을 주소 스키마의 네임스페이스로 설정하고, 가져오기의 <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A> 속성을 주소 스키마의 <xref:System.Xml.Schema.XmlSchema> 개체로 설정하고, 가져오기를 고객 스키마의 <xref:System.Xml.Schema.XmlSchema.Includes%2A> 속성에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-116">Creates an <xref:System.Xml.Schema.XmlSchemaImport> object, sets the <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A> property of the import to the namespace of the address schema, sets the <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A> property of the import to the <xref:System.Xml.Schema.XmlSchema> object of the address schema, and adds the import to the <xref:System.Xml.Schema.XmlSchema.Includes%2A> property of the customer schema.</span></span>  
  
4.  <span data-ttu-id="7d157-117"><xref:System.Xml.Schema.XmlSchema> 클래스의 <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> 및 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> 메서드를 사용하여 고객 스키마의 수정된 <xref:System.Xml.Schema.XmlSchemaSet> 개체를 다시 처리하고 컴파일하여 콘솔에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-117">Reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object of the customer schema using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>  
  
5.  <span data-ttu-id="7d157-118">마지막으로, 고객 스키마의 <xref:System.Xml.Schema.XmlSchema.Includes%2A> 속성을 사용하여 고객 스키마로 가져온 모든 스키마를 콘솔에 재귀적으로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-118">Finally, recursively writes all of the schemas imported into the customer schema to the console using the <xref:System.Xml.Schema.XmlSchema.Includes%2A> property of the customer schema.</span></span> <span data-ttu-id="7d157-119"><xref:System.Xml.Schema.XmlSchema.Includes%2A> 속성에서는 스키마에 포함하거나 가져오거나 다시 정의한 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-119">The <xref:System.Xml.Schema.XmlSchema.Includes%2A> property provides access to all the includes, imports, or redefines added to a schema.</span></span>  
  
 <span data-ttu-id="7d157-120">다음은 전체 코드 예제 및 콘솔에 작성된 고객 스키마와 주소 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="7d157-120">The following is the complete code example and the customer and address schemas written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaImportExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaImportExample/CPP/XmlSchemaImportExample.cpp#1)]
 [!code-csharp[XmlSchemaImportExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaImportExample/CS/XmlSchemaImportExample.cs#1)]
 [!code-vb[XmlSchemaImportExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaImportExample/VB/XmlSchemaImportExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://www.example.com/IPO" />  
  <xs:element name="Customer">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="FirstName" type="xs:string" />  
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
</xs:schema>  
<schema targetNamespace="http://www.example.com/IPO" xmlns="http://www.w3.org/2001/XMLSchema" xmlns:ipo="http://www.example.com/IPO">  
  <annotation>  
    <documentation xml:lang="en">  
      Addresses for International Purchase order schema  
      Copyright 2000 Example.com. All rights reserved.  
    </documentation>  
  </annotation>  
  <complexType name="Address">  
    <sequence>  
      <element name="name"   type="string"/>  
      <element name="street" type="string"/>  
      <element name="city"   type="string"/>  
    </sequence>  
  </complexType>  
  <complexType name="USAddress">  
    <complexContent>  
      <extension base="ipo:Address">  
        <sequence>  
          <element name="state" type="ipo:USState"/>  
          <element name="zip"   type="positiveInteger"/>  
        </sequence>  
      </extension>  
    </complexContent>  
  </complexType>  
  <!-- other Address derivations for more countries or regions -->  
  <simpleType name="USState">  
    <restriction base="string">  
      <enumeration value="AK"/>  
      <enumeration value="AL"/>  
      <enumeration value="AR"/>  
      <!-- and so on ... -->  
    </restriction>  
  </simpleType>  
</schema>  
```  
  
 <span data-ttu-id="7d157-121">`<xs:import />`, `<xs:include />` 및 `<xs:redefine />` 요소와 <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> 및 <xref:System.Xml.Schema.XmlSchemaRedefine> 클래스에 대한 자세한 내용은 [W3C XML Schema](https://www.w3.org/XML/Schema)(W3C XML 스키마) 및 <xref:System.Xml.Schema?displayProperty=nameWithType> 네임스페이스 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d157-121">For more information about the `<xs:import />`, `<xs:include />`, and `<xs:redefine />` elements and the <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> and <xref:System.Xml.Schema.XmlSchemaRedefine> classes, see the [W3C XML Schema](https://www.w3.org/XML/Schema) and the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace class reference documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d157-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d157-122">See Also</span></span>  
 [<span data-ttu-id="7d157-123">XML 스키마 개체 모델 개요</span><span class="sxs-lookup"><span data-stu-id="7d157-123">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)  
 [<span data-ttu-id="7d157-124">XML 스키마 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="7d157-124">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)  
 [<span data-ttu-id="7d157-125">XML 스키마 빌드</span><span class="sxs-lookup"><span data-stu-id="7d157-125">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)  
 [<span data-ttu-id="7d157-126">XML 스키마 통과</span><span class="sxs-lookup"><span data-stu-id="7d157-126">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)  
 [<span data-ttu-id="7d157-127">XML 스키마 편집</span><span class="sxs-lookup"><span data-stu-id="7d157-127">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)  
 [<span data-ttu-id="7d157-128">스키마 컴파일을 위한 XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="7d157-128">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
