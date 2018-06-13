---
title: '방법: 특정 특성 (Visual Basic)으로 요소 찾기'
ms.date: 07/20/2015
ms.assetid: 59fb7c19-d42f-40eb-8cf8-f1d5b9658eb7
ms.openlocfilehash: ea5221553e2bb4fd624ca6b10e615c5766bfcb0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643002"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-visual-basic"></a>방법: 특정 특성 (Visual Basic)으로 요소 찾기
이 항목에서는 특정 값을 가진 특성이 포함된 요소를 찾는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 값이 "Billing"인 `Address` element that has a `Type` 특성을 찾는 방법을 보여 줍니다.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)을 사용합니다.  
  
```vb  
Dim root As XElement = XElement.Load("PurchaseOrder.xml")  
Dim address As IEnumerable(Of XElement) = _  
    From el In root.<Address> _  
    Where el.@Type = "Billing" _  
    Select el  
For Each el As XElement In address  
    Console.WriteLine(el)  
Next  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```xml  
          <Address Type="Billing">  
  <Name>Tai Yee</Name>  
  <Street>8 Oak Avenue</Street>  
  <City>Old Town</City>  
  <State>PA</State>  
  <Zip>95819</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
 사용 하 여이 예제는 [XML 자식 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), [XML 특성 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), 및 [XML Value 속성](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다. 자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스에서 일반적인 구매 주문](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md)을 사용합니다.  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim address As IEnumerable(Of XElement) = _  
            From el In root.<aw:Address> _  
            Where el.@aw:Type = "Billing" _  
            Select el  
        For Each el As XElement In address  
            Console.WriteLine(el)  
        Next  
    End Sub  
End Module  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```xml  
<aw:Address aw:Type="Billing" xmlns:aw="http://www.adventure-works.com">  
  <aw:Name>Tai Yee</aw:Name>  
  <aw:Street>8 Oak Avenue</aw:Street>  
  <aw:City>Old Town</aw:City>  
  <aw:State>PA</aw:State>  
  <aw:Zip>95819</aw:Zip>  
  <aw:Country>USA</aw:Country>  
</aw:Address>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [기본 쿼리 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [표준 쿼리 연산자 개요(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [프로젝션 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
