---
title: "방법: (LINQ to XML) 새 형식 프로젝션 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a7cbbce130aa78a7e14ffd61a1dcd76b969e1b35
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a>방법: (LINQ to XML) 새 형식 프로젝션 (Visual Basic)
이 단원의 다른 예제에서는 결과를 반환 하는 쿼리를 보여 줍니다 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601>의 `string`, 및 <xref:System.Collections.Generic.IEnumerable%601>의 `int`.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> 이러한 결과 형식이 일반적이지만 모든 시나리오에 적합하지는 아닙니다. 많은 경우 반환 하는 쿼리를 만들 수는 <xref:System.Collections.Generic.IEnumerable%601>다른 형식의.</xref:System.Collections.Generic.IEnumerable%601>  
  
## <a name="example"></a>예제  
 이 예제에서는 `Select` 절에서 개체를 인스턴스화하는 방법을 보여 줍니다. 이 코드에서는 먼저 생성자를 사용하여 새 클래스를 정의한 다음 식이 새 클래스의 새 인스턴스이도록 `Select` 문을 수정합니다.  
  
 이 예제에서는 다음 XML 문서: [샘플 XML 파일: 일반적인 구매 주문 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)합니다.  
  
```vb  
Public Class NameQty  
    Public name As String  
    Public qty As Integer  
    Public Sub New(ByVal n As String, ByVal q As Integer)  
        name = n  
        qty = q  
    End Sub  
End Class  
  
Public Class Program  
    Shared Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
  
        Dim nqList As IEnumerable(Of NameQty) = _  
            From n In po...<Item> _  
            Select New NameQty( _  
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))  
  
        For Each n As NameQty In nqList  
            Console.WriteLine(n.name & ":" & n.qty)  
        Next  
    End Sub  
End Class  
```  
  
 사용 하 여이 예제는 `M:System.Xml.Linq.XElement.Element` 메서드 항목에 도입 된 [하는 방법: 단일 자식 요소 (LINQ to XML)를 검색 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)합니다. 또한, 캐스트를 사용하여 `M:System.Xml.Linq.XElement.Element` 메서드에서 반환하는 요소의 값을 검색합니다.  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a>참고 항목  
 [프로젝션 및 변환 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
