---
title: "방법: 요소 이름 필터링(LINQ to XML)(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1849fb03-f075-421f-863c-e8fb32773cdf
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 03f1be79322882e49b7cb619ff4578fda94450a7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-filter-on-element-names-linq-to-xml-c"></a><span data-ttu-id="6ffad-102">방법: 요소 이름 필터링(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="6ffad-102">How to: Filter on Element Names (LINQ to XML) (C#)</span></span>
<span data-ttu-id="6ffad-103"><xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>을 반환하는 메서드 중 하나를 호출하면 요소 이름을 기준으로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ffad-103">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ffad-104">예제</span><span class="sxs-lookup"><span data-stu-id="6ffad-104">Example</span></span>  
 <span data-ttu-id="6ffad-105">이 예제에서는 하위 요소의 컬렉션을 검색합니다. 하위 항목이 필터링되므로 컬렉션에는 지정된 이름을 가진 하위 항목만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ffad-105">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="6ffad-106">이 예제에서는 XML 문서 [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ffad-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants("ProductName")  
    select el;  
foreach(XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string) prdName);  
```  
  
 <span data-ttu-id="6ffad-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ffad-107">This code produces the following output:</span></span>  
  
```  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <span data-ttu-id="6ffad-108"><xref:System.Collections.Generic.IEnumerable%601> 컬렉션의 <xref:System.Xml.Linq.XElement>을 반환하는 다른 메서드는 같은 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6ffad-108">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="6ffad-109">이들 메서드 시그니처는 <xref:System.Xml.Linq.XContainer.Elements%2A> 및 <xref:System.Xml.Linq.XContainer.Descendants%2A>와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6ffad-109">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="6ffad-110">다음은 메서드 시그니처가 유사한 메서드의 전체 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6ffad-110">The following is the complete list of methods that have similar method signatures:</span></span>  
  
-   <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a><span data-ttu-id="6ffad-111">예제</span><span class="sxs-lookup"><span data-stu-id="6ffad-111">Example</span></span>  
 <span data-ttu-id="6ffad-112">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ffad-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="6ffad-113">자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ffad-113">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="6ffad-114">이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스에서 일반적인 구매 주문](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ffad-114">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants(aw + "ProductName")  
    select el;  
foreach (XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string)prdName);  
```  
  
 <span data-ttu-id="6ffad-115">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ffad-115">This code produces the following output:</span></span>  
  
```  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ffad-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ffad-116">See Also</span></span>  
 [<span data-ttu-id="6ffad-117">LINQ to XML 축(C#)</span><span class="sxs-lookup"><span data-stu-id="6ffad-117">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)

