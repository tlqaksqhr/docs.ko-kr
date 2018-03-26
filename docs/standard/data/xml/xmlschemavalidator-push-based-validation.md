---
title: XmlSchemaValidator 밀어넣기 기반 유효성 검사
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 911d4460-dd91-4958-85b2-2ca3299f9ec6
caps.latest.revision: ''
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 60c2effea612a579b4c66b7c30243b785b86a263
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2018
---
# <a name="xmlschemavalidator-push-based-validation"></a><span data-ttu-id="24f0a-102">XmlSchemaValidator 밀어넣기 기반 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="24f0a-102">XmlSchemaValidator Push-Based Validation</span></span>
<span data-ttu-id="24f0a-103"><xref:System.Xml.Schema.XmlSchemaValidator> 클래스는 밀어넣기 기반 방식으로 XML 스키마에 대해 XML 데이터의 유효성을 검사할 수 있는 효과적인 고성능 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-103">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides an efficient, high-performance mechanism to validate XML data against XML schemas in a push-based manner.</span></span> <span data-ttu-id="24f0a-104">예를 들어, <xref:System.Xml.Schema.XmlSchemaValidator> 클래스를 사용하면 XML 문서로 serialize한 다음 유효성 검사 XML 판독기를 사용하여 문서를 다시 구문 분석할 필요 없이 내부에서 직접 XML Infoset의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-104">For example, the <xref:System.Xml.Schema.XmlSchemaValidator> class allows you to validate an XML infoset in-place without having to serialize it as an XML document and then reparse the document using a validating XML reader.</span></span>  
  
 <span data-ttu-id="24f0a-105">사용자 지정 XML 데이터 소스에 대한 유효성 검사 엔진을 만드는 등의 고급 시나리오에서 또는 유효성 검사 XML 작성기를 만드는 방법으로 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-105">The <xref:System.Xml.Schema.XmlSchemaValidator> class can be used in advanced scenarios such as building validation engines over custom XML data sources or as a way to build a validating XML writer.</span></span>  
  
 <span data-ttu-id="24f0a-106">다음은 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스를 사용하여 `contosoBooks.xml` 스키마에 대해 `contosoBooks.xsd` 파일의 유효성을 검사하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-106">The following is an example of using the <xref:System.Xml.Schema.XmlSchemaValidator> class to validate the `contosoBooks.xml` file against the `contosoBooks.xsd` schema.</span></span> <span data-ttu-id="24f0a-107">이 예제에서는 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 `contosoBooks.xml` 파일을 deserialize하고 노드 값을 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스의 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-107">The example uses the <xref:System.Xml.Serialization.XmlSerializer> class to deserialize the `contosoBooks.xml` file and pass the value of the nodes to the methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24f0a-108">이 예제는 이 항목의 전체 단원에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-108">This example is used throughout the sections of this topic.</span></span>  
  
 [!code-csharp[XmlSchemaValidatorExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaValidatorExamples/CS/XmlSchemaValidatorExamples.cs#1)]
 [!code-vb[XmlSchemaValidatorExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaValidatorExamples/VB/XmlSchemaValidatorExamples.vb#1)]  
  
 <span data-ttu-id="24f0a-109">이 예제에서는 `contosoBooks.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-109">The example takes the `contosoBooks.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="24f0a-110">이 예제에서는 또한 `contosoBooks.xsd`를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-110">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" targetNamespace="http://www.contoso.com/books" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="bookstore">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element maxOccurs="unbounded" name="book">  
                    <xs:complexType>  
                        <xs:sequence>  
                            <xs:element name="title" type="xs:string" />  
                            <xs:element name="author">  
                                <xs:complexType>  
                                    <xs:sequence>  
                                        <xs:element minOccurs="0" name="name" type="xs:string" />  
                                        <xs:element minOccurs="0" name="first-name" type="xs:string" />  
                                        <xs:element minOccurs="0" name="last-name" type="xs:string" />  
                                    </xs:sequence>  
                                </xs:complexType>  
                            </xs:element>  
                            <xs:element name="price" type="xs:decimal" />  
                        </xs:sequence>  
                        <xs:attribute name="genre" type="xs:string" use="required" />  
                        <xs:attribute name="publicationdate" type="xs:date" use="required" />  
                        <xs:attribute name="ISBN" type="xs:string" use="required" />  
                    </xs:complexType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="validating-xml-data-using-xmlschemavalidator"></a><span data-ttu-id="24f0a-111">XmlSchemaValidator를 사용하여 XML 데이터의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="24f0a-111">Validating XML Data using XmlSchemaValidator</span></span>  
 <span data-ttu-id="24f0a-112">XML Infoset의 유효성 검사를 시작하려면 먼저 <xref:System.Xml.Schema.XmlSchemaValidator> 생성자를 사용하여 <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> 클래스의 새 인스턴스를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-112">To begin validating an XML infoset, you must first initialize a new instance of the <xref:System.Xml.Schema.XmlSchemaValidator> class using the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor.</span></span>  
  
 <span data-ttu-id="24f0a-113"><xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> 생성자는 <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet>, <xref:System.Xml.XmlNamespaceManager> 개체 및 <xref:System.Xml.Schema.XmlSchemaValidationFlags> 값을 매개 변수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-113">The <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor takes <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet>, and <xref:System.Xml.XmlNamespaceManager> objects as parameters as well as a <xref:System.Xml.Schema.XmlSchemaValidationFlags> value as a parameter.</span></span> <span data-ttu-id="24f0a-114"><xref:System.Xml.XmlNameTable> 개체는 스키마 네임스페이스, XML 네임스페이스 등의 잘 알려진 네임스페이스 문자열을 분해하는 데 사용되며 단순 내용의 유효성을 검사하는 동안 <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-114">The <xref:System.Xml.XmlNameTable> object is used to atomize well-known namespace strings like the schema namespace, the XML namespace, and so on, and is passed to the <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> method while validating simple content.</span></span> <span data-ttu-id="24f0a-115"><xref:System.Xml.Schema.XmlSchemaSet> 개체에는 XML Infoset의 유효성을 검사하는 데 사용되는 XML 스키마가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-115">The <xref:System.Xml.Schema.XmlSchemaSet> object contains the XML schemas used to validate the XML infoset.</span></span> <span data-ttu-id="24f0a-116"><xref:System.Xml.XmlNamespaceManager> 개체를 사용하여 유효성 검사 중에 나타난 네임스페이스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-116">The <xref:System.Xml.XmlNamespaceManager> object is used to resolve namespaces encountered during validation.</span></span> <span data-ttu-id="24f0a-117"><xref:System.Xml.Schema.XmlSchemaValidationFlags> 값을 사용하여 특정 유효성 검사 기능을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-117">The <xref:System.Xml.Schema.XmlSchemaValidationFlags> value is used to disable certain features of validation.</span></span>  
  
 <span data-ttu-id="24f0a-118"><xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> 생성자에 대한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-118">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>  
  
### <a name="initializing-validation"></a><span data-ttu-id="24f0a-119">유효성 검사 초기화</span><span class="sxs-lookup"><span data-stu-id="24f0a-119">Initializing Validation</span></span>  
 <span data-ttu-id="24f0a-120"><xref:System.Xml.Schema.XmlSchemaValidator> 개체를 생성한 후 <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> 개체 상태를 초기화하는 데 사용하는 오버로드된 <xref:System.Xml.Schema.XmlSchemaValidator> 메서드 두 개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-120">After an <xref:System.Xml.Schema.XmlSchemaValidator> object has been constructed, there are two overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods used to initialize the state of the <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span> <span data-ttu-id="24f0a-121">다음은 이 두 <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-121">The following are the two <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods.</span></span>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="24f0a-122">기본 <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> 메서드는 <xref:System.Xml.Schema.XmlSchemaValidator> 개체를 시작 상태로 초기화하며 <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>를 매개 변수로 사용하는 오버로드된 <xref:System.Xml.Schema.XmlSchemaObject> 메서드는 부분 유효성 검사를 위해 <xref:System.Xml.Schema.XmlSchemaValidator> 개체를 시작 상태로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-122">The default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state, and the overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state for partial validation.</span></span>  
  
 <span data-ttu-id="24f0a-123">두 <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> 메서드는 <xref:System.Xml.Schema.XmlSchemaValidator> 개체를 생성하거나 <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>을 호출한 직후에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-123">Both <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods can only be called immediately after an <xref:System.Xml.Schema.XmlSchemaValidator> object has been constructed or after a call to <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>.</span></span>  
  
 <span data-ttu-id="24f0a-124"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> 메서드의 예제는 소개 단원의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-124">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method, see the example in the introduction.</span></span> <span data-ttu-id="24f0a-125"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> 메서드에 대한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-125">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>  
  
#### <a name="partial-validation"></a><span data-ttu-id="24f0a-126">부분 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="24f0a-126">Partial Validation</span></span>  
 <span data-ttu-id="24f0a-127"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>를 매개 변수로 사용하는 <xref:System.Xml.Schema.XmlSchemaObject> 메서드는 부분 유효성 검사를 위해 <xref:System.Xml.Schema.XmlSchemaValidator> 개체를 시작 상태로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-127">The <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state for partial validation.</span></span>  
  
 <span data-ttu-id="24f0a-128">다음 예제에서는 부분 유효성 검사를 위해 <xref:System.Xml.Schema.XmlSchemaObject> 메서드를 사용하여 <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-128">In the following example, an <xref:System.Xml.Schema.XmlSchemaObject> is initialized for partial validation using the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="24f0a-129">`orderNumber` 개체의 <xref:System.Xml.XmlQualifiedName> 속성이 반환하는 <xref:System.Xml.Schema.XmlSchemaObjectTable> 컬렉션에서 <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A>으로 스키마 요소를 선택하여 <xref:System.Xml.Schema.XmlSchemaSet> 스키마 요소를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-129">The `orderNumber` schema element is passed by selecting the schema element by <xref:System.Xml.XmlQualifiedName> in the <xref:System.Xml.Schema.XmlSchemaObjectTable> collection returned by the <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> object.</span></span> <span data-ttu-id="24f0a-130">그러면 <xref:System.Xml.Schema.XmlSchemaValidator> 개체가 이 특정 요소의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-130">The <xref:System.Xml.Schema.XmlSchemaValidator> object then validates this specific element.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add(Nothing, "schema.xsd")  
schemaSet.Compile()  
Dim nameTable As NameTable = New NameTable()  
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)  
  
Dim validator As XmlSchemaValidator = New XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None)  
validator.Initialize(schemaSet.GlobalElements.Item(New XmlQualifiedName("orderNumber")))  
  
validator.ValidateElement("orderNumber", "", Nothing)  
validator.ValidateEndOfAttributes(Nothing)  
validator.ValidateText("123")  
validator.ValidateEndElement(Nothing)  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add(null, "schema.xsd");  
schemaSet.Compile();  
NameTable nameTable = new NameTable();  
XmlNamespaceManager manager = new XmlNamespaceManager(nameTable);  
  
XmlSchemaValidator validator = new XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None);  
validator.Initialize(schemaSet.GlobalElements[new XmlQualifiedName("orderNumber")]);  
  
validator.ValidateElement("orderNumber", "", null);  
validator.ValidateEndOfAttributes(null);  
validator.ValidateText("123");  
validator.ValidateEndElement(null);  
```  
  
 <span data-ttu-id="24f0a-131">이 예제에서는 다음 XML 스키마를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-131">The example takes the following XML schema as input.</span></span>  
  
 `<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">`  
  
 `<xs:element name="orderNumber" type="xs:int" />`  
  
 `</xs:schema>`  
  
 <span data-ttu-id="24f0a-132"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> 메서드에 대한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-132">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>  
  
### <a name="adding-additional-schemas"></a><span data-ttu-id="24f0a-133">스키마 추가</span><span class="sxs-lookup"><span data-stu-id="24f0a-133">Adding Additional Schemas</span></span>  
 <span data-ttu-id="24f0a-134"><xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> 클래스의 <xref:System.Xml.Schema.XmlSchemaValidator> 메서드를 사용하면 유효성 검사 중에 사용되는 스키마 집합에 XML 스키마를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-134">The <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method of the <xref:System.Xml.Schema.XmlSchemaValidator> class is used to add an XML schema to the set of schemas used during validation.</span></span> <span data-ttu-id="24f0a-135"><xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> 메서드를 사용하여 유효성을 검사 중인 XML Infoset에서 인라인 XML 스키마가 나타난 결과를 시뮬레이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-135">The <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method can be used to simulate the effect of encountering an inline XML schema in the XML infoset being validated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24f0a-136"><xref:System.Xml.Schema.XmlSchema> 매개 변수의 대상 네임스페이스는 이미 <xref:System.Xml.Schema.XmlSchemaValidator> 개체에 발생한 요소나 특성의 대상 네임스페이스와 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-136">The target namespace of the <xref:System.Xml.Schema.XmlSchema> parameter cannot match that of any element or attribute already encountered by the <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span>  
>   
>  <span data-ttu-id="24f0a-137"><xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> 값을 매개 변수로 <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> 생성자에 전달하지 않은 경우 <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> 메서드는 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-137">If the <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> value was not passed as a parameter to the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor, the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method does nothing.</span></span>  
  
 <span data-ttu-id="24f0a-138"><xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> 메서드의 결과는 유효성을 검사 중인 현재 XML 노드 컨텍스트에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-138">The result of the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method is dependant on the current XML node context being validated.</span></span> <span data-ttu-id="24f0a-139">유효성 검사 컨텍스트에 대한 자세한 내용은 이 항목의 "유효성 검사 컨텍스트" 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-139">For more information about validation contexts, see the "Validation Context" section of this topic.</span></span>  
  
 <span data-ttu-id="24f0a-140"><xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> 메서드에 대한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-140">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>  
  
### <a name="validating-elements-attributes-and-content"></a><span data-ttu-id="24f0a-141">요소, 특성 및 내용 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="24f0a-141">Validating Elements, Attributes, and Content</span></span>  
 <span data-ttu-id="24f0a-142"><xref:System.Xml.Schema.XmlSchemaValidator> 클래스는 XML Infoset에서 XML 스키마에 대해 요소, 특성 및 내용의 유효성을 검사할 수 있는 여러 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-142">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides several methods used to validate elements, attributes, and content in an XML infoset against XML schemas.</span></span> <span data-ttu-id="24f0a-143">다음 표에서는 이러한 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-143">The following table describes each of these methods.</span></span>  
  
|<span data-ttu-id="24f0a-144">메서드</span><span class="sxs-lookup"><span data-stu-id="24f0a-144">Method</span></span>|<span data-ttu-id="24f0a-145">설명</span><span class="sxs-lookup"><span data-stu-id="24f0a-145">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|<span data-ttu-id="24f0a-146">현재 컨텍스트에서 요소 이름의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-146">Validates the element name in the current context.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|<span data-ttu-id="24f0a-147">현재 요소 컨텍스트에서 또는 <xref:System.Xml.Schema.XmlSchemaAttribute> 메서드에 매개 변수로 전달된 <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> 개체에 대해 특성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-147">Validates the attribute in the current element context or against the <xref:System.Xml.Schema.XmlSchemaAttribute> object passed as a parameter to the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<span data-ttu-id="24f0a-148">요소 컨텍스트에 필수 특성이 모두 있는지 확인하고 <xref:System.Xml.Schema.XmlSchemaValidator> 개체를 준비하여 요소의 자식 내용의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-148">Verifies whether all the required attributes in the element context are present and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate the child content of the element.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|<span data-ttu-id="24f0a-149">현재 요소 컨텍스트에서 텍스트가 허용되는지 확인하고 현재 요소에 단순 내용이 있는지 확인하기 위해 텍스트를 누적합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-149">Validates whether text is allowed in the current element context, and accumulates the text for validation if the current element has simple content.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|<span data-ttu-id="24f0a-150">현재 요소 컨텍스트에서 공백이 허용되는지 확인하고 현재 요소에 단순 내용이 있는지 확인하기 위해 공백을 누적합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-150">Validates whether white-space is allowed in the current element context, and accumulates the white-space for validation whether the current element has simple content.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<span data-ttu-id="24f0a-151">단순 내용이 있는 요소의 데이터 형식에 따라 요소의 텍스트 내용이 유효한지 확인하고 현재 요소의 내용이 복합 내용이 있는 요소에 대해 완전한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-151">Verifies whether the text content of the element is valid according to its data type for elements with simple content, and verifies whether the content of the current element is complete for elements with complex content.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|<span data-ttu-id="24f0a-152">현재 요소 내용의 유효성 검사를 생략하고 <xref:System.Xml.Schema.XmlSchemaValidator> 개체를 준비하여 부모 요소의 컨텍스트에서 내용의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-152">Skips validation of the current element content and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate content in the parent element's context.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|<span data-ttu-id="24f0a-153"><xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints> 유효성 검사 옵션을 설정한 경우 유효성 검사를 종료하고 전체 XML 문서에 대한 identity 제약 조건을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-153">Ends validation and checks identity constraints for the entire XML document if the <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints> validation option is set.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="24f0a-154"><xref:System.Xml.Schema.XmlSchemaValidator> 클래스에는 앞의 표에서 설명한 각 메서드의 호출 시퀀스를 실행하고 호출을 발생시키는 상태 전환이 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-154">The <xref:System.Xml.Schema.XmlSchemaValidator> class has a defined state transition that enforces the sequence and occurrence of calls made to each of the methods described in the previous table.</span></span> <span data-ttu-id="24f0a-155"><xref:System.Xml.Schema.XmlSchemaValidator> 클래스의 특정 상태 전환에 대한 자세한 내용은 이 항목의 "XmlSchemaValidator 상태 전환" 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-155">The specific state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class is described in the "XmlSchemaValidator State Transition" section of this topic.</span></span>  
  
 <span data-ttu-id="24f0a-156">XML Infoset에서 요소, 특성 및 내용의 유효성을 검사하는 데 사용되는 메서드의 예는 이전 단원의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-156">For an example of the methods used to validate elements, attributes, and content in an XML infoset, see the example in the previous section.</span></span> <span data-ttu-id="24f0a-157">이러한 메서드에 대한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-157">For more information about these methods, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>  
  
#### <a name="validating-content-using-an-xmlvaluegetter"></a><span data-ttu-id="24f0a-158">XmlValueGetter를 사용하여 내용 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="24f0a-158">Validating Content Using an XmlValueGetter</span></span>  
 <span data-ttu-id="24f0a-159"><xref:System.Xml.Schema.XmlValueGetter>`delegate`를 사용하여 특성, 텍스트 또는 공백 노드의 값을 특성, 텍스트 또는 공백 노드의 XSD(XML 스키마 정의 언어) 형식과 호환되는 CLR(공용 언어 런타임) 형식으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-159">The <xref:System.Xml.Schema.XmlValueGetter>`delegate` can be used to pass the value of attribute, text, or white-space nodes as a Common Language Runtime (CLR) types compatible with the XML Schema Definition Language (XSD) type of the attribute, text, or white-space node.</span></span> <span data-ttu-id="24f0a-160">특성, 텍스트 또는 공백 노드의 CLR 값을 사용할 수 있는 경우 <xref:System.Xml.Schema.XmlValueGetter>`delegate`가 유용하며 `string`으로 변환하고 유효성을 검사하기 위해 다시 구문 분석하는 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-160">An <xref:System.Xml.Schema.XmlValueGetter>`delegate` is useful if the CLR value of an attribute, text, or white-space node is already available, and avoids the cost of converting it to a `string` and then reparsing it again for validation.</span></span>  
  
 <span data-ttu-id="24f0a-161"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> 및 <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> 메서드가 오버로드되며 특성, 텍스트 또는 공백 노드의 값을 `string` 또는 <xref:System.Xml.Schema.XmlValueGetter>`delegate`로 사용할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-161">The <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> methods are overloaded and accept the value of attribute, text, or white-space nodes as a `string` or <xref:System.Xml.Schema.XmlValueGetter>`delegate`.</span></span>  
  
 <span data-ttu-id="24f0a-162"><xref:System.Xml.Schema.XmlSchemaValidator> 클래스의 다음 메서드에서는 <xref:System.Xml.Schema.XmlValueGetter>`delegate`를 매개 변수로 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-162">The following methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class accept an <xref:System.Xml.Schema.XmlValueGetter>`delegate` as a parameter.</span></span>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>  
  
 <span data-ttu-id="24f0a-163">다음은 소개 단원의 <xref:System.Xml.Schema.XmlValueGetter> 클래스 예제에서 가져온 `delegate`<xref:System.Xml.Schema.XmlSchemaValidator> 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-163">The following is an example <xref:System.Xml.Schema.XmlValueGetter>`delegate` taken from the <xref:System.Xml.Schema.XmlSchemaValidator> class example in the introduction.</span></span> <span data-ttu-id="24f0a-164"><xref:System.Xml.Schema.XmlValueGetter>`delegate`는 특성 값을 <xref:System.DateTime> 개체로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-164">The <xref:System.Xml.Schema.XmlValueGetter>`delegate` returns the value of an attribute as a <xref:System.DateTime> object.</span></span> <span data-ttu-id="24f0a-165"><xref:System.DateTime>에서 반환된 이 <xref:System.Xml.Schema.XmlValueGetter> 개체의 유효성을 검사하기 위해 <xref:System.Xml.Schema.XmlSchemaValidator> 개체는 먼저 이 개체를 특성의 데이터 형식에 대한 ValueType으로 변환하고 변환된 값에서 패싯을 확인합니다. 여기서 ValueType은 XSD 형식에 대한 기본 CLR 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-165">To validate this <xref:System.DateTime> object returned by the <xref:System.Xml.Schema.XmlValueGetter>, the <xref:System.Xml.Schema.XmlSchemaValidator> object first converts it to the ValueType (ValueType is the default CLR mapping for the XSD type) for the data type of the attribute and then checks facets on the converted value.</span></span>  
  
```vb  
Shared dateTimeGetterContent As Object  
  
Shared Function dateTimeGetterHandle() As Object  
    Return dateTimeGetterContent  
End Function  
  
Shared Function dateTimeGetter(ByVal dateTime As DateTime) As XmlValueGetter  
    dateTimeGetterContent = dateTime  
    Return New XmlValueGetter(AddressOf dateTimeGetterHandle)  
End Function  
```  
  
```csharp  
static object dateTimeGetterContent;  
  
static object dateTimeGetterHandle()  
{  
    return dateTimeGetterContent;  
}  
  
static XmlValueGetter dateTimeGetter(DateTime dateTime)  
{  
    dateTimeGetterContent = dateTime;  
    return new XmlValueGetter(dateTimeGetterHandle);  
}  
```  
  
 <span data-ttu-id="24f0a-166"><xref:System.Xml.Schema.XmlValueGetter>`delegate`의 전체 예제는 소개 단원의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-166">For a complete example of the <xref:System.Xml.Schema.XmlValueGetter>`delegate`, see the example in the introduction.</span></span> <span data-ttu-id="24f0a-167"><xref:System.Xml.Schema.XmlValueGetter>`delegate`에 대한 자세한 내용은 <xref:System.Xml.Schema.XmlValueGetter> 및 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-167">For more information about the <xref:System.Xml.Schema.XmlValueGetter>`delegate`, see the <xref:System.Xml.Schema.XmlValueGetter>, and <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>  
  
#### <a name="post-schema-validation-information"></a><span data-ttu-id="24f0a-168">Post-Schema-Validation-Information</span><span class="sxs-lookup"><span data-stu-id="24f0a-168">Post-Schema-Validation-Information</span></span>  
 <span data-ttu-id="24f0a-169"><xref:System.Xml.Schema.XmlSchemaInfo> 클래스는 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스로 유효성을 검사하는 XML 노드의 Post-Schema-Validation-Information을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-169">The <xref:System.Xml.Schema.XmlSchemaInfo> class represents some of the Post-Schema-Validation-Information of an XML node validated by the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span> <span data-ttu-id="24f0a-170"><xref:System.Xml.Schema.XmlSchemaValidator> 클래스의 다양한 메서드에서는 <xref:System.Xml.Schema.XmlSchemaInfo> 개체를 선택적(`null`) `out` 매개 변수로 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-170">Various methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class accept an <xref:System.Xml.Schema.XmlSchemaInfo> object as an optional, (`null`) `out` parameter.</span></span>  
  
 <span data-ttu-id="24f0a-171">유효성 검사를 성공적으로 마치면 유효성 검사 결과와 함께 <xref:System.Xml.Schema.XmlSchemaInfo> 개체가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-171">Upon successful validation, properties of the <xref:System.Xml.Schema.XmlSchemaInfo> object are set with the results of the validation.</span></span> <span data-ttu-id="24f0a-172">예를 들어, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> 메서드를 사용하여 특성의 유효성을 검사하면 유효성 검사 결과와 함께 <xref:System.Xml.Schema.XmlSchemaInfo> 개체(지정한 경우)의 <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A> 및 <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> 속성이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-172">For example, upon successful validation of an attribute using the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method, the <xref:System.Xml.Schema.XmlSchemaInfo> object's (if specified) <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A>, and <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> properties are set with the results of the validation.</span></span>  
  
 <span data-ttu-id="24f0a-173">다음 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 메서드에서는 <xref:System.Xml.Schema.XmlSchemaInfo> 개체를 out 매개 변수로 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-173">The following <xref:System.Xml.Schema.XmlSchemaValidator> class methods accept an <xref:System.Xml.Schema.XmlSchemaInfo> object as an out parameter.</span></span>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>  
  
-   <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>  
  
 <span data-ttu-id="24f0a-174"><xref:System.Xml.Schema.XmlSchemaInfo> 클래스의 전체 예제는 소개 단원의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-174">For a complete example of the <xref:System.Xml.Schema.XmlSchemaInfo> class, see the example in the introduction.</span></span> <span data-ttu-id="24f0a-175"><xref:System.Xml.Schema.XmlSchemaInfo> 클래스에 대한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaInfo> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-175">For more information about the <xref:System.Xml.Schema.XmlSchemaInfo> class, see the <xref:System.Xml.Schema.XmlSchemaInfo> class reference documentation.</span></span>  
  
### <a name="retrieving-expected-particles-attributes-and-unspecified-default-attributes"></a><span data-ttu-id="24f0a-176">필요한 파티클, 특성 및 지정되지 않은 기본 특성 검색</span><span class="sxs-lookup"><span data-stu-id="24f0a-176">Retrieving Expected Particles, Attributes, and Unspecified Default Attributes</span></span>  
 <span data-ttu-id="24f0a-177"><xref:System.Xml.Schema.XmlSchemaValidator> 클래스는 현재 유효성 검사 컨텍스트에서 필요한 파티클, 특성 및 지정되지 않은 기본 특성을 검색하는 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 및 <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-177">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> methods to retrieve the expected particles, attributes, and unspecified default attributes in the current validation context.</span></span>  
  
#### <a name="retrieving-expected-particles"></a><span data-ttu-id="24f0a-178">필요한 파티클 검색</span><span class="sxs-lookup"><span data-stu-id="24f0a-178">Retrieving Expected Particles</span></span>  
 <span data-ttu-id="24f0a-179"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 메서드는 현재 요소 컨텍스트에서 필요한 파티클이 포함된 <xref:System.Xml.Schema.XmlSchemaParticle> 개체의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-179">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an array of <xref:System.Xml.Schema.XmlSchemaParticle> objects containing the expected particles in the current element context.</span></span> <span data-ttu-id="24f0a-180"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 메서드가 반환할 수 있는 유효한 파티클은 <xref:System.Xml.Schema.XmlSchemaElement> 및 <xref:System.Xml.Schema.XmlSchemaAny> 클래스의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-180">The valid particles that can be returned by the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method are instances of the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAny> classes.</span></span>  
  
 <span data-ttu-id="24f0a-181">내용 모델의 compositor가 `xs:sequence`인 경우 시퀀스에서 다음 파티클만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-181">When the compositor for the content model is an `xs:sequence`, only the next particle in the sequence is returned.</span></span> <span data-ttu-id="24f0a-182">내용 모델의 compositor가 `xs:all` 또는 `xs:choice`인 경우 현재 요소 컨텍스트에서 따를 수 있는 유효한 파티클이 모두 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-182">If the compositor for the content model is an `xs:all` or an `xs:choice`, then all valid particles that could follow in the current element context are returned.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24f0a-183"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 메서드를 호출한 직후에 <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> 메서드를 호출할 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 메서드는 모든 전역 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-183">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called immediately after calling the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns all global elements.</span></span>  
  
 <span data-ttu-id="24f0a-184">예를 들어, XSD(XML 스키마 정의 언어) 스키마 및 이 스키마를 따르는 XML 문서에서 `book` 요소의 유효성을 검사한 후에는 `book` 요소가 현재 요소 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-184">For example, in the XML Schema Definition Language (XSD) schema and XML document that follow, after validating the `book` element, the `book` element is the current element context.</span></span> <span data-ttu-id="24f0a-185"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 메서드는 <xref:System.Xml.Schema.XmlSchemaElement> 요소를 나타내는 단일 `title` 개체가 포함된 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-185">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an array containing a single <xref:System.Xml.Schema.XmlSchemaElement> object representing the `title` element.</span></span> <span data-ttu-id="24f0a-186">유효성 검사 컨텍스트가 `title` 요소인 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 메서드는 빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-186">When the validation context is the `title` element, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an empty array.</span></span> <span data-ttu-id="24f0a-187"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 요소의 유효성을 검사한 후 `title` 요소의 유효성을 검사하기 전에 `description` 메서드를 호출하면 <xref:System.Xml.Schema.XmlSchemaElement> 요소를 나타내는 단일 `description` 개체가 포함된 배열이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-187">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called after the `title` element has been validated but before the `description` element has been validated, it returns an array containing a single <xref:System.Xml.Schema.XmlSchemaElement> object representing the `description` element.</span></span> <span data-ttu-id="24f0a-188"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 요소의 유효성을 검사한 후 `description` 메서드를 호출하면 와일드카드를 나타내는 단일 <xref:System.Xml.Schema.XmlSchemaAny> 개체가 포함된 배열이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-188">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called after the `description` element has been validated then it returns an array containing a single <xref:System.Xml.Schema.XmlSchemaAny> object representing the wildcard.</span></span>  
  
```vb  
Dim reader As XmlReader =  XmlReader.Create("input.xml")   
  
Dim schemaSet As XmlSchemaSet =  New XmlSchemaSet()   
schemaSet.Add(Nothing, "schema.xsd")  
Dim manager As XmlNamespaceManager =  New XmlNamespaceManager(reader.NameTable)   
  
Dim validator As XmlSchemaValidator =  New XmlSchemaValidator(reader.NameTable,schemaSet,manager,XmlSchemaValidationFlags.None)  
validator.Initialize()  
  
validator.ValidateElement("book", "", Nothing)  
  
validator.ValidateEndOfAttributes(Nothing)  
For Each element As XmlSchemaElement In validator.GetExpectedParticles()  
    Console.WriteLine(element.Name)  
Next  
  
validator.ValidateElement("title", "", Nothing)  
validator.ValidateEndOfAttributes(Nothing)  
For Each element As XmlSchemaElement In validator.GetExpectedParticles()  
    Console.WriteLine(element.Name)  
Next  
validator.ValidateEndElement(Nothing)  
  
For Each element As XmlSchemaElement In validator.GetExpectedParticles()  
    Console.WriteLine(element.Name)  
Next  
  
validator.ValidateElement("description", "", Nothing)  
validator.ValidateEndOfAttributes(Nothing)  
validator.ValidateEndElement(Nothing)  
  
For Each particle As XmlSchemaParticle In validator.GetExpectedParticles()  
    Console.WriteLine(particle.GetType())  
Next  
  
validator.ValidateElement("namespace", "", Nothing)  
validator.ValidateEndOfAttributes(Nothing)  
validator.ValidateEndElement(Nothing)  
  
validator.ValidateEndElement(Nothing)  
```  
  
```csharp  
XmlReader reader = XmlReader.Create("input.xml");  
  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add(null, "schema.xsd");  
XmlNamespaceManager manager = new XmlNamespaceManager(reader.NameTable);  
  
XmlSchemaValidator validator = new XmlSchemaValidator(reader.NameTable, schemaSet, manager, XmlSchemaValidationFlags.None);  
validator.Initialize();  
  
validator.ValidateElement("book", "", null);  
  
validator.ValidateEndOfAttributes(null);  
foreach (XmlSchemaElement element in validator.GetExpectedParticles())  
{  
    Console.WriteLine(element.Name);  
}  
  
validator.ValidateElement("title", "", null);  
validator.ValidateEndOfAttributes(null);  
foreach (XmlSchemaElement element in validator.GetExpectedParticles())  
{  
    Console.WriteLine(element.Name);  
}  
validator.ValidateEndElement(null);  
  
foreach (XmlSchemaElement element in validator.GetExpectedParticles())  
{  
    Console.WriteLine(element.Name);  
}  
  
validator.ValidateElement("description", "", null);  
validator.ValidateEndOfAttributes(null);  
validator.ValidateEndElement(null);  
  
foreach (XmlSchemaParticle particle in validator.GetExpectedParticles())  
{  
    Console.WriteLine(particle.GetType());  
}  
  
validator.ValidateElement("namespace", "", null);  
validator.ValidateEndOfAttributes(null);  
validator.ValidateEndElement(null);  
  
validator.ValidateEndElement(null);  
```  
  
 <span data-ttu-id="24f0a-189">이 예제에서는 다음 XML을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-189">The example takes the following XML as input.</span></span>  
  
 `<xs:schema xmlns:xs="http://www.w3c.org/2001/XMLSchema">`  
  
 `<xs:element name="book">`  
  
 `<xs:sequence>`  
  
 `<xs:element name="title" type="xs:string" />`  
  
 `<xs:element name="description" type="xs:string" />`  
  
 `<xs:any processContent="lax" maxOccurs="unbounded" />`  
  
 `</xs:sequence>`  
  
 `</xs:element>`  
  
 `</xs:schema>`  
  
 <span data-ttu-id="24f0a-190">이 예제에서는 다음 XSD 스키마를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-190">The example takes the following XSD schema as input.</span></span>  
  
 `<book>`  
  
 `<title>My Book</title>`  
  
 `<description>My Book's Description</description>`  
  
 `<namespace>System.Xml.Schema</namespace>`  
  
 `</book>`  
  
> [!NOTE]
>  <span data-ttu-id="24f0a-191"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 클래스의 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> 및 <xref:System.Xml.Schema.XmlSchemaValidator> 메서드로 인한 결과는 유효성 검사가 실행 중인 현재 컨텍스트에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-191">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span> <span data-ttu-id="24f0a-192">자세한 내용은 이 항목의 “유효성 검사 컨텍스트” 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-192">For more information, see the "Validation Context" section of this topic.</span></span>  
  
 <span data-ttu-id="24f0a-193"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 메서드의 예제는 소개 단원의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-193">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method, see the example in the introduction.</span></span> <span data-ttu-id="24f0a-194"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 메서드에 대한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-194">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>  
  
#### <a name="retrieving-expected-attributes"></a><span data-ttu-id="24f0a-195">필요한 특성 검색</span><span class="sxs-lookup"><span data-stu-id="24f0a-195">Retrieving Expected Attributes</span></span>  
 <span data-ttu-id="24f0a-196"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> 메서드는 현재 요소 컨텍스트에서 필요한 특성이 포함된 <xref:System.Xml.Schema.XmlSchemaAttribute> 개체의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-196">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method returns an array of <xref:System.Xml.Schema.XmlSchemaAttribute> objects containing the expected attributes in the current element context.</span></span>  
  
 <span data-ttu-id="24f0a-197">예를 들어, 소개 단원의 예제에서는 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> 메서드를 사용하여 `book` 요소의 모든 특성을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-197">For example, in the example in the introduction, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method is used to retrieve all the attributes of the `book` element.</span></span>  
  
 <span data-ttu-id="24f0a-198"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> 메서드를 호출한 직후에 <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> 메서드를 호출하면 XML 문서에 나타날 수 있는 모든 특성이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-198">If you call the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method immediately after the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> method, all the attributes that could appear in the XML document are returned.</span></span> <span data-ttu-id="24f0a-199">그러나 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> 메서드를 한 번 이상 호출한 후 <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> 메서드를 호출하면 현재 요소에 대해 아직 유효성을 검사하지 않은 특성이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-199">However, if you call the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method after one or more calls to the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method, the attributes that have not yet been validated for the current element are returned.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24f0a-200"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 클래스의 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> 및 <xref:System.Xml.Schema.XmlSchemaValidator> 메서드로 인한 결과는 유효성 검사가 실행 중인 현재 컨텍스트에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-200">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span> <span data-ttu-id="24f0a-201">자세한 내용은 이 항목의 “유효성 검사 컨텍스트” 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-201">For more information, see the "Validation Context" section of this topic.</span></span>  
  
 <span data-ttu-id="24f0a-202"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> 메서드의 예제는 소개 단원의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-202">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method, see the example in the introduction.</span></span> <span data-ttu-id="24f0a-203"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> 메서드에 대한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-203">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>  
  
#### <a name="retrieving-unspecified-default-attributes"></a><span data-ttu-id="24f0a-204">지정되지 않은 기본 특성 검색</span><span class="sxs-lookup"><span data-stu-id="24f0a-204">Retrieving Unspecified Default Attributes</span></span>  
 <span data-ttu-id="24f0a-205"><xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> 메서드는 요소 컨텍스트에서 <xref:System.Collections.ArrayList> 메서드를 사용하여 기본값의 유효성을 검사하지 않은 특성의 <xref:System.Xml.Schema.XmlSchemaAttribute> 개체로 지정한 <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-205">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method populates the <xref:System.Collections.ArrayList> specified with <xref:System.Xml.Schema.XmlSchemaAttribute> objects for any attributes with default values that have not been previously validated using the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method in the element context.</span></span> <span data-ttu-id="24f0a-206">요소 컨텍스트의 각 특성에서 <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> 메서드를 호출한 후에 <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-206">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method should be called after calling the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method on each attribute in the element context.</span></span> <span data-ttu-id="24f0a-207">유효성을 검사 중인 XML 문서에 삽입할 기본 특성을 결정하려면 <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> 메서드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-207">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method should be used to determine what default attributes are to be inserted into the XML document being validated.</span></span>  
  
 <span data-ttu-id="24f0a-208"><xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> 메서드에 대한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-208">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>  
  
### <a name="handling-schema-validation-events"></a><span data-ttu-id="24f0a-209">스키마 유효성 검사 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="24f0a-209">Handling Schema Validation Events</span></span>  
 <span data-ttu-id="24f0a-210">유효성을 검사하는 동안 발생한 스키마 유효성 검사 경고 및 오류는 <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> 클래스의 <xref:System.Xml.Schema.XmlSchemaValidator> 이벤트로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-210">Schema validation warnings and errors encountered during validation are handled by the <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> event of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>  
  
 <span data-ttu-id="24f0a-211">스키마 유효성 검사 경고의 <xref:System.Xml.Schema.XmlSeverityType> 값은 <xref:System.Xml.Schema.XmlSeverityType.Warning>이며 스키마 유효성 검사 오류의 <xref:System.Xml.Schema.XmlSeverityType> 값은 <xref:System.Xml.Schema.XmlSeverityType.Error>입니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-211">Schema validation warnings have an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Warning> and schema validation errors have an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Error>.</span></span> <span data-ttu-id="24f0a-212"><xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler>를 지정하지 않으면 <xref:System.Xml.Schema.XmlSchemaValidationException> 값이 <xref:System.Xml.Schema.XmlSeverityType>인 모든 스키마 유효성 검사 오류에 대해 <xref:System.Xml.Schema.XmlSeverityType.Error>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-212">If no <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> has been assigned, an <xref:System.Xml.Schema.XmlSchemaValidationException> is thrown for all schema validation errors with an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Error>.</span></span> <span data-ttu-id="24f0a-213">그러나 <xref:System.Xml.Schema.XmlSchemaValidationException> 값이 <xref:System.Xml.Schema.XmlSeverityType>인 스키마 유효성 검사 경고에 대해서는 <xref:System.Xml.Schema.XmlSeverityType.Warning>이 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-213">However, an <xref:System.Xml.Schema.XmlSchemaValidationException> is not thrown for schema validation warnings with an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Warning>.</span></span>  
  
 <span data-ttu-id="24f0a-214">다음은 소개 단원의 예제에서 가져온 것으로, 스키마 유효성 검사 중에 발생한 스키마 유효성 검사 경고 및 오류를 받는 <xref:System.Xml.Schema.ValidationEventHandler>의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-214">The following is an example of a <xref:System.Xml.Schema.ValidationEventHandler> that receives schema validation warnings and errors encountered during schema validation taken from the example in the introduction.</span></span>  
  
```vb  
Shared Sub SchemaValidationEventHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
    Select Case e.Severity  
        Case XmlSeverityType.Error  
            Console.WriteLine(vbCrLf & "Error: {0}", e.Message)  
            Exit Sub  
        Case XmlSeverityType.Warning  
            Console.WriteLine(vbCrLf & "Warning: {0}", e.Message)  
            Exit Sub  
    End Select  
End Sub  
```  
  
```csharp  
static void SchemaValidationEventHandler(object sender, ValidationEventArgs e)  
{  
    switch (e.Severity)  
    {  
        case XmlSeverityType.Error:  
            Console.WriteLine("\nError: {0}", e.Message);  
            break;  
        case XmlSeverityType.Warning:  
            Console.WriteLine("\nWarning: {0}", e.Message);  
            break;  
    }  
}  
```  
  
 <span data-ttu-id="24f0a-215"><xref:System.Xml.Schema.ValidationEventHandler>의 전체 예제는 소개 단원의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-215">For a complete example of the <xref:System.Xml.Schema.ValidationEventHandler>, see the example in the introduction.</span></span> <span data-ttu-id="24f0a-216">자세한 내용은 <xref:System.Xml.Schema.XmlSchemaInfo> 클래스 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24f0a-216">For more information, see the <xref:System.Xml.Schema.XmlSchemaInfo> class reference documentation.</span></span>  
  
## <a name="xmlschemavalidator-state-transition"></a><span data-ttu-id="24f0a-217">XmlSchemaValidator 상태 전환</span><span class="sxs-lookup"><span data-stu-id="24f0a-217">XmlSchemaValidator State Transition</span></span>  
 <span data-ttu-id="24f0a-218"><xref:System.Xml.Schema.XmlSchemaValidator> 클래스에는 XML Infoset에서 요소, 특성 및 내용의 유효성을 검사하는 데 사용되는 각 메서드의 호출 시퀀스를 실행하고 호출을 발생시키는 상태 전환이 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-218">The <xref:System.Xml.Schema.XmlSchemaValidator> class has a defined state transition that enforces the sequence and occurrence of calls made to each of the methods used to validate elements, attributes, and content in an XML infoset.</span></span>  
  
 <span data-ttu-id="24f0a-219">다음 표에서는 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스의 상태 전환 및 각 상태에서 수행할 수 있는 메서드 호출의 시퀀스와 발생에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-219">The following table describes the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class, and the sequence and occurrence of method calls that can be made in each state.</span></span>  
  
|<span data-ttu-id="24f0a-220">상태</span><span class="sxs-lookup"><span data-stu-id="24f0a-220">State</span></span>|<span data-ttu-id="24f0a-221">전환</span><span class="sxs-lookup"><span data-stu-id="24f0a-221">Transition</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="24f0a-222">Validate</span><span class="sxs-lookup"><span data-stu-id="24f0a-222">Validate</span></span>|<span data-ttu-id="24f0a-223"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel\*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A></span><span class="sxs-lookup"><span data-stu-id="24f0a-223"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel\*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A></span></span>|  
|<span data-ttu-id="24f0a-224">TopLevel</span><span class="sxs-lookup"><span data-stu-id="24f0a-224">TopLevel</span></span>|<span data-ttu-id="24f0a-225"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; 요소</span><span class="sxs-lookup"><span data-stu-id="24f0a-225"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span></span>|  
|<span data-ttu-id="24f0a-226">요소</span><span class="sxs-lookup"><span data-stu-id="24f0a-226">Element</span></span>|<span data-ttu-id="24f0a-227"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\*)?</span><span class="sxs-lookup"><span data-stu-id="24f0a-227"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\*)?</span></span> <span data-ttu-id="24f0a-228"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;</span><span class="sxs-lookup"><span data-stu-id="24f0a-228"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;</span></span><br /><br /> <span data-ttu-id="24f0a-229"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span><span class="sxs-lookup"><span data-stu-id="24f0a-229"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span></span><br /><br /> <span data-ttu-id="24f0a-230"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span><span class="sxs-lookup"><span data-stu-id="24f0a-230"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span></span>|  
|<span data-ttu-id="24f0a-231">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="24f0a-231">Content</span></span>|<span data-ttu-id="24f0a-232"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; 요소</span><span class="sxs-lookup"><span data-stu-id="24f0a-232"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="24f0a-233">위 표에서 <xref:System.InvalidOperationException> 개체의 현재 상태에 따라 잘못된 시퀀스에서 메서드를 호출하면 각 메서드에 의해 <xref:System.Xml.Schema.XmlSchemaValidator>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-233">An <xref:System.InvalidOperationException> is thrown by each of the methods in the table above when the call to the method is made in the incorrect sequence according to the current state of an <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span>  
  
 <span data-ttu-id="24f0a-234">위의 상태 전환 표에서는 문장 부호를 사용하여 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 상태 전환의 각 상태에 대해 호출할 수 있는 메서드와 기타 상태를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-234">The state transition table above uses punctuation symbols to describe the methods and other states that can be called for each state of the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span> <span data-ttu-id="24f0a-235">사용된 문장 부호는 DTD(문서 종류 정의)에 대한 XML 표준 참조의 문장 부호와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-235">The symbols used are the same symbols found in the XML Standards reference for Document Type Definition (DTD).</span></span>  
  
 <span data-ttu-id="24f0a-236">다음 표에서는 위의 상태 전환 표에 나타난 문장 부호가 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스 상태 전환의 각 상태에 대해 호출할 수 있는 메서드와 기타 상태에 미치는 영향을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-236">The following table describes how the punctuation symbols found in the state transition table above affect the methods and other states that can be called for each state in the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>  
  
|<span data-ttu-id="24f0a-237">기호</span><span class="sxs-lookup"><span data-stu-id="24f0a-237">Symbol</span></span>|<span data-ttu-id="24f0a-238">설명</span><span class="sxs-lookup"><span data-stu-id="24f0a-238">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="24f0a-239">&#124;</span><span class="sxs-lookup"><span data-stu-id="24f0a-239">&#124;</span></span>|<span data-ttu-id="24f0a-240">세로 막대 앞이나 뒤의 메서드 또는 상태를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-240">Either method or state (the one before the bar or the one after it) can be called.</span></span>|  
|<span data-ttu-id="24f0a-241">?</span><span class="sxs-lookup"><span data-stu-id="24f0a-241">?</span></span>|<span data-ttu-id="24f0a-242">물음표 앞의 메서드나 상태는 선택 항목이지만 이 메서드나 상태를 호출할 경우에는 한 번만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-242">The method or state that precedes the question mark is optional but if it is called it can only be called once.</span></span>|  
|*|<span data-ttu-id="24f0a-243">\* 기호 앞의 메서드나 상태는 선택 항목이며 두 번 이상 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-243">The method or state that precedes the \* symbol is optional, and can be called more than once.</span></span>|  
  
## <a name="validation-context"></a><span data-ttu-id="24f0a-244">유효성 검사 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="24f0a-244">Validation Context</span></span>  
 <span data-ttu-id="24f0a-245">XML Infoset에서 요소, 특성 및 내용의 유효성을 검사하는 데 사용하는 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스의 메서드는 <xref:System.Xml.Schema.XmlSchemaValidator> 개체의 유효성 검사 컨텍스트를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-245">The methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class used to validate elements, attributes, and content in an XML infoset, change the validation context of an <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span> <span data-ttu-id="24f0a-246">예를 들어, <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> 메서드는 현재 요소 내용의 유효성 검사를 생략하고 <xref:System.Xml.Schema.XmlSchemaValidator> 개체를 준비하여 부모 요소의 컨텍스트에서 내용의 유효성을 검사합니다. 이 동작은 현재 요소의 모든 자식에 대한 유효성 검사를 생략하고 <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> 메서드를 호출하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-246">For example, the <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> method skips validation of the current element content and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate content in the parent element's context; it is equivalent to skipping validation for all the children of the current element and then calling the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> method.</span></span>  
  
 <span data-ttu-id="24f0a-247"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 클래스의 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> 및 <xref:System.Xml.Schema.XmlSchemaValidator> 메서드로 인한 결과는 유효성 검사가 실행 중인 현재 컨텍스트에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-247">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span>  
  
 <span data-ttu-id="24f0a-248">이 표에서는 XML Infoset에서 요소, 특성 및 내용의 유효성을 검사하는 데 사용하는 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스의 메서드 중 하나를 호출한 후 이러한 메서드를 호출한 결과를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-248">The following table describes the results of calling these methods after calling one of the methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class used to validate elements, attributes, and content in an XML infoset.</span></span>  
  
|<span data-ttu-id="24f0a-249">메서드</span><span class="sxs-lookup"><span data-stu-id="24f0a-249">Method</span></span>|<span data-ttu-id="24f0a-250">GetExpectedParticles</span><span class="sxs-lookup"><span data-stu-id="24f0a-250">GetExpectedParticles</span></span>|<span data-ttu-id="24f0a-251">GetExpectedAttributes</span><span class="sxs-lookup"><span data-stu-id="24f0a-251">GetExpectedAttributes</span></span>|<span data-ttu-id="24f0a-252">AddSchema</span><span class="sxs-lookup"><span data-stu-id="24f0a-252">AddSchema</span></span>|  
|------------|--------------------------|---------------------------|---------------|  
|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>|<span data-ttu-id="24f0a-253">기본 <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> 메서드를 호출할 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>는 모든 전역 요소가 포함된 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-253">If the default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method is called, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an array containing all global elements.</span></span><br /><br /> <span data-ttu-id="24f0a-254"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>를 매개 변수로 사용하는 오버로드된 <xref:System.Xml.Schema.XmlSchemaObject> 메서드를 호출하여 요소의 부분 유효성 검사를 초기화하는 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>는 <xref:System.Xml.Schema.XmlSchemaValidator> 개체가 초기화된 요소만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-254">If the overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter is called to initialize partial validation of an element, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns only the element to which the <xref:System.Xml.Schema.XmlSchemaValidator> object was initialized.</span></span>|<span data-ttu-id="24f0a-255">기본 <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> 메서드를 호출할 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>는 빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-255">If the default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method is called, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="24f0a-256"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>를 매개 변수로 사용하는 오버로드된 <xref:System.Xml.Schema.XmlSchemaObject> 메서드를 호출하여 특성의 부분 유효성 검사를 초기화하는 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>는 <xref:System.Xml.Schema.XmlSchemaValidator> 개체가 초기화된 특성만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-256">If the overload of the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter is called to initialize partial validation of an attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns only the attribute to which the <xref:System.Xml.Schema.XmlSchemaValidator> object was initialized.</span></span>|<span data-ttu-id="24f0a-257">전처리 오류가 없을 경우 <xref:System.Xml.Schema.XmlSchemaSet> 개체의 <xref:System.Xml.Schema.XmlSchemaValidator>에 스키마를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-257">Adds the schema to the <xref:System.Xml.Schema.XmlSchemaSet> of the <xref:System.Xml.Schema.XmlSchemaValidator> object if it has no preprocessing errors.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|<span data-ttu-id="24f0a-258">컨텍스트 요소가 유효한 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>는 컨텍스트 요소 자식으로 필요한 요소의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-258">If the context element is valid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as children of the context element.</span></span><br /><br /> <span data-ttu-id="24f0a-259">컨텍스트 요소가 잘못되었으면 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>가 빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-259">If the context element is invalid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span>|<span data-ttu-id="24f0a-260">컨텍스트 요소가 유효하고 이전에 <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>를 호출하지 않은 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>는 컨텍스트 요소에 정의된 모든 특성의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-260">If the context element is valid, and if no call to <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> has been previously made, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of all the attributes defined on the context element.</span></span><br /><br /> <span data-ttu-id="24f0a-261">일부 특성의 유효성을 이미 확인한 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>는 유효성을 검사할 나머지 특성의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-261">If some attributes have already been validated, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of the remaining attributes to be validated.</span></span><br /><br /> <span data-ttu-id="24f0a-262">컨텍스트 요소가 잘못되었으면 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>가 빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-262">If the context element is invalid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span>|<span data-ttu-id="24f0a-263">위와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-263">Same as above.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|<span data-ttu-id="24f0a-264">컨텍스트 특성이 최상위 특성이면 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>가 빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-264">If the context attribute is a top-level attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="24f0a-265">그렇지 않으면 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>는 컨텍스트 요소의 첫 번째 자식으로 필요한 요소의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-265">Otherwise <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="24f0a-266">컨텍스트 특성이 최상위 특성이면 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>가 빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-266">If the context attribute is a top-level attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="24f0a-267">그렇지 않으면 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>는 유효성을 검사할 나머지 특성의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-267">Otherwise <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the list of remaining attributes to be validated.</span></span>|<span data-ttu-id="24f0a-268">위와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-268">Same as above.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>|<span data-ttu-id="24f0a-269"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>는 컨텍스트 요소의 첫 번째 자식으로 필요한 요소의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-269"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="24f0a-270"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>는 컨텍스트 요소에 대해 유효성을 검사할 필수 특성 및 선택적 특성의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-270"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of the required and optional attributes that are yet to be validated for the context element.</span></span>|<span data-ttu-id="24f0a-271">위와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-271">Same as above.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<span data-ttu-id="24f0a-272"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>는 컨텍스트 요소의 첫 번째 자식으로 필요한 요소의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-272"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="24f0a-273"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>는 빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-273"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span>|<span data-ttu-id="24f0a-274">위와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-274">Same as above.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|<span data-ttu-id="24f0a-275">컨텍스트 요소의 contentType이 Mixed인 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>는 다음 위치에 필요한 요소의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-275">If the context element's contentType is Mixed, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected in the next position.</span></span><br /><br /> <span data-ttu-id="24f0a-276">컨텍스트 요소의 contentType이 TextOnly 또는 Empty인 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>는 빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-276">If the context element's contentType is TextOnly or Empty, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="24f0a-277">컨텍스트 요소의 contentType이 ElementOnly인 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>는 다음 위치에 필요한 요소의 시퀀스를 반환하지만 유효성 검사 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-277">If the context element's contentType is ElementOnly, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected in the next position but a validation error has already occurred.</span></span>|<span data-ttu-id="24f0a-278"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>는 특성의 유효성이 검사되지 않은 컨텍스트 요소의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-278"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the context element's list of attributes not validated.</span></span>|<span data-ttu-id="24f0a-279">위와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-279">Same as above.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|<span data-ttu-id="24f0a-280">컨텍스트 공백이 최상위 공백이면 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>가 빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-280">If the context white-space is top-level white-space, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="24f0a-281">그렇지 않으면 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> 메서드의 동작이 <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>와 동일하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-281">Otherwise the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method's behavior is the same as in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span></span>|<span data-ttu-id="24f0a-282">컨텍스트 공백이 최상위 공백이면 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>가 빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-282">If the context white-space is top-level white-space, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="24f0a-283">그렇지 않으면 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> 메서드의 동작이 <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>와 동일하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-283">Otherwise the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method's behavior is the same as in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span></span>|<span data-ttu-id="24f0a-284">위와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-284">Same as above.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<span data-ttu-id="24f0a-285"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>는 컨텍스트 요소(가능한 형제) 뒤에 필요한 요소의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-285"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected after the context element (possible siblings).</span></span>|<span data-ttu-id="24f0a-286"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>는 특성의 유효성이 검사되지 않은 컨텍스트 요소의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-286"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the context element's list of attributes not validated.</span></span><br /><br /> <span data-ttu-id="24f0a-287">컨텍스트 요소에 부모가 없을 경우 <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>는 빈 목록을 반환합니다. 컨텍스트 요소는 <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>가 호출된 현재 요소의 부모입니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-287">If the context element has no parent then <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty list (the context element is the parent of the current element on which <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> was called).</span></span>|<span data-ttu-id="24f0a-288">위와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-288">Same as above.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|<span data-ttu-id="24f0a-289"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-289">Same as <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span></span>|<span data-ttu-id="24f0a-290"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-290">Same as <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span></span>|<span data-ttu-id="24f0a-291">위와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-291">Same as above.</span></span>|  
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|<span data-ttu-id="24f0a-292">빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-292">Returns an empty array.</span></span>|<span data-ttu-id="24f0a-293">빈 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-293">Returns an empty array.</span></span>|<span data-ttu-id="24f0a-294">위와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-294">Same as above.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="24f0a-295"><xref:System.Xml.Schema.XmlSchemaValidator> 클래스의 다양한 속성이 반환하는 값은 위 표의 메서드를 호출해도 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24f0a-295">The values returned by the various properties of the <xref:System.Xml.Schema.XmlSchemaValidator> class are not altered by calling any of the methods in the above table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f0a-296">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24f0a-296">See Also</span></span>  
 <xref:System.Xml.Schema.XmlSchemaValidator>
