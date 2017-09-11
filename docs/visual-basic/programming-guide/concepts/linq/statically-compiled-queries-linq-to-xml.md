---
title: "정적으로 컴파일된 쿼리 (LINQ to XML) (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 83d6e37a00477cedc4a5a4c520ad79ff764d5ff7
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a><span data-ttu-id="ee351-102">정적으로 컴파일된 쿼리 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee351-102">Statically Compiled Queries (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="ee351-103">이점 중 하나는 가장 중요 한 성능 LINQ to XML을 반대인 <xref:System.Xml.XmlDocument>는 LINQ to XML의에서 쿼리가 정적으로 컴파일된다는 반면 XPath 쿼리는 런타임에 해석 되어야 합니다.</xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="ee351-103">One of the most important performance benefits LINQ to XML, as opposed to <xref:System.Xml.XmlDocument>, is that queries in LINQ to XML are statically compiled, whereas XPath queries must be interpreted at run time.</span></span> <span data-ttu-id="ee351-104">이 기능은 LINQ to XML에 기본 제공되므로 이를 활용하기 위해 별도의 단계를 수행할 필요는 없습니다. 그러나 이 두 가지 기술 중 하나를 선택해야 하는 경우를 위해 그 차이를 알고 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-104">This feature is built in to LINQ to XML, so you do not have to perform extra steps to take advantage of it, but it is helpful to understand the distinction when choosing between the two technologies.</span></span> <span data-ttu-id="ee351-105">이 항목에서는 그 차이에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-105">This topic explains the difference.</span></span>  
  
## <a name="statically-compiled-queries-vs-xpath"></a><span data-ttu-id="ee351-106">정적으로 컴파일된 쿼리와 XPath</span><span class="sxs-lookup"><span data-stu-id="ee351-106">Statically Compiled Queries vs. XPath</span></span>  
 <span data-ttu-id="ee351-107">다음 예제에서는 지정된 이름을 가진 하위 요소와 지정된 값을 가진 특성이 포함된 하위 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-107">The following example shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>  
  
 <span data-ttu-id="ee351-108">다음은 이에 해당하는 XPath 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-108">The following is the equivalent XPath expression:</span></span>  
  
```  
//Address[@Type='Shipping']  
```  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 = From el In po.Descendants("Address")  
            Where el.@Type = "Shipping"  
  
For Each el In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="ee351-109">이 예제의 쿼리 식은 메서드 기반 쿼리 구문에 대한 컴파일러로 다시 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-109">The query expression in this example is re-written by the compiler to method-based query syntax.</span></span> <span data-ttu-id="ee351-110">메서드 기반 쿼리 구문으로 작성된 다음 예제는 이전 쿼리에서와 같은 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-110">The following example, which is written in method-based query syntax, produces the same results as the previous one:</span></span>  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")  
  
For Each el In list1  
    Console.WriteLine(el)  
Next   
```  
  
 <span data-ttu-id="ee351-111"><xref:System.Linq.Enumerable.Where%2A>확장 메서드는.</xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="ee351-111">The <xref:System.Linq.Enumerable.Where%2A> method is an extension method.</span></span> <span data-ttu-id="ee351-112">자세한 내용은 참조 [확장 메서드](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-112">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="ee351-113">때문에 <xref:System.Linq.Enumerable.Where%2A>확장 메서드는 위의 쿼리는 다음과 같이 작성 된 것 처럼 컴파일됩니다:</xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="ee351-113">Because <xref:System.Linq.Enumerable.Where%2A> is an extension method, the query above is compiled as though it were written as follows:</span></span>  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")  
  
For Each el In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="ee351-114">이 예제의 결과는 위의 두 예제의 결과와 정확히 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-114">This example produces exactly the same results as the previous two examples.</span></span> <span data-ttu-id="ee351-115">이를 통해 쿼리가 정적으로 연결된 메서드 호출로 효과적으로 컴파일되었음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-115">This illustrates the fact that queries are effectively compiled into statically linked method calls.</span></span> <span data-ttu-id="ee351-116">이 예제에서는 반복기의 지연된 실행 의미 체계를 결합하여 성능을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-116">This, combined with the deferred execution semantics of iterators, improves performance.</span></span> <span data-ttu-id="ee351-117">반복기의 지연 된 실행 의미 체계에 대 한 자세한 내용은 참조 [지연 된 실행과 지연 계산은 LINQ to XML (Visual Basic)에서](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-117">For more information about the deferred execution semantics of iterators, see [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee351-118">이러한 예제는 컴파일러에서 작성할 수 있는 대표적인 코드 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-118">These examples are representative of the code that the compiler might write.</span></span> <span data-ttu-id="ee351-119">실제 구현은 이러한 예제와 약간 다를 수 있으나 성능은 이러한 예제와 같거나 매우 유사할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-119">The actual implementation might differ slightly from these examples, but the performance will be the same or similar to these examples.</span></span>  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a><span data-ttu-id="ee351-120">XmlDocument를 사용하여 XPath 식 실행</span><span class="sxs-lookup"><span data-stu-id="ee351-120">Executing XPath Expressions with XmlDocument</span></span>  
 <span data-ttu-id="ee351-121">다음 예제에서는 <xref:System.Xml.XmlDocument>는 이전 예제와 동일한 결과를 얻는:</xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="ee351-121">The following example uses <xref:System.Xml.XmlDocument> to accomplish the same results as the previous examples:</span></span>  
  
```vb  
Dim reader = Xml.XmlReader.Create("PurchaseOrders.xml")  
Dim doc As New Xml.XmlDocument()  
doc.Load(reader)  
Dim nl As Xml.XmlNodeList = doc.SelectNodes(".//Address[@Type='Shipping']")  
For Each n As Xml.XmlNode In nl  
    Console.WriteLine(n.OuterXml)  
Next  
reader.Close()  
```  
  
 <span data-ttu-id="ee351-122">이 쿼리는 LINQ to XML;를 사용 하는 예제와 동일한 출력 반환 유일한 차이점은 XML을 들여쓰기로 LINQ to XML에서 처리 하는 반면 <xref:System.Xml.XmlDocument>하지 않습니다.</xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="ee351-122">This query returns the same output as the examples that use LINQ to XML; the only difference is that LINQ to XML indents the printed XML, whereas <xref:System.Xml.XmlDocument> does not.</span></span>  
  
 <span data-ttu-id="ee351-123">그러나는 <xref:System.Xml.XmlDocument>방법은 일반적으로 수행 되지 않습니다 LINQ to XML 하기 때문에 <xref:System.Xml.XmlNode.SelectNodes%2A>메서드에 다음을 수행 해야 내부적으로 호출 될 때마다:</xref:System.Xml.XmlNode.SelectNodes%2A> </xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="ee351-123">However, the <xref:System.Xml.XmlDocument> approach generally does not perform as well as LINQ to XML, because the <xref:System.Xml.XmlNode.SelectNodes%2A> method must do the following internally every time it is called:</span></span>  
  
-   <span data-ttu-id="ee351-124">XPath 식이 포함된 문자열을 구문 분석하여 문자열을 토큰으로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-124">It parses the string that contains the XPath expression, breaking the string into tokens.</span></span>  
  
-   <span data-ttu-id="ee351-125">XPath 식이 올바른지 확인하기 위해 토큰의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-125">It validates the tokens to make sure that the XPath expression is valid.</span></span>  
  
-   <span data-ttu-id="ee351-126">식을 내부 식 트리로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-126">It translates the expression into an internal expression tree.</span></span>  
  
-   <span data-ttu-id="ee351-127">노드를 반복하여 식 계산 결과를 기준으로 결과 집합에 맞는 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-127">It iterates through the nodes, appropriately selecting the nodes for the result set based on the evaluation of the expression.</span></span>  
  
 <span data-ttu-id="ee351-128">이는 이에 해당하는 LINQ to XML 쿼리에서 수행하는 작업보다 훨씬 많습니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-128">This is significantly more than the work done by the corresponding LINQ to XML query.</span></span> <span data-ttu-id="ee351-129">구체적인 성능 차이 다양 한 유형의 쿼리를 다르지만 일반적 LINQ to XML 쿼리의 더 적은 작업을 수행을 따라서 보다 성능이 우수, <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument> 를 사용 하 여 XPath 식을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee351-129">The specific performance difference varies for different types of queries, but in general LINQ to XML queries do less work, and therefore perform better, than evaluating XPath expressions using <xref:System.Xml.XmlDocument>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee351-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee351-130">See Also</span></span>  
 [<span data-ttu-id="ee351-131">성능 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee351-131">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

