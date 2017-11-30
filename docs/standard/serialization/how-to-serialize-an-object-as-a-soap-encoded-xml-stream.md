---
title: "방법: 개체를 SOAP 인코딩된 XML 스트림으로 Serialize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b4b1054d079b24fefc2e8b0838807d74626f3fa0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="d3679-102">방법: 개체를 SOAP 인코딩된 XML 스트림으로 Serialize</span><span class="sxs-lookup"><span data-stu-id="d3679-102">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>
  
 <span data-ttu-id="d3679-103">SOAP 메시지는 XML을 사용하여 생성되므로 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 클래스를 직렬화하고 인코딩된 SOAP 메시지를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3679-103">Because a SOAP message is built using XML, the <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize classes and generate encoded SOAP messages.</span></span> <span data-ttu-id="d3679-104">결과 XML은 [World Wide Web 컨소시엄 문서의 5단원 “SOAP(Simple Object Access Protocol) 1.1”](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d3679-104">The resulting XML conforms to [section 5 of the World Wide Web Consortium document "Simple Object Access Protocol (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span></span> <span data-ttu-id="d3679-105">SOAP 메시지를 통해 통신하는 XML Web services를 만들 때는 특별한 SOAP 특성 집합을 클래스와 클래스 멤버에 적용하여 XML 스트림을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3679-105">When you are creating an XML Web service that communicates through SOAP messages, you can customize the XML stream by applying a set of special SOAP attributes to classes and members of classes.</span></span> <span data-ttu-id="d3679-106">특성 목록을 보려면 [인코딩된 SOAP serialization을 제어하는 특성](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3679-106">For a list of attributes, see [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="d3679-107">개체를 SOAP 인코딩된 XML 스트림으로 serialize하려면</span><span class="sxs-lookup"><span data-stu-id="d3679-107">To serialize an object as a SOAP-encoded XML stream</span></span>  
  
1.  <span data-ttu-id="d3679-108">[XML 스키마 정의 도구(Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)를 사용하여 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3679-108">Create the class using the [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
2.  <span data-ttu-id="d3679-109">`System.Xml.Serialization`에 있는 하나 이상의 특수 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3679-109">Apply one or more of the special attributes found in `System.Xml.Serialization`.</span></span> <span data-ttu-id="d3679-110">"인코딩된 SOAP serialization을 제어하는 특성"의 목록을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3679-110">See the list in "Attributes That Control Encoded SOAP Serialization."</span></span>  
  
3.  <span data-ttu-id="d3679-111">새 `XmlTypeMapping`를 만들고 serialize된 클래스의 형식으로 `SoapReflectionImporter` 메서드를 호출하여 `ImportTypeMapping`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3679-111">Create an `XmlTypeMapping` by creating a new `SoapReflectionImporter`, and invoking the `ImportTypeMapping` method with the type of the serialized class.</span></span>  
  
     <span data-ttu-id="d3679-112">다음 코드 예제에서는 `SoapReflectionImporter` 클래스의 `ImportTypeMapping` 메서드를 호출하여 `XmlTypeMapping`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3679-112">The following code example calls the `ImportTypeMapping` method of the `SoapReflectionImporter` class to create an `XmlTypeMapping`.</span></span>  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping =
        New SoapReflectionImporter().ImportTypeMapping(GetType(Group))  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping =
        new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
    ```  
  
4.  <span data-ttu-id="d3679-113">`XmlSerializer`을 `XmlTypeMapping` 생성자로 전달하여 <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3679-113">Create an instance of the `XmlSerializer` class by passing the `XmlTypeMapping` to the <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> constructor.</span></span>  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5.  <span data-ttu-id="d3679-114">`Serialize` 또는 `Deserialize` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d3679-114">Call the `Serialize` or `Deserialize` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3679-115">예제</span><span class="sxs-lookup"><span data-stu-id="d3679-115">Example</span></span>  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping =
    New SoapReflectionImporter().ImportTypeMapping(GetType(Group))
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping =
    new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3679-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3679-116">See Also</span></span>  
 [<span data-ttu-id="d3679-117">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="d3679-117">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 [<span data-ttu-id="d3679-118">인코딩된 SOAP serialization을 제어하는 특성</span><span class="sxs-lookup"><span data-stu-id="d3679-118">Attributes That Control Encoded SOAP Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)  
 [<span data-ttu-id="d3679-119">XML Web Services의 XML serialization</span><span class="sxs-lookup"><span data-stu-id="d3679-119">XML Serialization with XML Web Services</span></span>](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)  
 [<span data-ttu-id="d3679-120">방법: 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="d3679-120">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="d3679-121">방법: 개체 deserialize</span><span class="sxs-lookup"><span data-stu-id="d3679-121">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
 [<span data-ttu-id="d3679-122">방법: 인코딩된 SOAP XML serialization 재정의</span><span class="sxs-lookup"><span data-stu-id="d3679-122">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)
