---
title: "XML 및 SOAP Serialization | Microsoft Docs"
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
  - "serialization"
  - "serialization, serialization 정보"
  - "serialization, SOAP"
  - "SOAP, XML serialization"
  - "XML serialization"
  - "XML serialization, SOAP"
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# XML 및 SOAP Serialization
XML serialization은 개체의 public 필드와 속성 또는 메서드의 매개 변수와 반환 값을 특정 XSD\(XML 스키마 정의 언어\) 문서와 일치하는 XML 스트림으로 변환\(serialize\)합니다.XML serialization을 사용하면 저장이나 전송을 위해 직렬 형식\(이 경우 XML\)으로 변환되는 public 속성 및 필드가 있는 강력한 형식의 클래스가 만들어집니다.  
  
 XML은 공개 표준이기 때문에 XML 스트림은 플랫폼에 관계없이 필요에 따라 모든 응용 프로그램에서 처리될 수 있습니다.예를 들어 ASP.NET을 사용하여 만들어진 XML Web services는 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 데이터를 인터넷이나 인트라넷을 통해 XML Web services 응용 프로그램 간에 전달하는 XML 스트림을 만듭니다.이와 반대로 deserialization에서는 이러한 XML 스트림을 받아서 개체를 다시 만듭니다.  
  
 XML serialization은 SOAP 사양과 일치하는 XML 스트림으로 개체를 serialize하는 데 사용할 수도 있습니다.SOAP는 특히 XML을 사용하여 프로시저 호출을 전송하기 위해 디자인된 XML 기반 프로토콜입니다.  
  
 개체를 serialize하거나 deserialize하려면 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용합니다.클래스가 serialize되도록 하려면 XML 스키마 정의 도구를 사용합니다.  
  
## 단원 내용  
 [XML Serialization 소개](../../../docs/framework/serialization/introducing-xml-serialization.md)  
 serialization, 특히 XML serialization에 대한 일반 정의를 제공합니다.  
  
 [방법: 개체 Serialize](../../../docs/framework/serialization/how-to-serialize-an-object.md)  
 개체를 serialize하는 방법을 단계별로 설명합니다.  
  
 [방법: 개체 Deserialize](../../../docs/framework/serialization/how-to-deserialize-an-object.md)  
 개체를 deserialize하는 방법을 단계별로 설명합니다.  
  
 [XML Serialization 예제](../../../docs/framework/serialization/examples-of-xml-serialization.md)  
 XML serialization의 기본 사항을 보여 주는 예제를 제공합니다.  
  
 [XML 스키마 정의 도구 및 XML Serialization](../../../docs/framework/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 XML 스키마 정의 도구를 사용하여 특정 XSD\(XML 스키마 정의 언어\) 스키마를 준수하거나 .dll 파일에서 XML 스키마를 생성하는 방법을 설명합니다.  
  
 [특성을 사용하여 XML Serialization 제어](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)  
 특성을 사용하여 serialization을 제어하는 방법을 설명합니다.  
  
 [XML Serialization을 제어하는 특성](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md)  
 XML serialization의 제어에 사용되는 특성을 나열합니다.  
  
 [방법: XML 스트림의 대체 요소 이름 지정](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 serialization을 재정의하여 여러 XML 스트림을 생성하는 방법을 보여 주는 고급 시나리오를 소개합니다.  
  
 [방법: 파생 클래스의 Serialization 제어](../../../docs/framework/serialization/how-to-control-serialization-of-derived-classes.md)  
 파생 클래스의 serialization을 제어하는 방법을 보여 주는 예제를 제공합니다.  
  
 [방법: XML 요소 및 XML 특성 이름 한정](../../../docs/framework/serialization/how-to-qualify-xml-element-and-xml-attribute-names.md)  
 XML 네임스페이스가 XML 스트림에 사용되는 방법을 정의하고 제어하는 방법을 설명합니다.  
  
 [XML Web Services의 XML Serialization](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md)  
 XML serialization이 XML Web services에 사용되는 방식을 설명합니다.  
  
 [방법: 개체를 SOAP 인코딩된 XML 스트림으로 Serialize](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 World Wide Web 컨소시엄\(www.w3.org\) 문서 "SOAP\(Simple Object Access Protocol\) 1.1"의 5단원을 준수하는 인코딩된 SOAP XML 스트림을 만드는 방법을 설명합니다.  
  
 [방법: 인코딩된 SOAP XML Serialization 재정의](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 개체의 XML serialization을 SOAP 메시지로 재정의하는 프로세스를 설명합니다.  
  
 [인코딩된 SOAP Serialization을 제어하는 특성](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)  
 SOAP로 인코딩된 serialization의 제어에 사용되는 특성을 나열합니다.  
  
 [\<system.xml.serialization\> 요소](../../../docs/framework/serialization/system-xml-serialization-element.md)  
 XML serialization을 제어하기 위한 최상위 구성 요소입니다.  
  
 [\<dateTimeSerialization\> 요소](../../../docs/framework/serialization/datetimeserialization-element.md)  
 <xref:System.DateTime> 개체의 serialization 모드를 제어합니다.  
  
 [\<schemaImporterExtensions\> 요소](../../../docs/framework/serialization/schemaimporterextensions-element.md)  
 <xref:System.Xml.Serialization.XmlSchemaImporter> 클래스에서 사용하는 형식을 포함합니다.  
  
 [\<xmlSchemaImporterExtensions\>의 요소 \<add\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)  
 <xref:System.Xml.Serialization.XmlSchemaImporter> 클래스에서 사용하는 형식을 추가합니다.  
  
## 관련 단원  
 [Advanced Development Technologies](http://msdn.microsoft.com/ko-kr/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
 .NET Framework의 복잡한 개발 작업 및 기술에 대한 자세한 내용을 볼 수 있는 링크를 제공합니다.  
  
 [XML Web Services Created Using ASP.NET and XML Web Service Clients](http://msdn.microsoft.com/ko-kr/1e64af78-d705-4384-b08d-591a45f4379c)  
 ASP.NET을 사용하여 XML Web services를 프로그래밍하는 방법을 설명하는 항목을 제공합니다.  
  
## 참고 항목  
 [이진 Serialization](../../../docs/framework/serialization/binary-serialization.md)