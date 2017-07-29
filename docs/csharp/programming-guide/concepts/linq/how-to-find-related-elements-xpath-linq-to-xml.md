---
title: "방법: 관련 요소 찾기(XPath 및 LINQ to XML)(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 41b386ee-562d-4841-bd6b-e44a7eb69f26
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3cc73ab69adb66fd1158637a8a3c67008d8e8663
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-c"></a>방법: 관련 요소 찾기(XPath 및 LINQ to XML)(C#)
이 항목에서는 다른 요소의 값에 의해 참조되는 특성을 기준으로 선택하여 요소를 가져오는 방법을 비교합니다.  
  
 XPath 식은 다음과 같습니다.  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a>예제  
 이 예제에서는 12번째 `Order` 요소를 찾은 다음 해당 주문의 고객을 찾습니다.  
  
 .Net에서 목록의 인덱싱은 0부터 시작하고 XPath 조건자에서 노드 컬렉션의 인덱싱은 1부터 시작합니다. 이 예제에서는 이 차이를 반영합니다.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 고객 및 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md)을 사용합니다.  
  
```csharp  
XDocument co = XDocument.Load("CustomersOrders.xml");  
  
// LINQ to XML query  
XElement customer1 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .ToList()[11]  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// An alternate way to write the query that avoids creation  
// of a System.Collections.Generic.List:  
XElement customer2 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .Skip(11).First()  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// XPath expression  
XElement customer3 = co.XPathSelectElement(  
  ".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]");  
  
if (customer1 == customer2 && customer1 == customer3)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(customer1);  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Results are identical  
<Customer CustomerID="HUNGC">  
  <CompanyName>Hungry Coyote Import Store</CompanyName>  
  <ContactName>Yoshi Latimer</ContactName>  
  <ContactTitle>Sales Representative</ContactTitle>  
  <Phone>(503) 555-6874</Phone>  
  <Fax>(503) 555-2376</Fax>  
  <FullAddress>  
    <Address>City Center Plaza 516 Main St.</Address>  
    <City>Elgin</City>  
    <Region>OR</Region>  
    <PostalCode>97827</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
</Customer>  
```  
  
## <a name="see-also"></a>참고 항목  
 [XPath 사용자를 위한 LINQ to XML(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

