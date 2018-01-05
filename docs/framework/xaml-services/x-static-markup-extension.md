---
title: "x:Static 태그 확장명"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
caps.latest.revision: "25"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 647bfed7b321a949090f6da047f9b8105d335101
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xstatic-markup-extension"></a>x:Static 태그 확장명
에 정의 된 모든 값으로 정적 코드 엔터티 참조는 [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]– 규정을 준수 하는 방법입니다. 참조 되는 정적 속성 XAML에서 속성의 값을 제공 데 사용할 수 있습니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`prefix`|선택 사항입니다. 매핑된, 기본이 아닌 XAML 네임 스페이스를 참조 하는 접두사입니다. `prefix`명시적으로 표시 사용에서 기본 XAML 네임 스페이스에서 제공 하는 정적 속성을 거의 참조 하지 않기 때문입니다. 설명 부분을 참조하세요.|  
|`typeName`|필수. 원하는 정적 멤버를 정의 하는 유형의 이름입니다.|  
|`staticMemberName`|필수. 원하는 정적 값 멤버 (상수, 정적 속성, 필드 또는 열거형 값)의 이름입니다.|  
  
## <a name="remarks"></a>설명  
 참조 되는 코드 엔터티는 다음 중 하나 여야 합니다.  
  
-   상수  
  
-   정적 속성  
  
-   필드  
  
-   열거형 값  
  
 비정적 속성 같은 기타 코드 엔터티를 지정 하면 인지 XAML 태그 컴파일된 XAML 로드 시간 구문 분석 예외를 컴파일 타임 오류가 발생 합니다.  
  
 그러나 만들 수 있습니다 `x:Static` 정적 필드 또는 현재 XAML 문서에 대 한 기본 XAML 네임 스페이스에 없는 속성에 대 한 참조 접두사 매핑이 이렇게 해야 합니다. XAML 네임 스페이스는 거의 항상 XAML 문서의 루트 요소에 정의 됩니다.  
  
 기본 XAML 스키마 컨텍스트를 실행 하는 경우.NET Framework XAML 서비스 XAML 판독기 및 XAML 작성기에서 정적 속성에 대 한 조회 작업을 수행할 수 있습니다. 이 XAML 스키마 컨텍스트는 CLR 리플렉션을 사용 하 여 개체 그래프 생성에 필요한 정적 값을 제공 하도록 수 있습니다. `typeName` 지정는 실제로 XAML 형식 이름, CLR 형식 이름이 아니라 이름이 같은 기본적으로 모든 기존 CLR 기반 XAML 구현 프레임 워크를 사용 하는 경우 또는 기본 XAML 스키마 컨텍스트를 사용 하는 경우.  
  
 주의 해야 할 때 사용 하 여 `x:Static` 는 속성의 값의 형식을 참조 합니다. XAML에서 처리는 태그 확장에서 값을 제공 하는 시퀀스는 가치를 더하는 변환을 호출 하지 않습니다. 이 true 인 경우에 프로그램 `x:Static` 참조 텍스트 문자열을 생성 하 고 일반적으로 텍스트 문자열에 따라 특성 값에 대 한 값 변환 발생 또는 해당 특정 멤버에 대 한 반환 형식의 모든 멤버 값에 대 한 합니다.  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다. `x:Static` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.Markup.StaticExtension.Member%2A> 확장 클래스의 <xref:System.Windows.Markup.StaticExtension> 값으로 할당됩니다.  
  
 두 개의 다른 XAML 용도 기술적으로 가능 가지가 있습니다. 그러나이 사용은 덜 일반적인 불필요 하 게 자세한 정보 표시 되기 때문에:  
  
 **개체 요소 구문:** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName``" .../>`  
  
 **초기화 문자열에 대 한 명시적 멤버 속성이 있는 특성 구문:** `<` `object`  ``  `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName``}" .../>`  
  
 이 태그 확장에 대 한 처리 정의한.NET Framework XAML 서비스 구현에는 <xref:System.Windows.Markup.StaticExtension> 클래스입니다.  
  
 `x:Static`은 태그 확장입니다. XAML 용도에서 모든 마크업 확장의 `{` 및 `}` 는 XAML 프로세서 함을 인식 하는 태그 확장 값을 제공 해야 하는 규칙의 특성 구문에는 문자입니다. 태그 확장에 대한 자세한 내용은 [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)를 참조하세요.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 WPF 프로그래밍에 사용할 기본 XAML 네임 스페이스에는 많은 유용한 정적 속성이 있고 대부분의 유용한 정적 속성이 필요 없이 쉽게 사용할 수 있는 형식 변환기와 같은 지원 `{x:Static}` 합니다. 정적 속성에는 다음 중 하나는 XAML 네임 스페이스에 대 한 접두사를 매핑되어야 합니다.  
  
-   WPF에 존재 하 고 WPF에 대 한 기본 XAML 네임 스페이스에 속하지 않는 형식을 참조 하는 ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]). 이것은 사용 하기 위한 매우 일반적인 시나리오 `x:Static`합니다. 예를 들어, 사용할 수는 `x:Static` 에 XAML 네임 스페이스 매핑 사용 하 여 참조는 <xref:System> 의 정적 속성을 참조 하기 위해 CLR 네임 스페이스 및 mscorlib 어셈블리는 <xref:System.Environment> 클래스입니다.  
  
-   사용자 지정 어셈블리에서 형식을 참조 합니다.  
  
-   했지만 해당 형식이 WPF 기본 XAML 네임 스페이스의 일부가 되도록 매핑되지 않은 CLR 네임 스페이스 내에서 WPF 어셈블리에 있는 유형을 참조 합니다. WPF에 대 한 기본 XAML 네임 스페이스에 CLR 네임 스페이스 매핑은 다양 한 WPF 어셈블리에 대 한 정의 통해 수행 됩니다 (이 개념에 대 한 자세한 내용은 참조 [XAML 네임 스페이스 및 WPF XAML에 대 한 매핑을 Namespace](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). 매핑되지 않은 CLR 네임 스페이스는 해당 CLR 네임 스페이스가 클래스 정의 되지 않는 일반적으로 xaml의 경우와 같은 대부분의 구성 된 경우에 존재할 수 <xref:System.Windows.Threading>합니다.  
  
 WPF에 대 한 XAML 네임 스페이스 및 접두사를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [XAML 네임 스페이스 및 WPF XAML에 대 한 매핑 Namespace](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [x:Type 태그 확장](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [WPF에서 System.Xaml로 마이그레이션된 형식](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
