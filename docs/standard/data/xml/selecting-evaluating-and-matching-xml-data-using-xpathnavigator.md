---
title: "XPathNavigator를 사용하여 XML 데이터 선택, 평가 및 일치시키기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46e059f8-4dc8-4185-9236-784be95228ed
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a86fb36d367342ea0c5bc4968bdd5744bd0524e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="selecting-evaluating-and-matching-xml-data-using-xpathnavigator"></a><span data-ttu-id="18eda-102">XPathNavigator를 사용하여 XML 데이터 선택, 평가 및 일치시키기</span><span class="sxs-lookup"><span data-stu-id="18eda-102">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>
<span data-ttu-id="18eda-103"><xref:System.Xml.XPath.XPathNavigator> 클래스는 XPath 쿼리를 사용하여 <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체에서 노드를 선택하고, XPath 식 결과를 계산 및 검사하고, <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체에 있는 노드가 지정된 XPath 식과 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="18eda-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to select nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath query, evaluate and examine the results of an XPath expression, and determine if a node in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object matches a given XPath expression.</span></span> <span data-ttu-id="18eda-104">다음 항목에서는 이를 포함하여 <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체에서 노드를 선택, 평가 및 일치시키는 것과 관련된 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18eda-104">These and other concepts that relate to selecting, evaluating and matching nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object are described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18eda-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="18eda-105">In This Section</span></span>  
 [<span data-ttu-id="18eda-106">XPathNavigator를 사용 하 여 XML 데이터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="18eda-106">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="18eda-107">XPath 식을 사용하여 <xref:System.Xml.XPath.XPathNavigator> 또는 <xref:System.Xml.XPath.XPathDocument> 개체의 노드 집합을 선택하는 데 사용되는 <xref:System.Xml.XmlDocument> 클래스 메서드 집합에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18eda-107">Describes the set of <xref:System.Xml.XPath.XPathNavigator> class methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span>  
  
 [<span data-ttu-id="18eda-108">XPathNavigator를 사용 하 여 XPath 식 계산</span><span class="sxs-lookup"><span data-stu-id="18eda-108">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 <span data-ttu-id="18eda-109">XPath 식을 계산하는 데 사용되는 <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator> 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18eda-109">Describes the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to evaluate an XPath expression.</span></span>  
  
 [<span data-ttu-id="18eda-110">XPathNavigator를 사용 하 여 노드 일치 시키기</span><span class="sxs-lookup"><span data-stu-id="18eda-110">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 <span data-ttu-id="18eda-111">노드와 XPath 식이 일치하는지 확인하는 데 사용되는 <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator> 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18eda-111">Describes the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to determine if a node matches an XPath expression.</span></span>  
  
 [<span data-ttu-id="18eda-112">XPath 쿼리에서 인식 하는 노드 형식</span><span class="sxs-lookup"><span data-stu-id="18eda-112">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 <span data-ttu-id="18eda-113">XPath 쿼리에서 인식되는 노드 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18eda-113">Describes the types of nodes recognized in an XPath query.</span></span>  
  
 [<span data-ttu-id="18eda-114">XPath 쿼리 및 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="18eda-114">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 <span data-ttu-id="18eda-115">XPath 쿼리에서의 네임스페이스 사용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18eda-115">Describes the use of namespaces in an XPath query.</span></span>  
  
 [<span data-ttu-id="18eda-116">컴파일된 XPath 식</span><span class="sxs-lookup"><span data-stu-id="18eda-116">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)  
 <span data-ttu-id="18eda-117">컴파일된 XPath 쿼리를 나타내는 <xref:System.Xml.XPath.XPathExpression> 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18eda-117">Describes the <xref:System.Xml.XPath.XPathExpression> class that represents a compiled XPath query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18eda-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18eda-118">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="18eda-119">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="18eda-119">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="18eda-120">XPathDocument 및 XmlDocument를 사용 하 여 XML 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="18eda-120">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="18eda-121">XPathNavigator를 사용 하 여 XML 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="18eda-121">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="18eda-122">XPathNavigator를 사용 하 여 XML 데이터 편집</span><span class="sxs-lookup"><span data-stu-id="18eda-122">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="18eda-123">XPathNavigator를 사용 하 여 스키마 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="18eda-123">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
