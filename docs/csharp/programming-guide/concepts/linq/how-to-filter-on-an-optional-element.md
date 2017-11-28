---
title: "방법: 선택적 요소로 필터링(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f99e2f93-fca5-403f-8a0c-770761d4905a
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dc1b5384add88db209a71ec56dc1c5edf4caecb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-filter-on-an-optional-element-c"></a><span data-ttu-id="9bb3a-102">방법: 선택적 요소로 필터링(C#)</span><span class="sxs-lookup"><span data-stu-id="9bb3a-102">How to: Filter on an Optional Element (C#)</span></span>
<span data-ttu-id="9bb3a-103">요소가 XML 문서에 있는지 확실하지 않은 경우에도 해당 요소를 기준으로 필터링하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb3a-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="9bb3a-104">특정 요소에 자식 요소가 없는 경우 이 요소를 기준으로 필터링하여 null 참조 예외를 트리거하지 않도록 검색을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb3a-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="9bb3a-105">다음 예제에서는 `Child5` 요소에 `Type` 자식 요소가 없지만 쿼리가 여전히 제대로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb3a-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bb3a-106">예제</span><span class="sxs-lookup"><span data-stu-id="9bb3a-106">Example</span></span>  
 <span data-ttu-id="9bb3a-107">이 예제에서는 <xref:System.Xml.Linq.Extensions.Elements%2A> 확장 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb3a-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
var cList =  
    from typeElement in root.Elements().Elements("Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element("Text");  
foreach(string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="9bb3a-108">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb3a-108">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="9bb3a-109">예제</span><span class="sxs-lookup"><span data-stu-id="9bb3a-109">Example</span></span>  
 <span data-ttu-id="9bb3a-110">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bb3a-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="9bb3a-111">자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb3a-111">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
XNamespace ad = "http://www.adatum.com";  
var cList =  
    from typeElement in root.Elements().Elements(ad + "Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element(ad + "Text");  
foreach (string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="9bb3a-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb3a-112">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bb3a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bb3a-113">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="9bb3a-114">기본 쿼리(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="9bb3a-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="9bb3a-115">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="9bb3a-115">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="9bb3a-116">프로젝션 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="9bb3a-116">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
