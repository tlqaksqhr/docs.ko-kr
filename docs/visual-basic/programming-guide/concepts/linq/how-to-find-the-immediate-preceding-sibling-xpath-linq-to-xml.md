---
title: "방법: 직접 선행 형제 (XPath 및 LINQ to XML) 찾기 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6eb74dc4c106deadb92da1414e359d567fda6df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="923b0-102">방법: 직접 선행 형제 (XPath 및 LINQ to XML) 찾기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="923b0-102">How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="923b0-103">노드의 바로 이전 형제를 찾으려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="923b0-103">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="923b0-104">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]과 반대되는 XPath의 이전 형제 축에 대한 위치 조건자의 의미 차이 때문에 이 부분은 더 흥미로운 비교 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="923b0-104">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="923b0-105">예제</span><span class="sxs-lookup"><span data-stu-id="923b0-105">Example</span></span>  
 <span data-ttu-id="923b0-106">이 예제에서 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리는 <xref:System.Linq.Enumerable.Last%2A> 연산자를 사용하여 <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>에 의해 반환되는 컬렉션에서 마지막 노드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="923b0-106">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="923b0-107">이와 반대로 XPath 식은 값이 1인 조건자를 사용하여 바로 이전 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="923b0-107">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>  
  
```vb  
Dim root As XElement = _   
    <Root>  
        <Child1/>  
        <Child2/>  
        <Child3/>  
        <Child4/>  
    </Root>  
Dim child4 As XElement = root.Element("Child4")  
  
' LINQ to XML query  
Dim el1 As XElement = child4.ElementsBeforeSelf().Last()  
  
' XPath expression  
Dim el2 As XElement = _  
    DirectCast(child4.XPathEvaluate("preceding-sibling::*[1]"),  _  
    IEnumerable).Cast(Of XElement)().First()  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
```  
  
 <span data-ttu-id="923b0-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="923b0-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Child3 />  
```  
  
## <a name="see-also"></a><span data-ttu-id="923b0-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="923b0-109">See Also</span></span>  
 [<span data-ttu-id="923b0-110">LINQ to XML에 대 한 XPath 사용자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="923b0-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
