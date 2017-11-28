---
title: "방법: 복합 필터링으로 쿼리 작성(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0d663b777b0d1b02462a6557097938831ef870b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a><span data-ttu-id="e6db5-102">방법: 복합 필터링으로 쿼리 작성(C#)</span><span class="sxs-lookup"><span data-stu-id="e6db5-102">How to: Write Queries with Complex Filtering (C#)</span></span>
<span data-ttu-id="e6db5-103">복잡한 필터를 사용하여 LINQ to XML 쿼리를 작성하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6db5-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="e6db5-104">예를 들어, 특정 이름과 값을 가진 자식 요소가 있는 모든 요소를 찾으려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6db5-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="e6db5-105">이 항목에서는 복잡한 필터링을 사용하여 쿼리를 작성하는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e6db5-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6db5-106">예제</span><span class="sxs-lookup"><span data-stu-id="e6db5-106">Example</span></span>  
 <span data-ttu-id="e6db5-107">이 예제에서는 `PurchaseOrder` 특성이 "Shipping"과 같고 자식 `Address` 요소가 "NY"와 같은 자식 `Type` 요소가 있는 모든 `State` 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6db5-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="e6db5-108">이 예제에서는 `Where` 절에서 중첩 쿼리를 사용하며, `Any` 연산자는 컬렉션에 요소가 있는 경우 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e6db5-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="e6db5-109">메서드 기반 쿼리 구문을 사용하는 방법에 대한 자세한 내용은 [LINQ의 쿼리 구문 및 메서드 구문](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6db5-109">For information about using method-based query syntax, see [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="e6db5-110">이 예제에서는 XML 문서 [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6db5-110">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="e6db5-111">`Any` 연산자에 대한 자세한 내용은 [수량자 작업(C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6db5-111">For more information about the `Any` operator, see [Quantifier Operations (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where   
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="e6db5-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6db5-112">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="e6db5-113">예제</span><span class="sxs-lookup"><span data-stu-id="e6db5-113">Example</span></span>  
 <span data-ttu-id="e6db5-114">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6db5-114">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="e6db5-115">자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6db5-115">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="e6db5-116">이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스에서 여러 구매 주문](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6db5-116">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="e6db5-117">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6db5-117">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6db5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6db5-118">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [<span data-ttu-id="e6db5-119">기본 쿼리(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="e6db5-119">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="e6db5-120">프로젝션 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="e6db5-120">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)  
 [<span data-ttu-id="e6db5-121">수량자 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="e6db5-121">Quantifier Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md)
