---
title: "샘플 XSD 파일: Customers 및 Orders2"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0c0b414-c8e1-45e4-bb67-b5e650c97130
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2894970ab279ca73178876234762a6c139950e17
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="sample-xsd-file-customers-and-orders"></a><span data-ttu-id="02f3b-102">샘플 XSD 파일: Customers 및 Orders</span><span class="sxs-lookup"><span data-stu-id="02f3b-102">Sample XSD File: Customers and Orders</span></span>
<span data-ttu-id="02f3b-103">다음 XSD 파일은 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 설명서의 다양한 예제에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="02f3b-103">The following XSD file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="02f3b-104">이 파일에는 [샘플 XML 파일: Customers 및 Orders(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md)에 대한 스키마 정의가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02f3b-104">This file contains a schema definition for the [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span> <span data-ttu-id="02f3b-105">스키마에서는 XSD의 `xs:key` 및 `xs:keyref` 기능을 사용하여 `CustomerID` 요소의 `Customer` 특성을 키로 설정하고 각 `CustomerID` 요소의 `Order` 요소와 각 `CustomerID` 요소의 `Customer` 특성 간 관계를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02f3b-105">The schema uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="02f3b-106">사용 하 여이 관계를 활용 하는 LINQ 쿼리 작성에 대 한 예제는 `Join` 절 참조 [하는 방법: 두 컬렉션 조인 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-two-collections-linq-to-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="02f3b-106">For an example of writing LINQ queries that take advantage of this relationship using the `Join` clause, see [How to: Join Two Collections (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-two-collections-linq-to-xml.md).</span></span>  
  
## <a name="customersordersxsd"></a><span data-ttu-id="02f3b-107">CustomersOrders.xsd</span><span class="sxs-lookup"><span data-stu-id="02f3b-107">CustomersOrders.xsd</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name='Root'>  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name='Customers'>  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name='Customer' type='CustomerType' minOccurs='0' maxOccurs='unbounded' />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name='Orders'>  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name='Order' type='OrderType' minOccurs='0' maxOccurs='unbounded' />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
    <xs:key name='CustomerIDKey'>  
      <xs:selector xpath='Customers/Customer'/>  
      <xs:field xpath='@CustomerID'/>  
    </xs:key>  
    <xs:keyref name='CustomerIDKeyRef' refer='CustomerIDKey'>  
      <xs:selector xpath='Orders/Order'/>  
      <xs:field xpath='CustomerID'/>  
    </xs:keyref>  
  </xs:element>  
  <xs:complexType name='CustomerType'>  
    <xs:sequence>  
      <xs:element name='CompanyName' type='xs:string'/>  
      <xs:element name='ContactName' type='xs:string'/>  
      <xs:element name='ContactTitle' type='xs:string'/>  
      <xs:element name='Phone' type='xs:string'/>  
      <xs:element name='Fax' minOccurs='0' type='xs:string'/>  
      <xs:element name='FullAddress' type='AddressType'/>  
    </xs:sequence>  
    <xs:attribute name='CustomerID' type='xs:token'/>  
  </xs:complexType>  
  <xs:complexType name='AddressType'>  
    <xs:sequence>  
      <xs:element name='Address' type='xs:string'/>  
      <xs:element name='City' type='xs:string'/>  
      <xs:element name='Region' type='xs:string'/>  
      <xs:element name='PostalCode' type='xs:string' />  
      <xs:element name='Country' type='xs:string'/>  
    </xs:sequence>  
    <xs:attribute name='CustomerID' type='xs:token'/>  
  </xs:complexType>  
  <xs:complexType name='OrderType'>  
    <xs:sequence>  
      <xs:element name='CustomerID' type='xs:token'/>  
      <xs:element name='EmployeeID' type='xs:token'/>  
      <xs:element name='OrderDate' type='xs:dateTime'/>  
      <xs:element name='RequiredDate' type='xs:dateTime'/>  
      <xs:element name='ShipInfo' type='ShipInfoType'/>  
    </xs:sequence>  
  </xs:complexType>  
  <xs:complexType name='ShipInfoType'>  
    <xs:sequence>  
      <xs:element name='ShipVia' type='xs:integer'/>  
      <xs:element name='Freight' type='xs:decimal'/>  
      <xs:element name='ShipName' type='xs:string'/>  
      <xs:element name='ShipAddress' type='xs:string'/>  
      <xs:element name='ShipCity' type='xs:string'/>  
      <xs:element name='ShipRegion' type='xs:string'/>  
      <xs:element name='ShipPostalCode' type='xs:string'/>  
      <xs:element name='ShipCountry' type='xs:string'/>  
    </xs:sequence>  
    <xs:attribute name='ShippedDate' type='xs:dateTime'/>  
  </xs:complexType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02f3b-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02f3b-108">See Also</span></span>  
 [<span data-ttu-id="02f3b-109">샘플 XML 문서(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="02f3b-109">Sample XML Documents (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
