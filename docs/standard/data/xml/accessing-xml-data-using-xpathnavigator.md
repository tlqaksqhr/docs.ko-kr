---
title: "XPathNavigator를 사용하여 XML 데이터 액세스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c57b46e6-5c77-408f-bc4e-67a5dcc9cc05
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 27f5bccc2ab5f229e8b726b3bff18ea7a590f5c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-xml-data-using-xpathnavigator"></a><span data-ttu-id="0b083-102">XPathNavigator를 사용하여 XML 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="0b083-102">Accessing XML Data using XPathNavigator</span></span>
<span data-ttu-id="0b083-103"><xref:System.Xml.XPath.XPathNavigator> 클래스는 <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체에서 노드를 탐색하고 XML 데이터를 추출하고 강력한 형식의 XML 데이터에 액세스하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b083-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to navigate nodes, extract XML data and access strongly typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b083-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="0b083-104">In This Section</span></span>  
 [<span data-ttu-id="0b083-105">XPathNavigator를 사용 하 여 노드 집합 탐색</span><span class="sxs-lookup"><span data-stu-id="0b083-105">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="0b083-106"><xref:System.Xml.XPath.XPathNavigator> 또는 <xref:System.Xml.XPath.XPathDocument> 개체에서 노드를 탐색하는 데 사용하는 <xref:System.Xml.XmlDocument> 클래스의 노드 집합 탐색 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b083-106">Describes the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class used to navigate nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="0b083-107">특성 및 XPathNavigator를 사용 하 여 Namespace 노드 탐색</span><span class="sxs-lookup"><span data-stu-id="0b083-107">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="0b083-108"><xref:System.Xml.XPath.XPathNavigator> 클래스의 특성 및 네임스페이스 노드 탐색 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b083-108">Describes the attribute and namespace node navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="0b083-109">XPathNavigator를 사용 하 여 XML 데이터를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b083-109">Extract XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="0b083-110"><xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체에서 XML 데이터를 추출하는 다양한 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b083-110">Describes the various methods of extracting XML data from an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="0b083-111">강력한 형식의 XPathNavigator를 사용 하 여 XML 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="0b083-111">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="0b083-112"><xref:System.Xml.XPath.XPathDocument> 클래스를 사용하여 <xref:System.Xml.XmlDocument> 또는 <xref:System.Xml.XPath.XPathNavigator> 개체에서 강력한 형식의 XML 데이터에 액세스하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b083-112">Describes accessing strongly-typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="0b083-113">사용자 정의 함수 및 변수</span><span class="sxs-lookup"><span data-stu-id="0b083-113">User Defined Functions and Variables</span></span>](../../../../docs/standard/data/xml/user-defined-functions-and-variables.md)  
 <span data-ttu-id="0b083-114">확장 함수 및 변수를 지원하는 인터페이스 <xref:System.Xml.Xsl.XsltContext> 및 <xref:System.Xml.Xsl.IXsltContextFunction>과 함께 사용자 지정 <xref:System.Xml.Xsl.IXsltContextVariable> 클래스 구현에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b083-114">Describes implementing a custom <xref:System.Xml.Xsl.XsltContext> class along with the interfaces <xref:System.Xml.Xsl.IXsltContextFunction> and <xref:System.Xml.Xsl.IXsltContextVariable> that support extension functions and variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b083-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b083-115">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="0b083-116">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="0b083-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="0b083-117">XPathDocument 및 XmlDocument를 사용 하 여 XML 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="0b083-117">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="0b083-118">XPathNavigator를 사용 하 여 일치 하는 XML 데이터 선택, 평가 및</span><span class="sxs-lookup"><span data-stu-id="0b083-118">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="0b083-119">XPathNavigator를 사용 하 여 XML 데이터 편집</span><span class="sxs-lookup"><span data-stu-id="0b083-119">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="0b083-120">XPathNavigator를 사용 하 여 스키마 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="0b083-120">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
