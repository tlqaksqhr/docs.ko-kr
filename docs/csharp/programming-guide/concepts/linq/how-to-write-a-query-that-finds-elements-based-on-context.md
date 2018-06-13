---
title: '방법: 컨텍스트에 따라 요소를 찾는 쿼리 작성(C#)'
ms.date: 07/20/2015
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
ms.openlocfilehash: 3b09be121c3e1da12614d1c09a806b09386732df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322015"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a><span data-ttu-id="83ea6-102">방법: 컨텍스트에 따라 요소를 찾는 쿼리 작성(C#)</span><span class="sxs-lookup"><span data-stu-id="83ea6-102">How to: Write a Query that Finds Elements Based on Context (C#)</span></span>
<span data-ttu-id="83ea6-103">컨텍스트에 따라 요소를 선택하는 쿼리를 작성해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ea6-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="83ea6-104">이전 또는 다음 형제 요소를 기준으로 필터링하거나,</span><span class="sxs-lookup"><span data-stu-id="83ea6-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="83ea6-105">자식 또는 상위 요소를 기준으로 필터링하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ea6-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="83ea6-106">쿼리를 작성하고 `where` 절에서 쿼리의 결과를 사용하여 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83ea6-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="83ea6-107">먼저 null에 대해 테스트하고 값을 테스트해야 하는 경우에는 `let` 절에서 쿼리를 수행한 다음 `where` 절에서 결과를 사용하는 것이 더 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="83ea6-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83ea6-108">예</span><span class="sxs-lookup"><span data-stu-id="83ea6-108">Example</span></span>  
 <span data-ttu-id="83ea6-109">다음 예제에서는 `p` 요소 바로 이전에 있는 모든 `ul` 요소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83ea6-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants("p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name.LocalName == "ul"  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="83ea6-110">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83ea6-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="83ea6-111">예</span><span class="sxs-lookup"><span data-stu-id="83ea6-111">Example</span></span>  
 <span data-ttu-id="83ea6-112">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83ea6-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="83ea6-113">자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83ea6-113">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
XNamespace ad = "http://www.adatum.com";  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants(ad + "p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name == ad.GetName("ul")  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="83ea6-114">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83ea6-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="83ea6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83ea6-115">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Parse%2A>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A>  
 <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
 <xref:System.Linq.Enumerable.FirstOrDefault%2A>  
 [<span data-ttu-id="83ea6-116">기본 쿼리(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="83ea6-116">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
