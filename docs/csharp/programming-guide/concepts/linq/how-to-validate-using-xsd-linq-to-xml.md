---
title: '방법: XSD를 사용하여 유효성 검사(LINQ to XML)(C#)'
ms.date: 07/20/2015
ms.assetid: 6a7f83a9-2d74-4c2b-8417-0a8595879516
ms.openlocfilehash: 9b26481eb1e0fd103f92ed56e0e2f7c83d2ccbb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321599"
---
# <a name="how-to-validate-using-xsd-linq-to-xml-c"></a><span data-ttu-id="aec1d-102">방법: XSD를 사용하여 유효성 검사(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="aec1d-102">How to: Validate Using XSD (LINQ to XML) (C#)</span></span>
<span data-ttu-id="aec1d-103"><xref:System.Xml.Schema> 네임스페이스에는 XSD(XML 스키마 정의 언어) 파일에 대해 XML 트리의 유효성을 쉽게 검사할 수 있도록 하는 확장 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec1d-103">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XML Schema Definition Language (XSD) file.</span></span> <span data-ttu-id="aec1d-104">자세한 내용은 <xref:System.Xml.Schema.Extensions.Validate%2A> 메서드 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aec1d-104">For more information, see the <xref:System.Xml.Schema.Extensions.Validate%2A> method documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aec1d-105">예</span><span class="sxs-lookup"><span data-stu-id="aec1d-105">Example</span></span>  
 <span data-ttu-id="aec1d-106">다음 예제에서는 <xref:System.Xml.Schema.XmlSchemaSet>을 만든 다음 스키마 집합에 대해 두 <xref:System.Xml.Linq.XDocument> 개체의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="aec1d-106">The following example creates an <xref:System.Xml.Schema.XmlSchemaSet>, then validates two <xref:System.Xml.Linq.XDocument> objects against the schema set.</span></span> <span data-ttu-id="aec1d-107">문서 중 하나는 유효하고 다른 하나는 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aec1d-107">One of the documents is valid, the other is not.</span></span>  
  
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
  
 <span data-ttu-id="aec1d-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aec1d-108">This example produces the following output:</span></span>  
  
```  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a><span data-ttu-id="aec1d-109">예</span><span class="sxs-lookup"><span data-stu-id="aec1d-109">Example</span></span>  
 <span data-ttu-id="aec1d-110">다음 예제에서는 [샘플 XML 파일: Customers 및 Orders(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md)의 XML 문서가 [샘플 XSD 파일: Customers 및 Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)의 스키마별로 유효한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aec1d-110">The following example validates that the XML document from [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) is valid per the schema from [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="aec1d-111">소스 XML 문서를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="aec1d-111">It then modifies the source XML document.</span></span> <span data-ttu-id="aec1d-112">여기에서는 첫 번째 고객에 대한 `CustomerID` 특성을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="aec1d-112">It changes the `CustomerID` attribute on the first customer.</span></span> <span data-ttu-id="aec1d-113">변경한 후에는 주문이 존재하지 않는 고객을 참조하게 되므로 XML 문서가 더 이상 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aec1d-113">After the change, orders will then refer to a customer that does not exist, so the XML document will no longer validate.</span></span>  
  
 <span data-ttu-id="aec1d-114">이 예제에서는 XML 문서 [샘플 XML 파일: 고객 및 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aec1d-114">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
 <span data-ttu-id="aec1d-115">이 예제에서는 XSD 스키마로 [샘플 XSD 파일: Customers 및 Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aec1d-115">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span>  
  
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
  
 <span data-ttu-id="aec1d-116">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aec1d-116">This example produces the following output:</span></span>  
  
```  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a><span data-ttu-id="aec1d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aec1d-117">See Also</span></span>  
 <xref:System.Xml.Schema.Extensions.Validate%2A>  
 [<span data-ttu-id="aec1d-118">XML 트리 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="aec1d-118">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
