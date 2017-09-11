---
title: "LINQ to XML 이벤트 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e2358808dfeafab1576a686563e6025f90e78954
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-events-visual-basic"></a><span data-ttu-id="438f5-102">LINQ to XML 이벤트 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="438f5-102">LINQ to XML Events (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="438f5-103">이벤트를 사용 하는 XML 트리가 변경 될 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="438f5-103"> events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="438f5-104">모든 <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 의 인스턴스에 이벤트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="438f5-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="438f5-105">그런 다음 이벤트 처리기가 수정에 대 한 이벤트 수신 <xref:System.Xml.Linq.XObject>와 해당 하위 항목의.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="438f5-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="438f5-106">예를 들어, 이벤트 처리기를 트리의 루트에 추가하고 해당 이벤트 처리기에서 트리의 모든 수정을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="438f5-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="438f5-107">에 대 한 예제 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XObject.Changing>및 <xref:System.Xml.Linq.XObject.Changed>.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing> 이벤트 참조</span><span class="sxs-lookup"><span data-stu-id="438f5-107">For examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="438f5-108">형식 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="438f5-108">Types and Events</span></span>  
 <span data-ttu-id="438f5-109">이벤트 작업을 할 때 다음 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="438f5-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="438f5-110">형식</span><span class="sxs-lookup"><span data-stu-id="438f5-110">Type</span></span>|<span data-ttu-id="438f5-111">설명</span><span class="sxs-lookup"><span data-stu-id="438f5-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="438f5-112"><xref:System.Xml.Linq.XObjectChange></xref:System.Xml.Linq.XObjectChange></span><span class="sxs-lookup"><span data-stu-id="438f5-112"><xref:System.Xml.Linq.XObjectChange></span></span>|<span data-ttu-id="438f5-113"><xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 에 대 한 이벤트가 발생할 때 이벤트 형식을 지정합니다</span><span class="sxs-lookup"><span data-stu-id="438f5-113">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="438f5-114"><xref:System.Xml.Linq.XObjectChangeEventArgs></xref:System.Xml.Linq.XObjectChangeEventArgs></span><span class="sxs-lookup"><span data-stu-id="438f5-114"><xref:System.Xml.Linq.XObjectChangeEventArgs></span></span>|<span data-ttu-id="438f5-115">에 대 한 데이터를 제공 된 <xref:System.Xml.Linq.XObject.Changing>및 <xref:System.Xml.Linq.XObject.Changed>이벤트.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></span><span class="sxs-lookup"><span data-stu-id="438f5-115">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="438f5-116">다음 이벤트는 XML 트리를 수정할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="438f5-116">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="438f5-117">Event</span><span class="sxs-lookup"><span data-stu-id="438f5-117">Event</span></span>|<span data-ttu-id="438f5-118">설명</span><span class="sxs-lookup"><span data-stu-id="438f5-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="438f5-119"><xref:System.Xml.Linq.XObject.Changing></xref:System.Xml.Linq.XObject.Changing></span><span class="sxs-lookup"><span data-stu-id="438f5-119"><xref:System.Xml.Linq.XObject.Changing></span></span>|<span data-ttu-id="438f5-120">이 바로 전에 발생 <xref:System.Xml.Linq.XObject>또는 해당 하위 항목이 변경 되기.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="438f5-120">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<span data-ttu-id="438f5-121"><xref:System.Xml.Linq.XObject.Changed></xref:System.Xml.Linq.XObject.Changed></span><span class="sxs-lookup"><span data-stu-id="438f5-121"><xref:System.Xml.Linq.XObject.Changed></span></span>|<span data-ttu-id="438f5-122">발생 경우는 <xref:System.Xml.Linq.XObject>변경 되거나 해당 하위 항목의 변경 된.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="438f5-122">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="438f5-123">예제</span><span class="sxs-lookup"><span data-stu-id="438f5-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="438f5-124">설명</span><span class="sxs-lookup"><span data-stu-id="438f5-124">Description</span></span>  
 <span data-ttu-id="438f5-125">XML 트리에 특정 집계 정보를 유지 관리하려는 경우 이벤트가 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="438f5-125">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="438f5-126">예를 들어, 청구서의 개별 품목에 대한 합계인 청구서 총계를 유지 관리하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="438f5-126">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="438f5-127">이 예제에서는 이벤트를 사용하여 복합 요소 `Items` 아래의 모든 자식 요소에 대한 총계를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="438f5-127">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="438f5-128">코드</span><span class="sxs-lookup"><span data-stu-id="438f5-128">Code</span></span>  
  
```vb  
Module Module1  
    Dim WithEvents items As XElement = Nothing  
    Dim total As XElement = Nothing  
    Dim root As XElement = _  
            <Root>  
                <Total>0</Total>  
                <Items></Items>  
            </Root>  
  
    Private Sub XObjectChanged( _  
            ByVal sender As Object, _  
            ByVal cea As XObjectChangeEventArgs) _  
            Handles items.Changed  
        Select Case cea.ObjectChange  
            Case XObjectChange.Add  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
            Case XObjectChange.Remove  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
        End Select  
        Console.WriteLine("Changed {0} {1}", _  
                            sender.GetType().ToString(), _  
                            cea.ObjectChange.ToString())  
    End Sub  
  
    Sub Main()  
        total = root.<Total>(0)  
        items = root.<Items>(0)  
        items.SetElementValue("Item1", 25)  
        items.SetElementValue("Item2", 50)  
        items.SetElementValue("Item2", 75)  
        items.SetElementValue("Item3", 133)  
        items.SetElementValue("Item1", Nothing)  
        items.SetElementValue("Item4", 100)  
        Console.WriteLine("Total:{0}", CInt(total))  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="438f5-129">설명</span><span class="sxs-lookup"><span data-stu-id="438f5-129">Comments</span></span>  
 <span data-ttu-id="438f5-130">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="438f5-130">This code produces the following output:</span></span>  
  
```  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="438f5-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="438f5-131">See Also</span></span>  
 [<span data-ttu-id="438f5-132">고급 LINQ to XML 프로그래밍 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="438f5-132">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
