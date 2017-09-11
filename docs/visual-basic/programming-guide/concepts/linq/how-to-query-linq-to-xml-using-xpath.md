---
title: "방법: LINQ to XML XPath (Visual Basic)를 사용 하 여 쿼리 | Microsoft 문서"
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
ms.assetid: e1f69a20-1efa-452d-9089-c472fa84b3d5
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 586182367ea26539384ea630dde301fe447915b8
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-query-linq-to-xml-using-xpath-visual-basic"></a><span data-ttu-id="bfb75-102">방법: LINQ to XML XPath (Visual Basic)를 사용 하 여 쿼리</span><span class="sxs-lookup"><span data-stu-id="bfb75-102">How to: Query LINQ to XML Using XPath (Visual Basic)</span></span>
<span data-ttu-id="bfb75-103">이 항목에서는 XPath를 사용하여 XML 트리를 쿼리할 수 있도록 하는 확장명 메서드에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb75-103">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="bfb75-104">이러한 확장 메서드를 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</xref:System.Xml.XPath.Extensions?displayProperty=fullName> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfb75-104">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="bfb75-105">레거시 코드의 광범위한 사용과 같이 XPath를 사용하여 쿼리할 매우 구체적인 이유가 없는 한 LINQ to XML과 함께 XPath를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb75-105">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="bfb75-106">XPath 쿼리의 성능은 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리의 성능보다 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb75-106">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfb75-107">예제</span><span class="sxs-lookup"><span data-stu-id="bfb75-107">Example</span></span>  
 <span data-ttu-id="bfb75-108">다음 예제에서는 작은 XML 트리를 만들고 사용 하 여 <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>요소 집합을 선택 합니다.</xref:System.Xml.XPath.Extensions.XPathSelectElements%2A></span><span class="sxs-lookup"><span data-stu-id="bfb75-108">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child1>2</Child1>  
        <Child1>3</Child1>  
        <Child2>4</Child2>  
        <Child2>5</Child2>  
        <Child2>6</Child2>  
    </Root>  
  
Dim list As IEnumerable(Of XElement) = root.XPathSelectElements("./Child2")  
For Each el As XElement In list  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="bfb75-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb75-109">This example produces the following output:</span></span>  
  
```  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfb75-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfb75-110">See Also</span></span>  
 [<span data-ttu-id="bfb75-111">고급 쿼리 기술 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfb75-111">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)

