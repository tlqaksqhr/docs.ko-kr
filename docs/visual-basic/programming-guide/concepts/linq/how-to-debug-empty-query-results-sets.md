---
title: "방법: 빈 쿼리 결과 집합 (Visual Basic) 디버깅 | Microsoft 문서"
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
ms.assetid: b242c90a-d2b8-4309-8a1e-e4e70736c727
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 85a0d070c415924ef116367b0202c01bef6d8ace
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-debug-empty-query-results-sets-visual-basic"></a><span data-ttu-id="ebe1d-102">방법: 빈 쿼리 결과 집합 (Visual Basic) 디버깅</span><span class="sxs-lookup"><span data-stu-id="ebe1d-102">How to: Debug Empty Query Results Sets (Visual Basic)</span></span>
<span data-ttu-id="ebe1d-103">XML 트리를 쿼리할 때 가장 일반적인 문제 중 하나는 XML 트리에 기본 네임스페이스가 있으면 개발자가 경우에 따라 XML이 네임스페이스에 없는 것처럼 쿼리를 작성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1d-103">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="ebe1d-104">이 항목의 첫 번째 예제 집합에서는 기본 네임스페이스의 XML이 로드되고 적절하지 않게 쿼리되는 일반적인 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1d-104">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, and is queried improperly.</span></span>  
  
 <span data-ttu-id="ebe1d-105">두 번째 예제 집합에서는 네임스페이스의 XML을 쿼리할 수 있도록 필요한 수정을 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1d-105">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
 <span data-ttu-id="ebe1d-106">자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1d-106">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebe1d-107">예제</span><span class="sxs-lookup"><span data-stu-id="ebe1d-107">Example</span></span>  
 <span data-ttu-id="ebe1d-108">이 예제에서는 네임스페이스에 XML을 만들고 빈 결과 집합을 반환하는 쿼리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1d-108">This example shows creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns='http://www.adventure-works.com'>  
        <Child>1</Child>  
        <Child>2</Child>  
        <Child>3</Child>  
        <AnotherChild>4</AnotherChild>  
        <AnotherChild>5</AnotherChild>  
        <AnotherChild>6</AnotherChild>  
    </Root>  
Dim c1 As IEnumerable(Of XElement) = _  
        From el In root.<Child> _  
        Select el  
Console.WriteLine("Result set follows:")  
For Each el As XElement In c1  
    Console.WriteLine(el.Value)  
Next  
Console.WriteLine("End of result set")  
```  
  
 <span data-ttu-id="ebe1d-109">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1d-109">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="ebe1d-110">예제</span><span class="sxs-lookup"><span data-stu-id="ebe1d-110">Example</span></span>  
 <span data-ttu-id="ebe1d-111">이 예제에서는 네임스페이스에 XML을 만들고 제대로 코딩된 쿼리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1d-111">This example shows creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="ebe1d-112">솔루션을 선언 하 고 전역 기본 네임 스페이스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1d-112">The solution is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="ebe1d-113">이렇게 하면 기본 네임스페이스에 모든 XML 속성이 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1d-113">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="ebe1d-114">예제가 제대로 작동하도록 하기 위해 다른 수정은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1d-114">No other modifications are required to the example to make it work properly.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ebe1d-115">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1d-115">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebe1d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebe1d-116">See Also</span></span>  
 [<span data-ttu-id="ebe1d-117">기본 쿼리 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebe1d-117">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
