---
title: "&lt;TypeInstantiation&gt; 요소(.NET 네이티브) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5eada64-075b-4162-9655-ded84e4681f2
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# &lt;TypeInstantiation&gt; 요소(.NET 네이티브)
생성된 제네릭 형식에 런타임 리플렉션 정책을 적용합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<TypeInstantiation Name="type_name"  
                   Arguments="type_arguments"  
                   Activate="policy_type"  
                   Browse="policy_type"  
                   Dynamic="policy_type"  
                   Serialize="policy_type"  
                   DataContractSerializer="policy_setting"  
                   DataContractJsonSerializer="policy_setting"  
                   XmlSerializer="policy_setting"  
                   MarshalObject="policy_setting"  
                   MarshalDelegate="policy_setting"  
                   MarshalStructure="policy_setting" />  
  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|특성 형식|설명|  
|---------------|--------------------|-----------------|  
|`Name`|일반|필수 특성입니다. 형식 이름을 지정합니다.|  
|`Arguments`|일반|필수 특성입니다. 제네릭 형식 인수를 지정합니다. 인수가 여러 개이면 쉼표로 구분합니다.|  
|`Activate`|반사|선택적 특성입니다. 인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.|  
|`Browse`|반사|선택적 특성입니다. 프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.|  
|`Dynamic`|반사|선택적 특성입니다. 동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.|  
|`Serialize`|Serialization|선택적 특성입니다. Newtonsoft JSON serializer 등의 라이브러리를 통해 형식 인스턴스를 serialize 및 deserialize할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.|  
|`DataContractSerializer`|Serialization|선택적 특성입니다. 정책을 사용 하는 serialization에 대 한 제어는 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> 클래스입니다.|  
|`DataContractJsonSerializer`|Serialization|선택적 특성입니다. 정책을 사용 하는 JSON serialization에 대 한 제어는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> 클래스입니다.|  
|`XmlSerializer`|Serialization|선택적 특성입니다. 정책을 사용 하는 XML serialization에 대 한 제어는 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> 클래스입니다.|  
|`MarshalObject`|Interop|선택적 특성입니다. Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.|  
|`MarshalDelegate`|Interop|선택적 특성입니다. 네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.|  
|`MarshalStructure`|Interop|선택적 특성입니다. 구조체를 네이티브 코드로 마샬링하는 정책을 제어합니다.|  
  
## <a name="name-attribute"></a>Name 특성  
  
|값|설명|  
|-----------|-----------------|  
|*type_name*|형식 이름입니다. 이 경우 `<TypeInstantiation>` 의 자식 요소입니다는 [ <> \> ](../../../docs/framework/net-native/namespace-element-net-native.md) 요소는 [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) 요소 또는 다른 `<TypeInstantiation>` 요소를 *type_name* 네임 스페이스가 없는 형식 이름을 지정할 수 있습니다. 그렇지 않으면 *type_name* 정규화 된 형식 이름을 포함 해야 합니다. 형식 이름은 데코레이팅되지 않습니다. 예를 들어는 <xref:System.Collections.Generic.List%601?displayProperty=fullName> 개체는 `<TypeInstantiation>` 요소는 다음과 같이 표시 될 수 있습니다.<br /><br /> `\<TypeInstantiation Name=System.Collections.Generic.List Dynamic="Required Public" />`|  
  
## <a name="arguments-attribute"></a>인수 특성  
  
|값|설명|  
|-----------|-----------------|  
|*type_argument*|제네릭 형식 인수를 지정합니다. 인수가 여러 개이면 쉼표로 구분합니다. 각 인수는 정규화된 형식 이름으로 구성되어야 합니다.|  
  
## <a name="all-other-attributes"></a>기타 모든 특성  
  
|값|설명|  
|-----------|-----------------|  
|*policy_setting*|생성된 제네릭 형식에 대해 이 정책 형식에 적용할 설정입니다. 가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다. 자세한 내용은 참조 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/event-element-net-native.md)|이 형식에 속하는 이벤트에 리플렉션 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/field-element-net-native.md)|이 형식에 속하는 필드에 리플렉션 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/impliestype-element-net-native.md)|포함 `<TypeInstantiation>` 요소가 나타내는 형식에 정책이 적용된 경우 형식에 해당 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|이 형식에 속하는 메서드에 리플렉션 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|이 형식에 속하는 생성된 제네릭 메서드에 리플렉션 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/property-element-net-native.md)|이 형식에 속하는 속성에 리플렉션 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|중첩된 형식에 리플렉션 정책을 적용합니다.|  
|`<TypeInstantiation>`|생성된 중첩 제네릭 형식에 리플렉션 정책을 적용합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/application-element-net-native.md)|런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 응용 프로그램 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다.|  
|[<>\>](../../../docs/framework/net-native/assembly-element-net-native.md)|지정된 어셈블리의 모든 형식에 리플렉션 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/library-element-net-native.md)|런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.|  
|[<>\>](../../../docs/framework/net-native/namespace-element-net-native.md)|네임스페이스의 모든 형식에 리플렉션 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.|  
|`<TypeInstantiation>`|생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.|  
  
## <a name="remarks"></a>설명  
 리플렉션, serialization 및 interop 특성은 모두 선택 사항입니다. 그러나 이러한 특성이 하나 이상 있어야 합니다.  
  
 하는 경우는 `<TypeInstantiation>` 요소는 자식은 [ <> \</> \> ](../../../docs/framework/net-native/assembly-element-net-native.md), [ <> \</> \> ](../../../docs/framework/net-native/namespace-element-net-native.md), 또는 [ <> \</> \> ](../../../docs/framework/net-native/type-element-net-native.md), 요소를 부모 요소에 의해 정의 된 정책 설정을 재정의 합니다. 하는 경우는 [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) 요소 정의 해당 제네릭 형식 정의 `<TypeInstantiation>` 요소는 지정한 생성 된 제네릭 형식의 인스턴스화에 대해서만 런타임 리플렉션 정책을 재정의 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 리플렉션을 사용 하 여에서 생성 된 제네릭 형식 정의 검색할 <xref:System.Collections.Generic.Dictionary%602> 개체.</TKey, TValue> 또한 리플렉션을 대 한 정보를 표시를 사용 하 여 <xref:System.Type> 생성 된 제네릭 형식 및 제네릭 형식 정의 나타내는 개체입니다. 변수 `b` 예제는 한 [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) 제어 합니다.  
  
 [!code-csharp[ProjectN_Reflection#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/makegenerictype1.cs#2)]  
  
 사용 하 여 컴파일하면는 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 도구 체인을 예제에서는 throw 한 [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) 호출 하는 줄에서 예외는 <xref:System.Type.GetGenericTypeDefinition%2A?displayProperty=fullName> 메서드. 다음 `<TypeInstantiation>` 요소를 런타임 지시문 파일에 추가하면 예외를 방지하고 필요한 메타데이터를 제공할 수 있습니다.  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
     <TypeInstantiation Name="System.Collections.Generic.Dictionary"  
                        Arguments="System.String,GenericType.Example"  
                        Dynamic="Required Public" />  
  </Application>  
</Directives>  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 지시문 (rd.xml) 구성 파일 참조](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [런타임 지시문 요소](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)