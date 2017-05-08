---
title: "Binding 태그 확장 | Microsoft Docs"
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
  - "Binding"
helpviewer_keywords: 
  - "태그 확장 바인딩"
  - "XAML, 태그 바인딩 확장"
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Binding 태그 확장
중간 식 개체를 만들고 런타임에 요소 및 해당 바인딩에 적용되는 데이터 컨텍스트를 해석하여 속성 값이 데이터 바인딩된 값으로 되는 것을 연기합니다.  
  
## 바인딩 식 사용  
  
```  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## 구문 참고  
 이러한 구문에서 `[]` 및 `*`는 리터럴이 아니라  표기법의 일부로, 0개 이상의 *bindProp*`=`*value* 쌍을 사용할 수 있음을 나타냅니다. 각 쌍은 `,` 구분 기호로 구분되고 앞에는 *bindProp*`=`*value* 쌍이 옵니다.  
  
 "바인딩 확장을 사용하여 설정할 수 있는 바인딩 속성" 단원에 나열된 모든 속성은 대신 <xref:System.Windows.Data.Binding> 개체 요소의 특성을 사용하여 설정할 수 있습니다.  그러나 이것은 <xref:System.Windows.Data.Binding>의 태그 확장 사용이 아니라 단지 CLR <xref:System.Windows.Data.Binding> 클래스의 속성을 설정하는 특성의 일반적인 XAML 처리입니다.  즉, `<Binding` *bindProp1*`="`*value1*`"[` *bindPropN*`="`*valueN*`"]*/>`은 `Binding` 식 대신 사용되는 <xref:System.Windows.Data.Binding> 개체 요소의 특성에 해당하는 구문입니다.  <xref:System.Windows.Data.Binding>의 특정 속성에 XAML 특성을 사용하는 방법에 대한 자세한 내용은 .NET Framework 클래스 라이브러리에서 <xref:System.Windows.Data.Binding>의 관련된 속성에 대한 "XAML 특성 사용" 단원을 참조하십시오.  
  
## XAML 값  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|설정할 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.BindingBase> 속성의 이름입니다.  `Binding` 확장을 사용하여 모든 <xref:System.Windows.Data.Binding> 속성을 설정할 수는 없으며, 일부 속성은 고급 중첩 태그 확장을 사용해야만 `Binding` 식에서 설정할 수 있습니다.  "Binding 확장을 사용하여 설정할 수 있는 Binding 속성" 단원을 참조하십시오.|  
|`value1, valueN`|속성을 설정할 값입니다.  특성 값 처리는 궁극적으로 설정되는 특정 <xref:System.Windows.Data.Binding> 속성의 형식 및 논리와 관련이 있습니다.|  
|`path`|암시적 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> 속성을 설정하는 경로 문자열  [PropertyPath XAML 구문](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)을 참조하십시오.|  
  
## 정규화되지 않은 {Binding}  
 "바인딩 식 사용"에 표시된 것처럼 `{Binding}`을 사용하면 기본값을 가진 <xref:System.Windows.Data.Binding> 개체가 만들어집니다. 이 개체의 초기 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> 는 `null`입니다.  만든 <xref:System.Windows.Data.Binding>이 런타임 데이터 컨텍스트에서 설정되는 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> 및 <xref:System.Windows.Data.Binding.Source%2A?displayProperty=fullName>와 같은 키 데이터 바인딩 속성을 사용할 수도 있으므로 이 기능은 대부분의 시나리오에서 유용합니다.  데이터 컨텍스트의 개념에 대한 자세한 내용은 [데이터 바인딩](../../../../docs/framework/wpf/data/data-binding-wpf.md)을 참조하십시오.  
  
## 암시적 경로  
 `Binding` 태그 확장에서는 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>를 개념적 "기본 속성"으로 사용하며, 이 경우 `Path=`가 식에 나타나지 않아도 됩니다.  암시적 경로를 사용하여 `Binding` 식을 지정하는 경우 <xref:System.Windows.Data.Binding> 속성이 이름을 기준으로 지정되는 다른 모든 `bindProp`\=`value` 쌍보다 먼저, 식에서 첫 번째로 암시적 경로가 표시되어야 합니다.  예를 들어, `{Binding PathString}`에서 `PathString`은 태그 확장을 사용하여 만든 <xref:System.Windows.Data.Binding>의 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> 값으로 평가되는 문자열입니다.  쉼표 구분 기호 뒤에 다른 명명된 속성을 포함하여 암시적 경로를 추가할 수 있습니다\(예: `{Binding LastName, Mode=TwoWay}`\).  
  
## Binding 확장을 사용하여 설정할 수 있는 Binding 속성  
 `Binding` 태그 확장\/식 구문을 통해 설정할 수 있는 <xref:System.Windows.Data.BindingBase> 또는 <xref:System.Windows.Data.Binding>의 읽기\/쓰기 속성이 많기 때문에 이 항목에 나오는 구문에서는 제네릭 `bindProp`\=`value` 근사값을 사용합니다.  암시적 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>를 제외하고 순서에 관계없이 설정할 수 있습니다.  명시적으로 `Path=`를 지정할 수도 있으며, 이 경우 순서에 관계없이 설정할 수 있습니다.  기본적으로 쉼표로 구분된 `bindProp`\=`value` 쌍을 사용하여 아래 목록의 속성을 하나도 설정하지 않거나 하나 이상을 설정할 수 있습니다.  
  
 이러한 속성 값 중 몇 개는 XAML에서 텍스트 구문의 네이티브 형식 변환을 지원하지 않는 개체 형식을 필요로 하기 때문에 특성 값으로 설정하기 위해 태그 확장이 필요합니다.  자세한 내용은 각 속성에 대한 .NET Framework 클래스 라이브러리의 XAML 특성 사용 단원을 참조하십시오. 고급 태그 확장을 사용하거나 사용하지 않고 XAML 특성 구문에 사용하는 문자열은 기본적으로 `Binding` 식에 지정한 값과 같습니다. 단, `Binding` 식에서는 각 `bindProp`\=`value`를 따옴표로 묶지 않습니다.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: 가능한 바인딩 그룹을 식별하는 문자열입니다.  이것은 비교적 고급 바인딩 개념입니다. <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>에 대한 참조 페이지를 참조하십시오.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: 부울이며, `true` 또는 `false`일 수 있습니다.  기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>: 식에서 `bindProp`\=`value` 문자열로 설정할 수 있지만, 이렇게 하려면 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)과 같은 값의 개체 참조가 필요합니다.  이 경우 사용자 지정 변환기 클래스의 인스턴스가 값입니다.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>: 식에서 표준 기반 식별자로 설정할 수 있습니다. <xref:System.Windows.Data.Binding.ConverterCulture%2A>에 대한 참조 항목을 참조하십시오.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>: 식에서 `bindProp`\=`value` 문자열로 설정할 수 있지만 전달되는 매개 변수 형식에 따라 달라집니다.  값의 참조 형식을 전달하려면 중첩된 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)과 같은 개체 참조가 필요합니다.  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>: <xref:System.Windows.Data.Binding.RelativeSource%2A> 및 <xref:System.Windows.Data.Binding.Source%2A>와 함께 사용할 수 없으며, 이러한 각 바인딩 속성은 특별한 바인딩 방법을 나타냅니다.  자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: 식에서 `bindProp`\=`value` 문자열로 설정할 수 있지만 전달되는 값 형식에 따라 달라집니다.  참조 형식을 전달하려면 중첩된 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)과 같은 개체 참조가 필요합니다.  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>: 부울이며, `true` 또는 `false`일 수 있습니다.  기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>: *value*는 <xref:System.Windows.Data.BindingMode> 열거형의 상수 이름입니다.  예를 들면 `{Binding Mode=OneWay}`와 같습니다.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: 부울이며, `true` 또는 `false`일 수 있습니다.  기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: 부울이며, `true` 또는 `false`일 수 있습니다.  기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: 부울이며, `true` 또는 `false`일 수 있습니다.  기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>: 데이터 개체나 일반 개체 모델에 경로를 설명하는 문자열입니다.  해당 형식은 이 항목에서 적절하게 설명할 수 없는 개체 모델을 이동하기 위해 다른 여러 규칙을 제공합니다.  자세한 내용은 [PropertyPath XAML 구문](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)를 참조하십시오.  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: <xref:System.Windows.Data.Binding.ElementName%2A> 및 <xref:System.Windows.Data.Binding.Source%2A>와 함께 사용할 수 없으며, 이러한 각 바인딩 속성은 특별한 바인딩 방법을 나타냅니다.  자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  값을 지정하려면 중첩된 [RelativeSource MarkupExtension](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)을 사용해야 합니다.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>: <xref:System.Windows.Data.Binding.RelativeSource%2A> 및 <xref:System.Windows.Data.Binding.ElementName%2A>과 함께 사용할 수 없으며, 이러한 각 바인딩 속성은 특별한 바인딩 방법을 나타냅니다.  자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  중첩된 확장, 일반적으로 키 리소스 사전의 개체 데이터 소스를 참조하는 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)을 사용해야 합니다.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>: 바인딩된 데이터에 대한 문자열 형식 규칙을 설명하는 문자열입니다.  이것은 비교적 고급 바인딩 개념입니다. <xref:System.Windows.Data.BindingBase.StringFormat%2A>에 대한 참조 페이지를 참조하십시오.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: 식에서 `bindProp`\=`value` 문자열로 설정할 수 있지만 전달되는 매개 변수 형식에 따라 달라집니다.  값의 참조 형식을 전달하려면 중첩된 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)과 같은 개체 참조가 필요합니다.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *value*는 <xref:System.Windows.Data.UpdateSourceTrigger> 열거형의 상수 이름입니다.  예를 들면 `{Binding UpdateSourceTrigger=LostFocus}`와 같습니다.  특정 컨트롤은 이 바인딩 속성에 대해 기본값이 다를 수 있습니다.  자세한 내용은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>를 참조하십시오.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: 부울이며, `true` 또는 `false`일 수 있습니다.  기본값은 `false`입니다.  설명 부분을 참조하십시오.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: 부울이며, `true` 또는 `false`일 수 있습니다.  기본값은 `false`입니다.  설명 부분을 참조하십시오.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>: XML 데이터 소스의 XMLDOM 경로를 설명하는 문자열입니다.  자세한 내용은 [XMLData Provider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)를 참조하십시오.  
  
 다음은 `Binding` 태그 확장\/`{Binding}` 식 형식을 사용하여 설정할 수 없는 <xref:System.Windows.Data.Binding>의 속성입니다.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: 이 속성을 사용하려면 콜백 구현에 대한 참조가 필요합니다.  이벤트 처리기 이외의 콜백\/메서드는 XAML 구문에서 참조할 수 없습니다.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>: 속성이 <xref:System.Windows.Controls.ValidationRule> 개체의 제네릭 컬렉션을 사용합니다.  <xref:System.Windows.Data.Binding> 개체 요소의 속성 요소로 표현할 수 있지만 `Binding` 식에 사용하기 위해 쉽게 사용할 수 있는 특성\-구문 분석 방법이 없습니다.  <xref:System.Windows.Data.Binding.ValidationRules%2A>의 참조 항목을 참조하십시오.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## 설명  
  
> [!IMPORTANT]
>  종속성 속성 우선 순위의 관점에서 `Binding` 식은 로컬에 설정된 값에 해당합니다.  이미 `Binding` 식이 있는 속성에 로컬 값을 설정하면 `Binding`이 완전히 제거됩니다.  자세한 내용은 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)를 참조하십시오.  
  
 데이터 바인딩에 대한 기본적인 수준의 설명은 이 항목에서 다루지 않습니다.  자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding> 및 <xref:System.Windows.Data.PriorityBinding>에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 확장 구문을 지원하지 않습니다. 그 대신 속성 요소를 사용합니다.  <xref:System.Windows.Data.MultiBinding> 및 <xref:System.Windows.Data.PriorityBinding>의 참조 항목을 참조하십시오.  
  
 XAML에 대한 부울 값은 대소문자를 구분하지 않습니다.  예를 들어 `{Binding NotifyOnValidationError=true}` 또는 `{Binding NotifyOnValidationError=True}`를 지정할 수 있습니다.  
  
 데이터 유효성 검사와 관련된 바인딩은 일반적으로 `{Binding ...}` 식이 아닌 명시적 `Binding` 요소로 지정되며 식에 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 또는 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>를 설정하는 것은 이례적입니다.  그 이유는 자매 속성 <xref:System.Windows.Data.Binding.ValidationRules%2A>를 식 형식에 미리 설정할 수 없기 때문입니다.  자세한 내용은 [바인딩 유효성 검사 구현](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)을 참조하십시오.  
  
 `Binding`은 태그 확장입니다.  태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 특성으로 지정하는 것보다 더 포괄적입니다.  XAML의 모든 태그 확장은 특성 구문에 `{` 및 `}` 문자를 사용하며 여기서 특성 구문은 XAML 프로세서가 태그 확장이 문자열 내용을 처리해야 함을 인식하는 데 사용하는 규칙입니다.  자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)를 참조하십시오.  
  
 `Binding`은 WPF의 XAML 구현의 확장 기능을 구현하는 <xref:System.Windows.Data.Binding> 클래스가 XAML과 관련 없는 기타 메서드 및 속성도 구현한다는 점에서 예외적인 태그 확장입니다.  외부 멤버를 통해 <xref:System.Windows.Data.Binding>은 XAML 태그 확장으로 작동할 뿐 아니라 다양한 데이터 바인딩 시나리오를 다룰 수 있는, 보다 다양하며 독립적인 클래스가 될 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Data.Binding>   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)