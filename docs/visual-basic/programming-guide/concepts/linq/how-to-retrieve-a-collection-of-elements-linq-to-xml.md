---
title: "방법: 요소 (LINQ to XML)의 컬렉션을 검색 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 2269f9de-8fb9-4666-b8a1-a4e754fa6a81
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bfe4450d268125f021795dfb61885f4c2cb81151
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-visual-basic"></a>방법: 요소 (LINQ to XML)의 컬렉션을 검색 (Visual Basic)
이 항목에서 설명 된 <xref:System.Xml.Linq.XContainer.Elements%2A>메서드.</xref:System.Xml.Linq.XContainer.Elements%2A> 이 메서드는 요소의 자식 요소 컬렉션을 검색합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `purchaseOrder` 요소의 자식 요소를 반복합니다.  
  
 이 예제에서는 다음 XML 문서: [샘플 XML 파일: 일반적인 구매 주문 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)합니다.  
  
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
  
 이 예제의 결과는 다음과 같습니다.  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 축 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
