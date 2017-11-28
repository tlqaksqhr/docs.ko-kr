---
title: "방법: XPath를 사용하여 LINQ to XML 쿼리(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1cb47b5b4b85536feeb5006fe6dd31580ca651b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a><span data-ttu-id="4ad74-102">방법: XPath를 사용하여 LINQ to XML 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="4ad74-102">How to: Query LINQ to XML Using XPath (C#)</span></span>
<span data-ttu-id="4ad74-103">이 항목에서는 XPath를 사용하여 XML 트리를 쿼리할 수 있도록 하는 확장명 메서드에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad74-103">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="4ad74-104">이러한 확장 메서드 사용에 대한 자세한 내용은 <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ad74-104">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="4ad74-105">레거시 코드의 광범위한 사용과 같이 XPath를 사용하여 쿼리할 매우 구체적인 이유가 없는 한 LINQ to XML과 함께 XPath를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad74-105">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="4ad74-106">XPath 쿼리의 성능은 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리의 성능보다 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad74-106">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ad74-107">예제</span><span class="sxs-lookup"><span data-stu-id="4ad74-107">Example</span></span>  
 <span data-ttu-id="4ad74-108">다음 예제에서는 작은 XML 트리를 만들고 <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>를 사용하여 요소 집합을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad74-108">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child1", 2),  
    new XElement("Child1", 3),  
    new XElement("Child2", 4),  
    new XElement("Child2", 5),  
    new XElement("Child2", 6)  
);  
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");  
foreach (XElement el in list)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="4ad74-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad74-109">This example produces the following output:</span></span>  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ad74-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ad74-110">See Also</span></span>  
 [<span data-ttu-id="4ad74-111">고급 쿼리 기술(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="4ad74-111">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
