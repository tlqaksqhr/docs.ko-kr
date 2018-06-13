---
title: '방법: XML 요소 및 XML 특성 이름 한정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
ms.openlocfilehash: 95b99bb093282352b6f8e2b9f04cba773e64259d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585716"
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="23178-102">방법: XML 요소 및 XML 특성 이름 한정</span><span class="sxs-lookup"><span data-stu-id="23178-102">How to: Qualify XML Element and XML Attribute Names</span></span>
[<span data-ttu-id="23178-103">코드 예제</span><span class="sxs-lookup"><span data-stu-id="23178-103">Code Example</span></span>](#cpconworkingwithxmlnamespacesanchor1)  
  
 <span data-ttu-id="23178-104"><xref:System.Xml.Serialization.XmlSerializerNamespaces> 클래스의 인스턴스에 의해 포함된 XML 네임스페이스는 "Namespaces in XML"이라는 World Wide Web 컨소시엄(www.w3.org) 사양을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23178-104">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (www.w3.org) specification called "Namespaces in XML."</span></span>  
  
 <span data-ttu-id="23178-105">XML 네임스페이스는 XML 문서에서 XML 요소 및 XML 특성의 이름을 정규화하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23178-105">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="23178-106">정규화된 이름은 콜론으로 구분된 접두사와 로컬 이름으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="23178-106">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="23178-107">접두사는 자리 표시자로만 사용되며 네임스페이스를 지정하는 URI에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="23178-107">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="23178-108">보편적으로 관리되는 URI 네임스페이스와 로컬 이름을 조합하면 보편적으로 고유한 이름이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="23178-108">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>  
  
 <span data-ttu-id="23178-109">`XmlSerializerNamespaces`의 인스턴스를 만들고 네임스페이스 쌍을 개체에 추가하면 XML 문서에 사용되는 접두사를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23178-109">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>  
  
### <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="23178-110">XML 문서에서 정규화된 이름을 만들려면</span><span class="sxs-lookup"><span data-stu-id="23178-110">To create qualified names in an XML document</span></span>  
  
1.  <span data-ttu-id="23178-111">`XmlSerializerNamespaces` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="23178-111">Create an instance of the `XmlSerializerNamespaces` class.</span></span>  
  
2.  <span data-ttu-id="23178-112">모든 접두사와 네임스페이스 쌍을 `XmlSerializerNamespaces`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23178-112">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>  
  
3.  <span data-ttu-id="23178-113">적절한 `System.Xml.Serialization` 특성을 <xref:System.Xml.Serialization.XmlSerializer>가 XML 문서로 serialize할 각 멤버나 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="23178-113">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>  
  
     <span data-ttu-id="23178-114">사용할 수 있는 특성은 <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute> 및 <xref:System.Xml.Serialization.XmlTypeAttribute>입니다.</span><span class="sxs-lookup"><span data-stu-id="23178-114">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>  
  
4.  <span data-ttu-id="23178-115">각 특성의 `Namespace` 속성을 `XmlSerializerNamespaces`의 네임스페이스 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="23178-115">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>  
  
5.  <span data-ttu-id="23178-116">`XmlSerializerNamespaces`의 `Serialize` 메서드에 `XmlSerializer`를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="23178-116">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23178-117">예제</span><span class="sxs-lookup"><span data-stu-id="23178-117">Example</span></span>  
 <span data-ttu-id="23178-118">다음 예제에서는 `XmlSerializerNamespaces`를 만들고 두 개의 접두사와 네임스페이스 쌍을 개체에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23178-118">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="23178-119">코드에서는 `XmlSerializer` 클래스의 인스턴스를 serialize하는 데 사용되는 `Books`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="23178-119">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="23178-120">코드는 `Serialize`를 사용하여 `XmlSerializerNamespaces` 메서드를 호출하여 XML이 접두사가 지정된 네임스페이스를 포함할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23178-120">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>  
  
```vb  
Option Explicit   
public class Price  
{  
    [XmlAttribute(Namespace = "http://www.cpandl.com")]  
    public string currency;  
    [XmlElement(Namespace = "http://www.cohowinery.com")]  
    public decimal price;  
}  
  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Serialization  
  
Public Class Run  
  
    Public Shared Sub Main()  
        Dim test As New Run()  
        test.SerializeObject("XmlNamespaces.xml")  
    End Sub 'Main  
  
    Public Sub SerializeObject(filename As String)  
        Dim mySerializer As New XmlSerializer(GetType(Books))  
        ' Writing a file requires a TextWriter.  
        Dim myWriter As New StreamWriter(filename)  
  
        ' Creates an XmlSerializerNamespaces and adds two  
        ' prefix-namespace pairs.   
        Dim myNamespaces As New XmlSerializerNamespaces()  
        myNamespaces.Add("books", "http://www.cpandl.com")  
        myNamespaces.Add("money", "http://www.cohowinery.com")  
  
        ' Creates a Book.  
        Dim myBook As New Book()  
        myBook.TITLE = "A Book Title"  
        Dim myPrice As New Price()  
        myPrice.price = CDec(9.95)  
        myPrice.currency = "US Dollar"  
        myBook.PRICE = myPrice  
        Dim myBooks As New Books()  
        myBooks.Book = myBook  
        mySerializer.Serialize(myWriter, myBooks, myNamespaces)  
        myWriter.Close()  
    End Sub  
End Class  
  
Public Class Books  
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
    Public Book As Book  
End Class 'Books  
  
<XmlType([Namespace] := "http://www.cpandl.com")> _  
Public Class Book  
  
    <XmlElement([Namespace] := "http://www.cpandl.com")> _  
    Public TITLE As String  
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
    Public PRICE As Price  
End Class  
  
Public Class Price  
    <XmlAttribute([Namespace] := "http://www.cpandl.com")> _  
    Public currency As String  
    Public <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
        price As Decimal  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Serialization;  
  
public class Run  
{  
    public static void Main()  
    {  
        Run test = new Run();  
        test.SerializeObject("XmlNamespaces.xml");  
    }  
    public void SerializeObject(string filename)  
    {  
        XmlSerializer mySerializer = new XmlSerializer(typeof(Books));  
        // Writing a file requires a TextWriter.  
        TextWriter myWriter = new StreamWriter(filename);  
  
        // Creates an XmlSerializerNamespaces and adds two  
        // prefix-namespace pairs.  
        XmlSerializerNamespaces myNamespaces =   
        new XmlSerializerNamespaces();  
        myNamespaces.Add("books", "http://www.cpandl.com");  
        myNamespaces.Add("money", "http://www.cohowinery.com");  
  
        // Creates a Book.  
        Book myBook = new Book();  
        myBook.TITLE = "A Book Title";  
        Price myPrice = new Price();  
        myPrice.price = (decimal) 9.95;  
        myPrice.currency = "US Dollar";  
        myBook.PRICE = myPrice;  
        Books myBooks = new Books();  
        myBooks.Book = myBook;  
        mySerializer.Serialize(myWriter,myBooks,myNamespaces);  
        myWriter.Close();  
    }  
}  
  
public class Books  
{  
    [XmlElement(Namespace = "http://www.cohowinery.com")]  
    public Book Book;  
}  
  
[XmlType(Namespace ="http://www.cpandl.com")]  
public class Book  
{  
    [XmlElement(Namespace = "http://www.cpandl.com")]  
    public string TITLE;  
    [XmlElement(Namespace ="http://www.cohowinery.com")]  
    public Price PRICE;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="23178-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23178-121">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="23178-122">XML 스키마 정의 도구 및 XML serialization</span><span class="sxs-lookup"><span data-stu-id="23178-122">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 [<span data-ttu-id="23178-123">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="23178-123">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="23178-124">XmlSerializer 클래스</span><span class="sxs-lookup"><span data-stu-id="23178-124">XmlSerializer Class</span></span>](xref:System.Xml.Serialization.XmlSerializer)  
 [<span data-ttu-id="23178-125">XML serialization을 제어하는 특성</span><span class="sxs-lookup"><span data-stu-id="23178-125">Attributes That Control XML Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md)  
 [<span data-ttu-id="23178-126">방법: XML 스트림의 대체 요소 이름 지정</span><span class="sxs-lookup"><span data-stu-id="23178-126">How to: Specify an Alternate Element Name for an XML Stream</span></span>](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 [<span data-ttu-id="23178-127">방법: 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="23178-127">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="23178-128">방법: 개체 deserialize</span><span class="sxs-lookup"><span data-stu-id="23178-128">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
