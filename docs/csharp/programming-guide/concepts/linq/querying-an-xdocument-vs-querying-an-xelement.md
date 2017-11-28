---
title: "XDocument 쿼리와 XElement 쿼리 비교(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b315a9b298a786cbb78eb18efd4ecf3ea8e0b90c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a><span data-ttu-id="b465a-102">XDocument 쿼리와 XElement 쿼리 비교(C#)</span><span class="sxs-lookup"><span data-stu-id="b465a-102">Querying an XDocument vs. Querying an XElement (C#)</span></span>
<span data-ttu-id="b465a-103"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>를 통해 문서를 로드하는 경우에는 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>를 통해 로드하는 경우와 약간 다르게 쿼리를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-103">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="b465a-104">XDocument.Load와 XElement.Load의 비교</span><span class="sxs-lookup"><span data-stu-id="b465a-104">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="b465a-105"><xref:System.Xml.Linq.XElement>를 통해 XML 문서를 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>에 로드하면 XML 트리의 루트에 있는 <xref:System.Xml.Linq.XElement>에 로드된 문서의 루트 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-105">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="b465a-106">그러나 <xref:System.Xml.Linq.XDocument>를 통해 동일한 XML 문서를 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>에 로드하면 트리의 루트가 <xref:System.Xml.Linq.XDocument> 노드이고 로드된 문서의 루트 요소가 <xref:System.Xml.Linq.XElement>의 허용된 하나의 자식 <xref:System.Xml.Linq.XDocument> 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-106">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="b465a-107">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 축은 루트 노드와 상대적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-107">The [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="b465a-108">이 첫 번째 예제에서는 <xref:System.Xml.Linq.XElement.Load%2A>를 사용하여 XML 트리를 로드한 다음</span><span class="sxs-lookup"><span data-stu-id="b465a-108">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="b465a-109">트리 루트의 자식 요소에 대해 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-109">It then queries for the child elements of the root of the tree.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XElement.Load");  
Console.WriteLine("----");  
XElement doc = XElement.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="b465a-110">예상대로 이 예제는 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-110">As expected, this example produces the following output:</span></span>  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="b465a-111">다음 예제는 XML 트리가 <xref:System.Xml.Linq.XDocument> 대신 <xref:System.Xml.Linq.XElement>에 로드되는 점을 제외하고 위의 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-111">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="b465a-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-112">This example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="b465a-113">동일한 쿼리에서 세 자식 노드 대신 하나의 `Root` 노드를 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-113">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="b465a-114">이를 처리하는 한 가지 방법은 축 메서드에 액세스하기 전에 다음과 같이 <xref:System.Xml.Linq.XDocument.Root%2A> 속성을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-114">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Root.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="b465a-115">이 쿼리는 이제 <xref:System.Xml.Linq.XElement>에서 시작하는 트리에 대한 쿼리와 동일한 방식으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-115">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="b465a-116">예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b465a-116">The example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b465a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b465a-117">See Also</span></span>  
 [<span data-ttu-id="b465a-118">기본 쿼리(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="b465a-118">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
