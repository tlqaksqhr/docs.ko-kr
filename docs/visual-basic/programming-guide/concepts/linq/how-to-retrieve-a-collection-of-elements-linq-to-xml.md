---
title: "방법: 요소 (LINQ to XML)의 컬렉션을 검색 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2269f9de-8fb9-4666-b8a1-a4e754fa6a81
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3d8cc558191b1ad672660e0d9ada4c4653cd1a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-visual-basic"></a><span data-ttu-id="0b3b6-102">방법: 요소 (LINQ to XML)의 컬렉션을 검색 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b3b6-102">How to: Retrieve a Collection of Elements (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="0b3b6-103">이 항목에서는 <xref:System.Xml.Linq.XContainer.Elements%2A> 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b3b6-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="0b3b6-104">이 메서드는 요소의 자식 요소 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0b3b6-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b3b6-105">예제</span><span class="sxs-lookup"><span data-stu-id="0b3b6-105">Example</span></span>  
 <span data-ttu-id="0b3b6-106">이 예제에서는 `purchaseOrder` 요소의 자식 요소를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="0b3b6-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="0b3b6-107">이 예제에서는 XML 문서 [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b3b6-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim childElements As IEnumerable(Of XElement)  
childElements = _  
    From el In po.Elements() _  
    Select el  
For Each el As XElement In childElements  
    Console.WriteLine("Name: " & el.Name.ToString())  
Next  
```  
  
 <span data-ttu-id="0b3b6-108">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b3b6-108">This example produces the following output.</span></span>  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b3b6-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b3b6-109">See Also</span></span>  
 [<span data-ttu-id="0b3b6-110">LINQ to XML 축(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b3b6-110">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
