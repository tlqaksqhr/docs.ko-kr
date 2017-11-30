---
title: "XPathNavigator를 사용하여 강력한 형식의 XML 데이터 액세스"
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
ms.assetid: 898e0f52-8a7c-4d1f-afcd-6ffb28b050b4
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 61c78adff541ac2ba261d31776478a0468e21d4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-strongly-typed-xml-data-using-xpathnavigator"></a><span data-ttu-id="11359-102">XPathNavigator를 사용하여 강력한 형식의 XML 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="11359-102">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>
<span data-ttu-id="11359-103">XPath 2.0 데이터 모델의 인스턴스로서 <xref:System.Xml.XPath.XPathNavigator> 클래스는 CLR(공용 언어 런타임) 형식에 매핑되는 강력한 형식의 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-103">As an instance of the XPath 2.0 data model, the <xref:System.Xml.XPath.XPathNavigator> class can contain strongly-typed data that maps to common language runtime (CLR) types.</span></span> <span data-ttu-id="11359-104">XPath 2.0 데이터 모델에 따르면 요소와 특성에만 강력한 형식의 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-104">According to the XPath 2.0 data model, only elements and attributes can contain strongly-typed data.</span></span> <span data-ttu-id="11359-105"><xref:System.Xml.XPath.XPathNavigator> 클래스는 데이터 형식을 변환하는 메커니즘뿐 아니라 강력한 형식의 데이터로 <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체 내의 데이터에 액세스할 수 있는 메커니즘도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-105">The <xref:System.Xml.XPath.XPathNavigator> class provides mechanisms for accessing data within an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object as strongly-typed data as well as mechanisms for converting from one data type to another.</span></span>  
  
## <a name="type-information-exposed-by-xpathnavigator"></a><span data-ttu-id="11359-106">XPathNavigator에 의해 노출된 형식 정보</span><span class="sxs-lookup"><span data-stu-id="11359-106">Type Information Exposed by XPathNavigator</span></span>  
 <span data-ttu-id="11359-107">XML 1.0 데이터가 DTD, XSD(XML 스키마 정의 언어) 스키마 또는 기타 메커니즘으로 처리되지 않을 경우 기술적인 측면에서 XML 1.0 데이터에는 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-107">XML 1.0 data is technically without type, unless processed with a DTD, XML schema definition language (XSD) schema, or other mechanism.</span></span> <span data-ttu-id="11359-108">XML 요소나 특성에 연결할 수 있는 형식 정보 범주에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-108">There are a number of categories of type information that can be associated with an XML element or attribute.</span></span>  
  
-   <span data-ttu-id="11359-109">단순 CLR 형식: XML 스키마 언어는 CLR(공용 언어 런타임) 형식을 직접 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-109">Simple CLR Types: None of the XML Schema languages support Common Language Runtime (CLR) types directly.</span></span> <span data-ttu-id="11359-110">가장 적합한 CLR 형식으로 단순 요소 및 특성 내용을 볼 수 있으므로 스키마 정보가 없을 경우 이 내용을 보다 적합한 형식으로 구체화할 수 있는 추가된 스키마 정보를 사용하여 모든 단순 내용에 <xref:System.String> 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-110">Because it is useful to be able to view simple element and attribute content as the most appropriate CLR type, all simple content can be typed as <xref:System.String> in the absence of schema information with any added schema information potentially refining this content to a more appropriate type.</span></span> <span data-ttu-id="11359-111"><xref:System.Xml.XPath.XPathNavigator.ValueType%2A> 속성을 사용하여 단순 요소 및 특성 내용의 가장 일치하는 CLR 형식을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-111">You can find the best matching CLR type of simple element and attribute content by using the <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> property.</span></span> <span data-ttu-id="11359-112">CLR 형식에 대 한 스키마 기본 제공 형식 매핑에 대 한 자세한 내용은 참조 [System.Xml 클래스의 형식 지원](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-112">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span></span>  
  
-   <span data-ttu-id="11359-113">단순 (CLR) 형식 목록: 단순 내용이 있는 요소나 특성에 공백으로 구분된 값 목록이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-113">Lists of Simple (CLR) Types: An element or attribute with simple content can contain a list of values separated by white space.</span></span> <span data-ttu-id="11359-114">값은 XML 스키마에 의해 "목록 형식"으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="11359-114">The values are specified by an XML Schema to be a "list type."</span></span> <span data-ttu-id="11359-115">XML 스키마가 없을 경우 이러한 단순 내용은 단일 텍스트 노드로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="11359-115">In the absence of an XML Schema, such simple content would be treated as a single text node.</span></span> <span data-ttu-id="11359-116">XML 스키마를 사용할 수 있는 경우 이 단순 내용을 일련의 atomic 값으로 노출할 수 있습니다. 각 atomic 값은 CLR 개체 컬렉션으로 매핑되는 단순 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="11359-116">When an XML Schema is available, this simple content can be exposed as a series of atomic values each having a simple type that maps to a collection of CLR objects.</span></span> <span data-ttu-id="11359-117">CLR 형식에 대 한 스키마 기본 제공 형식 매핑에 대 한 자세한 내용은 참조 [System.Xml 클래스의 형식 지원](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-117">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span></span>  
  
-   <span data-ttu-id="11359-118">형식화된 값: 스키마에 의해 유효성이 검사되는 단순 형식의 특성 또는 요소에는 형식화된 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-118">Typed Value: A schema-validated attribute or element with a simple type has a typed value.</span></span> <span data-ttu-id="11359-119">이 값은 numeric, string, date 형식 등의 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="11359-119">This value is a primitive type such as a numeric, string, or date type.</span></span> <span data-ttu-id="11359-120">XSD의 모든 기본 제공 단순 형식을 CLR 형식으로 매핑할 수 있습니다. 이 CLR 형식을 사용하면 단순히 <xref:System.String>으로 노드 값에 액세스하는 대신 더욱 적합한 형식으로 노드 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-120">All the built-in simple types in XSD can be mapped to CLR types that provide access to the value of a node as a more appropriate type instead of just as a <xref:System.String>.</span></span> <span data-ttu-id="11359-121">특성이나 요소 자식이 있는 요소는 복합 형식으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="11359-121">An element with attributes or element children is considered to be a complex type.</span></span> <span data-ttu-id="11359-122">단순 내용(자식으로 텍스트 노드만 포함)이 있는 복합 형식의 형식화된 값은 단순 내용의 단순 형식의 형식화된 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-122">The typed value of a complex type with simple content (only text nodes as children) is the same as that of the simple type of its content.</span></span> <span data-ttu-id="11359-123">복합 내용(하나 이상의 자식 요소 포함)이 있는 복합 형식의 형식화된 값은 <xref:System.String>으로 반환된 모든 자식 텍스트 노드를 연결한 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="11359-123">The typed value of a complex type with complex content (one or more child elements) is the string value of the concatenation of all its child text nodes returned as a <xref:System.String>.</span></span> <span data-ttu-id="11359-124">CLR 형식에 대 한 스키마 기본 제공 형식 매핑에 대 한 자세한 내용은 참조 [System.Xml 클래스의 형식 지원](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-124">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span></span>  
  
-   <span data-ttu-id="11359-125">스키마 언어 관련 형식 이름: 대부분의 경우 외부 스키마를 적용함으로써 부수적으로 설정되는 CLR 형식을 사용하여 노드 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-125">Schema-Language Specific Type Name: In most cases, the CLR types, which are set as a side-effect of applying an external schema, are used to provide access to the value of a node.</span></span> <span data-ttu-id="11359-126">그러나 XML 문서에 적용된 특정 스키마와 연결된 형식을 검사해야 할 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-126">However, there may be situations where you may want to examine the type associated with a particular schema applied to an XML document.</span></span> <span data-ttu-id="11359-127">예를 들어, XML 문서를 검색하여 "PurchaseOrder" 형식의 내용이 포함된 것으로 확인된 모든 요소를 연결된 스키마에 따라 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-127">For example, you may wish to search through an XML document, extracting all elements that are determined to have content of type "PurchaseOrder" according to an attached schema.</span></span> <span data-ttu-id="11359-128">이러한 형식 정보는 스키마 유효성 검사 결과로만 설정할 수 있으며 <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> 및 <xref:System.Xml.XPath.XPathNavigator> 속성을 통해 이 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-128">Such type information can be set only as a result of schema validation and this information is accessed through the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> and <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="11359-129">자세한 내용은 아래의 PSVI(Post Schema Validation Infoset) 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11359-129">For more information, see The Post Schema Validation Infoset (PSVI) section below.</span></span>  
  
-   <span data-ttu-id="11359-130">스키마 언어 관련 형식 리플렉션: XML 문서에 적용된 스키마 관련 형식의 세부 정보를 얻어야 할 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-130">Schema-Language Specific Type Reflection: In other cases, you may want to obtain further details of the schema-specific type applied to an XML document.</span></span> <span data-ttu-id="11359-131">예를 들어, XML 파일을 읽을 때 사용자 지정 계산을 수행하기 위해 XML 문서에서 유효한 각 노드의 `maxOccurs` 특성을 추출해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-131">For example, when reading an XML file, you may want to extract the `maxOccurs` attribute for each valid node in the XML document in order to perform some custom calculation.</span></span> <span data-ttu-id="11359-132">이 정보는 스키마 유효성 검사를 통해서만 설정되므로 <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator> 속성을 통해 이 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-132">Because this information is set only through schema validation, it is accessed through the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="11359-133">자세한 내용은 아래의 PSVI(Post Schema Validation Infoset) 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11359-133">For more information, see The Post Schema Validation Infoset (PSVI) section below.</span></span>  
  
## <a name="xpathnavigator-typed-accessors"></a><span data-ttu-id="11359-134">XPathNavigator의 형식화된 접근자</span><span class="sxs-lookup"><span data-stu-id="11359-134">XPathNavigator Typed Accessors</span></span>  
 <span data-ttu-id="11359-135">다음 표에서는 노드에 대한 형식 정보에 액세스하는 데 사용할 수 있는 <xref:System.Xml.XPath.XPathNavigator> 클래스의 다양한 속성 및 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11359-135">The following table shows the various properties and methods of the <xref:System.Xml.XPath.XPathNavigator> class that can be used to access the type information about a node.</span></span>  
  
|<span data-ttu-id="11359-136">속성</span><span class="sxs-lookup"><span data-stu-id="11359-136">Property</span></span>|<span data-ttu-id="11359-137">설명</span><span class="sxs-lookup"><span data-stu-id="11359-137">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.XmlType%2A>|<span data-ttu-id="11359-138">유효한 경우 노드에 대한 XML 스키마 형식 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-138">This contains the XML schema type information for the node if it is valid.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>|<span data-ttu-id="11359-139">유효성 검사 후 추가된 노드의 Post Schema Validation Infoset이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-139">This contains the Post Schema Validation Infoset of the node that is added after validation.</span></span> <span data-ttu-id="11359-140">유효성 정보와 XML 스키마 형식 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-140">This includes the XML schema type information, as well as validity information.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueType%2A>|<span data-ttu-id="11359-141">형식화된 노드 값의 CLR 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="11359-141">The CLR type of the typed value of the node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>|<span data-ttu-id="11359-142">하나 이상의 CLR 값의 형식이 노드의 XML 스키마 형식에 가장 일치하는 노드 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="11359-142">The content of the node as one or more CLR values whose type is the closest match to the XML schema type of the node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsBoolean%2A>|<span data-ttu-id="11359-143">현재 노드의 <xref:System.String> 값은 <xref:System.Boolean>에 대한 XPath 2.0 캐스팅 규칙에 따라 `xs:boolean` 값을 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-143">The <xref:System.String> value of the current node cast to a <xref:System.Boolean> value, according to the XPath 2.0 casting rules for `xs:boolean`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDateTime%2A>|<span data-ttu-id="11359-144">현재 노드의 <xref:System.String> 값은 <xref:System.DateTime>에 대한 XPath 2.0 캐스팅 규칙에 따라 `xs:datetime` 값을 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-144">The <xref:System.String> value of the current node cast to a <xref:System.DateTime> value, according to the XPath 2.0 casting rules for `xs:datetime`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>|<span data-ttu-id="11359-145">현재 노드의 <xref:System.String> 값은 <xref:System.Double>에 대한 XPath 2.0 캐스팅 규칙에 따라 `xsd:double` 값을 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-145">The <xref:System.String> value of the current node cast to a <xref:System.Double> value, according to the XPath 2.0 casting rules for `xsd:double`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>|<span data-ttu-id="11359-146">현재 노드의 <xref:System.String> 값은 <xref:System.Int32>에 대한 XPath 2.0 캐스팅 규칙에 따라 `xs:integer` 값을 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-146">The <xref:System.String> value of the current node cast to a <xref:System.Int32> value, according to the XPath 2.0 casting rules for `xs:integer`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A>|<span data-ttu-id="11359-147">현재 노드의 <xref:System.String> 값은 <xref:System.Int64>에 대한 XPath 2.0 캐스팅 규칙에 따라 `xs:integer` 값을 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-147">The <xref:System.String> value of the current node cast to a <xref:System.Int64> value, according to the XPath 2.0 casting rules for `xs:integer`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAs%2A>|<span data-ttu-id="11359-148">노드 내용은 XPath 2.0 캐스팅 규칙에 따라 대상 형식을 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-148">The contents of the node cast to the target type according to the XPath 2.0 casting rules.</span></span>|  
  
 <span data-ttu-id="11359-149">CLR 형식에 대 한 스키마 기본 제공 형식 매핑에 대 한 자세한 내용은 참조 [System.Xml 클래스의 형식 지원](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-149">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span></span>  
  
## <a name="the-post-schema-validation-infoset-psvi"></a><span data-ttu-id="11359-150">PSVI(Post Schema Validation Infoset)</span><span class="sxs-lookup"><span data-stu-id="11359-150">The Post Schema Validation Infoset (PSVI)</span></span>  
 <span data-ttu-id="11359-151">XML 스키마 프로세서는 XML Infoset을 입력으로 허용하며 이 XML Infoset을 PSVI(Post Schema Validation Infoset)로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-151">An XML Schema processor accepts an XML Infoset as input and converts it into a Post Schema Validation Infoset (PSVI).</span></span> <span data-ttu-id="11359-152">PSVI는 원래 입력 XML Infoset의 기존 정보 항목에 새 정보 항목과 새 속성을 추가한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11359-152">A PSVI is the original input XML infoset with new information items added and new properties added to existing information items.</span></span> <span data-ttu-id="11359-153"><xref:System.Xml.XPath.XPathNavigator>에 의해 노출된 PSVI에는 XML Infoset에 추가된 정보의 광범위한 클래스 세 개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-153">There are three broad classes of information added to the XML Infoset in the PSVI that are exposed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
1.  <span data-ttu-id="11359-154">유효성 검사 결과: 요소나 특성에 대한 유효성 검사가 성공적으로 수행되었는지 여부를 나타내는 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="11359-154">Validation Outcomes: Information as to whether an element or attribute was successfully validated or not.</span></span> <span data-ttu-id="11359-155">그러면 <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> 속성에 들어 있는 <xref:System.Xml.XPath.XPathNavigator> 속성에 의해 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="11359-155">This is exposed by the <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> property of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
2.  <span data-ttu-id="11359-156">기본 정보: 스키마에 지정된 기본값을 통해 요소 또는 특성 값을 얻었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11359-156">Default Information: Indications as to whether the value of the element or attribute was obtained via default values specified in the schema or not.</span></span> <span data-ttu-id="11359-157">그러면 <xref:System.Xml.Schema.IXmlSchemaInfo.IsDefault%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> 속성에 들어 있는 <xref:System.Xml.XPath.XPathNavigator> 속성에 의해 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="11359-157">This is exposed by the <xref:System.Xml.Schema.IXmlSchemaInfo.IsDefault%2A> property of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
3.  <span data-ttu-id="11359-158">형식 주석: 형식 정의 또는 요소와 특성 선언 등의 스키마 구성 요소에 대한 참조 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="11359-158">Type Annotations: References to schema components that may be type definitions or element and attribute declarations.</span></span> <span data-ttu-id="11359-159">유효한 경우 <xref:System.Xml.XPath.XPathNavigator.XmlType%2A>의 <xref:System.Xml.XPath.XPathNavigator> 속성에는 노드에 대한 특정 형식 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-159">The <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property of the <xref:System.Xml.XPath.XPathNavigator> contains the specific type information of the node if it is valid.</span></span> <span data-ttu-id="11359-160">노드의 유효성을 검사한 후 노드를 편집한 경우와 같이 노드의 유효성을 알 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="11359-160">If the validity of a node is unknown, such as when it was validated then subsequently edited.</span></span> <span data-ttu-id="11359-161"><xref:System.Xml.XPath.XPathNavigator.XmlType%2A> 속성은 `null`로 설정되지만 <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> 클래스에 대한 <xref:System.Xml.XPath.XPathNavigator> 속성의 다양한 속성을 통해 형식 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-161">then the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property is set to `null` but type information is still available from the various properties of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 <span data-ttu-id="11359-162">다음 예제에서는 <xref:System.Xml.XPath.XPathNavigator>에 의해 노출된 Post Schema Validation Infoset의 정보를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11359-162">The following example illustrates using information in the Post Schema Validation Infoset exposed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("books.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("published", "http://www.contoso.com/books")  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name)  
Console.WriteLine(navigator.SchemaInfo.Validity)  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("books.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("published", "http://www.contoso.com/books");  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name);  
Console.WriteLine(navigator.SchemaInfo.Validity);  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs);  
```  
  
 <span data-ttu-id="11359-163">이 예제에서는 `books.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-163">The example takes the `books.xml` file as input.</span></span>  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="11359-164">이 예제에서는 또한 `books.xsd` 스키마를 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-164">The example also takes the `books.xsd` schema as input.</span></span>  
  
```xml  
<xs:schema xmlns="http://www.contoso.com/books"   
attributeFormDefault="unqualified" elementFormDefault="qualified"   
targetNamespace="http://www.contoso.com/books"   
xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="publishedType">  
        <xs:restriction base="xs:date">  
            <xs:minInclusive value="2003-01-01" />  
            <xs:maxInclusive value="2003-12-31" />  
        </xs:restriction>  
    </xs:simpleType>  
    <xs:complexType name="bookType">  
        <xs:sequence>  
            <xs:element name="title" type="xs:string"/>  
            <xs:element name="price" type="xs:decimal"/>  
            <xs:element name="published" type="publishedType"/>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="booksType">  
        <xs:sequence>  
            <xs:element name="book" type="bookType" />  
        </xs:sequence>  
    </xs:complexType>  
    <xs:element name="books" type="booksType" />  
</xs:schema>  
```  
  
## <a name="obtain-typed-values-using-valueas-properties"></a><span data-ttu-id="11359-165">ValueAs 속성을 사용하여 형식화된 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="11359-165">Obtain Typed Values Using ValueAs Properties</span></span>  
 <span data-ttu-id="11359-166"><xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>의 <xref:System.Xml.XPath.XPathNavigator> 속성에 액세스하여 형식화된 노드 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-166">The typed value of a node can be retrieved by accessing the <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> property of the <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="11359-167">형식화된 노드 값을 다른 형식으로 변환해야 할 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-167">In certain cases you may want to convert the typed value of a node to a different type.</span></span> <span data-ttu-id="11359-168">일반적인 예는 XML 노드로부터 숫자 값을 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11359-168">A common example is to get a numeric value from an XML node.</span></span> <span data-ttu-id="11359-169">예를 들어, 무효화되고 형식화되지 않은 다음 XML 문서를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="11359-169">For example, consider the following unvalidated and untyped XML document.</span></span>  
  
```xml  
<books>  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="11359-170"><xref:System.Xml.XPath.XPathNavigator>가 `price` 요소에 있을 경우 <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> 속성은 `null`이 되고 <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> 속성은 <xref:System.String>이 되며 <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> 속성은 문자열 `10.00`이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11359-170">If the <xref:System.Xml.XPath.XPathNavigator> is positioned on the `price` element the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property would be `null`, the <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> property would be <xref:System.String>, and the <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> property would be the string `10.00`.</span></span>  
  
 <span data-ttu-id="11359-171">그러나 여전히 <xref:System.Xml.XPath.XPathItem.ValueAs%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A> 또는 <xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A> 같은 메서드 및 속성을 사용하여 숫자 값으로 값을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11359-171">However, it is still possible to extract the value as a numeric value using the <xref:System.Xml.XPath.XPathItem.ValueAs%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>, or <xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A> method and properties.</span></span> <span data-ttu-id="11359-172">다음 예제에서는 <xref:System.Xml.XPath.XPathItem.ValueAs%2A> 메서드를 사용하여 이러한 캐스팅을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11359-172">The following example illustrates performing such a cast using the <xref:System.Xml.XPath.XPathItem.ValueAs%2A> method.</span></span>  
  
```vb  
Dim document As New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "")  
navigator.MoveToChild("book", "")  
navigator.MoveToChild("price", "")  
  
Dim price = navigator.ValueAs(GetType(Decimal))  
Dim discount As Decimal = 0.2  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * discount))  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "");  
navigator.MoveToChild("book", "");  
navigator.MoveToChild("price", "");  
  
Decimal price = (decimal)navigator.ValueAs(typeof(decimal));  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * (decimal)0.20));  
```  
  
 <span data-ttu-id="11359-173">CLR 형식에 대 한 스키마 기본 제공 형식 매핑에 대 한 자세한 내용은 참조 [System.Xml 클래스의 형식 지원](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-173">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11359-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11359-174">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="11359-175">System.Xml 클래스의 형식 지원</span><span class="sxs-lookup"><span data-stu-id="11359-175">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)  
 [<span data-ttu-id="11359-176">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="11359-176">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="11359-177">XPathNavigator를 사용 하 여 노드 집합 탐색</span><span class="sxs-lookup"><span data-stu-id="11359-177">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)  
 [<span data-ttu-id="11359-178">특성 및 XPathNavigator를 사용 하 여 Namespace 노드 탐색</span><span class="sxs-lookup"><span data-stu-id="11359-178">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 [<span data-ttu-id="11359-179">XPathNavigator를 사용 하 여 XML 데이터를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="11359-179">Extract XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)
