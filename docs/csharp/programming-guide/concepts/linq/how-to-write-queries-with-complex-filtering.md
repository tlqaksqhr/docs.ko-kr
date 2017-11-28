---
title: "방법: 복합 필터링으로 쿼리 작성(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0d663b777b0d1b02462a6557097938831ef870b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a>방법: 복합 필터링으로 쿼리 작성(C#)
복잡한 필터를 사용하여 LINQ to XML 쿼리를 작성하려는 경우가 있습니다. 예를 들어, 특정 이름과 값을 가진 자식 요소가 있는 모든 요소를 찾으려고 할 수 있습니다. 이 항목에서는 복잡한 필터링을 사용하여 쿼리를 작성하는 예제를 제공합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `PurchaseOrder` 특성이 "Shipping"과 같고 자식 `Address` 요소가 "NY"와 같은 자식 `Type` 요소가 있는 모든 `State` 요소를 찾는 방법을 보여 줍니다. 이 예제에서는 `Where` 절에서 중첩 쿼리를 사용하며, `Any` 연산자는 컬렉션에 요소가 있는 경우 `true`를 반환합니다. 메서드 기반 쿼리 구문을 사용하는 방법에 대한 자세한 내용은 [LINQ의 쿼리 구문 및 메서드 구문](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)을 참조하세요.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)을 사용합니다.  
  
 `Any` 연산자에 대한 자세한 내용은 [수량자 작업(C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md)을 참조하세요.  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where   
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
99505  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다. 자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스에서 여러 구매 주문](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md)을 사용합니다.  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
99505  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [기본 쿼리(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [프로젝션 작업(C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)  
 [수량자 작업(C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md)
