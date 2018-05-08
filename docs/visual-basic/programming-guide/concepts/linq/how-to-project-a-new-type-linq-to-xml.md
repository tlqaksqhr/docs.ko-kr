---
title: '방법: (LINQ to XML) 새 형식 프로젝션 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
ms.openlocfilehash: da45c527ef9943cabf207a0b475a8a2114d5c6d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a>방법: (LINQ to XML) 새 형식 프로젝션 (Visual Basic)
이 단원의 다른 예제에서는 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601>의 `string` 및 <xref:System.Collections.Generic.IEnumerable%601>의 `int`로 결과를 반환하는 쿼리를 보여 줍니다. 이러한 결과 형식이 일반적이지만 모든 시나리오에 적합하지는 아닙니다. 대부분의 경우 다른 형식의 <xref:System.Collections.Generic.IEnumerable%601>을 반환하는 쿼리를 작성하려고 할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `Select` 절에서 개체를 인스턴스화하는 방법을 보여 줍니다. 이 코드에서는 먼저 생성자를 사용하여 새 클래스를 정의한 다음 식이 새 클래스의 새 인스턴스이도록 `Select` 문을 수정합니다.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)을 사용합니다.  
  
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
  
 사용 하 여이 예제는 `M:System.Xml.Linq.XElement.Element` 메서드 항목에 도입 된 [하는 방법: 단일 자식 요소 (LINQ to XML) 검색 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)합니다. 또한, 캐스트를 사용하여 `M:System.Xml.Linq.XElement.Element` 메서드에서 반환하는 요소의 값을 검색합니다.  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a>참고 항목  
 [프로젝션 및 변형 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
