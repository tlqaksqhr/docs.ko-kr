---
title: "x:Static Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StaticExtension"
  - "xStatic"
  - "x:Static"
helpviewer_keywords: 
  - "x:Static markup extension [XAML Services]"
  - "Static markup extension in XAML [XAML Services]"
  - "XAML [XAML Services], x:Static markup extension"
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
caps.latest.revision: 25
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 25
---
# x:Static Markup Extension
[!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] 규격에 맞는 방식으로 정의된 모든 정적 값별 코드 엔터티를 참조합니다.  참조되는 정적 속성은 XAML에서 속성 값을 제공하기 위해 사용할 수 있습니다.  
  
## XAML 특성 사용  
  
```  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`prefix`|선택적 요소.  매핑된 기본값이 아닌 XAML 네임스페이스를 나타내는 접두사입니다.  `prefix`은 기본 XAML 네임스페이스에서 제공하는 정적 속성을 거의 참조하지 않기 때문에 명시적으로 사용을 표시합니다.  설명 부분을 참조하십시오.|  
|`typeName`|필수 요소.  원하는 정적 멤버를 정의하는 형식의 이름입니다.|  
|`staticMemberName`|필수 요소.  원하는 정적 값 멤버\(상수, 정적 속성, 필드 또는 열거형 값\)의 이름입니다.|  
  
## 설명  
 참조되는 코드 엔터티는 다음 중 하나여야 합니다.  
  
-   상수  
  
-   정적 속성  
  
-   필드  
  
-   열거형 값입니다.  
  
 비정적 속성 같은 다른 코드 엔터티를 지정하면 XAML 태그가 컴파일되거나 XAML 로드 시간을 구문 분석 예외의 경우 컴파일 시간 오류가 발생합니다.  
  
 `x:Static`에서 현재 XAML 문서에 대한 기본 XAML 네임스페이스에 포함되지 않은 정적 필드나 속성을 참조할 수도 있지만 이 경우에는 접두사 매핑이 필요합니다.  XAML 네임스페이스는 거의 항상 XAML 문서의 루트 요소에 정의됩니다.  
  
 정적 속성에 대한 조회 작업은 기본 XAML 스키마 컨텍스트에서 실행될 때 .NET Framework XAML 서비스 및 XAML 판독기\/XAML 작성기에 의해 수행할 수 있습니다.  이 XAML 스키마 컨텍스트는 CLR 리플렉션을 사용하여 개체 그래프 생성을 위해 필요한 정적 값을 제공할 수 있습니다.  사용자가 지정한 `typeName`은 이 이름이 기본 XAML 스키마 컨텍스트를 사용하는 경우나 기존 CLR을 기반으로 XAML에 구현된 프레임워크를 사용할 경우 기본적으로 동일하더라도 실제로 CLR 형식 이름이 아닌 XAML 형식 이름입니다.  
  
 속성 값의 형식은 아닌 것을 `x:Static` 참조할 때는 주의하십시오.  XAML 처리 시퀀스에서 태그 확장을 통해 제공되는 값은 추가 값 변환을 호출하지 않습니다.  이는 `x:Static` 참조가 텍스트 문자열을 만들고 텍스트 문자열을 기반으로 하는 특성 값의 값 변환은 특정 멤버 또는 반환 형식의 멤버 값에 대해 발생하는 경우에도 해당합니다.  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.  `x:Static` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.Markup.StaticExtension> 확장 클래스의 <xref:System.Windows.Markup.StaticExtension.Member%2A> 값으로 할당됩니다.  
  
 기술적으로 가능한 다른 XAML 용도는 두 가지가 있습니다.  그러나 불필요하게 자세하기 때문에 이러한 사용은 그리 일반적이지 않습니다.  
  
 **개체 요소 구문:** `<x:Static Member="``prefix``:``typeName``.``staticMemberName``" .../>`  
  
 **초기화 문자열에 대한 명시적인 구성원 속성이 있는 특성 구문:** `<``object````property``="{x:Static Member=``prefix``:``typeName``.``staticMemberName``}" .../>`  
  
 .NET Framework XAML 서비스 구현에서 이 태그 확장에 대한 처리는 <xref:System.Windows.Markup.StaticExtension> 클래스를 통해 정의됩니다.  
  
 `x:Static`은 태그 확장입니다.  XAML의 모든 태그 확장은 특성 구문에 `{` 및 `}` 문자를 사용하며 여기서 특성 구문은 XAML 프로세서가 태그 확장이 값을 제공해야 함을 인식하는 데 사용하는 규칙입니다.  태그 확장에 대한 자세한 내용은 [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)를 참조하십시오.  
  
## WPF 사용 정보  
 WPF 프로그래밍에 사용하는 기본 XAML 네임스페이스에는 많은 유용한 정적 속성이 포함되어 있지 않으며 대부분의 유용한 정적 속성은 `{x:Static}`이 없이도 쉽게 사용할 수 있는 형식 변환기 같은 기능을 지원합니다.  정적 속성에 대해 다음 중 하나에 해당하는 경우 XAML 네임스페이스의 접두사를 매핑해야 합니다.  
  
-   WPF에 포함되었지만 WPF \([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]\)에 대한 기본 XAML 네임스페이스에 속하지 않는 형식을 참조하고 있습니다.  이 시나리오는 `x:Static`을 사용할 때 비교적 일반적인 시나리오입니다.  예를 들어 <xref:System> CLR 네임스페이스와 mscorlib 어셈블리에 대한 XAML 네임스페이스 매핑이 포함된 `x:Static` 참조를 사용하여 <xref:System.Environment> 클래스의 정적 속성을 참조할 수 있습니다.  
  
-   사용자 지정 어셈블리에서 형식을 참조하는 경우  
  
-   WPF 어셈블리에 포함되었지만 WPF 기본 XAML 네임스페이스의 일부로 매핑되지 않은 CLR 네임스페이스에 포함된 형식을 참조하는 경우.  CLR 네임스페이스를 WPF에 대한 기본 XAML 네임스페이스로 매핑하는 작업은 다양한 WPF 어셈블리의 정의에 따라 수행됩니다\(이 개념에 대한 자세한 내용은 [WPF XAML을 위한 XAML 네임스페이스 및 네임스페이스 매핑](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md) 참조\).  해당 CLR 네임스페이스가 일반적으로 <xref:System.Windows.Threading> 같은 XAML에 사용되지 않는 클래스 정의로 대부분 구성되어 있는 경우 매핑되지 않은 CLR 네임스페이스가 존재할 수 있습니다.  
  
 WPF용 접두사 및 XAML 네임스페이스에 대한 자세한 내용은 [WPF XAML을 위한 XAML 네임스페이스 및 네임스페이스 매핑](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)을 참조하십시오.  
  
## 참고 항목  
 [x:Type Markup Extension](../../../docs/framework/xaml-services/x-type-markup-extension.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)