---
title: "방법: XML 스트림의 대체 요소 이름 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XML serialization, overriding
- serialization, overriding
- XML stream, specifying alternate element name for
- overriding XML serialization
- classes, overriding
- overriding classes
ms.assetid: 5cc1c0b0-f94b-4525-9a41-88a582cd6668
caps.latest.revision: 7
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: bd06d53ff1d28b3b3ec9937b4c3efdb1d784c481
ms.contentlocale: ko-kr
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-specify-an-alternate-element-name-for-an-xml-stream"></a>방법: XML 스트림의 대체 요소 이름 지정
[코드 예제](#cpconoverridingserializationofclasseswithxmlattributeoverridesclassanchor1)  
  
 [XmlSerializer](https://msdn.microsoft.com/library/system.xml.serialization.xmlserializer.aspx)를 사용하면 동일한 클래스 집합을 가진 XML 스트림을 두 개 이상 생성할 수 있습니다. 두 개의 서로 다른 XML Web services에 약간만 다른 동일한 기본 정보가 필요한 경우 이런 작업이 필요할 수 있습니다. 예를 들어 책 주문을 처리하기 때문에 둘 모두에 ISBN 번호가 필요한 두 개의 XML Web services를 가정해 보겠습니다. 한 서비스는 \<ISBN> 태그를 사용하고 다른 서비스는 \<BookID> 태그를 사용합니다. `Book`이라는 필드가 포함된 `ISBN`이라는 클래스가 있습니다. `Book` 클래스의 인스턴스가 serialize될 때 기본적으로 멤버 이름(ISBN)을 태그 요소 이름으로 사용합니다. 첫 번째 XML Web services의 경우에는 예상된 동작입니다. 하지만 XML 스트림을 두 번째 XML Web services로 전송하려면 태그의 요소 이름이 `BookID`가 되도록 serialization을 재정의해야 합니다.  
  
### <a name="to-create-an-xml-stream-with-an-alternate-element-name"></a>대체 요소 이름을 사용하여 XML 스트림을 만들려면  
  
1.  <xref:System.Xml.Serialization.XmlElementAttribute> 클래스의 인스턴스를 만듭니다.  
  
2.  <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A>의 <xref:System.Xml.Serialization.XmlElementAttribute>을 "BookID"로 설정합니다.  
  
3.  <xref:System.Xml.Serialization.XmlAttributes> 클래스의 인스턴스를 만듭니다.  
  
4.  `XmlElementAttribute`의 <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> 속성을 통해 액세스되는 컬렉션에 <xref:System.Xml.Serialization.XmlAttributes> 개체를 추가합니다.  
  
5.  <xref:System.Xml.Serialization.XmlAttributeOverrides> 클래스의 인스턴스를 만듭니다.  
  
6.  `XmlAttributes`를 <xref:System.Xml.Serialization.XmlAttributeOverrides>에 추가하고 재정의할 개체의 형식과 재정의될 멤버의 이름을 전달합니다.  
  
7.  `XmlSerializer`로 `XmlAttributeOverrides` 클래스의 인스턴스를 만듭니다.  
  
8.  `Book` 클래스의 인스턴스를 만들고 이를 serialize 또는 deserialize합니다.  
  
## <a name="example"></a>예제  
  
```vb  
Public Class SerializeOverride()  
    ' Creates an XmlElementAttribute with the alternate name.  
    Dim myElementAttribute As XmlElementAttribute = _  
    New XmlElementAttribute()  
    myElementAttribute.ElementName = "BookID"  
    Dim myAttributes As XmlAttributes = New XmlAttributes()  
    myAttributes.XmlElements.Add(myElementAttribute)  
    Dim myOverrides As XmlAttributeOverrides = New XmlAttributeOverrides()  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes)  
    Dim mySerializer As XmlSerializer = _  
    New XmlSerializer(GetType(Book), myOverrides)  
    Dim b As Book = New Book()  
    b.ISBN = "123456789"  
    ' Creates a StreamWriter to write the XML stream to.  
    Dim writer As StreamWriter = New StreamWriter("Book.xml")  
    mySerializer.Serialize(writer, b);  
End Class  
```  
  
```csharp  
public class SerializeOverride()  
{  
    // Creates an XmlElementAttribute with the alternate name.  
    XmlElementAttribute myElementAttribute = new XmlElementAttribute();  
    myElementAttribute.ElementName = "BookID";  
    XmlAttributes myAttributes = new XmlAttributes();  
    myAttributes.XmlElements.Add(myElementAttribute);  
    XmlAttributeOverrides myOverrides = new XmlAttributeOverrides();  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes);  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(Book), myOverrides)  
    Book b = new Book();  
    b.ISBN = "123456789"  
    // Creates a StreamWriter to write the XML stream to.  
    StreamWriter writer = new StreamWriter("Book.xml");  
    mySerializer.Serialize(writer, b);  
}  
```  
  
 해당 XML 스트림은 다음과 같을 수 있습니다.  
  
```xml  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Serialization.XmlElementAttribute>   
 <xref:System.Xml.Serialization.XmlAttributes>   
 <xref:System.Xml.Serialization.XmlAttributeOverrides>   
 [XML 및 SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)   
 [XmlSerializer](https://msdn.microsoft.com/library/system.xml.serialization.xmlserializer.aspx)   
 [방법: 개체 직렬화](../../../docs/standard/serialization/how-to-serialize-an-object.md)   
 [방법: 개체 deserialize](../../../docs/standard/serialization/how-to-deserialize-an-object.md)   
 [방법: 개체 deserialize](../../../docs/standard/serialization/how-to-deserialize-an-object.md)

