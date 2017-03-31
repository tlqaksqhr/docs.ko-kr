---
title: "방법: XSD를 사용하여 유효성 검사(LINQ to XML)(C#) | Microsoft 문서"
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
ms.assetid: 6a7f83a9-2d74-4c2b-8417-0a8595879516
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c3a510c91b74df1e5d0ad26655fa33e8447ea850
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-validate-using-xsd-linq-to-xml-c"></a>방법: XSD를 사용하여 유효성 검사(LINQ to XML)(C#)
<xref:System.Xml.Schema> 네임스페이스에는 XSD(XML 스키마 정의 언어) 파일에 대해 XML 트리의 유효성을 쉽게 검사할 수 있도록 하는 확장 메서드가 포함되어 있습니다. 자세한 내용은 <xref:System.Xml.Schema.Extensions.Validate%2A> 메서드 설명서를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Xml.Schema.XmlSchemaSet>를 만든 다음 스키마 집합과 비교해서 두 <xref:System.Xml.Linq.XDocument> 개체의 유효성을 검사합니다. 문서 중 하나는 유효하고 다른 하나는 유효하지 않습니다.  
  
```csharp  
string xsdMarkup =  
    @"<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>  
       <xsd:element name='Root'>  
        <xsd:complexType>  
         <xsd:sequence>  
          <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>  
          <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>  
         </xsd:sequence>  
        </xsd:complexType>  
       </xsd:element>  
      </xsd:schema>";  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", XmlReader.Create(new StringReader(xsdMarkup)));  
  
XDocument doc1 = new XDocument(  
    new XElement("Root",  
        new XElement("Child1", "content1"),  
        new XElement("Child2", "content1")  
    )  
);  
  
XDocument doc2 = new XDocument(  
    new XElement("Root",  
        new XElement("Child1", "content1"),  
        new XElement("Child3", "content1")  
    )  
);  
  
Console.WriteLine("Validating doc1");  
bool errors = false;  
doc1.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("doc1 {0}", errors ? "did not validate" : "validated");  
  
Console.WriteLine();  
Console.WriteLine("Validating doc2");  
errors = false;  
doc2.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("doc2 {0}", errors ? "did not validate" : "validated");  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 [샘플 XML 파일: Customers 및 Orders(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md)의 XML 문서가 [샘플 XSD 파일: Customers 및 Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)의 스키마별로 유효한지 확인합니다. 소스 XML 문서를 수정합니다. 여기에서는 첫 번째 고객에 대한 `CustomerID` 특성을 변경합니다. 변경한 후에는 주문이 존재하지 않는 고객을 참조하게 되므로 XML 문서가 더 이상 유효하지 않습니다.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 고객 및 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md)을 사용합니다.  
  
 이 예제에서는 XSD 스키마로 [샘플 XSD 파일: Customers 및 Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)을 사용합니다.  
  
```csharp  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", "CustomersOrders.xsd");  
  
Console.WriteLine("Attempting to validate");  
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");  
bool errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
  
Console.WriteLine();  
// Modify the source document so that it will not validate.  
custOrdDoc.Root.Element("Orders").Element("Order").Element("CustomerID").Value = "AAAAA";  
Console.WriteLine("Attempting to validate after modification");  
errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Schema.Extensions.Validate%2A>   
 [XML 트리 만들기(C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
