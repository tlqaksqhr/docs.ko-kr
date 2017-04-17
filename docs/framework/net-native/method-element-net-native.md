---
title: "&lt;메서드&gt; 요소(.NET 네이티브) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 348b49e5-589d-4eb2-a597-d6ff60ab52d1
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# &lt;메서드&gt; 요소(.NET 네이티브)
생성자 또는 메서드에 런타임 리플렉션 정책을 적용합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<Method Name="method_name"  
        Signature="method_signature"  
        Browse="policy_type"  
        Dynamic="policy_type" />  
  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|특성 형식|설명|  
|---------------|--------------------|-----------------|  
|`Name`|일반|필수 특성입니다. 메서드 이름을 지정합니다.|  
|`Signature`|일반|선택적 특성입니다. 메서드 시그니처를 지정합니다. 매개 변수가 여러 개이면 쉼표로 구분합니다. 예를 들어, 다음 `<Method>` 요소에 대 한 정책 정의 <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29> 메서드.<br /><br /> `<Type Name="System.DateTime">    <Method Name="ToString" Signature="System.String,System.IFormatProvider"            Dynamic="Required" /> </Type>`<br /><br /> 특성이 없으면 런타임 지시문은 메서드의 모든 오버로드에 적용됩니다.|  
|`Browse`|반사|선택적 특성입니다. 메서드에 대한 정보 쿼리 또는 메서드 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.|  
|`Dynamic`|반사|선택적 특성입니다. 동적 프로그래밍을 수행할 수 있도록 생성자 또는 메서드에 대한 런타임 액세스를 제어합니다. 이 정책을 사용하면 런타임에 멤버를 동적으로 호출할 수 있습니다.|  
  
## <a name="name-attribute"></a>Name 특성  
  
|값|설명|  
|-----------|-----------------|  
|*method_name*|메서드 이름입니다. 메서드의 형식은 부모에 의해 정의 된 [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) 또는 [ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소입니다.|  
  
## <a name="signature-attribute"></a>시그니처 특성  
  
|값|설명|  
|-----------|-----------------|  
|*method_signature*|메서드 시그니처를 구성하는 매개 변수 형식입니다. 매개 변수가 여러 개이면 `"System.String,System.Int32,System.Int32)"`와 같이 쉼표로 구분합니다. 매개 변수 형식 이름은 정규화해야 합니다.|  
  
## <a name="all-other-attributes"></a>기타 모든 특성  
  
|값|설명|  
|-----------|-----------------|  
|*policy_setting*|이 정책 형식에 적용할 설정입니다. 가능한 값은 `Auto`, `Excluded`, `Included` 및 `Required`입니다. 자세한 내용은 참조 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/parameter-element-net-native.md)|메서드에 전달된 인수의 형식에 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|제네릭 형식 또는 메서드의 매개 변수 형식에 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/impliestype-element-net-native.md)|포함 `<Method>` 요소가 나타내는 메서드에 정책이 적용된 경우 형식에 해당 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/typeparameter-element-net-native.md)|가 나타내는 형식에 정책을 적용 한 <xref:System.Type> 메서드에 전달 된 인수입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.|  
  
## <a name="remarks"></a>설명  
 제네릭 메서드의 `<Method>` 요소는 자체 정책이 없는 모든 인스턴스화에 해당 정책을 적용합니다.  
  
 `Signature` 특성을 사용하여 특정 메서드 오버로드에 대한 정책을 지정할 수 있습니다. `Signature` 특성이 없는 경우 런타임 지시문은 메서드의 모든 오버로드에 적용됩니다.  
  
 `<Method>` 요소를 사용하여 생성자에 대해 런타임 리플렉션 정책을 정의할 수는 없습니다. Instead, use the `Activate` attribute of the  [<>\>](../../../docs/framework/net-native/assembly-element-net-native.md), [<>\>](../../../docs/framework/net-native/namespace-element-net-native.md), [<>\>](../../../docs/framework/net-native/type-element-net-native.md), or [<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.  
  
## <a name="example"></a>예제  
 다음 예제의 `Stringify` 메서드는 리플렉션을 사용하여 개체를 문자열 표현으로 변환하는 범용 서식 지정 메서드입니다. 개체의 기본을 호출 하는 것 외에도 `ToString` 메서드를 메서드는 개체를 전달 하 여 서식이 지정 된 결과 문자열을 생성 수 `ToString` 메서드는 형식 문자열을 한 <xref:System.IFormatProvider> 구현 중 하나 또는 둘 다. 중 하나를 호출할 수도 있습니다는 <xref:System.Convert.ToString%2A?displayProperty=fullName> 숫자를 이진,&16; 진수 또는&8; 진수 표현으로 변환 하는 오버 로드 합니다.  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 다음과 같은 코드를 통해 `Stringify` 메서드를 호출할 수 있습니다.  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 그러나.NET 네이티브에서 컴파일하면 예제 수는 여러 예외가 throw 런타임에 포함 하 여 <xref:System.NullReferenceException> 및 [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) 예외,이 때문에 발생는 `Stringify` 방법은 동적으로.NET Framework 클래스 라이브러리의 기본 형식 서식 지정을 지 원하는 데 주로 사용 됩니다. 기본 지시문 파일이 해당 메타데이터를 제공하지 않기 때문입니다. 그러나 해당 메타 데이터를 사용할 수 있는 경우에 예제에서는 throw [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) 예외 때문에 적절 한 `ToString` 구현이 네이티브 코드에 포함 되지 않았기 합니다.  
  
 이러한 예외 제거할 수를 사용 하 여는 [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) 고, 추가 하 여 해당 메타 데이터가 있어야 하는 형식을 정의 하는 요소 `<Method>` 메서드의 구현에서는 가능한 오버 로드 하는 요소 수 동적으로 호출할도 제공 됩니다. 다음은 이러한 예외를 방지하고 예제가 오류 없이 실행되도록 하는 default.rd.xml 파일입니다.  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <Assembly Name="*Application*" Dynamic="Required All" />  
  
     <Type Name = "System.Convert" Browse="Required Public" Dynamic="Required Public" >  
        <Method Name="ToString"    Dynamic ="Required" />  
     </Type>  
     <Type Name="System.Double" Browse="Required Public">  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int32" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int64" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Namespace Name="System" >  
        <Type Name="Byte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="DateTime" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Decimal" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Guid" Browse ="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Int16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="SByte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Single" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="TimeSpan" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="UInt16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt32" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt64" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
     </Namespace>  
  </Application>  
</Directives>  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 지시문 (rd.xml) 구성 파일 참조](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [런타임 지시문 요소](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [<>\>요소](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)