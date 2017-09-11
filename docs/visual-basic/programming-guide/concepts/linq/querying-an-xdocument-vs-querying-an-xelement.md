---
title: "XDocument 쿼리와 (Visual Basic) XElement 쿼리 비교 | Microsoft 문서"
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
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 93f0f7f50ad305540a6afef2374d4b948de48705
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a><span data-ttu-id="c589d-102">XDocument 쿼리와 (Visual Basic) XElement 쿼리 비교</span><span class="sxs-lookup"><span data-stu-id="c589d-102">Querying an XDocument vs. Querying an XElement (Visual Basic)</span></span>
<span data-ttu-id="c589d-103"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> 통해 로드 하는 경우 보다 약간 다르게 쿼리를 작성 해야 한다는 것을 알 수 있습니다</xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> 통해 문서를 로드 하는 경우</span><span class="sxs-lookup"><span data-stu-id="c589d-103">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="c589d-104">XDocument.Load와 XElement.Load의 비교</span><span class="sxs-lookup"><span data-stu-id="c589d-104">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="c589d-105">XML 문서를 로드할 때는 <xref:System.Xml.Linq.XElement>통해 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement>트리 XML의 루트에 로드 된 문서의 루트 요소를 포함 합니다.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c589d-105">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="c589d-106">그러나 로드 하면 동일한 XML 문서에 <xref:System.Xml.Linq.XDocument> <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>는 트리의 루트는 <xref:System.Xml.Linq.XDocument>노드와 로드 된 문서의 루트 요소는 허용 되는 자식 <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> 의 노드</xref:System.Xml.Linq.XElement> 는 하나</xref:System.Xml.Linq.XDocument> 는</xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> ,</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="c589d-106">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="c589d-107">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 축은 루트 노드와 상대적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c589d-107">The [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="c589d-108"><xref:System.Xml.Linq.XElement.Load%2A>.</xref:System.Xml.Linq.XElement.Load%2A> 를 사용 하 여 XML 트리를 로드 하는 첫 번째 예제</span><span class="sxs-lookup"><span data-stu-id="c589d-108">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="c589d-109">트리 루트의 자식 요소에 대해 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="c589d-109">It then queries for the child elements of the root of the tree.</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XElement.Load")  
Console.WriteLine("----")  
Dim doc As XElement = XElement.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="c589d-110">예상대로 이 예제는 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="c589d-110">As expected, this example produces the following output:</span></span>  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="c589d-111">다음 예제는 위와 <xref:System.Xml.Linq.XDocument> <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 대신</xref:System.Xml.Linq.XDocument> 에 XML 트리에 로드 되는 예외와 동일</span><span class="sxs-lookup"><span data-stu-id="c589d-111">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="c589d-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c589d-112">This example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="c589d-113">동일한 쿼리에서 세 자식 노드 대신 하나의 `Root` 노드를 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="c589d-113">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="c589d-114">이 처리 하는 접근 방식을 사용 하는 것은 <xref:System.Xml.Linq.XDocument.Root%2A>다음과 같이 축 메서드에 액세스 하기 전에 속성:</xref:System.Xml.Linq.XDocument.Root%2A></span><span class="sxs-lookup"><span data-stu-id="c589d-114">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Root.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="c589d-115">이 쿼리는 이제 동일한 수행 방식으로의 쿼리 트리를 기반으로 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c589d-115">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="c589d-116">예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c589d-116">The example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c589d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c589d-117">See Also</span></span>  
 [<span data-ttu-id="c589d-118">기본 쿼리 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c589d-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
