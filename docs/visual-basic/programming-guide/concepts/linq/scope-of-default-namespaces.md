---
title: "Visual Basic에서 기본 네임 스페이스 범위 | Microsoft 문서"
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
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 138115cb1a5ec2e2c513419a32a9ebaec9c90d61
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="scope-of-default-namespaces-in-visual-basic"></a><span data-ttu-id="d76b5-102">Visual Basic에서 기본 네임 스페이스의 범위</span><span class="sxs-lookup"><span data-stu-id="d76b5-102">Scope of Default Namespaces in Visual Basic</span></span>
<span data-ttu-id="d76b5-103">XML 트리에 나타나는 기본 네임스페이스는 쿼리에 범위에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d76b5-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="d76b5-104">있으면 기본 네임 스페이스에 있는 XML을 선언는 <xref:System.Xml.Linq.XNamespace>변수는 쿼리에서 사용할 정규화 된 이름을 확인 하 고 로컬 이름과 결합.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="d76b5-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="d76b5-105">XML 트리를 쿼리할 때 가장 일반적인 문제 중 하나는 XML 트리에 기본 네임스페이스가 있으면 개발자가 경우에 따라 XML이 네임스페이스에 없는 것처럼 쿼리를 작성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d76b5-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="d76b5-106">이 항목의 첫 번째 예제 집합에서는 기본 네임스페이스의 XML이 로드되지만 적절하지 않게 쿼리되는 일반적인 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d76b5-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="d76b5-107">두 번째 예제 집합에서는 네임스페이스의 XML을 쿼리할 수 있도록 필요한 수정을 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d76b5-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d76b5-108">예제</span><span class="sxs-lookup"><span data-stu-id="d76b5-108">Example</span></span>  
 <span data-ttu-id="d76b5-109">이 예제에서는 네임스페이스에 XML을 만들고 빈 결과 집합을 반환하는 쿼리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d76b5-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d76b5-110">코드</span><span class="sxs-lookup"><span data-stu-id="d76b5-110">Code</span></span>  
  
```vb  
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
  
### <a name="comments"></a><span data-ttu-id="d76b5-111">설명</span><span class="sxs-lookup"><span data-stu-id="d76b5-111">Comments</span></span>  
 <span data-ttu-id="d76b5-112">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d76b5-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="d76b5-113">예제</span><span class="sxs-lookup"><span data-stu-id="d76b5-113">Example</span></span>  
 <span data-ttu-id="d76b5-114">이 예제에서는 네임스페이스에 XML을 만들고 제대로 코딩된 쿼리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d76b5-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="d76b5-115">위의 잘못 코딩 된 예제와 달리 Visual Basic을 사용 하는 경우의 올바른 방법은 선언 하 고 전역 기본 네임 스페이스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76b5-115">In contrast to the incorrectly coded example above, the correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="d76b5-116">이렇게 하면 기본 네임스페이스에 모든 XML 속성이 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d76b5-116">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="d76b5-117">예제가 제대로 작동하도록 하기 위해 다른 수정은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d76b5-117">No other modifications are required to the example to make it work properly.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d76b5-118">코드</span><span class="sxs-lookup"><span data-stu-id="d76b5-118">Code</span></span>  
  
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
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="d76b5-119">설명</span><span class="sxs-lookup"><span data-stu-id="d76b5-119">Comments</span></span>  
 <span data-ttu-id="d76b5-120">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d76b5-120">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="d76b5-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d76b5-121">See Also</span></span>  
 [<span data-ttu-id="d76b5-122">XML 네임 스페이스 (Visual Basic) 작업</span><span class="sxs-lookup"><span data-stu-id="d76b5-122">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
