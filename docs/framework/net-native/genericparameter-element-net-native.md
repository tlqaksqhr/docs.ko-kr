---
title: "&lt;GenericParameter&gt; 요소(.NET 네이티브) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# &lt;GenericParameter&gt; 요소(.NET 네이티브)
제네릭 형식 또는 메서드의 매개 변수 형식에 정책을 적용합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type" />  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|특성 형식|설명|  
|---------------|--------------------|-----------------|  
|`Name`|일반|필수 특성입니다. 제네릭 매개 변수의 이름입니다. 제네릭 대리자에 대 한 예를 들어 <xref:System.Func%603>의 값은 `Name` 특성은 "TResult" 런타임 정책을 대리자의 반환 값에 적용할.\</T1, T2, TResult>|  
|`Activate`|반사|선택적 특성입니다. 인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.|  
|`Browse`|반사|선택적 특성입니다. 프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.|  
|`Dynamic`|반사|선택적 특성입니다. 동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.|  
|`Serialize`|Serialization|선택적 특성입니다. Newtonsoft JSON serializer 등의 라이브러리를 통해 형식 인스턴스를 serialize 및 deserialize할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.|  
|`DataContractSerializer`|Serialization|선택적 특성입니다. 정책을 사용 하는 serialization에 대 한 제어는 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> 클래스입니다.|  
|`DataContractJsonSerializer`|Serialization|선택적 특성입니다. 정책을 사용 하는 JSON serialization에 대 한 제어는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> 클래스입니다.|  
|`XmlSerializer`|Serialization|선택적 특성입니다. 정책을 사용 하는 XML serialization에 대 한 제어는 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> 클래스입니다.|  
|`MarshalObject`|Interop|선택적 특성입니다. Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.|  
|`MarshalDelegate`|Interop|선택적 특성입니다. 네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.|  
|`MarshalStructure`|Interop|선택적 특성입니다. 값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.|  
  
## <a name="name-attribute"></a>Name 특성  
  
|값|설명|  
|-----------|-----------------|  
|*generic_parameter_name*|필수 특성입니다. 제네릭 형식 매개 변수의 이름입니다. 제네릭 대리자에 대 한 예를 들어 <xref:System.Func%603>, *generic_parameter_name* 의 값이 "TResult" 런타임 정책을 대리자의 반환 값에 적용 합니다.\</T1, T2, TResult>|  
  
## <a name="all-other-attributes"></a>기타 모든 특성  
  
|값|설명|  
|-----------|-----------------|  
|*policy_setting*|이 정책 형식에 적용할 설정입니다. 가능한 값은 `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다. 자세한 내용은 참조 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|생성자 또는 메서드에 런타임 리플렉션 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|클래스 또는 구조체와 같은 특정 형식에 런타임 리플렉션 정책을 적용합니다.|  
  
## <a name="remarks"></a>설명  
 `<GenericParameter>` 요소는 자식은 [ <> \> ](../../../docs/framework/net-native/method-element-net-native.md) 또는 [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) 요소는 제네릭 형식 또는 메서드 시그니처에서 해당 이름으로 지정 되는 특정 제네릭 형식 매개 변수에 정책을 적용 하는 데 사용 됩니다.  
  
 `<GenericParameter>` 요소는 serializer와 함께 사용하면 가장 유용합니다. 다음 예제에서는 `<GenericParameter>` 요소 형식에 정책을 적용 하려면 `T` NewtonSoft JSON serializer에 대 한 호출에서 [JsonConvert.DeserializeObject<>\>(String)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm) 메서드 오버 로드 합니다.  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [<>\>요소](../../../docs/framework/net-native/method-element-net-native.md)   
 [<>\>요소](../../../docs/framework/net-native/type-element-net-native.md)   
 [런타임 지시문 (rd.xml) 구성 파일 참조](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [런타임 지시문 요소](../../../docs/framework/net-native/runtime-directive-elements.md)