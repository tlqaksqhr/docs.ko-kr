---
title: XML Serialization을 제어하는 특성
ms.date: 03/30/2017
helpviewer_keywords:
- classes, serializing
- XmlSerializer class, serializing
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
- XML Schema, serializing
ms.assetid: 414b820f-a696-4206-b576-2711d85490c7
ms.openlocfilehash: 3c6e46c97a943f1c77ffd12dd2b3bc85a64b3c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="attributes-that-control-xml-serialization"></a>XML Serialization을 제어하는 특성
다음 표의 특성을 클래스 및 클래스 멤버에 적용하여 <xref:System.Xml.Serialization.XmlSerializer>가 클래스 인스턴스를 serialize 또는 deserialize하는 방법을 제어할 수 있습니다. 이러한 특성이 XML serialization을 제어하는 방법을 이해하려면 [특성을 사용하여 XML Serialization 제어](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)를 참조하세요.  
  
 이러한 특성을 사용하면 XML Web services를 통해 생성된 리터럴 스타일 SOAP 메시지를 제어할 수도 있습니다. 이러한 특성을 XML Web services 메서드에 적용하는 방법에 대한 자세한 내용은 [XML Web Services의 XML serialization](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)을 참조하세요.  
  
 특성에 대한 자세한 내용은 [특성](../../../docs/standard/attributes/index.md)을 참조하세요.  
  
|특성|적용 대상|설명|  
|---------------|----------------|---------------|  
|<xref:System.Xml.Serialization.XmlAnyAttributeAttribute>|<xref:System.Xml.XmlAttribute> 개체의 배열을 반환하는 반환 값 또는 public 필드, 속성, 매개 변수입니다.|deserialize할 때 배열은 스키마에 알려지지 않은 모든 XML 특성을 나타내는 <xref:System.Xml.XmlAttribute> 개체로 채워집니다.|  
|<xref:System.Xml.Serialization.XmlAnyElementAttribute>|<xref:System.Xml.XmlElement> 개체의 배열을 반환하는 반환 값 또는 public 필드, 속성, 매개 변수입니다.|deserialize할 때 배열은 스키마에 알려지지 않은 모든 XML 요소를 나타내는 <xref:System.Xml.XmlElement> 개체로 채워집니다.|  
|<xref:System.Xml.Serialization.XmlArrayAttribute>|복잡한 개체의 배열을 반환하는 반환 값 또는 public 필드, 특성, 매개 변수입니다.|배열의 멤버는 XML 배열의 멤버로 생성됩니다.|  
|<xref:System.Xml.Serialization.XmlArrayItemAttribute>|복잡한 개체의 배열을 반환하는 반환 값 또는 public 필드, 특성, 매개 변수입니다.|배열에 삽입할 수 있는 파생된 형식입니다. 일반적으로 <xref:System.Xml.Serialization.XmlArrayAttribute>와 함께 적용됩니다.|  
|<xref:System.Xml.Serialization.XmlAttributeAttribute>|public 필드, 속성, 매개 변수 또는 반환 값입니다.|멤버는 XML 특성으로 serialize됩니다.|  
|<xref:System.Xml.Serialization.XmlChoiceIdentifierAttribute>|public 필드, 속성, 매개 변수 또는 반환 값입니다.|멤버는 열거형을 사용하여 명확히 할 수 있습니다.|  
|<xref:System.Xml.Serialization.XmlElementAttribute>|public 필드, 속성, 매개 변수 또는 반환 값입니다.|필드 또는 속성은 XML 요소로 serialize됩니다.|  
|<xref:System.Xml.Serialization.XmlEnumAttribute>|열거형 식별자인 public 필드입니다.|열거형 멤버의 요소 이름입니다.|  
|<xref:System.Xml.Serialization.XmlIgnoreAttribute>|public 속성 및 필드입니다.|속성 또는 필드는 포함 클래스가 serialize될 때 무시되어야 합니다.|  
|<xref:System.Xml.Serialization.XmlIncludeAttribute>|public 파생 클래스 선언 및 WSDL(웹 서비스 설명 언어) 문서에 대한 public 메서드의 반환 값입니다.|스키마를 생성할 때 클래스를 포함해야 합니다(serialize될 때 인식되도록).|  
|<xref:System.Xml.Serialization.XmlRootAttribute>|public 클래스 선언입니다.|특성 대상의 XML serialization을 XML 루트 요소로 제어합니다. 특성을 사용하여 네임스페이스와 요소 이름을 지정합니다.|  
|<xref:System.Xml.Serialization.XmlTextAttribute>|public 속성 및 필드입니다.|속성 또는 필드는 XML 텍스트로 serialize되어야 합니다.|  
|<xref:System.Xml.Serialization.XmlTypeAttribute>|public 클래스 선언입니다.|XML 형식의 이름 및 네임스페이스입니다.|  
  
 모두 <xref:System.Xml.Serialization> 네임스페이스에서 찾을 수 있는 이러한 특성 이외에 <xref:System.ComponentModel.DefaultValueAttribute> 특성도 필드에 적용할 수 있습니다. **DefaultValueAttribute**는 지정된 값이 없는 경우 멤버에 자동으로 할당될 값을 설정합니다.  
  
 인코드된 SOAP XML serialization을 제어하려면 [인코드된 SOAP serialization을 제어하는 특성](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XML 및 SOAP serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [특성을 사용하여 XML serialization 제어](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 [방법: XML 스트림의 대체 요소 이름 지정](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 [방법: 개체 직렬화](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [방법: 개체 deserialize](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
