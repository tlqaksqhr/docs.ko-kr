---
title: "방법: XML 요소 및 XML 특성 이름 한정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "XML 요소 한정"
  - "XML 이름 한정"
  - "XML 네임스페이스, 요소 및 이름 한정"
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 방법: XML 요소 및 XML 특성 이름 한정
[코드 예제](#cpconworkingwithxmlnamespacesanchor1)  
  
 [XmlSerializerNamespaces](frlrfSystemXmlSerializationXmlSerializerNamespacesClassTopic) 클래스의 인스턴스에 의해 포함된 XML 네임스페이스는 "Namespaces in XML"이라는 World Wide Web 컨소시엄\(www.w3.org\) 사양을 따라야 합니다.  
  
 XML 네임스페이스는 XML 문서에서 XML 요소 및 XML 특성의 이름을 정규화하는 메서드를 제공합니다.정규화된 이름은 콜론으로 구분된 접두사와 로컬 이름으로 이루어집니다.접두사는 자리 표시자로만 사용되며 네임스페이스를 지정하는 URI에 매핑됩니다.보편적으로 관리되는 URI 네임스페이스와 로컬 이름을 조합하면 보편적으로 고유한 이름이 만들어집니다.  
  
 **XmlSerializerNamespaces**의 인스턴스를 만들고 네임스페이스 쌍을 개체에 추가하면 XML 문서에 사용되는 접두사를 지정할 수 있습니다.  
  
### XML 문서에서 정규화된 이름을 만들려면  
  
1.  **XmlSerializerNamespaces** 클래스의 인스턴스를 만듭니다.  
  
2.  모든 접두사와 네임스페이스 쌍을 **XmlSerializerNamespaces**에 추가합니다.  
  
3.  적절한 **System.Xml.Serialization** 특성을 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)가 XML 문서로 serialize할 각 멤버나 클래스에 적용합니다.  
  
     사용할 수 있는 특성은 [XmlAnyElementAttribute](frlrfSystemXmlSerializationXmlAnyElementAttributeClassTopic), [XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic), [XmlArrayItemAttribute](frlrfSystemXmlSerializationXmlArrayItemAttributeClassTopic), [XmlAttributeAttribute](frlrfSystemXmlSerializationXmlAttributeAttributeClassTopic), [XmlElementAttribute](frlrfSystemXmlSerializationXmlElementAttributeClassTopic), [XmlRootAttribute](frlrfSystemXmlSerializationXmlRootAttributeClassTopic) 및 [XmlTypeAttribute](frlrfSystemXmlSerializationXmlTypeAttributeClassTopic)입니다.  
  
4.  각 특성의 **Namespace** 속성을 **XmlSerializerNamespaces**의 네임스페이스 값 중 하나로 설정합니다.  
  
5.  **XmlSerializer**의 **Serialize** 메서드에 **XmlSerializerNamespaces**를 전달합니다.  
  
## 예제  
 다음 예제에서는 **XmlSerializerNamespaces**를 만들고 두 개의 접두사와 네임스페이스 쌍을 개체에 추가합니다.코드에서는 `Books` 클래스의 인스턴스를 serialize하는 데 사용되는 **XmlSerializer**를 만듭니다.코드는 **XmlSerializerNamespaces**를 사용하여 **Serialize** 메서드를 호출하여 XML이 접두사가 지정된 네임스페이스를 포함할 수 있게 됩니다.  
  
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
  
## 참고 항목  
 [XML 스키마 정의 도구 및 XML Serialization](../../../docs/framework/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)   
 [XML Serialization 소개](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [XmlSerializer Class](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [XML Serialization을 제어하는 특성](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md)   
 [XmlSerializerNamespaces Class](frlrfSystemXmlSerializationXmlSerializerNamespacesClassTopic)   
 [방법: XML 스트림의 대체 요소 이름 지정](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)   
 [방법: 개체 Serialize](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [방법: 개체 Deserialize](../../../docs/framework/serialization/how-to-deserialize-an-object.md)