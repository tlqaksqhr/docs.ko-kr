---
title: XPath 데이터 모델을 사용하여 XML 데이터 처리
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 536c6fce-1453-4654-9c72-bca54d47e081
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ae129d0be4afb91aedb050ff4b90aff1ce058976
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569959"
---
# <a name="process-xml-data-using-the-xpath-data-model"></a><span data-ttu-id="9a95f-102">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="9a95f-102">Process XML Data Using the XPath Data Model</span></span>
<span data-ttu-id="9a95f-103"><xref:System.Xml?displayProperty=nameWithType> 네임스페이스는 <xref:System.Xml.XmlDocument> 또는 <xref:System.Xml.XPath.XPathDocument> 클래스를 사용하여 XML 문서, 조각, 노드 또는 메모리 내 노드 집합의 프로그래밍 방식 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a95f-103">The <xref:System.Xml?displayProperty=nameWithType> namespace provides a programmatic representation of XML documents, fragments, nodes, or node-sets in-memory, using the <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> classes.</span></span>  
  
 <span data-ttu-id="9a95f-104"><xref:System.Xml.XPath.XPathDocument> 클래스는 XPath 데이터 모델을 사용하여 빠른 속도의 읽기 전용 메모리 내 XML 문서 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a95f-104">The <xref:System.Xml.XPath.XPathDocument> class provides a fast, read-only, in-memory representation of an XML document using the XPath data model.</span></span> <span data-ttu-id="9a95f-105"><xref:System.Xml.XmlDocument> 클래스는 W3C DOM(문서 개체 모델) Level 1 Core 및 DOM Level 2 Core를 구현하는 XML 문서의 편집 가능한 메모리 내 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a95f-105">The <xref:System.Xml.XmlDocument> class provides an editable in-memory representation of an XML document implementing W3C Document Object Model (DOM) Level 1 Core and Core DOM Level 2.</span></span> <span data-ttu-id="9a95f-106">두 클래스는 <xref:System.Xml.XPath.IXPathNavigable> 인터페이스를 구현하며 기본 XML 데이터를 선택, 평가 및 탐색하고 경우에 따라 편집하는 데 사용되는 <xref:System.Xml.XPath.XPathNavigator> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9a95f-106">Both classes implement the <xref:System.Xml.XPath.IXPathNavigable> interface and return an <xref:System.Xml.XPath.XPathNavigator> object used to select, evaluate, navigate, and in some cases, edit the underlying XML data.</span></span>  
  
 <span data-ttu-id="9a95f-107">다음 단원에서는 <xref:System.Xml.XPath.XPathNavigator> 클래스를 반환하는 클래스를 기반으로 이 클래스의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a95f-107">The following sections describe the functionality of the <xref:System.Xml.XPath.XPathNavigator> class based on the class that returns it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a95f-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9a95f-108">In This Section</span></span>  
 [<span data-ttu-id="9a95f-109">XPathDocument 및 XmlDocument를 사용하여 XML 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="9a95f-109">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 <span data-ttu-id="9a95f-110">읽기 전용 <xref:System.Xml.XPath.XPathDocument> 클래스 개체를 만들어 XML 문서를 읽는 방법 및 편집 가능한 <xref:System.Xml.XmlDocument> 클래스 개체를 만들어 XML 문서를 읽고 편집하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a95f-110">Describes how to create a read-only <xref:System.Xml.XPath.XPathDocument> class object to read an XML document and how to create an editable <xref:System.Xml.XmlDocument> class object to read and edit an XML document.</span></span> <span data-ttu-id="9a95f-111">또한 이 항목에서는 각 클래스에서 <xref:System.Xml.XPath.XPathNavigator> 개체를 반환하여 XML 문서를 탐색하고 편집하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a95f-111">This topic also describes how return an <xref:System.Xml.XPath.XPathNavigator> object from each class to navigate and edit an XML document.</span></span>  
  
 [<span data-ttu-id="9a95f-112">XPathNavigator를 사용하여 XML 데이터 선택, 평가 및 일치시키기</span><span class="sxs-lookup"><span data-stu-id="9a95f-112">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="9a95f-113">XPath 쿼리를 사용하여 <xref:System.Xml.XPath.XPathNavigator> 또는 <xref:System.Xml.XPath.XPathDocument> 개체에서 노드를 선택하고, XPath 식 결과를 평가 및 검사하고, XML 문서에 있는 노드가 지정된 XPath 식과 일치하는지 확인하는 <xref:System.Xml.XmlDocument> 클래스의 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a95f-113">Describes the methods of the <xref:System.Xml.XPath.XPathNavigator> class used to select nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath query, evaluate and examine the results of an XPath expression, and determine if a node in an XML document matches a given XPath expression.</span></span>  
  
 [<span data-ttu-id="9a95f-114">XPathNavigator를 사용하여 XML 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="9a95f-114">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="9a95f-115"><xref:System.Xml.XPath.XPathNavigator> 또는 <xref:System.Xml.XPath.XPathDocument> 개체에서 노드를 탐색하고, XML 데이터를 추출하고, 강력한 형식의 XML 데이터에 액세스하는 <xref:System.Xml.XmlDocument> 클래스의 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a95f-115">Describes the methods of the <xref:System.Xml.XPath.XPathNavigator> class used to navigate nodes, extract XML data and access strongly typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="9a95f-116">XPathNavigator를 사용하여 XML 데이터 편집</span><span class="sxs-lookup"><span data-stu-id="9a95f-116">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="9a95f-117"><xref:System.Xml.XPath.XPathNavigator> 개체에 포함된 XML 문서에서 노드와 값을 삽입하거나 수정 및 제거하는 <xref:System.Xml.XmlDocument> 클래스의 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a95f-117">Describes the methods of the <xref:System.Xml.XPath.XPathNavigator> class used to insert, modify and remove nodes and values from an XML document contained in an <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="9a95f-118">XPathNavigator를 사용하여 스키마 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="9a95f-118">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 <span data-ttu-id="9a95f-119"><xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체에 포함된 XML 내용의 유효성을 검사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a95f-119">Describes the ways to validate the XML content contained in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a95f-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a95f-120">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="9a95f-121">DOM 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="9a95f-121">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)
