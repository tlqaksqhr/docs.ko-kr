---
title: "방법: 단일 자식 요소 검색(LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ce37db9e-76fa-46eb-b4cc-e8f32d22ad90
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 722a6b6630fd08a328a26dcef4d72a8cdd817924
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-c"></a><span data-ttu-id="0e715-102">방법: 단일 자식 요소 검색(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="0e715-102">How to: Retrieve a Single Child Element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="0e715-103">이 항목에서는 자식 요소의 이름이 제공되는 경우 단일 자식 요소를 검색하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="0e715-104">자식 요소의 이름과 해당 이름을 가진 요소가 하나만 있음을 알고 있는 경우 컬렉션 대신 한 요소만 검색하는 것이 편리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="0e715-105"><xref:System.Xml.Linq.XContainer.Element%2A> 메서드는 지정된 <xref:System.Xml.Linq.XElement>을 가진 첫 번째 자식 <xref:System.Xml.Linq.XName>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="0e715-106">Visual Basic에서 단일 자식 요소를 검색하려는 경우 일반적인 방법은 XML 속성을 사용한 다음 배열 인덱서 표기법을 사용하여 첫 번째 요소를 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e715-107">예제</span><span class="sxs-lookup"><span data-stu-id="0e715-107">Example</span></span>  
 <span data-ttu-id="0e715-108">다음 예제에서는 <xref:System.Xml.Linq.XContainer.Element%2A> 메서드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="0e715-109">이 예제에서는 `po`라는 XML 트리를 가져와서 `Comment`라는 첫 번째 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="0e715-110">Visual Basic 예제에서는 배열 인덱서 표기법을 사용하여 단일 요소를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="0e715-111">이 예제에서는 XML 문서 [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
XElement e = po.Element("DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="0e715-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="0e715-113">예제</span><span class="sxs-lookup"><span data-stu-id="0e715-113">Example</span></span>  
 <span data-ttu-id="0e715-114">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="0e715-115">자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e715-115">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="0e715-116">이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스에서 일반적인 구매 주문](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement e = po.Element(aw + "DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="0e715-117">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e715-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e715-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e715-118">See Also</span></span>  
 [<span data-ttu-id="0e715-119">LINQ to XML 축(C#)</span><span class="sxs-lookup"><span data-stu-id="0e715-119">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
