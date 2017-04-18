---
title: "인코딩된 SOAP Serialization을 제어하는 특성 | Microsoft Docs"
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
  - "특성 [.NET Framework], XML serialization"
  - "serialization, 특성"
  - "SOAP, XML serialization"
  - "XML serialization, 특성"
  - "XML serialization, SOAP"
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 인코딩된 SOAP Serialization을 제어하는 특성
World Wide Web 컨소시엄\(www.w3.org\) 문서 "SOAP\(Simple Object Access Protocol\) 1.1"에는 SOAP 매개 변수를 인코딩할 수 있는 방법을 설명하는 선택적 단원\(5단원\)이 포함되어 있습니다.사양의 5단원을 따르려면 [System.Xml.Serialization](frlrfSystemXmlSerialization) 네임스페이스에 속한 특별한 특성 집합을 사용해야 합니다.이러한 특성을 클래스 및 클래스 멤버에 적절하게 적용한 다음 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)를 사용하여 클래스의 인스턴스를 serialize합니다.  
  
 다음 표에서는 특성, 해당 특성을 적용할 수 있는 위치 및 해당 특성이 수행하는 작업을 보여 줍니다.이러한 특성을 사용하여 XML serialization을 제어하는 방법에 대한 자세한 내용은 [방법: 개체를 SOAP 인코딩된 XML 스트림으로 Serialize](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) 및 [방법: 인코딩된 SOAP XML Serialization 재정의](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)를 참조하십시오.  
  
 특성에 대한 자세한 내용은 [특성](../../../docs/standard/attributes/index.md)을 참조하십시오.  
  
|특성|적용 대상|설명|  
|--------|-----------|--------|  
|[SoapAttributeAttribute](frlrfSystemXmlSerializationSoapAttributeAttributeClassTopic)|public 필드, 속성, 매개 변수 또는 반환 값입니다.|클래스 멤버는 XML 특성으로 serialize됩니다.|  
|[SoapElementAttribute](frlrfSystemXmlSerializationSoapElementAttributeClassTopic)|public 필드, 속성, 매개 변수 또는 반환 값입니다.|클래스는 XML 요소로 serialize됩니다.|  
|[SoapEnumAttribute](frlrfSystemXmlSerializationSoapEnumAttributeClassTopic)|열거형 식별자인 public 필드입니다.|열거형 멤버의 요소 이름입니다.|  
|[SoapIgnoreAttribute](frlrfSystemXmlSerializationSoapIgnoreAttributeClassTopic)|public 속성 및 필드입니다.|속성 또는 필드는 포함 클래스가 serialize될 때 무시되어야 합니다.|  
|[SoapIncludeAttribute](frlrfSystemXmlSerializationSoapIncludeAttributeClassTopic)|WSDL\(웹 서비스 설명 언어\) 문서에 대한 공용 파생 클래스 선언 및 공용 메서드입니다.|스키마를 생성할 때 형식을 포함해야 합니다\(serialize될 때 인식되도록\).|  
|[SoapTypeAttribute](frlrfSystemXmlSerializationSoapTypeAttributeClassTopic)|public 클래스 선언입니다.|클래스는 XML 형식으로 serialize되어야 합니다.|  
  
## 참고 항목  
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [방법: 개체를 SOAP 인코딩된 XML 스트림으로 Serialize](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)   
 [방법: 인코딩된 SOAP XML Serialization 재정의](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)   
 [특성](../../../docs/standard/attributes/index.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [방법: 개체 Serialize](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [방법: 개체 Deserialize](../../../docs/framework/serialization/how-to-deserialize-an-object.md)