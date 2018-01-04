---
title: "StaticResource 태그 확장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97b83feb9d19760208d9cc103290c5c6293c30c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="staticresource-markup-extension"></a>StaticResource 태그 확장
에 대 한 값을 제공 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이미 정의 된 리소스에 대 한 참조를 조회 하 여 property 특성입니다. 해당 리소스에 대 한 조회 동작은 현재 태그에서 이전에 로드 된 리소스 로드 시간 조회, 유사 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지와 다른 응용 프로그램 소스 및으로 해당 리소스 값이 생성 되는 런타임 개체에서 속성 값입니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`key`|요청한 리소스의 키입니다. 이 키는 처음 할당 된 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md) 리소스 태그에 작성 되거나 변수로 제공 된 경우는 `key` 를 호출할 때 매개 변수 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 코드에서 리소스를 만든 경우.|  
  
## <a name="remarks"></a>설명  
  
> [!IMPORTANT]
>  A `StaticResource` 정의 된 리소스에 대 한 정방향 참조를 확인 하려고 하지 해야 구문적으로 내에서 더는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일입니다. 이와 같이 지원 되지 않으며 정방향 참조 시도 로드 시 성능 저하가 발생 이러한 참조는 실패 하지 않는 경우에 때 나타내는 내부 해시 테이블을 <xref:System.Windows.ResourceDictionary> 검색 됩니다. 최상의 결과 전방 참조를 방지할 수 있도록 리소스 사전에서 컴퍼지션을 조정 합니다. 전방 참조를 방지 수 없는 경우 사용 하 여 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) 대신 합니다.  
  
 지정 된 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 로 식별 하는 기존 리소스에 해당 해야는 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md) 특정 수준에서 페이지, 응용 프로그램, 사용 가능한 컨트롤 테마 및 외부의 리소스 또는 시스템 리소스입니다. 리소스 조회 순서 대로 발생합니다. 정적 및 동적 리소스에 대 한 리소스 조회 동작에 대 한 자세한 내용은 참조 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.  
  
 리소스 키에 정의 된 모든 문자열일 수는 [XamlName 문법](../../../../docs/framework/xaml-services/xamlname-grammar.md)합니다. 리소스 키는 다른 개체 형식을와 같은 될 수도 있습니다는 <xref:System.Type>합니다. A <xref:System.Type> 컨트롤은 방식의 테마를 사용해 암시적 스타일 키를 통해 기본 키입니다. 자세한 내용은 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하십시오.  
  
 리소스 참조 선언적 다른 방법을 사용 하는 한 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)합니다.  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다. `StaticResource` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 확장 클래스의 <xref:System.Windows.StaticResourceExtension> 값으로 할당됩니다.  
  
 `StaticResource`개체 요소 구문에서 사용할 수 있습니다. 이 경우의 값을 지정 하는 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 속성은 필수입니다.  
  
 `StaticResource` 속성을 다음과 같이 속성=값 쌍으로 지정하는 자세한 특성 사용 구문에도 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>을 사용할 수 있습니다.  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 자세한 정보 표시는 대개 설정 가능한 속성이 둘 이상이거나 일부 속성이 선택 사항인 확장의 경우에 유용합니다. 
          `StaticResource`에는 설정 가능한 속성이 하나뿐이고 이 속성은 필수적 속성이므로 자세한 정보 표시를 사용하지 않는 것이 일반적입니다.  
  
 에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 구현이 태그 확장에 대 한 처리가 정의한는 <xref:System.Windows.StaticResourceExtension> 클래스입니다.  
  
 `StaticResource`은 태그 확장입니다. 태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다. 자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [리소스 및 코드](../../../../docs/framework/wpf/advanced/resources-and-code.md)
