---
title: "방법: Descendants 메서드 (Visual Basic)를 사용 하 여 단일 하위 항목 찾기 | Microsoft 문서"
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
ms.assetid: 0c03468c-efc8-4140-98f3-fb67acd9e8e1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7f0b2fd3a14f1401e88b4f0ca6b5feab69182770
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-visual-basic"></a><span data-ttu-id="95d41-102">방법: Descendants 메서드 (Visual Basic)를 사용 하 여 단일 하위 항목 찾기</span><span class="sxs-lookup"><span data-stu-id="95d41-102">How to: Find a Single Descendant Using the Descendants Method (Visual Basic)</span></span>
<span data-ttu-id="95d41-103">사용할 수는 <xref:System.Xml.Linq.XContainer.Descendants%2A>명명 된 요소를 신속 하 게 코드를 작성 하는 단일을 고유 하 게 찾을 축 메서드.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="95d41-103">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="95d41-104">이 기법은 지정된 이름을 가진 특정 하위 요소를 찾으려는 경우 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="95d41-104">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="95d41-105">원하는 요소를 이동 하는 코드를 작성할 수도 있지만 보다 빠르고 쉽게 사용 하 여 코드를 작성 하는 경우가 많습니다는 <xref:System.Xml.Linq.XContainer.Descendants%2A>축.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="95d41-105">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95d41-106">예제</span><span class="sxs-lookup"><span data-stu-id="95d41-106">Example</span></span>  
 <span data-ttu-id="95d41-107">사용 하 여이 예제는 <xref:System.Linq.Enumerable.First%2A>표준 쿼리 연산자.</xref:System.Linq.Enumerable.First%2A></span><span class="sxs-lookup"><span data-stu-id="95d41-107">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1>GC1 Value</GrandChild1>  
        </Child1>  
        <Child2>  
            <GrandChild2>GC2 Value</GrandChild2>  
        </Child2>  
        <Child3>  
            <GrandChild3>GC3 Value</GrandChild3>  
        </Child3>  
        <Child4>  
            <GrandChild4>GC4 Value</GrandChild4>  
        </Child4>  
    </Root>  
Dim grandChild3 As String = _  
    (From el In root...<GrandChild3> _  
    Select el).First()  
Console.WriteLine(grandChild3)  
```  
  
 <span data-ttu-id="95d41-108">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95d41-108">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="95d41-109">예제</span><span class="sxs-lookup"><span data-stu-id="95d41-109">Example</span></span>  
 <span data-ttu-id="95d41-110">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95d41-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="95d41-111">자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="95d41-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child1>  
                    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
                </aw:Child1>  
                <aw:Child2>  
                    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
                </aw:Child2>  
                <aw:Child3>  
                    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
                </aw:Child3>  
                <aw:Child4>  
                    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
                </aw:Child4>  
            </aw:Root>  
        Dim grandChild3 As String = _  
            (From el In root...<aw:GrandChild3> _  
            Select el).First()  
        Console.WriteLine(grandChild3)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="95d41-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95d41-112">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="see-also"></a><span data-ttu-id="95d41-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95d41-113">See Also</span></span>  
 [<span data-ttu-id="95d41-114">기본 쿼리 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95d41-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
