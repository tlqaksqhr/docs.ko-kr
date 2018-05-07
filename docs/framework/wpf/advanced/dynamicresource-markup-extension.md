---
title: DynamicResource 태그 확장
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: c09d009a8cc90e050f6cfb1a8d2abd5c61c5b19f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dynamicresource-markup-extension"></a>DynamicResource 태그 확장
에 대 한 값을 제공 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 정의 된 리소스에 대 한 참조가 되도록 지연 하 여 property 특성입니다. 해당 리소스에 대 한 조회 동작은 런타임에 조회과 같습니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>XAML 속성 요소 사용  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`key`|요청한 리소스의 키입니다. 이 키는 처음 할당 된 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md) 리소스 태그에 작성 되거나 변수로 제공 된 경우는 `key` 를 호출할 때 매개 변수 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 코드에서 리소스를 만든 경우.|  
  
## <a name="remarks"></a>설명  
 A `DynamicResource` 초기 컴파일 중에 임시 표현식은 만들고 때문 요청 된 리소스 값이 개체를 생성 하기 위해 실제로 필요할 때까지 리소스에 대 한 조회를 연기 합니다. 이 수 이후는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지가 로드 됩니다. 리소스 값 섹션은 현재 페이지 범위에서 시작 하는 모든 활성 리소스 사전에 대해 키 검색 및 컴파일에서 자리 표시자 식에 대 한 대체 됩니다.  
  
> [!IMPORTANT]
>  종속성 속성의 우선 순위를 기준으로 한 `DynamicResource` 식은 동적 리소스 참조 적용 되는 위치에 해당 합니다. 이전에 속성에 대 한 로컬 값을 설정 하는 경우는 `DynamicResource` 식을 로컬 값으로는 `DynamicResource` 완전히 제거 됩니다. 자세한 내용은 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)를 참조하세요.  
  
 특정 리소스 액세스 시나리오에 특히 적합 한는 `DynamicResource` 반대인는 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)합니다. 참조 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md) 관련 이점과 성능에 미치는 영향에 대 한 토론에 대 한 `DynamicResource` 및 `StaticResource`합니다.  
  
 지정 된 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 에 의해 결정 되는 기존 리소스에 해당 해야 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md) 특정 수준에서 페이지, 응용 프로그램, 사용 가능한 컨트롤 테마 및 외부의 리소스 또는 시스템 리소스 및 리소스 조회 순서 대로 발생 합니다. 정적 및 동적 리소스에 대 한 리소스 조회에 대 한 자세한 내용은 참조 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.  
  
 리소스 키에 정의 된 모든 문자열일 수 있습니다는 [XamlName 문법](../../../../docs/framework/xaml-services/xamlname-grammar.md)합니다. 리소스 키 수도 있습니다 다른 개체 형식 같은 <xref:System.Type>합니다. A <xref:System.Type> 테마 컨트롤은 방식의 기본 키입니다. 자세한 내용은 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하십시오.  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 리소스 값을 조회에 대 한 같은 <xref:System.Windows.FrameworkElement.FindResource%2A>에서 사용 되는 동일한 리소스 조회 논리에 따라 `DynamicResource`합니다.  
  
 리소스 참조 선언적 다른 방법을 사용 하는 한 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)합니다.  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다. `DynamicResource` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 확장 클래스의 <xref:System.Windows.DynamicResourceExtension> 값으로 할당됩니다.  
  
 `DynamicResource` 개체 요소 구문에서 사용할 수 있습니다. 이 경우의 값을 지정 하는 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 속성은 필수입니다.  
  
 `DynamicResource` 속성을 다음과 같이 속성=값 쌍으로 지정하는 자세한 특성 사용 구문에도 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>을 사용할 수 있습니다.  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 자세한 정보 표시는 대개 설정 가능한 속성이 둘 이상이거나 일부 속성이 선택 사항인 확장의 경우에 유용합니다. 
          `DynamicResource`에는 설정 가능한 속성이 하나뿐이고 이 속성은 필수적 속성이므로 자세한 정보 표시를 사용하지 않는 것이 일반적입니다.  
  
 에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 구현이 태그 확장에 대 한 처리가 정의한는 <xref:System.Windows.DynamicResourceExtension> 클래스입니다.  
  
 `DynamicResource`은 태그 확장입니다. 태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다. 자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [리소스 및 코드](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [x:Key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md)  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
