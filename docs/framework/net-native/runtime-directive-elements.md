---
title: "런타임 지시문 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2566c5ebe8c94610c8f7e258da7c77adb86a49f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="runtime-directive-elements"></a>런타임 지시문 요소
런타임 지시문(rd.xml) 파일 형식은 다음 지시문 런타임 요소를 지원합니다. 계층적 표현에 대해서는 [런타임 지시문(rd.xml) 구성 파일 참조](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)를 참조하세요.  
  
 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)  
 앱에서 사용하는 모든 형식에 런타임 리플렉션 정책을 적용합니다. 런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 응용 프로그램 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다. 이 요소는 [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) 요소의 자식입니다.  
  
 [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)  
 런타임 정책을 어셈블리의 모든 형식에 적용합니다. 이 요소는 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 및 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 요소의 자식입니다.  
  
 [\<AttributeImplies>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)  
 포함 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 지시문이 특성이면 해당 특성이 적용되는 코드 요소에 런타임 정책을 적용합니다.  
  
 [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)]용 모든 런타임 지시문의 루트 요소입니다. 해당 자식 요소는 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 및 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)입니다.  
  
 [\<Event>](../../../docs/framework/net-native/event-element-net-native.md)  
 런타임 정책을 이벤트에 적용합니다. 이 요소는 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 및 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 자식입니다.  
  
 [\<Field>](../../../docs/framework/net-native/field-element-net-native.md)  
 런타임 정책을 필드에 적용합니다. 이 요소는 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 및 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 자식입니다.  
  
 [\<GenericParameter>](../../../docs/framework/net-native/genericparameter-element-net-native.md)  
 제네릭 형식 또는 메서드의 매개 변수 형식에 런타임 정책을 적용합니다.  
  
 [\<ImpliesType>](../../../docs/framework/net-native/impliestype-element-net-native.md)  
 포함 형식 또는 메서드에 런타임 정책이 적용된 경우 해당 정책을 형식에 적용합니다.  
  
 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)  
 런타임 정책을 어셈블리의 모든 형식에 적용합니다. 이 요소는 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 및 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 요소의 자식입니다.  
  
 [\<Method>](../../../docs/framework/net-native/method-element-net-native.md)  
 런타임 정책을 메서드에 적용합니다. 이 요소는 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 및 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 자식입니다.  
  
 [\<MethodInstantiation>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)  
 생성된 제네릭 메서드에 런타임 정책을 적용합니다. 이 요소는 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 및 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 자식입니다.  
  
 [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)  
 네임스페이스의 모든 형식에 런타임 정책을 적용합니다.  
  
 [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md)  
 메서드에 전달된 인수의 형식에 런타임 정책을 적용합니다.  
  
 [\<Property>](../../../docs/framework/net-native/property-element-net-native.md)  
 런타임 정책을 속성에 적용합니다. 이 요소는 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 및 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 자식입니다.  
  
 [\<Subtypes>](../../../docs/framework/net-native/subtypes-element-net-native.md)  
 포함 형식에서 상속된 모든 클래스에 런타임 정책을 적용합니다.  
  
 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)  
 런타임 정책을 형식에 적용합니다.  
  
 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)  
 생성된 제네릭 형식에 런타임 정책을 적용합니다.  
  
 [\<TypeParameter>](../../../docs/framework/net-native/typeparameter-element-net-native.md)  
 메서드로 전달된 <xref:System.Type> 인수가 나타내는 형식에 런타임 정책을 적용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [rd.xml 구성 파일 참조](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
