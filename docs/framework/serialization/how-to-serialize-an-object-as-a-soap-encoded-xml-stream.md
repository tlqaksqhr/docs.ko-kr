---
title: "방법: 개체를 SOAP 인코딩된 XML 스트림으로 Serialize | Microsoft Docs"
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
  - "serialization, SOAP"
  - "SOAP, XML serialization"
  - "XML serialization, SOAP"
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 방법: 개체를 SOAP 인코딩된 XML 스트림으로 Serialize
[코드 예제](#cpconxmlserializationusingsoapprotocolanchor1)  
  
 SOAP 메시지는 XML을 사용하여 생성되므로 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)를 사용하여 클래스를 serialize하고 인코딩된 SOAP 메시지를 생성할 수 있습니다.결과 XML은 World Wide Web 컨소시엄\(www.w3.org\) 문서의 5단원 "SOAP\(Simple Object Access Protocol\) 1.1"을 따릅니다.SOAP 메시지를 통해 통신하는 XML Web services를 만들 때는 특별한 SOAP 특성 집합을 클래스와 클래스 멤버에 적용하여 XML 스트림을 사용자 지정할 수 있습니다.특성 목록은 [인코딩된 SOAP Serialization을 제어하는 특성](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)을 참조하십시오.  
  
### 개체를 SOAP 인코딩된 XML 스트림으로 serialize하려면  
  
1.  [XML 스키마 정의 도구\(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md)를 사용하여 클래스를 만듭니다.  
  
2.  **System.Xml.Serialization**에 있는 하나 이상의 특수 특성을 적용합니다."인코딩된 SOAP serialization을 제어하는 특성"의 목록을 참조하십시오.  
  
3.  새 **SoapReflectionImporter**를 만들고 serialize된 클래스의 형식으로 **ImportTypeMapping** 메서드를 호출하여 **XmlTypeMapping**을 만듭니다.  
  
     다음 코드 예제에서는 **SoapReflectionImporter** 클래스의 **ImportTypeMapping**메서드를 호출하여 **XmlTypeMapping**을 만듭니다.  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping = (New SoapReflectionImporter(). _  
    ImportTypeMapping(GetType(Group))  
  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping = (new SoapReflectionImporter().  
    ImportTypeMapping(typeof(Group));  
    ```  
  
4.  **XmlTypeMapping**을 <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> 생성자로 전달하여 **XmlSerializer** 클래스의 인스턴스를 만듭니다.  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5.  **Serialize** 또는 **Deserialize** 메서드를 호출합니다.  
  
## 예제  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping = (New SoapReflectionImporter(). _  
ImportTypeMapping(GetType(Group))  
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping = (new SoapReflectionImporter().ImportTypeMapping(typeof(Group));  
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## 참고 항목  
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [인코딩된 SOAP Serialization을 제어하는 특성](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)   
 [XML Web Services의 XML Serialization](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md)   
 [방법: 개체 Serialize](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [방법: 개체 Deserialize](../../../docs/framework/serialization/how-to-deserialize-an-object.md)   
 [방법: 인코딩된 SOAP XML Serialization 재정의](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)