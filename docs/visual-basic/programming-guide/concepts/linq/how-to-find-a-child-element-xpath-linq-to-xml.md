---
title: "방법: 자식 요소 (XPath 및 LINQ to XML) 찾기 (Visual Basic) | Microsoft 문서"
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
ms.assetid: adb46c98-a650-42e2-b62d-835920fe8421
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b54bc8a2b7821399857f716c35a651c24de10f3f
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-visual-basic"></a>방법: 자식 요소 (XPath 및 LINQ to XML) 찾기 (Visual Basic)
이 항목에서는 XPath 자식 요소 축과 비교는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XContainer.Element%2A>메서드.</xref:System.Xml.Linq.XContainer.Element%2A>  
  
 XPath 식은 `DeliveryNotes`입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 자식 요소 `DeliveryNotes`를 찾습니다.  
  
 이 예제에서는 다음 XML 문서: [샘플 XML 파일: 여러 구매 주문 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)합니다.  
  
```vb  
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")  
Dim po As XElement = cpo.Root.<PurchaseOrder>.FirstOrDefault  
  
'LINQ to XML query  
Dim el1 As XElement = po.<DeliveryNotes>.FirstOrDefault  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("DeliveryNotes")  
' same as "child::DeliveryNotes"  
' same as "./DeliveryNotes"  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML에 대 한 XPath 사용자 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
