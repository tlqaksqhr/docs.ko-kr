---
title: "x:FactoryMethod 지시문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 0d53db49961c2a75e4547f6b57240cefd2cc17c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod 지시문
XAML 프로세서는 지원 형식 해결 한 후 개체를 초기화 하는 데 사용 해야 하는 생성자가 아닌 다른 방법을 지정 합니다.  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>XAML 특성 사용, x: 인수  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>XAML 특성 사용, x: 요소와 인수  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`methodname`|XAML 프로세서 호출로 지정 된 인스턴스를 초기화 하는 메서드의 문자열 메서드 이름을 `object`합니다. 설명 부분을 참조하세요.|  
|`oneOrMoreObjectElements`|팩터리 메서드 매개 변수를 지정 하는 개체에 대 한 하나 이상의 개체 요소입니다. 순서는 중요 하지 않습니다. 인수는 팩터리 메서드에 전달 해야 하는 순서를 의미 합니다.|  
  
## <a name="remarks"></a>설명  
 경우 `methodname` 는 인스턴스 메서드이므로 정규화 할 수 없습니다.  
  
 정적 메서드는 팩터리 메서드를 사용할 수 있습니다. 경우 `methodname` 정적 메서드입니다 `methodname` 으로 제공 되는 *typeName*. *methodName* 조합, 여기서 *typeName* 정적 팩터리 메서드를 정의 하는 클래스의 이름을 지정 합니다. *typeName* 접두사로 한정 된 형식에 매핑된 xmlns 참조 하는 경우 일 수 있습니다. *typeName* 와 다른 type 수 `typeof(``object``)`합니다.  
  
 팩터리 메서드는 관련 개체 요소를 지 원하는 형식의 선언된 된 공용 메서드가 이어야 합니다.  
  
 팩터리 메서드는 관련 개체에 할당 될 수 있는 인스턴스를 반환 해야 합니다. 팩터리 메서드가 null을 반환 해야 합니다.  
  
 `x:Arguments`팩터리 메서드의 시그니처에 가장 일치 하는 원칙에서 작동합니다. 일치 하는 매개 변수 개수를 먼저 평가 됩니다. 매개 변수 개수에 대 한 가능한 일치 항목을 여러 개 있으면 계산 되 고 가장 일치 하는 다음 매개 변수 유형이입니다. 이 평가 단계 이후에 모호성도 지 XAML 프로세서 동작이 정의 되지 않습니다.  
  
 `x:FactoryMethod` 지시문 태그가 포함 된 개체 요소 형식을 참조 하지 않기 때문에 요소 사용이 일반적인 의미에서 속성 요소 사용 되지 않습니다. 예상 하지만 해당 요소의 사용 특성 사용 보다 일반적이 지 않습니다. `x:Arguments`(특성 또는 요소 사용)와 함께 사용할 수 있습니다 `x:FactoryMethod` 요소를 사용 하지만이 특별히에 표시 되지 않으면 Usage 섹션.  
  
 `x:FactoryMethod`요소는 다른 속성 요소의 앞에 야, 대로 앞에 야 모든 `x:Arguments` 도 요소로 제공 되며 모든 콘텐츠/내부 텍스트/초기화 텍스트 앞에 야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [x:Arguments 지시문](../../../docs/framework/xaml-services/x-arguments-directive.md)
