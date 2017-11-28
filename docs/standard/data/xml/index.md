---
title: "XML 문서 및 데이터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e695047f-3c0f-4045-8708-5baea91cc380
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 38382609fb21069fd69a84eb8b9de4701efeaf2c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xml-documents-and-data"></a><span data-ttu-id="d0b73-102">XML 문서 및 데이터</span><span class="sxs-lookup"><span data-stu-id="d0b73-102">XML Documents and Data</span></span>
<span data-ttu-id="d0b73-103">.NET Framework에서 XML 인식 응용 프로그램을 쉽게 작성할 수 있도록 하는 종합적이고 통합된 클래스 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-103">The .NET Framework provides a comprehensive and integrated set of classes that enable you to build XML-aware apps easily.</span></span> <span data-ttu-id="d0b73-104">다음 네임스페이스의 클래스에서는 XML 구문 분석 및 작성, 메모리에서의 XML 데이터 편집, 데이터 유효성 검사 및 XSLT 변형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-104">The classes in the following namespaces support parsing and writing XML, editing XML data in memory, data validation, and XSLT transformation.</span></span>  
  
-   <xref:System.Xml>  
  
-   <xref:System.Xml.XPath>  
  
-   <xref:System.Xml.Xsl>  
  
-   <xref:System.Xml.Schema>  
  
-   <xref:System.Xml.Linq>  
  
 <span data-ttu-id="d0b73-105">전체 목록은 [System.Xml Namespaces](http://msdn.microsoft.com/library/gg145036.aspx) 웹 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0b73-105">For a full list, see the [System.Xml Namespaces](http://msdn.microsoft.com/library/gg145036.aspx) webpage.</span></span>  
  
 <span data-ttu-id="d0b73-106">이러한 네임스페이스의 클래스는 W3C(World Wide Web 컨소시엄) 권장 사항을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-106">The classes in these namespaces support World Wide Web Consortium (W3C) recommendations.</span></span> <span data-ttu-id="d0b73-107">예:</span><span class="sxs-lookup"><span data-stu-id="d0b73-107">For example:</span></span>  
  
-   <span data-ttu-id="d0b73-108"><xref:System.Xml.XmlDocument?displayProperty=nameWithType> 클래스는 [W3C DOM(문서 개체 모델) Level 1 Core](http://www.w3.org/TR/REC-DOM-Level-1/) 및 [DOM Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/) 권장 사항을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-108">The <xref:System.Xml.XmlDocument?displayProperty=nameWithType> class implements the [W3C Document Object Model (DOM) Level 1 Core](http://www.w3.org/TR/REC-DOM-Level-1/) and [DOM Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/) recommendations.</span></span>  
  
-   <span data-ttu-id="d0b73-109"><xref:System.Xml.XmlReader?displayProperty=nameWithType> 및 <xref:System.Xml.XmlWriter?displayProperty=nameWithType> 클래스는 [W3C XML 1.0](http://www.w3.org/TR/2006/REC-xml-20060816/) 및 [XML의 네임스페이스](http://www.w3.org/TR/REC-xml-names/) 권장 사항을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-109">The <xref:System.Xml.XmlReader?displayProperty=nameWithType> and <xref:System.Xml.XmlWriter?displayProperty=nameWithType> classes support the [W3C XML 1.0](http://www.w3.org/TR/2006/REC-xml-20060816/) and the [Namespaces in XML](http://www.w3.org/TR/REC-xml-names/) recommendations.</span></span>  
  
-   <span data-ttu-id="d0b73-110"><xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> 클래스의 스키마는 [W3C XML 스키마 1장: 구조](http://www.w3.org/TR/xmlschema-1/) 및 [XML 스키마 2장: 데이터 형식](http://www.w3.org/TR/xmlschema-2/) 권장 사항을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-110">Schemas in the <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> class support the [W3C XML Schema Part 1: Structures](http://www.w3.org/TR/xmlschema-1/) and [XML Schema Part 2: Datatypes](http://www.w3.org/TR/xmlschema-2/) recommendations.</span></span>  
  
-   <span data-ttu-id="d0b73-111"><xref:System.Xml.Xsl?displayProperty=nameWithType> 네임스페이스의 클래스는 [W3C XSLT 1.0](http://www.w3.org/TR/xslt) 권장 사항을 준수하는 XSLT 변환을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-111">Classes in the <xref:System.Xml.Xsl?displayProperty=nameWithType> namespace support XSLT transformations that conform to the [W3C XSLT 1.0](http://www.w3.org/TR/xslt) recommendation.</span></span>  
  
 <span data-ttu-id="d0b73-112">.NET Framework의 XML 클래스는 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-112">The XML classes in the .NET Framework provide these benefits:</span></span>  
  
-   <span data-ttu-id="d0b73-113">**생산성**</span><span class="sxs-lookup"><span data-stu-id="d0b73-113">**Productivity.**</span></span> <span data-ttu-id="d0b73-114">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)을 사용하면 XML을 사용하여 더욱 쉽게 프로그래밍하고 SQL과 유사한 쿼리 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-114">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) makes it easier to program with XML and provides a query experience that is similar to SQL.</span></span>  
  
-   <span data-ttu-id="d0b73-115">**확장성**</span><span class="sxs-lookup"><span data-stu-id="d0b73-115">**Extensibility.**</span></span> <span data-ttu-id="d0b73-116">.NET Framework의 XML 클래스는 추상 기본 클래스와 가상 메서드를 사용하여 확장 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-116">The XML classes in the .NET Framework are extensible through the use of abstract base classes and virtual methods.</span></span> <span data-ttu-id="d0b73-117">예를 들어, 캐시 스트림을 로컬 디스크에 저장하는 <xref:System.Xml.XmlUrlResolver> 클래스의 파생 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-117">For example, you can create a derived class of the <xref:System.Xml.XmlUrlResolver> class that stores the cache stream to the local disk.</span></span>  
  
-   <span data-ttu-id="d0b73-118">**플러그형 아키텍처**</span><span class="sxs-lookup"><span data-stu-id="d0b73-118">**Pluggable architecture.**</span></span> <span data-ttu-id="d0b73-119">.NET Framework는 구성 요소를 서로 이용할 수 있고, 구성 요소 간에 데이터를 스트리밍할 수 있는 아키텍처를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-119">The .NET Framework provides an architecture in which components can utilize one another, and data can be streamed between components.</span></span> <span data-ttu-id="d0b73-120">예를 들어 <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체와 같은 데이터 저장소는 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 변환할 수 있고, 출력이 다른 저장소로 스트리밍되거나 웹 서비스에서 스트림으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-120">For example, a data store, such as an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object, can be transformed with the <xref:System.Xml.Xsl.XslCompiledTransform> class, and the output can then be streamed either into another store or returned as a stream from a web service.</span></span>  
  
-   <span data-ttu-id="d0b73-121">**성능.**</span><span class="sxs-lookup"><span data-stu-id="d0b73-121">**Performance.**</span></span> <span data-ttu-id="d0b73-122">응용 프로그램 성능 개선을 위해 .NET Framework의 일부 XML 클래스는 다음과 같은 특징을 가진 스트리밍 기반 모델을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-122">For better app performance, some of the XML classes in the .NET Framework support a streaming-based model with the following characteristics:</span></span>  
  
    -   <span data-ttu-id="d0b73-123">앞으로만 이동 가능한 풀 모델 구문 분석을 위한 최소 캐시(<xref:System.Xml.XmlReader>)</span><span class="sxs-lookup"><span data-stu-id="d0b73-123">Minimal caching for forward-only, pull-model parsing (<xref:System.Xml.XmlReader>).</span></span>  
  
    -   <span data-ttu-id="d0b73-124">앞으로만 이동 가능한 유효성 검사(<xref:System.Xml.XmlReader>)</span><span class="sxs-lookup"><span data-stu-id="d0b73-124">Forward-only validation (<xref:System.Xml.XmlReader>).</span></span>  
  
    -   <span data-ttu-id="d0b73-125">노드 생성이 단일 가상 노드로 최소화되지만 문서에 임의로 액세스할 수 있는 커서 스타일 탐색(<xref:System.Xml.XPath.XPathNavigator>).</span><span class="sxs-lookup"><span data-stu-id="d0b73-125">Cursor style navigation that minimizes node creation to a single virtual node while providing random access to the document (<xref:System.Xml.XPath.XPathNavigator>).</span></span>  
  
     <span data-ttu-id="d0b73-126">성능 향상을 위해 XSLT 처리가 필요할 때마다 <xref:System.Xml.XPath.XPathDocument> 클래스를 사용합니다. <xref:System.Xml.Xsl.XslCompiledTransform>는  클래스와 함께 효율적으로 사용하도록 디자인된 XPath 쿼리를 위한 최적화된 읽기 전용 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-126">For better performance whenever XSLT processing is required, you can use the <xref:System.Xml.XPath.XPathDocument> class, which is an optimized, read-only store for XPath queries designed to work efficiently with the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
-   <span data-ttu-id="d0b73-127">**ADO.NET과의 통합**</span><span class="sxs-lookup"><span data-stu-id="d0b73-127">**Integration with ADO.NET.**</span></span> <span data-ttu-id="d0b73-128">XML 클래스 및 [ADO.NET](../../../../docs/framework/data/adonet/index.md)은 관계형 데이터와 XML을 하나로 결합하도록 긴밀히 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-128">The XML classes and [ADO.NET](../../../../docs/framework/data/adonet/index.md) are tightly integrated to bring together relational data and XML.</span></span> <span data-ttu-id="d0b73-129"><xref:System.Data.DataSet> 클래스는 데이터베이스에서 파생된 데이터의 메모리 내 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-129">The <xref:System.Data.DataSet> class is an in-memory cache of data retrieved from a database.</span></span> <span data-ttu-id="d0b73-130"><xref:System.Data.DataSet> 클래스에서는 <xref:System.Xml.XmlReader> 및 <xref:System.Xml.XmlWriter> 클래스를 사용하여 XML을 읽고 쓰며, 내부 관계형 스키마 구조를 XSD(XML 스키마)로 유지할 수 있을 뿐 아니라 XML 문서의 스키마 구조를 예측할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-130">The <xref:System.Data.DataSet> class has the ability to read and write XML by using the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> classes, to persist its internal relational schema structure as XML schemas (XSD), and to infer the schema structure of an XML document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d0b73-131">단원 내용</span><span class="sxs-lookup"><span data-stu-id="d0b73-131">In This Section</span></span>  
 [<span data-ttu-id="d0b73-132">XML 처리 옵션</span><span class="sxs-lookup"><span data-stu-id="d0b73-132">XML Processing Options</span></span>](../../../../docs/standard/data/xml/xml-processing-options.md)  
 <span data-ttu-id="d0b73-133">XML 데이터를 처리하는 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-133">Discusses options for processing XML data.</span></span>  
  
 [<span data-ttu-id="d0b73-134">메모리 내 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="d0b73-134">Processing XML Data In-Memory</span></span>](../../../../docs/standard/data/xml/processing-xml-data-in-memory.md)  
 <span data-ttu-id="d0b73-135">메모리 내 XML 데이터 처리에 대한 세 가지 모델을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-135">Discusses the three models for processing XML data in-memory.</span></span> <span data-ttu-id="d0b73-136">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13), <xref:System.Xml.XmlDocument> 클래스(W3C 문서 개체 모델 기반) 및 <xref:System.Xml.XPath.XPathDocument> 클래스(XPath 데이터 모델 기반).</span><span class="sxs-lookup"><span data-stu-id="d0b73-136">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13), the <xref:System.Xml.XmlDocument> class (based on the W3C Document Object Model), and the <xref:System.Xml.XPath.XPathDocument> class (based on the XPath data model).</span></span>  
  
 [<span data-ttu-id="d0b73-137">XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="d0b73-137">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)  
 <span data-ttu-id="d0b73-138">XSLT 프로세서의 사용 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-138">Describes how to use the XSLT processor.</span></span>  
  
 [<span data-ttu-id="d0b73-139">XML SOM(스키마 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="d0b73-139">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 <span data-ttu-id="d0b73-140"><xref:System.Xml.Schema.XmlSchema> 클래스를 제공하여 XSD(XML 스키마)를 빌드 및 조작하고 스키마를 로드 및 편집하는 데 사용되는 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-140">Describes the classes used for building and manipulating XML Schemas (XSD) by providing an <xref:System.Xml.Schema.XmlSchema> class to load and edit a schema.</span></span>  
  
 [<span data-ttu-id="d0b73-141">XML과 관계형 데이터 및 ADO.NET의 통합</span><span class="sxs-lookup"><span data-stu-id="d0b73-141">XML Integration with Relational Data and ADO.NET</span></span>](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md)  
 <span data-ttu-id="d0b73-142">.NET Framework에서 <xref:System.Data.DataSet> 개체 및 <xref:System.Xml.XmlDataDocument> 개체를 사용하여 관계형 데이터와 계층형 데이터에 실시간으로 동시에 액세스할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-142">Describes how the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the <xref:System.Data.DataSet> object and the <xref:System.Xml.XmlDataDocument> object.</span></span>  
  
 [<span data-ttu-id="d0b73-143">XML 문서의 네임스페이스 관리</span><span class="sxs-lookup"><span data-stu-id="d0b73-143">Managing Namespaces in an XML Document</span></span>](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)  
 <span data-ttu-id="d0b73-144"><xref:System.Xml.XmlNamespaceManager> 클래스를 사용하여 네임스페이스 정보를 저장하고 유지 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-144">Describes how the <xref:System.Xml.XmlNamespaceManager> class is used to store and maintain namespace information.</span></span>  
  
 [<span data-ttu-id="d0b73-145">System.Xml 클래스의 형식 지원</span><span class="sxs-lookup"><span data-stu-id="d0b73-145">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)  
 <span data-ttu-id="d0b73-146">XML 데이터 형식을 CLR 형식으로 매핑하는 방법, XML 데이터 형식을 변환하는 방법 및 <xref:System.Xml> 클래스의 기능을 지원하는 기타 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-146">Describes how XML data types map to CLR types, how to convert XML data types, and other type support features in the <xref:System.Xml> classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d0b73-147">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d0b73-147">Related Sections</span></span>  
 [<span data-ttu-id="d0b73-148">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d0b73-148">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="d0b73-149">ADO.NET을 사용하여 데이터에 액세스하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-149">Provides information on how to access data using ADO.NET.</span></span>  
  
 [<span data-ttu-id="d0b73-150">보안</span><span class="sxs-lookup"><span data-stu-id="d0b73-150">Security</span></span>](../../../../docs/standard/security/index.md)  
 <span data-ttu-id="d0b73-151">.NET Framework 보안 시스템을 개략적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-151">Provides an overview of the .NET Framework security system.</span></span>  
  
 [<span data-ttu-id="d0b73-152">XML 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="d0b73-152">XML Developer Center</span></span>](http://go.microsoft.com/fwlink/?linkid=42458)  
 <span data-ttu-id="d0b73-153">XML 개발자를 위한 추가 기술 정보, 다운로드, 뉴스 그룹 및 기타 리소스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b73-153">Provides additional technical information, downloads, newsgroups, and other resources for XML developers.</span></span>
