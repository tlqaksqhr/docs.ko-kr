---
title: System.Xml 클래스의 형식 지원
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb47eec7153624b1822b6393bb4a1621b1cd63db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569696"
---
# <a name="type-support-in-the-systemxml-classes"></a><span data-ttu-id="651ee-102">System.Xml 클래스의 형식 지원</span><span class="sxs-lookup"><span data-stu-id="651ee-102">Type Support in the System.Xml Classes</span></span>
<span data-ttu-id="651ee-103">.NET Framework 버전 2.0에서는 형식 지원 기능을 포함하도록 핵심 XML 클래스가 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="651ee-103">In the .NET Framework version 2.0, the core XML classes have been enhanced to include type support features.</span></span> <span data-ttu-id="651ee-104"><xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> 및 <xref:System.Xml.XPath.XPathNavigator> 클래스에는 XML 스키마 형식과 CLR(공용 언어 런타임) 형식 간의 변환 기능을 비롯한 형식 지원 기능이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="651ee-104">The <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes include type support features including the ability to convert between XML Schema types and common language runtime (CLR) types.</span></span>  
  
 <span data-ttu-id="651ee-105">.NET Framework 버전 2.0에서는 형식 지원 기능을 포함하도록 <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> 및 <xref:System.Xml.XPath.XPathNavigator> 클래스가 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="651ee-105">In the .NET Framework version 2.0, the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes have been enhanced to include type support features.</span></span>  
  
-   <span data-ttu-id="651ee-106"><xref:System.Xml.XmlReader> 및 <xref:System.Xml.XPath.XPathNavigator> 클래스는 각각 노드에서 스키마 정보를 반환하는 **SchemaInfo** 속성을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="651ee-106">The <xref:System.Xml.XmlReader> and <xref:System.Xml.XPath.XPathNavigator> classes each include a **SchemaInfo** property that returns the schema information on a node.</span></span>  
  
-   <span data-ttu-id="651ee-107">**ReadContentAs**와 **ReadElementContentAs** 및 <xref:System.Xml.XmlReader> 클래스의 메서드는 텍스트 값을 읽어온 후 단일 메서드 호출에서 CLR 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="651ee-107">The **ReadContentAs** and **ReadElementContentAs** and methods on the <xref:System.Xml.XmlReader> class read a text value and convert it to a CLR value in a single method call.</span></span>  
  
-   <span data-ttu-id="651ee-108"><xref:System.Xml.XmlWriter.WriteValue%2A> 클래스의 <xref:System.Xml.XmlWriter> 메서드는 XML을 작성할 때 CLR 형식을 XML 스키마 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="651ee-108">The <xref:System.Xml.XmlWriter.WriteValue%2A> method on the <xref:System.Xml.XmlWriter> class converts a CLR type to an XML Schema type when writing out XML.</span></span>  
  
-   <span data-ttu-id="651ee-109">**ValueAs** 및 <xref:System.Xml.XPath.XPathNavigator> 클래스의 <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> 속성은 노드 값을 반환하고 단일 메서드 호출에서 이 값을 CLR 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="651ee-109">The **ValueAs** and <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> properties on the <xref:System.Xml.XPath.XPathNavigator> class return a node value and convert it to a CLR value in a single method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="651ee-110">.NET Framework 버전 1.0에서는 XML 스키마와 CLR 형식 간에 변환하려면 <xref:System.Xml.XmlConvert> 클래스가 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="651ee-110">In the .NET Framework version 1.0 the <xref:System.Xml.XmlConvert> class was needed to convert between XML Schema and CLR types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="651ee-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="651ee-111">In This Section</span></span>  
 [<span data-ttu-id="651ee-112">CLR 형식에 XML 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="651ee-112">Mapping XML Data Types to CLR Types</span></span>](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 <span data-ttu-id="651ee-113">기본적으로 XML 데이터 형식을 CLR 형식에 매핑하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="651ee-113">Describes the default mappings of XML data types to CLR types.</span></span>  
  
 [<span data-ttu-id="651ee-114">XML 형식 지원 구현 참고 사항</span><span class="sxs-lookup"><span data-stu-id="651ee-114">XML Type Support Implementation Notes</span></span>](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 <span data-ttu-id="651ee-115">형식 지원 구현에 대해 상세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="651ee-115">Discusses some of the type support implementation details.</span></span>  
  
 [<span data-ttu-id="651ee-116">XML 데이터 형식 변환</span><span class="sxs-lookup"><span data-stu-id="651ee-116">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 <span data-ttu-id="651ee-117"><xref:System.Xml.XmlConvert> 클래스를 사용하여 XML 스키마와 CLR 형식 간에 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="651ee-117">Describes how to use the <xref:System.Xml.XmlConvert> class to convert between XML Schema and CLR types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="651ee-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="651ee-118">Related Sections</span></span>  
 [<span data-ttu-id="651ee-119">XPathNavigator를 사용하여 강력한 형식의 XML 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="651ee-119">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
