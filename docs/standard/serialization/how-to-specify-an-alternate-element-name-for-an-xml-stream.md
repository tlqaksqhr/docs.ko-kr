---
title: '방법: XML 스트림의 대체 요소 이름 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML serialization, overriding
- serialization, overriding
- XML stream, specifying alternate element name for
- overriding XML serialization
- classes, overriding
- overriding classes
ms.assetid: 5cc1c0b0-f94b-4525-9a41-88a582cd6668
ms.openlocfilehash: d0e48c9c28c8d9447b22fa5ea7a8024442e09295
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587712"
---
# <a name="how-to-specify-an-alternate-element-name-for-an-xml-stream"></a><span data-ttu-id="443c0-102">방법: XML 스트림의 대체 요소 이름 지정</span><span class="sxs-lookup"><span data-stu-id="443c0-102">How to: Specify an Alternate Element Name for an XML Stream</span></span>
[<span data-ttu-id="443c0-103">코드 예제</span><span class="sxs-lookup"><span data-stu-id="443c0-103">Code Example</span></span>](#cpconoverridingserializationofclasseswithxmlattributeoverridesclassanchor1)  
  
 <span data-ttu-id="443c0-104">[XmlSerializer](https://msdn.microsoft.com/library/system.xml.serialization.xmlserializer.aspx)를 사용하면 동일한 클래스 집합을 가진 XML 스트림을 두 개 이상 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-104">Using the [XmlSerializer](https://msdn.microsoft.com/library/system.xml.serialization.xmlserializer.aspx), you can generate more than one XML stream with the same set of classes.</span></span> <span data-ttu-id="443c0-105">두 개의 서로 다른 XML Web services에 약간만 다른 동일한 기본 정보가 필요한 경우 이런 작업이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-105">You might want to do this because two different XML Web services require the same basic information, with only slight differences.</span></span> <span data-ttu-id="443c0-106">예를 들어 책 주문을 처리하기 때문에 둘 모두에 ISBN 번호가 필요한 두 개의 XML Web services를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-106">For example, imagine two XML Web services that process orders for books, and thus both require ISBN numbers.</span></span> <span data-ttu-id="443c0-107">한 서비스는 \<ISBN> 태그를 사용하고 다른 서비스는 \<BookID> 태그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-107">One service uses the tag \<ISBN> while the second uses the tag \<BookID>.</span></span> <span data-ttu-id="443c0-108">`Book`이라는 필드가 포함된 `ISBN`이라는 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-108">You have a class named `Book` that contains a field named `ISBN`.</span></span> <span data-ttu-id="443c0-109">`Book` 클래스의 인스턴스가 serialize될 때 기본적으로 멤버 이름(ISBN)을 태그 요소 이름으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-109">When an instance of the `Book` class is serialized, it will, by default, use the member name (ISBN) as the tag element name.</span></span> <span data-ttu-id="443c0-110">첫 번째 XML Web services의 경우에는 예상된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-110">For the first XML Web service, this is as expected.</span></span> <span data-ttu-id="443c0-111">하지만 XML 스트림을 두 번째 XML Web services로 전송하려면 태그의 요소 이름이 `BookID`가 되도록 serialization을 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-111">But to send the XML stream to the second XML Web service, you must override the serialization so that the tag's element name is `BookID`.</span></span>  
  
### <a name="to-create-an-xml-stream-with-an-alternate-element-name"></a><span data-ttu-id="443c0-112">대체 요소 이름을 사용하여 XML 스트림을 만들려면</span><span class="sxs-lookup"><span data-stu-id="443c0-112">To create an XML stream with an alternate element name</span></span>  
  
1.  <span data-ttu-id="443c0-113"><xref:System.Xml.Serialization.XmlElementAttribute> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-113">Create an instance of the <xref:System.Xml.Serialization.XmlElementAttribute> class.</span></span>  
  
2.  <span data-ttu-id="443c0-114"><xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A>의 <xref:System.Xml.Serialization.XmlElementAttribute>을 "BookID"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-114">Set the <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> of the <xref:System.Xml.Serialization.XmlElementAttribute> to "BookID".</span></span>  
  
3.  <span data-ttu-id="443c0-115"><xref:System.Xml.Serialization.XmlAttributes> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-115">Create an instance of the <xref:System.Xml.Serialization.XmlAttributes> class.</span></span>  
  
4.  <span data-ttu-id="443c0-116">`XmlElementAttribute`의 <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> 속성을 통해 액세스되는 컬렉션에 <xref:System.Xml.Serialization.XmlAttributes> 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-116">Add the `XmlElementAttribute` object to the collection accessed through the <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> property of <xref:System.Xml.Serialization.XmlAttributes> .</span></span>  
  
5.  <span data-ttu-id="443c0-117"><xref:System.Xml.Serialization.XmlAttributeOverrides> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-117">Create an instance of the <xref:System.Xml.Serialization.XmlAttributeOverrides> class.</span></span>  
  
6.  <span data-ttu-id="443c0-118">`XmlAttributes`를 <xref:System.Xml.Serialization.XmlAttributeOverrides>에 추가하고 재정의할 개체의 형식과 재정의될 멤버의 이름을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-118">Add the `XmlAttributes` to the <xref:System.Xml.Serialization.XmlAttributeOverrides>, passing the type of the object to override and the name of the member being overridden.</span></span>  
  
7.  <span data-ttu-id="443c0-119">`XmlSerializer`로 `XmlAttributeOverrides` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-119">Create an instance of the `XmlSerializer` class with `XmlAttributeOverrides`.</span></span>  
  
8.  <span data-ttu-id="443c0-120">`Book` 클래스의 인스턴스를 만들고 이를 serialize 또는 deserialize합니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-120">Create an instance of the `Book` class, and serialize or deserialize it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="443c0-121">예제</span><span class="sxs-lookup"><span data-stu-id="443c0-121">Example</span></span>  
  
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
  
 <span data-ttu-id="443c0-122">해당 XML 스트림은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="443c0-122">The XML stream might resemble the following.</span></span>  
  
```xml  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## <a name="see-also"></a><span data-ttu-id="443c0-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="443c0-123">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlElementAttribute>  
 <xref:System.Xml.Serialization.XmlAttributes>  
 <xref:System.Xml.Serialization.XmlAttributeOverrides>  
 [<span data-ttu-id="443c0-124">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="443c0-124">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 [<span data-ttu-id="443c0-125">XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="443c0-125">XmlSerializer</span></span>](https://msdn.microsoft.com/library/system.xml.serialization.xmlserializer.aspx)  
 [<span data-ttu-id="443c0-126">방법: 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="443c0-126">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="443c0-127">방법: 개체 deserialize</span><span class="sxs-lookup"><span data-stu-id="443c0-127">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
 [<span data-ttu-id="443c0-128">방법: 개체 deserialize</span><span class="sxs-lookup"><span data-stu-id="443c0-128">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
