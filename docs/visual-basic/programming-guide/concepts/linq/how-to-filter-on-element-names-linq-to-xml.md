---
title: "방법: 요소 이름 (LINQ to XML)에 대 한 필터 (Visual Basic) | Microsoft 문서"
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
ms.assetid: b1437b4a-48aa-4546-834a-d6d3ab015fe1
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 07f7867b0fc5cf79ba5ce06f95b07b5c538e83d3
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-filter-on-element-names-linq-to-xml-visual-basic"></a>방법: 요소 이름 (LINQ to XML)에 대 한 필터 (Visual Basic)
반환 하는 방법 중 하나를 호출 하면 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>, 요소 이름 필터링 할 수 있습니다.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>  
  
## <a name="example"></a>예제  
 이 예제에서는 하위 요소의 컬렉션을 검색합니다. 하위 항목이 필터링되므로 컬렉션에는 지정된 이름을 가진 하위 항목만 포함됩니다.  
  
 이 예제에서는 다음 XML 문서: [샘플 XML 파일: 일반적인 구매 주문 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)합니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 이 코드의 결과는 다음과 같습니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 반환 하는 다른 방법 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>컬렉션 동일한 패턴을 따릅니다.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> 이들 메서드 시그니처는 <xref:System.Xml.Linq.XContainer.Elements%2A>및 <xref:System.Xml.Linq.XContainer.Descendants%2A>.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XContainer.Elements%2A> 비슷합니다. 다음은 메서드 시그니처가 유사한 메서드의 전체 목록입니다.  
  
-   <xref:System.Xml.Linq.XNode.Ancestors%2A></xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Descendants%2A></xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Elements%2A></xref:System.Xml.Linq.XContainer.Elements%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A></xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A></xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A></xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a>예제  
 다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다. 자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.  
  
 이 예제에서는 다음 XML 문서를 사용 하 여: [샘플 XML 파일: 일반적인 구매 주문에는 Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md)합니다.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim items As IEnumerable(Of XElement) = _  
            From el In po...<aw:ProductName> _  
            Select el  
        For Each prdName As XElement In items  
            Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
        Next  
    End Sub  
End Module  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 축 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
