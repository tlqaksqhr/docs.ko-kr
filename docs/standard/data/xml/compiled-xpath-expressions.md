---
title: "컴파일된 XPath 식"
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
ms.assetid: e25dd95f-b64c-4d8b-a3a4-379e1aa0ad55
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f7b812d5d6f75e39e9eebcc003686ff88d009e9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="compiled-xpath-expressions"></a><span data-ttu-id="b7d75-102">컴파일된 XPath 식</span><span class="sxs-lookup"><span data-stu-id="b7d75-102">Compiled XPath Expressions</span></span>
<span data-ttu-id="b7d75-103"><xref:System.Xml.XPath.XPathExpression> 개체는 <xref:System.Xml.XPath.XPathExpression.Compile%2A> 클래스의 정적 <xref:System.Xml.XPath.XPathExpression> 메서드 또는 <xref:System.Xml.XPath.XPathNavigator.Compile%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator> 메서드 중 하나에서 반환된 컴파일된 XPath 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-103">An <xref:System.Xml.XPath.XPathExpression> object represents a compiled XPath query returned from either the static <xref:System.Xml.XPath.XPathExpression.Compile%2A> method of the <xref:System.Xml.XPath.XPathExpression> class or the <xref:System.Xml.XPath.XPathNavigator.Compile%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="the-xpathexpression-class"></a><span data-ttu-id="b7d75-104">XPathExpression 클래스</span><span class="sxs-lookup"><span data-stu-id="b7d75-104">The XPathExpression Class</span></span>  
 <span data-ttu-id="b7d75-105">같은 XPath 쿼리를 두 번 이상 사용하는 경우 <xref:System.Xml.XPath.XPathExpression> 개체가 나타내는 컴파일된 XPath 쿼리는 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-105">A compiled XPath query represented by an <xref:System.Xml.XPath.XPathExpression> object is useful if the same XPath query is being used more than once.</span></span>  
  
 <span data-ttu-id="b7d75-106">예를 들어, 매번 XPath 쿼리를 나타내는 문자열을 사용하는 대신 <xref:System.Xml.XPath.XPathNavigator.Select%2A> 메서드를 여러 번 호출할 경우 <xref:System.Xml.XPath.XPathExpression.Compile%2A> 클래스의 <xref:System.Xml.XPath.XPathExpression> 메서드 또는 <xref:System.Xml.XPath.XPathNavigator.Compile%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator> 메서드를 사용하여 <xref:System.Xml.XPath.XPathExpression> 개체에서 XPath 쿼리를 컴파일하고 캐시하면 다시 사용이 가능하며 성능도 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-106">For example, when calling the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method multiple times, instead of using a string representing the XPath query each time, use the <xref:System.Xml.XPath.XPathExpression.Compile%2A> method of the <xref:System.Xml.XPath.XPathExpression> class or the <xref:System.Xml.XPath.XPathNavigator.Compile%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class to compile and cache the XPath query in an <xref:System.Xml.XPath.XPathExpression> object for reuse and improved performance.</span></span>  
  
 <span data-ttu-id="b7d75-107">컴파일한 후에는 XPath 쿼리에서 반환되는 형식에 따라 <xref:System.Xml.XPath.XPathExpression> 개체를 다음 <xref:System.Xml.XPath.XPathNavigator> 클래스 메서드에 대한 입력으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-107">Once compiled, the <xref:System.Xml.XPath.XPathExpression> object may be used as input to the following <xref:System.Xml.XPath.XPathNavigator> class methods depending on the type returned from the XPath query.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.XPath.XPathNavigator.Matches%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 <span data-ttu-id="b7d75-108">다음 표에서는 각 W3C XPath 반환 형식, 해당 Microsoft .NET Framework 형식 및 반환 형식을 기준으로 <xref:System.Xml.XPath.XPathExpression> 개체와 함께 사용할 수 있는 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-108">The following table describes each of the W3C XPath return types, their Microsoft .NET Framework equivalencies, and what methods the <xref:System.Xml.XPath.XPathExpression> object may be used with based on its return type.</span></span>  
  
|<span data-ttu-id="b7d75-109">W3C XPath 반환 형식</span><span class="sxs-lookup"><span data-stu-id="b7d75-109">W3C XPath Return Type</span></span>|<span data-ttu-id="b7d75-110">해당 .NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="b7d75-110">.NET Framework Equivalent Type</span></span>|<span data-ttu-id="b7d75-111">설명</span><span class="sxs-lookup"><span data-stu-id="b7d75-111">Description</span></span>|<span data-ttu-id="b7d75-112">메서드</span><span class="sxs-lookup"><span data-stu-id="b7d75-112">Methods</span></span>|  
|---------------------------|------------------------------------|-----------------|-------------|  
|`Node set`|<xref:System.Xml.XPath.XPathNodeIterator>|<span data-ttu-id="b7d75-113">문서 순서에 따라 중복 없이 생성된, 정렬되지 않은 노드 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-113">An unordered collection of nodes without duplicates created in document order.</span></span>|<span data-ttu-id="b7d75-114"><xref:System.Xml.XPath.XPathNavigator.Select%2A> 또는 <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A></span><span class="sxs-lookup"><span data-stu-id="b7d75-114"><xref:System.Xml.XPath.XPathNavigator.Select%2A> or <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A></span></span>|  
|`Boolean`|<xref:System.Boolean>|<span data-ttu-id="b7d75-115">`true` 또는 `false` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-115">A `true` or `false` value.</span></span>|<span data-ttu-id="b7d75-116"><xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> 또는</span><span class="sxs-lookup"><span data-stu-id="b7d75-116"><xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> or</span></span><br /><br /> <xref:System.Xml.XPath.XPathNavigator.Matches%2A>|  
|`Number`|<xref:System.Double>|<span data-ttu-id="b7d75-117">부동 소수점 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-117">A floating-point number.</span></span>|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
|`String`|<xref:System.String>|<span data-ttu-id="b7d75-118">UCS 문자 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-118">A sequence of UCS characters.</span></span>|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
  
> [!NOTE]
>  <span data-ttu-id="b7d75-119"><xref:System.Xml.XPath.XPathNavigator.Matches%2A> 메서드에는 XPath 식을 매개 변수로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-119">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method accepts an XPath expression as its parameter.</span></span> <span data-ttu-id="b7d75-120"><xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> 메서드는 W3C XPath 반환 형식이 아닌 <xref:System.Xml.XPath.XPathNavigator> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-120">The <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> method returns an <xref:System.Xml.XPath.XPathNavigator> object, not one of the W3C XPath return types.</span></span>  
  
### <a name="the-returntype-property"></a><span data-ttu-id="b7d75-121">ReturnType 속성</span><span class="sxs-lookup"><span data-stu-id="b7d75-121">The ReturnType Property</span></span>  
 <span data-ttu-id="b7d75-122">XPath 쿼리를 <xref:System.Xml.XPath.XPathExpression> 개체로 컴파일한 후 <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> 개체의 <xref:System.Xml.XPath.XPathExpression> 속성을 사용하여 XPath 쿼리가 반환하는 대상을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-122">After an XPath query has been compiled into an <xref:System.Xml.XPath.XPathExpression> object, you can use the <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property of the <xref:System.Xml.XPath.XPathExpression> object to determine what the XPath query returns.</span></span>  
  
 <span data-ttu-id="b7d75-123"><xref:System.Xml.XPath.XPathExpression.ReturnType%2A> 속성은 W3C XPath 반환 형식을 나타내는 다음 <xref:System.Xml.XPath.XPathResultType> 열거형 값 중 하나를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-123">The <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property returns one of the following <xref:System.Xml.XPath.XPathResultType> enumeration values representing the W3C XPath return types.</span></span>  
  
-   <xref:System.Xml.XPath.XPathResultType.Any>  
  
-   <xref:System.Xml.XPath.XPathResultType.Boolean>  
  
-   <xref:System.Xml.XPath.XPathResultType.Error>  
  
-   <xref:System.Xml.XPath.XPathResultType.Navigator>  
  
-   <xref:System.Xml.XPath.XPathResultType.NodeSet>  
  
-   <xref:System.Xml.XPath.XPathResultType.Number>  
  
-   <xref:System.Xml.XPath.XPathResultType.String>  
  
 <span data-ttu-id="b7d75-124">다음 예제에서는 <xref:System.Xml.XPath.XPathExpression> 개체를 사용하여 `books.xml` 파일에서 숫자 및 노드 집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-124">The following example uses the <xref:System.Xml.XPath.XPathExpression> object to return a number and a node set from the `books.xml` file.</span></span> <span data-ttu-id="b7d75-125">각 <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> 개체의 <xref:System.Xml.XPath.XPathExpression> 속성과 <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> 및 <xref:System.Xml.XPath.XPathNavigator.Select%2A> 메서드의 결과가 콘솔에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-125">The <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property of each <xref:System.Xml.XPath.XPathExpression> object as well as the results from the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> and <xref:System.Xml.XPath.XPathNavigator.Select%2A> methods are written to the console.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Returns a number.  
Dim query1 As XPathExpression = navigator.Compile("bookstore/book/price/text()*10")  
Console.WriteLine(query1.ReturnType)  
  
Dim number As Double = CType(navigator.Evaluate(query1), Double)  
Console.WriteLine(number)  
  
' Returns a node set.  
Dim query2 As XPathExpression = navigator.Compile("bookstore/book/price")  
Console.WriteLine(query2.ReturnType)  
  
Dim nodes As XPathNodeIterator = navigator.Select(query2)  
nodes.MoveNext()  
Console.WriteLine(nodes.Current.Value)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Returns a number.  
XPathExpression query1 = navigator.Compile("bookstore/book/price/text()*10");  
Console.WriteLine(query1.ReturnType);  
  
Double number = (Double)navigator.Evaluate(query1);  
Console.WriteLine(number);  
  
// Returns a node set.  
XPathExpression query2 = navigator.Compile("bookstore/book/price");  
Console.WriteLine(query2.ReturnType);  
  
XPathNodeIterator nodes = navigator.Select(query2);  
nodes.MoveNext();  
Console.WriteLine(nodes.Current.Value);  
```  
  
 <span data-ttu-id="b7d75-126">이 예제에서는 `books.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-126">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="higher-performance-xpath-expressions"></a><span data-ttu-id="b7d75-127">XPath 식의 성능 향상</span><span class="sxs-lookup"><span data-stu-id="b7d75-127">Higher Performance XPath Expressions</span></span>  
 <span data-ttu-id="b7d75-128">성능을 향상시키려면 쿼리에 가능한 가장 구체적인 XPath 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-128">For better performance, use the most specific XPath expression possible in your queries.</span></span> <span data-ttu-id="b7d75-129">예를 들어, `book` 노드가 `bookstore` 노드의 자식 노드이고 `bookstore` 노드가 XML 문서에서 최상위 요소인 경우 XPath 식 `/bookstore/book`을 사용하면 `//book`을 사용하는 것보다 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-129">For example, if the `book` node is a child node of the `bookstore` node and the `bookstore` node is the top-most element in an XML document, using the XPath expression `/bookstore/book` is faster than using `//book`.</span></span> <span data-ttu-id="b7d75-130">`//book` XPath 식은 XML 트리에서 모든 노드를 검색하여 일치하는 노드를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-130">The `//book` XPath expression will scan every node in the XML tree to identify matching nodes.</span></span>  
  
 <span data-ttu-id="b7d75-131">또한 선택 기준이 단순한 경우 <xref:System.Xml.XPath.XPathNavigator> 클래스에서 제공하는 노드 집합 탐색 메서드를 사용하면 <xref:System.Xml.XPath.XPathNavigator> 클래스에서 제공하는 선택 메서드를 사용하는 것보다 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-131">Additionally, using the node set navigation methods supplied by the <xref:System.Xml.XPath.XPathNavigator> class may result in improved performance over the selection methods supplied by the <xref:System.Xml.XPath.XPathNavigator> class in cases where your selection criteria are simple.</span></span> <span data-ttu-id="b7d75-132">예를 들어, 현재 노드의 첫 번째 자식을 선택해야 할 경우 <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A> 메서드를 사용하는 것이 `child::*[1]` XPath 식 및 <xref:System.Xml.XPath.XPathNavigator.Select%2A> 메서드를 사용하는 것보다 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-132">For example, if you need to select the first child of the current node, it is faster to use the <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A> method than to use the `child::*[1]` XPath expression and the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method.</span></span>  
  
 <span data-ttu-id="b7d75-133">노드에 대 한 자세한 내용은 집합 탐색 메서드는 <xref:System.Xml.XPath.XPathNavigator> 클래스를 참조 하십시오. [노드 집합 탐색을 사용 하 여 XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-133">For more information about the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class, see [Node Set Navigation Using XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d75-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7d75-134">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="b7d75-135">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="b7d75-135">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="b7d75-136">XPathNavigator를 사용 하 여 XML 데이터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d75-136">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="b7d75-137">XPathNavigator를 사용 하 여 XPath 식 계산</span><span class="sxs-lookup"><span data-stu-id="b7d75-137">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [<span data-ttu-id="b7d75-138">XPathNavigator를 사용 하 여 노드 일치 시키기</span><span class="sxs-lookup"><span data-stu-id="b7d75-138">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 [<span data-ttu-id="b7d75-139">XPath 쿼리에서 인식 하는 노드 형식</span><span class="sxs-lookup"><span data-stu-id="b7d75-139">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 [<span data-ttu-id="b7d75-140">XPath 쿼리 및 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="b7d75-140">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
