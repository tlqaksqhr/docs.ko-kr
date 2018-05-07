---
title: '&lt;유형&gt; 요소(.NET 네이티브)'
ms.date: 03/30/2017
ms.assetid: 1e88d368-a886-4f1e-8eb6-6127979a9fce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad20cf4528f5ca7d23f80570cc34712d33b74d93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="lttypegt-element-net-native"></a>&lt;유형&gt; 요소(.NET 네이티브)
클래스 또는 구조체와 같은 특정 형식에 런타임 정책을 적용합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<Type Name="type_name"  
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
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|특성 형식|설명|  
|---------------|--------------------|-----------------|  
|`Name`|일반|필수 특성입니다. 형식 이름을 지정합니다.|  
|`Activate`|반사|선택적 특성입니다. 인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.|  
|`Browse`|반사|선택적 특성입니다. 프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.|  
|`Dynamic`|반사|선택적 특성입니다. 동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.|  
|`Serialize`|Serialization|선택적 특성입니다. Newtonsoft JSON serializer 등의 라이브러리를 통해 형식 인스턴스를 serialize 및 deserialize할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.|  
|`DataContractSerializer`|Serialization|선택적 특성입니다. <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.|  
|`DataContractJsonSerializer`|Serialization|선택적 특성입니다. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.|  
|`XmlSerializer`|Serialization|선택적 특성입니다. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.|  
|`MarshalObject`|Interop|선택적 특성입니다. Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.|  
|`MarshalDelegate`|Interop|선택적 특성입니다. 네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.|  
|`MarshalStructure`|Interop|선택적 특성입니다. 값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.|  
  
## <a name="name-attribute"></a>Name 특성  
  
|값|설명|  
|-----------|-----------------|  
|*type_name*|형식 이름입니다. 이 `<Type>` 요소가 [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md) 요소 또는 다른 `<Type>` 요소의 자식인 경우 *type_name*은 네임스페이스가 없는 형식 이름을 포함할 수 있습니다. 그러지 않으면 *type_name*은 정규화된 형식 이름을 포함해야 합니다.|  
  
## <a name="all-other-attributes"></a>기타 모든 특성  
  
|값|설명|  
|-----------|-----------------|  
|*policy_setting*|이 정책 형식에 적용할 설정입니다. 가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다. 자세한 내용은 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)을 참조하세요.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<AttributeImplies>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)|포함 형식이 특성이면 해당 특성이 적용되는 코드 요소에 대해 런타임 정책을 정의합니다.|  
|[\<Event>](../../../docs/framework/net-native/event-element-net-native.md)|이 형식에 속하는 이벤트에 리플렉션 정책을 적용합니다.|  
|[\<Field>](../../../docs/framework/net-native/field-element-net-native.md)|이 형식에 속하는 필드에 리플렉션 정책을 적용합니다.|  
|[\<GenericParameter>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|제네릭 형식의 매개 변수 형식에 정책을 적용합니다.|  
|[\<ImpliesType>](../../../docs/framework/net-native/impliestype-element-net-native.md)|포함 `<Type>` 요소가 나타내는 형식에 정책이 적용된 경우 형식에 해당 정책을 적용합니다.|  
|[\<Method>](../../../docs/framework/net-native/method-element-net-native.md)|이 형식에 속하는 메서드에 리플렉션 정책을 적용합니다.|  
|[\<MethodInstantiation>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|이 형식에 속하는 생성된 제네릭 메서드에 리플렉션 정책을 적용합니다.|  
|[\<Property>](../../../docs/framework/net-native/property-element-net-native.md)|이 형식에 속하는 속성에 리플렉션 정책을 적용합니다.|  
|[\<Subtypes>](../../../docs/framework/net-native/subtypes-element-net-native.md)|포함 형식에서 상속된 모든 클래스에 런타임 정책을 적용합니다.|  
|`<Type>`|중첩된 형식에 리플렉션 정책을 적용합니다.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|생성된 제네릭 형식에 리플렉션 정책을 적용합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 응용 프로그램 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다.|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|지정된 어셈블리의 모든 형식에 리플렉션 정책을 적용합니다.|  
|[\<Library>](../../../docs/framework/net-native/library-element-net-native.md)|런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.|  
|[\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)|네임스페이스의 모든 형식에 리플렉션 정책을 적용합니다.|  
|`<Type>`|형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.|  
  
## <a name="remarks"></a>설명  
 리플렉션, serialization 및 interop 특성은 모두 선택 사항입니다. 이러한 특성이 없으면 `<Type>` 요소는 하위 형식이 개별 멤버의 정책을 정의하는 컨테이너로 사용됩니다.  
  
 `<Type>` 요소는 [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md), [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md), `<Type>` 또는 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 자식인 경우 부모 요소가 정의하는 정책 설정을 재정의합니다.  
  
 제네릭 형식의 `<Type>` 요소는 자체 정책이 없는 모든 인스턴스화에 해당 정책을 적용합니다. 생성된 제네릭 형식의 정책은 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소에 의해 정의됩니다.  
  
 제네릭 형식의 경우 해당 이름은 억음 악센트 기호(\`)와 제네릭 매개 변수의 수가 차례로 붙는 형식으로 데코레이팅됩니다. 예를 들어 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 클래스 `<Type>` 요소의 `Name` 특성은 `Name="System.Collections.Generic.List`1”`로 표시됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 리플렉션을 사용하여 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 클래스의 필드, 속성 및 메서드에 대한 정보를 표시합니다. 예제의 `b` 변수는 [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) 컨트롤입니다. 이 예제에서는 형식 정보만 검색하므로 메타데이터 사용 가능 여부는 `Browse` 정책 설정에 의해 제어됩니다.  
  
 [!code-csharp[ProjectN_Reflection#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/browsegenerictype1.cs#3)]  
  
 <xref:System.Collections.Generic.List%601> 클래스의 메타데이터는 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 도구 체인에 의해 자동으로 포함되지 않으므로 이 예제는 런타임에 요청된 멤버 정보를 표시하지 못합니다. 필요한 메타데이터를 제공하려면 다음 `<Type>` 요소를 런타임 지시문 파일에 추가합니다. 여기서는 부모 [<Namespace\>](../../../docs/framework/net-native/namespace-element-net-native.md) 요소를 제공했으므로 `<Type>` 요소에 정규화된 형식 이름을 제공하지 않아도 됩니다.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="*Application*" Dynamic="Required All" />  
      <Namespace Name ="System.Collections.Generic" >  
        <Type Name="List`1" Browse="Required All" />   
     </Namespace>  
   </Application>  
</Directives>  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 리플렉션을 사용하여 <xref:System.Reflection.PropertyInfo> 속성을 나타내는 <xref:System.String.Chars%2A?displayProperty=nameWithType> 개체를 검색합니다. 그런 다음 <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> 메서드를 사용하여 문자열에서 7번째 문자의 값을 검색하고 문자열의 모든 문자를 표시합니다. 예제의 `b` 변수는 [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) 컨트롤입니다.  
  
 [!code-csharp[ProjectN_Reflection#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/propertyinfo1.cs#1)]  
  
 <xref:System.String> 개체의 메타데이터를 사용할 수 없으므로 <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> 도구 체인으로 컴파일한 경우 <xref:System.NullReferenceException> 메서드를 호출하면 런타임에 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 예외가 throw됩니다. 예외를 방지하고 필요한 메타데이터를 제공하려면 다음 `<Type>` 요소를 런타임 지시문 파일에 추가합니다.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
    <Type Name="System.String" Dynamic="Required Public"/> -->  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 지시문(rd.xml) 구성 파일 참조](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [런타임 지시문 요소](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
