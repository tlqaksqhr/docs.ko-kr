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
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2b7756845f155c4683015d54b41f2ecc09b29333
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-events-visual-basic"></a>LINQ to XML 이벤트 (Visual Basic)
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]이벤트를 사용 하는 XML 트리가 변경 될 때 알림을 받을 수 있습니다.  
  
 모든 <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 의 인스턴스에 이벤트를 추가할 수 있습니다. 그런 다음 이벤트 처리기가 수정에 대 한 이벤트 수신 <xref:System.Xml.Linq.XObject>와 해당 하위 항목의.</xref:System.Xml.Linq.XObject> 예를 들어, 이벤트 처리기를 트리의 루트에 추가하고 해당 이벤트 처리기에서 트리의 모든 수정을 처리할 수 있습니다.  
  
 에 대 한 예제 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XObject.Changing>및 <xref:System.Xml.Linq.XObject.Changed>.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing> 이벤트 참조  
  
## <a name="types-and-events"></a>형식 및 이벤트  
 이벤트 작업을 할 때 다음 형식을 사용할 수 있습니다.  
  
|형식|설명|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange></xref:System.Xml.Linq.XObjectChange>|<xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 에 대 한 이벤트가 발생할 때 이벤트 형식을 지정합니다|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs></xref:System.Xml.Linq.XObjectChangeEventArgs>|에 대 한 데이터를 제공 된 <xref:System.Xml.Linq.XObject.Changing>및 <xref:System.Xml.Linq.XObject.Changed>이벤트.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing>|  
  
 다음 이벤트는 XML 트리를 수정할 때 발생합니다.  
  
|Event|설명|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing></xref:System.Xml.Linq.XObject.Changing>|이 바로 전에 발생 <xref:System.Xml.Linq.XObject>또는 해당 하위 항목이 변경 되기.</xref:System.Xml.Linq.XObject>|  
|<xref:System.Xml.Linq.XObject.Changed></xref:System.Xml.Linq.XObject.Changed>|발생 경우는 <xref:System.Xml.Linq.XObject>변경 되거나 해당 하위 항목의 변경 된.</xref:System.Xml.Linq.XObject>|  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 XML 트리에 특정 집계 정보를 유지 관리하려는 경우 이벤트가 유용합니다. 예를 들어, 청구서의 개별 품목에 대한 합계인 청구서 총계를 유지 관리하려고 할 수 있습니다. 이 예제에서는 이벤트를 사용하여 복합 요소 `Items` 아래의 모든 자식 요소에 대한 총계를 유지 관리합니다.  
  
### <a name="code"></a>코드  
  
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
  
### <a name="comments"></a>설명  
 이 코드의 결과는 다음과 같습니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [고급 LINQ to XML 프로그래밍 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
