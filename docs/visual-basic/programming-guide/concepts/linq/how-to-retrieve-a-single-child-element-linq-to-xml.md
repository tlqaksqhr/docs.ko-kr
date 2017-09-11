---
title: "방법: 단일 자식 요소 (LINQ to XML) 검색 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 006a6afbb07ceea64b8fcc6cdab1d4fd31ae3c87
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a><span data-ttu-id="7dbc1-102">방법: 단일 자식 요소 (LINQ to XML) 검색 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dbc1-102">How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="7dbc1-103">이 항목에서는 자식 요소의 이름이 제공되는 경우 단일 자식 요소를 검색하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="7dbc1-104">자식 요소의 이름과 해당 이름을 가진 요소가 하나만 있음을 알고 있는 경우 컬렉션 대신 한 요소만 검색하는 것이 편리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="7dbc1-105"><xref:System.Xml.Linq.XContainer.Element%2A>메서드가 반환 된 첫 번째 자식 <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 지정</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Element%2A></span><span class="sxs-lookup"><span data-stu-id="7dbc1-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="7dbc1-106">Visual Basic에서 단일 자식 요소를 검색하려는 경우 일반적인 방법은 XML 속성을 사용한 다음 배열 인덱서 표기법을 사용하여 첫 번째 요소를 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dbc1-107">예제</span><span class="sxs-lookup"><span data-stu-id="7dbc1-107">Example</span></span>  
 <span data-ttu-id="7dbc1-108">다음 예제에서는 <xref:System.Xml.Linq.XContainer.Element%2A>메서드.</xref:System.Xml.Linq.XContainer.Element%2A></span><span class="sxs-lookup"><span data-stu-id="7dbc1-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="7dbc1-109">이 예제에서는 `po`라는 XML 트리를 가져와서 `Comment`라는 첫 번째 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="7dbc1-110">Visual Basic 예제에서는 배열 인덱서 표기법을 사용하여 단일 요소를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="7dbc1-111">이 예제에서는 다음 XML 문서: [샘플 XML 파일: 일반적인 구매 주문 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim e As XElement = po.<DeliveryNotes>(0)  
Console.WriteLine(e)  
```  
  
 <span data-ttu-id="7dbc1-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="7dbc1-113">예제</span><span class="sxs-lookup"><span data-stu-id="7dbc1-113">Example</span></span>  
 <span data-ttu-id="7dbc1-114">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="7dbc1-115">자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-115">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="7dbc1-116">이 예제에서는 다음 XML 문서를 사용 하 여: [샘플 XML 파일: 일반적인 구매 주문에는 Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim e As XElement = po.<aw:DeliveryNotes>(0)  
        Console.WriteLine(e)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="7dbc1-117">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7dbc1-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7dbc1-118">See Also</span></span>  
 [<span data-ttu-id="7dbc1-119">LINQ to XML 축 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dbc1-119">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)

