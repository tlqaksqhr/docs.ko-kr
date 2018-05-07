---
title: TemplateBinding 태그 확장
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: d425d17405bc8241c3fd85c77c6672265a060900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="templatebinding-markup-extension"></a>TemplateBinding 태그 확장
컨트롤 템플릿의 속성 값을 템플릿 기반 컨트롤의 다른 속성 값에 연결합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a>XAML 특성 사용(템플릿 또는 스타일의 Setter 속성의 경우)  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`propertyName`|setter 구문에 설정할 속성의 <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>입니다.|  
|`sourceProperty`|템플릿을 기반으로 만들 형식에 존재하는 또 다른 종속성 속성이며 해당 <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>으로 지정됩니다.<br /><br /> 또는<br /><br /> 템플릿을 기반으로 만들 대상 형식과는 다른 형식으로 정의되는 "점으로 구분된" 속성 이름이며 실제로는 <xref:System.Windows.PropertyPath>입니다. 참조 [PropertyPath XAML 구문](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)합니다.|  
  
## <a name="remarks"></a>설명  
 A `TemplateBinding` 는 최적화 된 형태의 [바인딩](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) 유사 템플릿 시나리오는 `Binding` 사용 하 여 생성 `{Binding RelativeSource={RelativeSource TemplatedParent}}`합니다. `TemplateBinding`은 속성이 기본적으로 양방향 바인딩과 관련되었더라도 항상 단방향 바인딩입니다. 관련된 두 속성은 모두 종속성 속성이어야 합니다.  
  
 [RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) 와 함께 또는 대신 사용 되는 다른 태그 확장은 `TemplateBinding` 템플릿 내에서 상대 속성 바인딩을 수행 하려면.  
  
 컨트롤 템플릿을 설명 하는 개념으로 서은 여기서 다루지 않습니다. 자세한 내용은 참조 [컨트롤 스타일 및 템플릿](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)합니다.  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다. `TemplateBinding` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.TemplateBindingExtension.Property%2A> 확장 클래스의 <xref:System.Windows.TemplateBindingExtension> 값으로 할당됩니다.  
  
 다른 요소 구문도 가능하지만 실제 환경에서 적용하지 않으므로 표시하지 않았습니다. `TemplateBinding`은 평가된 식을 사용하여 setter 내에 값을 채우는 데 사용됩니다. `TemplateBinding`에 대한 개체 요소 구문을 사용하여 `<Setter.Property>` 속성 요소 구문을 채우는 경우 작업이 번거롭습니다.  
  
 `TemplateBinding` 속성을 다음과 같이 속성=값 쌍으로 지정하는 자세한 특성 사용 구문에도 <xref:System.Windows.TemplateBindingExtension.Property%2A>을 사용할 수 있습니다.  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 자세한 정보 표시는 대개 설정 가능한 속성이 둘 이상이거나 일부 속성이 선택 사항인 확장의 경우에 유용합니다. 
          `TemplateBinding`에는 설정 가능한 속성이 하나뿐이고 이 속성은 필수적 속성이므로 자세한 정보 표시를 사용하지 않는 것이 일반적입니다.  
  
 에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 프로세서 구현에서이 태그 확장에 대 한 처리가 정의한는 <xref:System.Windows.TemplateBindingExtension> 클래스입니다.  
  
 `TemplateBinding`은 태그 확장입니다. 태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다. XAML 용도에서 모든 마크업 확장의 `{` 및 `}` XAML 프로세서는 기준인 태그 확장 특성을 처리 해야 한다는 것을 인식 하는 규칙의 특성 구문에는 문자입니다. 자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [RelativeSource 태그 확장](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)  
 [Binding 태그 확장](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)
