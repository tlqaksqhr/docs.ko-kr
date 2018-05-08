---
title: '방법: 복합 필터링 (Visual Basic)으로 쿼리를 작성 합니다.'
ms.date: 07/20/2015
ms.assetid: bf286ffc-7990-4b00-a4eb-ee3d70129950
ms.openlocfilehash: 500cd9cdc62252eff3addc26006c4ce815ae1b4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-queries-with-complex-filtering-visual-basic"></a>방법: 복합 필터링 (Visual Basic)으로 쿼리를 작성 합니다.
복잡한 필터를 사용하여 LINQ to XML 쿼리를 작성하려는 경우가 있습니다. 예를 들어, 특정 이름과 값을 가진 자식 요소가 있는 모든 요소를 찾으려고 할 수 있습니다. 이 항목에서는 복잡한 필터링을 사용하여 쿼리를 작성하는 예제를 제공합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `PurchaseOrder` 특성이 "Shipping"과 같고 자식 `Address` 요소가 "NY"와 같은 자식 `Type` 요소가 있는 모든 `State` 요소를 찾는 방법을 보여 줍니다. 이 예제에서는 `Where` 절에서 중첩 쿼리를 사용하며, `Any` 연산자는 컬렉션에 요소가 있는 경우 `True`를 반환합니다.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)을 사용합니다.  
  
 에 대 한 자세한 내용은 `Any` 연산자 참조 [수량자 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)합니다.  
  
```vb  
Dim root As XElement = XElement.Load("PurchaseOrders.xml")  
Dim purchaseOrders As IEnumerable(Of XElement) = _  
    From el In root.<PurchaseOrder> _  
    Where _  
        (From add In el.<Address> _  
        Where _  
             add.@Type = "Shipping" And _  
             add.<State>.Value = "NY" _  
        Select add) _  
    .Any() _  
    Select el  
For Each el As XElement In purchaseOrders  
    Console.WriteLine(el.@PurchaseOrderNumber)  
Next  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
99505  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다. 자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스에서 여러 구매 주문](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md)을 사용합니다.  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim purchaseOrders As IEnumerable(Of XElement) = _  
            From el In root.<aw:PurchaseOrder> _  
            Where _  
                (From add In el.<aw:Address> _  
                Where _  
                     add.@aw:Type = "Shipping" And _  
                     add.<aw:State>.Value = "NY" _  
                Select add) _  
            .Any() _  
            Select el  
        For Each el As XElement In purchaseOrders  
            Console.WriteLine(el.@aw:PurchaseOrderNumber)  
        Next  
    End Sub  
End Module  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
99505  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [기본 쿼리 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [XML Child 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [XML Attribute 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)  
 [XML 값 속성](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [프로젝션 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)  
 [수량자 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)
