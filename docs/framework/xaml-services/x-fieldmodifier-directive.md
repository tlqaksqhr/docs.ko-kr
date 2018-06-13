---
title: x:FieldModifier 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 1c7cb10a8021189aaac0ab8cfe5cc04ff8e67905
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565061"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier 지시문
명명 된 개체 참조에 대 한 필드 정의 된 XAML 컴파일 동작을 수정 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 대신 액세스는 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 기본 동작입니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|*공용*|지정 하기 위해 전달 된 정확한 문자열 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 와 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 사용 되는 코드 숨김 프로그래밍 언어에 따라 달라 집니다. 설명 부분을 참조하세요.|  
  
## <a name="dependencies"></a>종속성  
 XAML 프로덕션에 사용 하는 경우 `x:FieldModifier` 어디에서 든 지 해당 XAML 프로덕션의 루트 요소를 선언 해야 합니다는 [X:class 지시문](../../../docs/framework/xaml-services/x-class-directive.md)합니다.  
  
## <a name="remarks"></a>설명  
 `x:FieldModifier` 클래스 또는 해당 멤버의 일반 액세스 수준 선언에 대 한 관련이 없습니다. XAML 처리 동작에 대해서만 때 관련이 XAML 프로덕션의 일부인 특정 XAML 개체가 처리 되 고 응용 프로그램의 개체 그래프에서 액세스할 수 있는 개체가 됩니다. 기본적으로 소비자는 개체 그래프를 직접 수정할 수 없도록 방지 하는 이러한 개체에 대 한 필드 참조를 비공개로 유지 됩니다. 대신 소비자 레이아웃 루트, 자식 요소 컬렉션을 전용된 공용 속성을 가져옴으로써와 같은 프로그래밍 모델에 의해 설정 된 표준 패턴을 사용 하 여 개체 그래프를 수정 해야 등에입니다.  
  
 에 대 한 값은 `x:FieldModifier` 특성 프로그래밍 언어에 따라 다르며 특정 프레임 워크의 목적은 달라질 수 있습니다. 사용할 문자열을 각 언어 구현 하는 방법에 따라 달라 집니다 해당 <xref:System.CodeDom.Compiler.CodeDomProvider> 및 형식 변환기에 대 한 의미를 정의 하려면 반환 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 및 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, 해당 언어는 대/소문자 구분 여부입니다.  
  
-   C#을 지정 하려면 전달할 문자열 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 은 `public`합니다.  
  
-   Microsoft Visual Basic.NET을 지정 하려면 전달할 문자열에 대 한 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 은 `Public`합니다.  
  
-   에 대 한 [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], XAML 위한 대상이 현재 존재 하는 이므로 전달할 문자열 이므로 정의 되지 않습니다.  
  
 지정할 수도 있습니다 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` C#에서는 `Friend` Visual Basic에서) 지정 하지만 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 별로 사용 되지 않습니다 때문에 `NotPublic` 동작은 기본적으로 이미로 합니다.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 어셈블리 외부의 코드는 XAML을 컴파일한 XAML을 만든 요소에 대 한 액세스를 해야 함을 자주 없기 때문에 기본 동작입니다. WPF 보안 아키텍처 XAML 컴파일 동작와 함께 설정 하지 않으면 공용으로 요소 인스턴스를 저장 하는 필드를 선언 하지 것입니다는 `x:FieldModifier` 공용 액세스를 허용 하도록 합니다.  
  
 `x:FieldModifier` 사용 하 여 요소에만 관련이 [X:name 지시문](../../../docs/framework/xaml-services/x-name-directive.md) 공개 된 후 필드를 참조 하도록 해당 이름을 사용 되기 때문에 있습니다.  
  
 기본적으로 루트 요소에 대 한 partial 클래스는 공용 필드 그러나 해야 public이 아닌를 사용 하 여는 [X:classmodifier 지시문](../../../docs/framework/xaml-services/x-classmodifier-directive.md)합니다. [X:classmodifier 지시문](../../../docs/framework/xaml-services/x-classmodifier-directive.md) 루트 요소 클래스의 인스턴스 액세스 수준에도 영향을 줍니다. 모두 넣을 수 `x:Name` 및 `x:FieldModifier` 루트에 요소를 하지만이 공용 필드의 복사본을 만듭니다는 true 루트 요소 클래스 액세스 수준으로 여전히 루트 요소에 의해 제어 [X:classmodifier 지시문](../../../docs/framework/xaml-services/x-classmodifier-directive.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [WPF의 코드 숨김 및 XAML](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [x:Name 지시문](../../../docs/framework/xaml-services/x-name-directive.md)  
 [WPF 응용 프로그램 빌드(WPF)](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [x:ClassModifier 지시문](../../../docs/framework/xaml-services/x-classmodifier-directive.md)
