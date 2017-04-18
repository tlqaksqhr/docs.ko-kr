---
title: "Serialization1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Serialization
Serialization은 개체 쉽게 유지 또는 전송할 수 있는 형식으로 변환 합니다. 예를 들어 개체 serialize를 HTTP를 사용 하 고 대상 컴퓨터에서 역직렬화 할 인터넷을 통해 전송할 수 있습니다.  
  
 .NET Framework는 다양 한 serialization 시나리오에 맞게 최적화 하는 세 가지 기본 serialization 기술을 제공 합니다. 다음 표에서 이러한 기술 및 해당이 기술과 관련 된 기본 Framework 형식을 나열 합니다.  
  
|**기술 이름**|**기본 형식**|**시나리오**|  
|---------------|---------------|--------------|  
|**데이터 계약 Serialization**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|일반 지 속성<br />웹 서비스<br />JSON|  
|**XML Serialization**|<xref:System.Xml.Serialization.XmlSerializer>|XML 형식으로 전체 XML의 모양 제어 하 여|  
|**런타임 Serialization \(이진 및 SOAP\)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|  
  
 **✓ 수행** serialization 새로운 형식을 디자인할 때 고려해 야 합니다.  
  
## 지원에 올바른 Serialization 기술 선택  
 **✓ 고려** 형식의 인스턴스가 유지 되거나 웹 서비스에서 사용 되어야 할 수 있는 경우 데이터 계약 Serialization을 지원 합니다.  
  
 **✓ 고려** 형식이 serialize 될 때 생성 되는 XML 형식 보다 더 많은 제어 해야 하는 경우 대신 또는 데이터 계약 Serialization 외에도 XML Serialization을 지원 합니다.  
  
 이 일부 상호 운용성에 XML 사용 하 여 필요한 시나리오 생성 지원 되지 않는 데이터 계약 Serialization에서 예를 들어 XML 특성을 생성 하는 할 수 있습니다.  
  
 **✓ 고려** 형식의 인스턴스에서.NET Remoting 경계를 통과 하는 경우 런타임 Serialization을 지원 합니다.  
  
 **X 방지** 일반적인 지 속성 이유에 대해서만 런타임 Serialization 또는 XML Serialization을 지원 합니다. 데이터 계약 Serialization을 더 선호 합니다.  
  
## 데이터 계약 Serialization 지원  
 형식은 적용 하 여 데이터 계약 Serialization을 지원할 수는 <xref:System.Runtime.Serialization.DataContractAttribute> 형식에 및 <xref:System.Runtime.Serialization.DataMemberAttribute> 형식의 멤버 \(필드 및 속성\)에 있습니다.  
  
 **✓ 고려** 형식을 부분 신뢰 환경에서 사용할 수 있는 경우 형식이 공용 데이터 멤버를 표시 합니다.  
  
 완전 신뢰에서 데이터 계약 serializer을 serialize 및 public이 아닌 형식과 멤버를 deserialize 할 수 있지만 공용 멤버만 직렬화 및 부분 신뢰 환경에서 역직렬화 할 수 있습니다.  
  
 **✓ 수행** 되어 있는 모든 속성에 getter 및 setter를 구현 <xref:System.Runtime.Serialization.DataMemberAttribute>합니다. 데이터 계약 serializer에 getter와 setter 되려면 직렬화 가능 형식에 대 한 필요 합니다. \(.NET Framework 3.5 s p 1에서는 일부 컬렉션 속성 수 가져오기 전용입니다.\) 부분 신뢰 환경에서 사용 하지 않을 형식의 속성 접근자 중 하나 또는 모두가 public이 아닌 수 있습니다.  
  
 **✓ 고려** deserialize 된 인스턴스의 초기화에 대 한 serialization 콜백을 사용 합니다.  
  
 생성자는 개체가 deserialize 될 때는 호출 되지 않습니다. \(규칙의 예외는. 컬렉션의 생성자로 표시 된 <xref:System.Runtime.Serialization.CollectionDataContractAttribute> deserialization 중에 호출 됩니다.\) 따라서 정상적인 생성 하는 동안 실행 되는 논리는 serialization 콜백을 중 하나로 구현 해야 합니다.  
  
 `OnDeserializedAttribute` 가장 일반적으로 사용 되는 콜백 특성이입니다. 제품군의 다른 특성은 <xref:System.Runtime.Serialization.OnDeserializingAttribute>,  <xref:System.Runtime.Serialization.OnSerializingAttribute>, 및 <xref:System.Runtime.Serialization.OnSerializedAttribute>합니다. 이러한 각각 serialization 전후 마지막으로, serialization, deserialization을 수행 하기 전에 실행 되는 콜백을 표시 하는 데 사용 될 수 있습니다.  
  
 **✓ 것이 좋습니다** 를 사용 하는 <xref:System.Runtime.Serialization.KnownTypeAttribute> 복잡 한 개체 그래프를 역직렬화 할 때 사용 해야 하는 추상 형식을 나타냅니다.  
  
 **✓ 수행** 만들거나 직렬화 형식을 변경할 때 뒤로 및 앞으로 호환성을 고려해 야 합니다.  
  
 Serialize 된 스트림을의 이후 버전의 형식에서 형식의 현재 버전으로 deserialize 할 수 또는 그 반대로 합니다.  
  
 데이터 계약 특성을 명시적 매개 변수를 사용 하 여 계약을 유지 하기 위해 특별 한 주의 하지 않는 한 해당 이름, 형식 또는 이후 버전의 형식에서 순서도도 개인 및 내부 데이터 멤버를 변경할 수 없습니다를 이해 하 고 있는지 확인 합니다.  
  
 직렬화 가능 형식으로 변경 하는 경우 직렬화의 호환성을 테스트 합니다. 새 버전은 이전 버전으로 역직렬화 하는 동안 시도 하 고 그 반대의 경우도 마찬가지입니다.  
  
 **✓ 고려** 구현 <xref:System.Runtime.Serialization.IExtensibleDataObject> 서로 다른 버전의 형식 간에 라운드트립이 가능 하도록 합니다.  
  
 라운드트립 시 데이터가 손실 된다는 것을 확인 하는 serializer를 사용 하는 인터페이스입니다.<xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=fullName> 속성은 현재 버전에서는 알 수 없는 형식의 이후 버전에서 모든 데이터를 저장 하는 데 사용 하 고 있으므로 데이터 멤버에 저장할 것 수 없습니다. 현재 버전은 이후에으로 serialize 하거나 deserialize 이후 버전, 추가 데이터 될 때 사용할 수 있는 serialize 된 스트림의 합니다.  
  
## XML Serialization 지원  
 데이터 계약 Serialization 주 \(기본값\)은.NET Framework의 serialization 기술 이지만 데이터 계약 Serialization을 지원 하지 않는 serialization 시나리오도 있습니다. 예를 들어 serializer에서 생성 하거나 사용 하는 XML의 모양 대 한 모든 권한을 부여 하지 않습니다. 이러한 세밀 하 게 제어가 필요한 경우 XML Serialization을 사용할 수 있으며이 serialization 기술을 지원 하기 위한 형식을 디자인 해야 합니다.  
  
 **X 방지** 생성 되는 XML의 모양을 제어 하는 매우 강력한 이유가 없다면 XML serialization 형식을 디자인 합니다. 이 serialization 기술은 이전 섹션에서 설명한 데이터 계약 Serialization으로 대체 되었습니다.  
  
 **✓ 고려** 구현는 <xref:System.Xml.Serialization.IXmlSerializable> XML Serialization 특성을 적용 하 여 제공 된 것 보다는 serialize 된 XML의 모양 보다 더 많은 제어 하려는 경우 인터페이스입니다. 인터페이스의 두 가지 방법 <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> 및 <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, serialize 된 XML 스트림을 완전히 제어할 수 있습니다. 적용 하 여 형식에 대해 생성 되는 XML 스키마를 제어할 수 있습니다는 `XmlSchemaProviderAttribute`합니다.  
  
## 런타임 Serialization 지원  
 런타임 Serialization에는.NET Remoting에서 사용 하는 기술입니다. .NET Remoting을 사용 하 여 형식이 전송 될 것을 생각 되는 경우 런타임 Serialization을 지원 하는지 확인 해야 합니다.  
  
 적용 하 여 런타임 Serialization에 대 한 기본 지원을 제공할 수 있습니다는 <xref:System.SerializableAttribute>, 고급 시나리오에는 포함 간단한 런타임 직렬화 가능한 패턴을 구현 하 고 \(구현 <xref:System.Runtime.Serialization.ISerializable> serialization 생성자를 제공 하 고\).  
  
 **✓ 고려** 형식을.NET Remoting과 함께 사용 될 경우 런타임 Serialization을 지원 합니다. 예를 들어는 <xref:System.AddIn?displayProperty=fullName> 간에 교환 되는 모든 형식 및.NET Remoting을 사용 하는 네임 스페이스 `System.AddIn` 추가 기능의 런타임 Serialization을 지원 해야 합니다.  
  
 **✓ 고려** 완벽 하 게 serialization 프로세스 제어 하려는 경우 런타임 직렬화 가능한 패턴을 구현 합니다. 예를 들어 데이터를 변환 하려면 직렬화 또는 역직렬화 가져옵니다 것입니다.  
  
 패턴은 매우 간단 합니다. 하기만 하면는 구현 하는 <xref:System.Runtime.Serialization.ISerializable> 인터페이스 및 개체가 deserialize 될 때 사용 되는 특별 한 생성자를 제공 합니다.  
  
 **✓ 수행** serialization 생성자를 보호 하 고 입력 하 고이 예제에 표시 된 대로 정확 하 게 명명 된 두 개의 매개 변수를 제공 합니다.  
  
```  
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}  
```  
  
 **✓ 수행** 구현는 `ISerializable` 멤버가 명시적으로 합니다.  
  
 **✓ 수행** 에 링크 요청을 적용할 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 구현 합니다. 이렇게 하면 완전히 신뢰할 수 있는 코어 및 런타임 Serializer가 멤버에 액세스할 수 있습니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)