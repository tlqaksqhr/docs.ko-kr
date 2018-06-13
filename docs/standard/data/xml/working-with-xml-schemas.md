---
title: XML 스키마 사용
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83fddd00f44b184fa066f6c47b90b01fac7ef7bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570655"
---
# <a name="working-with-xml-schemas"></a><span data-ttu-id="2ec01-102">XML 스키마 사용</span><span class="sxs-lookup"><span data-stu-id="2ec01-102">Working with XML Schemas</span></span>
<span data-ttu-id="2ec01-103">XML 문서 구조, 요소 관계, 데이터 형식, 내용 제약 조건 등을 정의하려면 DTD(문서 종류 정의) 또는 XSD(XML 스키마 정의 언어) 스키마를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ec01-103">To define the structure of an XML document, as well as its element relationships, data types, and content constraints, you use a document type definition (DTD) or XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="2ec01-104">XML 문서가 제대로 구성된 것으로 간주되더라도 W3C(World Wide Web 컨소시엄) XML(Extensible Markup Language) 1.0 권장 사항에 정의된 구문 요구 사항을 모두 만족할 경우 제대로 구성되고 DTD나 스키마에 정의된 제약 조건을 준수해야만 유효한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ec01-104">Although an XML document is considered to be well-formed if it meets all the syntactical requirements defined by the World Wide Web Consortium (W3C) Extensible Markup Language (XML) 1.0 Recommendation, it is not considered valid unless it is both well-formed and conforms to the constraints defined by its DTD or schema.</span></span> <span data-ttu-id="2ec01-105">그러므로 유효한 모든 XML 문서가 제대로 구성되었더라도 제대로 구성된 XML 문서가 모두 유효한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2ec01-105">Therefore, although all valid XML documents are well-formed, not all well-formed XML documents are valid.</span></span>  
  
 <span data-ttu-id="2ec01-106">XML에 대한 자세한 내용은 [W3C XML 1.0 Recommendation](https://www.w3.org/TR/REC-xml/)(W3C XML 1.0 권장 사항)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ec01-106">For more information about XML, see the [W3C XML 1.0 Recommendation](https://www.w3.org/TR/REC-xml/).</span></span> <span data-ttu-id="2ec01-107">XML 스키마에 대한 자세한 내용은 [W3C XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/) 및 [W3C XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/)의 권장 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ec01-107">For more information about XML Schema, see the [W3C XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/) and the [W3C XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/) recommendations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ec01-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2ec01-108">In This Section</span></span>  
 [<span data-ttu-id="2ec01-109">XML SOM(스키마 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="2ec01-109">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 <span data-ttu-id="2ec01-110">파일에서 XSD(XML 스키마 정의 언어) 스키마를 읽거나 프로그래밍 방식으로 메모리 내 스키마를 만들 수 있는 클래스 집합을 제공하는 <xref:System.Xml.Schema?displayProperty=nameWithType> 네임스페이스의 SOM(스키마 개체 모델)에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ec01-110">Discusses the Schema Object Model (SOM) in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that provides a set of classes that allows you to read a Schema definition language (XSD) schema from a file or programmatically create a schema in-memory.</span></span>  
  
 [<span data-ttu-id="2ec01-111">스키마 컴파일을 위한 XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="2ec01-111">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 <span data-ttu-id="2ec01-112">XSD 스키마를 저장하고 유효성을 검사할 수 있는 캐시인 <xref:System.Xml.Schema.XmlSchemaSet> 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ec01-112">Discusses the <xref:System.Xml.Schema.XmlSchemaSet> class that is a cache where XSD schemas can be stored and validated.</span></span>  
  
 [<span data-ttu-id="2ec01-113">XmlSchemaValidator 밀어넣기 기반 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2ec01-113">XmlSchemaValidator Push-Based Validation</span></span>](../../../../docs/standard/data/xml/xmlschemavalidator-push-based-validation.md)  
 <span data-ttu-id="2ec01-114">밀어넣기 기반 방식으로 XSD 스키마에 대해 XML 데이터의 유효성을 검사할 수 있는 효과적인 고성능 메커니즘을 제공하는 <xref:System.Xml.Schema.XmlSchemaValidator> 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ec01-114">Discusses the <xref:System.Xml.Schema.XmlSchemaValidator> class that provides an efficient, high-performance mechanism to validate XML data against XSD schemas in a push-based manner.</span></span>  
  
 [<span data-ttu-id="2ec01-115">XML 스키마 유추</span><span class="sxs-lookup"><span data-stu-id="2ec01-115">Inferring an XML Schema</span></span>](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 <span data-ttu-id="2ec01-116"><xref:System.Xml.Schema.XmlSchemaInference> 클래스를 사용하여 XML 문서 구조에서 XSD 스키마를 유추하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ec01-116">Discusses how to use the <xref:System.Xml.Schema.XmlSchemaInference> class to infer an XSD schema from the structure of an XML document.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2ec01-117">참조</span><span class="sxs-lookup"><span data-stu-id="2ec01-117">Reference</span></span>  
 <span data-ttu-id="2ec01-118"><xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="2ec01-118"><xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader></span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2ec01-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="2ec01-119">Related Sections</span></span>  
 [<span data-ttu-id="2ec01-120">DOM에서의 XML 문서 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2ec01-120">Validating an XML Document in the DOM</span></span>](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
 <span data-ttu-id="2ec01-121">DOM(문서 개체 모델)에서 XML의 유효성을 검사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ec01-121">Discusses how to validate the XML in the Document Object Model (DOM).</span></span> <span data-ttu-id="2ec01-122">XML을 DOM에 로드할 때 유효성을 검사하거나 DOM에서 이전에 무효화한 XML 문서의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ec01-122">You can validate the XML as it is loaded into the DOM, or validate a previously unvalidated XML document in the DOM.</span></span>  
  
 [<span data-ttu-id="2ec01-123">XPathNavigator를 사용하여 스키마 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2ec01-123">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 <span data-ttu-id="2ec01-124"><xref:System.Xml.XPath.XPathNavigator> 클래스를 사용하여 탐색 및 편집하는 XML의 유효성 검사 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ec01-124">Discusses how to validate XML being navigated and edited using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
