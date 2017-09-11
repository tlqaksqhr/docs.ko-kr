---
title: "방법: 컨텍스트 (Visual Basic)를 기반으로 하는 요소를 찾는 쿼리를 작성 합니다. | Microsoft 문서"
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
ms.assetid: 0b085290-ddc1-4126-aaa0-e4c95a3d9a09
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fd497c4d63c59eed1873f77f474bfb76eb0194c4
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-visual-basic"></a><span data-ttu-id="7176c-102">방법: 컨텍스트 (Visual Basic)를 기반으로 하는 요소를 찾는 쿼리를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7176c-102">How to: Write a Query that Finds Elements Based on Context (Visual Basic)</span></span>
<span data-ttu-id="7176c-103">컨텍스트에 따라 요소를 선택하는 쿼리를 작성해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7176c-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="7176c-104">이전 또는 다음 형제 요소를 기준으로 필터링하거나,</span><span class="sxs-lookup"><span data-stu-id="7176c-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="7176c-105">자식 또는 상위 요소를 기준으로 필터링하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7176c-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="7176c-106">쿼리를 작성하고 `where` 절에서 쿼리의 결과를 사용하여 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7176c-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="7176c-107">먼저 null에 대해 테스트하고 값을 테스트해야 하는 경우에는 `let` 절에서 쿼리를 수행한 다음 `where` 절에서 결과를 사용하는 것이 더 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="7176c-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7176c-108">예제</span><span class="sxs-lookup"><span data-stu-id="7176c-108">Example</span></span>  
 <span data-ttu-id="7176c-109">다음 예제에서는 `p` 요소 바로 이전에 있는 모든 `ul` 요소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7176c-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```vb  
Dim doc As XElement = _  
    <Root>  
        <p id='1'/>  
        <ul>abc</ul>  
        <Child>  
            <p id='2'/>  
            <notul/>  
            <p id='3'/>  
            <ul>def</ul>  
            <p id='4'/>  
        </Child>  
        <Child>  
            <p id='5'/>  
            <notul/>  
            <p id='6'/>  
            <ul>abc</ul>  
            <p id='7'/>  
        </Child>  
    </Root>  
  
Dim items As IEnumerable(Of XElement) = _  
    From e In doc...<p> _  
    Let z = e.ElementsAfterSelf().FirstOrDefault() _  
    Where z IsNot Nothing AndAlso z.Name.LocalName = "ul" _  
    Select e  
  
For Each e As XElement In items  
    Console.WriteLine("id = {0}", e.@<id>)  
Next  
  
```  
  
 <span data-ttu-id="7176c-110">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7176c-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="7176c-111">예제</span><span class="sxs-lookup"><span data-stu-id="7176c-111">Example</span></span>  
 <span data-ttu-id="7176c-112">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7176c-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="7176c-113">자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7176c-113">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim doc As XElement = _  
            <Root>  
                <p id='1'/>  
                <ul>abc</ul>  
                <Child>  
                    <p id='2'/>  
                    <notul/>  
                    <p id='3'/>  
                    <ul>def</ul>  
                    <p id='4'/>  
                </Child>  
                <Child>  
                    <p id='5'/>  
                    <notul/>  
                    <p id='6'/>  
                    <ul>abc</ul>  
                    <p id='7'/>  
                </Child>  
            </Root>  
  
        Dim items As IEnumerable(Of XElement) = _  
            From e In doc...<p> _  
            Let z = e.ElementsAfterSelf().FirstOrDefault() _  
            Where z IsNot Nothing AndAlso z.Name = GetXmlNamespace().GetName("ul") _  
            Select e  
  
        For Each e As XElement In items  
            Console.WriteLine("id = {0}", e.@<id>)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="7176c-114">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7176c-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="7176c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7176c-115">See Also</span></span>  
 <span data-ttu-id="7176c-116"><xref:System.Xml.Linq.XElement.Parse%2A></xref:System.Xml.Linq.XElement.Parse%2A></span><span class="sxs-lookup"><span data-stu-id="7176c-116"><xref:System.Xml.Linq.XElement.Parse%2A></span></span>   
 <span data-ttu-id="7176c-117"><xref:System.Xml.Linq.XContainer.Descendants%2A></xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="7176c-117"><xref:System.Xml.Linq.XContainer.Descendants%2A></span></span>   
 <span data-ttu-id="7176c-118"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="7176c-118"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span></span>   
 <span data-ttu-id="7176c-119"><xref:System.Linq.Enumerable.FirstOrDefault%2A></xref:System.Linq.Enumerable.FirstOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="7176c-119"><xref:System.Linq.Enumerable.FirstOrDefault%2A></span></span>   
<span data-ttu-id="7176c-120"> [기본 쿼리 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="7176c-120"> [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)</span></span>
