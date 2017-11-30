---
title: "방법: XSD (LINQ to XML)를 사용 하 여 유효성 검사 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0fe88d4-4e77-49e7-90de-8953feeccc21
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53b4f96e4fe31588c948d8e860be2c3bd3fa372a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-using-xsd-linq-to-xml-visual-basic"></a><span data-ttu-id="b5c41-102">방법: XSD (LINQ to XML)를 사용 하 여 유효성 검사 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5c41-102">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="b5c41-103"><xref:System.Xml.Schema> 네임스페이스에는 XSD(XML 스키마 정의 언어) 파일에 대해 XML 트리의 유효성을 쉽게 검사할 수 있도록 하는 확장 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5c41-103">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XML Schema Definition Language (XSD) file.</span></span> <span data-ttu-id="b5c41-104">자세한 내용은 <xref:System.Xml.Schema.Extensions.Validate%2A> 메서드 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5c41-104">For more information, see the <xref:System.Xml.Schema.Extensions.Validate%2A> method documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5c41-105">예제</span><span class="sxs-lookup"><span data-stu-id="b5c41-105">Example</span></span>  
 <span data-ttu-id="b5c41-106">다음 예제에서는 <xref:System.Xml.Schema.XmlSchemaSet>을 만든 다음 스키마 집합에 대해 두 <xref:System.Xml.Linq.XDocument> 개체의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c41-106">The following example creates an <xref:System.Xml.Schema.XmlSchemaSet>, then validates two <xref:System.Xml.Linq.XDocument> objects against the schema set.</span></span> <span data-ttu-id="b5c41-107">문서 중 하나는 유효하고 다른 하나는 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5c41-107">One of the documents is valid, the other is not.</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim xsdMarkup As XElement = _  
        <xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>  
            <xsd:element name='Root'>  
                <xsd:complexType>  
                    <xsd:sequence>  
                        <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>  
                        <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>  
                    </xsd:sequence>  
                </xsd:complexType>  
            </xsd:element>  
        </xsd:schema>  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", xsdMarkup.CreateReader)  
  
    Dim doc1 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child2>content1</Child2>  
        </Root>  
  
    Dim doc2 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child3>content1</Child3>  
        </Root>  
  
    Console.WriteLine("Validating doc1")  
    errors = False  
    doc1.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc1 {0}", IIf(errors = True, "did not validate", "validated"))  
  
    Console.WriteLine()  
    Console.WriteLine("Validating doc2")  
    errors = False  
    doc2.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc2 {0}", IIf(errors = True, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="b5c41-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c41-108">This example produces the following output:</span></span>  
  
```  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a><span data-ttu-id="b5c41-109">예제</span><span class="sxs-lookup"><span data-stu-id="b5c41-109">Example</span></span>  
 <span data-ttu-id="b5c41-110">다음 예제에서는 [샘플 XML 파일: Customers 및 Orders(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md)의 XML 문서가 [샘플 XSD 파일: Customers 및 Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md)의 스키마별로 유효한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c41-110">The following example validates that the XML document from [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) is valid per the schema from [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span> <span data-ttu-id="b5c41-111">소스 XML 문서를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c41-111">It then modifies the source XML document.</span></span> <span data-ttu-id="b5c41-112">여기에서는 첫 번째 고객에 대한 `CustomerID` 특성을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c41-112">It changes the `CustomerID` attribute on the first customer.</span></span> <span data-ttu-id="b5c41-113">변경한 후에는 주문이 존재하지 않는 고객을 참조하게 되므로 XML 문서가 더 이상 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5c41-113">After the change, orders will then refer to a customer that does not exist, so the XML document will no longer validate.</span></span>  
  
 <span data-ttu-id="b5c41-114">이 예제에서는 XML 문서 [샘플 XML 파일: 고객 및 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c41-114">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="b5c41-115">이 예제에서는 XSD 스키마로 [샘플 XSD 파일: Customers 및 Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c41-115">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", "CustomersOrders.xsd")  
  
    Console.WriteLine("Attempting to validate")  
    Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
  
    Console.WriteLine()  
    ' Modify the source document so that it will not validate.  
    custOrdDoc.<Root>.<Orders>.<Order>.<CustomerID>(0).Value = "AAAAA"  
    Console.WriteLine("Attempting to validate after modification")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="b5c41-116">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c41-116">This example produces the following output:</span></span>  
  
```  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5c41-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5c41-117">See Also</span></span>  
 <xref:System.Xml.Schema.Extensions.Validate%2A>  
 [<span data-ttu-id="b5c41-118">XML 트리 만들기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5c41-118">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
