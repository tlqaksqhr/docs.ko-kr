---
title: "Binding 태그 확장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d2bbca799e1eda1abae3d199dd71e004b17c4c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="binding-markup-extension"></a>Binding 태그 확장
중간 식 개체 만들기와 런타임 시 해당 바인딩 요소에 적용 되는 데이터 컨텍스트를 해석 하는 데이터 바인딩된 값이 되도록 하 여 속성 값을 연기 합니다.  
  
## <a name="binding-expression-usage"></a>바인딩 식 사용  
  
```  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## <a name="syntax-notes"></a>구문 정보  
 이러한 구문에서는 `[]` 및 `*` 는 리터럴이 있습니다. 임을 나타내는 표기법의 일부인 0 개 이상의 *과*`=`*값* 쌍을 사용할 수와 `,` 이전 형식과 작업 사이 구분 기호 *과*  `=` *값* 쌍입니다.  
  
 "바인딩 속성을 수 있습니다 수 설정 된 바인딩 확장" 섹션에 나열 된 속성 중 하나라도 수 대신 설정할 수의 특성을 사용 하는 <xref:System.Windows.Data.Binding> object 요소입니다. 그러나 그렇지 않은 실제로 태그 확장 사용의 <xref:System.Windows.Data.Binding>, CLR의 속성을 설정 하는 특성의 일반적인 XAML 처리만는 <xref:System.Windows.Data.Binding> 클래스입니다. 즉, `<Binding` *bindProp1*`="`*value1* `"[` *bindPropN*`="`*값* `"]*/>` 의 특성에 해당 하는 구문은 <xref:System.Windows.Data.Binding> 대신 요소 사용 개체는 `Binding` 식 사용 합니다. 특정 속성의 XAML 특성 사용에 대 한 자세한 내용은 <xref:System.Windows.Data.Binding>의 관련 속성의 "XAML 특성 사용" 섹션을 참조 <xref:System.Windows.Data.Binding> .NET Framework 클래스 라이브러리에서.  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|이름에서 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.BindingBase> 속성을 설정 합니다. 일부 <xref:System.Windows.Data.Binding> 사용 속성을 설정할 수 있습니다는 `Binding` 확장과 일부 속성은 내에서 설정할 수는 `Binding` 추가 사용 하 여 식을 중첩 태그 확장입니다. "바인딩 속성을 수 있습니다 수 설정 된 바인딩 확장" 섹션을 참조 하십시오.|  
|`value1, valueN`|속성을 설정 하는 값입니다. 특성 값의 처리는 궁극적으로 형식 및 특정의 논리에 <xref:System.Windows.Data.Binding> 속성이 설정 되 고 있습니다.|  
|`path`|암시적으로 설정 하는 경로 문자열 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 속성입니다. 참고 항목 [PropertyPath XAML 구문](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)합니다.|  
  
## <a name="unqualified-binding"></a>정규화 되지 않은 {바인딩}  
 `{Binding}` "바인딩 식 사용"에 표시 된 사용량을 만듭니다는 <xref:System.Windows.Data.Binding> 초기를 포함 하는 기본 값으로 개체 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 의 `null`합니다. 이 대부분의 시나리오에서 유용 하기 때문에 만든 <xref:System.Windows.Data.Binding> 와 같은 주요 데이터 바인딩 속성을 사용할 수도 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> 런타임 데이터 컨텍스트에서 설정 합니다. 데이터 컨텍스트 클래스의 개념에 대 한 자세한 내용은 참조 하십시오. [데이터 바인딩](../../../../docs/framework/wpf/data/data-binding-wpf.md)합니다.  
  
## <a name="implicit-path"></a>암시적 경로  
 `Binding` 태그 확장 사용 하 여 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 를 개념적으로 "기본 속성" 여기서 `Path=` 는 식에 표시할 필요가 없습니다. 지정 하는 경우는 `Binding` 암시적 경로 식의 암시적 경로 전에 다른 모든 식에서 첫 번째로 나타나야 합니다 `bindProp` = `value` 쌍은 <xref:System.Windows.Data.Binding> 속성 이름으로 지정 합니다. 예를 들어: `{Binding PathString}`여기서 `PathString` 의 값으로 평가 되는 문자열 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 에 <xref:System.Windows.Data.Binding> 태그 확장 사용 하 여 생성 합니다. 예를 들어 쉼표 구분 기호 뒤 다른 명명 된 속성을 가진 암시적 경로 추가할 수 있습니다 `{Binding LastName, Mode=TwoWay}`합니다.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>바인딩 확장으로 설정할 수 있는 바인딩 속성  
 이 항목에 표시 된 구문에는 제네릭 사용 `bindProp` = `value` 추정치의 많은 읽기/쓰기 속성이 있기 때문에 <xref:System.Windows.Data.BindingBase> 또는 <xref:System.Windows.Data.Binding> 를 통해 설정할 수는 `Binding` 태그 확장 / 식 구문입니다. 어떤 순서로 든 암시적 제외 하 고 설정할 수 있습니다 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>합니다. (명시적으로 지정 하는 옵션이 있는 `Path=`,이 경우 순서에 관계 없이 설정할 수 있습니다). 기본적으로, 설정할 수 있습니다 0 개 이상의 속성을 아래 목록에서 사용 하 여 `bindProp` = `value` 쌍은 쉼표로 구분 합니다.  
  
 이러한 속성 값 중 몇 가지 xaml에서는 텍스트 구문에서 네이티브 형식 변환을 지원 하지 않는 개체 형식이 필요로 하기 때문에 태그 확장 특성 값으로 설정 하는 데 필요 합니다. 자세한 내용은;에 대 한 각 속성에 대 한.NET Framework 클래스 라이브러리의 XAML 특성 사용 섹션을 확인 XAML 특성 구문에 대 한 사용 하는 문자열 또는 태그 확장을 추가 하지 않고 사용은 기본적으로에서 지정한 값과 같으면는 `Binding` 각 주위에 따옴표를 배치 하지 마십시오 예외와 함께 식을 `bindProp` = `value` 에 `Binding` 식입니다.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: 바인딩 가능한 그룹을 식별 하는 문자열입니다. 이 비교적 고급 바인딩 개념입니다. 참조 페이지에 대 한 참조 <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>합니다.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>:으로 설정할 수는 `bindProp` = `value` 식에 있지만 이렇게 하려면 문자열 값에 대해 같은 개체 참조에 필요는 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)합니다. 이 예에서 값은 사용자 지정 변환기 클래스의 인스턴스입니다.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>: 표준 기반 식별자가 식에서 설정할 수 에 대 한 참조 항목을 참조 <xref:System.Windows.Data.Binding.ConverterCulture%2A>합니다.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>:으로 설정할 수는 `bindProp` = `value` 문자열 식에 있지만이 전달 되 고 매개 변수의 형식에 따라 달라 집니다. 값에 대 한 참조 형식에 전달 하는 경우 같은 중첩 된 개체 참조 필요 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)합니다.  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>:와 함께 사용할 수 없는 <xref:System.Windows.Data.Binding.RelativeSource%2A> 및 <xref:System.Windows.Data.Binding.Source%2A>각 바인딩 속성을 이러한에서 특정 바인딩 방법을 나타냅니다. 참조 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>:으로 설정할 수는 `bindProp` = `value` 문자열 식에 있지만이 전달 되는 값의 형식에 따라 달라 집니다. 같은 중첩 된 개체 참조가 필요 참조 형식을 전달 하는 경우 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)합니다.  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>: *값* 에서 이름인 상수는 <xref:System.Windows.Data.BindingMode> 열거형입니다. 예를 들어, `{Binding Mode=OneWay}`을 입력합니다.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>: 데이터 개체 또는 일반 개체 모델에 대 한 경로 설명 하는 문자열입니다. 형식은이 항목에 적절 하 게 설명할 수 없는 개체 모델을 탐색 하는 데 몇 가지 다른 규칙을 제공 합니다. 참조 [PropertyPath XAML 구문](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)합니다.  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: 함께 사용할 수 없습니다 <xref:System.Windows.Data.Binding.ElementName%2A> 및 <xref:System.Windows.Data.Binding.Source%2A>각 바인딩 속성을 이러한에서 특정 바인딩 방법을 나타냅니다. 참조 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다. 중첩 된 필요 [RelativeSource MarkupExtension](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) 사용량 값을 지정 합니다.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>:와 함께 사용할 수 없는 <xref:System.Windows.Data.Binding.RelativeSource%2A> 및 <xref:System.Windows.Data.Binding.ElementName%2A>각 바인딩 속성을 이러한에서 특정 바인딩 방법을 나타냅니다. 참조 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다. 일반적으로 중첩 된 확장 사용 필요는 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) 키가 지정 된 리소스 사전에서 개체 데이터 소스를 참조 합니다.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>: 바인딩된 데이터에 대 한 문자열 형식 규칙을 설명 하는 문자열입니다. 이 비교적 고급 바인딩 개념입니다. 참조 페이지에 대 한 참조 <xref:System.Windows.Data.BindingBase.StringFormat%2A>합니다.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>:으로 설정할 수는 `bindProp` = `value` 문자열 식에 있지만이 전달 되 고 매개 변수의 형식에 따라 달라 집니다. 같은 중첩 된 개체 참조를 요구 하는 값에 대 한 참조 형식을 전달 하는 경우 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)합니다.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *값* 에서 이름인 상수는 <xref:System.Windows.Data.UpdateSourceTrigger> 열거형입니다. 예를 들어, `{Binding UpdateSourceTrigger=LostFocus}`을 입력합니다. 특정 컨트롤은 잠재적으로이 바인딩은 속성에 대 한 다른 기본 값을 갖습니다. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>을 참조하세요.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다. 설명 부분을 참조하세요.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다. 설명 부분을 참조하세요.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>: XML 데이터 소스 XMLDOM에 경로 설명 하는 문자열입니다. 참조 [는 XMLDataProvider와 XPath 쿼리를 사용 하 여 XML 데이터에 바인딩할](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)합니다.  
  
 다음의 속성은 <xref:System.Windows.Data.Binding> 를 사용 하 여 설정할 수 없는 `Binding` 태그 확장 /`{Binding}` 식 형식입니다.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>:이 속성에서는 콜백 구현에 대 한 참조입니다. XAML 구문에서 콜백/메서드 이외의 이벤트 처리기를 참조할 수 없습니다.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>: 속성의 제네릭 컬렉션을 가져와서 <xref:System.Windows.Controls.ValidationRule> 개체입니다. 속성 요소로 표현할 수는 <xref:System.Windows.Data.Binding> 개체 요소의 하지만에 사용 하기 위해에 특성 구문 분석 원활 하 게 사용 방법이 `Binding` 식입니다. 참조 항목을 참조 <xref:System.Windows.Data.Binding.ValidationRules%2A>합니다.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>설명  
  
> [!IMPORTANT]
>  종속성 속성의 우선 순위를 기준으로 한 `Binding` 식을 로컬에서 설정에 해당 하는 값입니다. 이전에 속성에 대 한 로컬 값을 설정 하는 경우는 `Binding` 식의 `Binding` 완전히 제거 됩니다. 자세한 내용은 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)를 참조하세요.  
  
 기본적인 수준에서 데이터 바인딩을 설명 하는이 항목에서 다루지 않습니다. 참조 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding>및 <xref:System.Windows.Data.PriorityBinding> 지원 하지 않는 한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 확장 구문입니다. 속성 요소를 대신 사용 합니다. 에 대 한 참조 항목을 참조 <xref:System.Windows.Data.MultiBinding> 및 <xref:System.Windows.Data.PriorityBinding>합니다.  
  
 XAML에 대 한 부울 값 대/소문자를 구분 합니다. 중 하나를 지정할 수는 예를 들어 `{Binding NotifyOnValidationError=true}` 또는 `{Binding NotifyOnValidationError=True}`합니다.  
  
 데이터 유효성 검사와 관련 된 바인딩은 일반적으로 명시적으로 지정 `Binding` 요소 아니라는 `{Binding ...}` 식 및 설정을 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 또는 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 식에서 일반적이 않은 합니다. 즉, 부록 속성 <xref:System.Windows.Data.Binding.ValidationRules%2A> 식 형식에서 쉽게 설정할 수 없습니다. 자세한 내용은 참조 [구현 바인딩 유효성 검사](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)합니다.  
  
 `Binding`은 태그 확장입니다. 태그 확장은 리터럴 값 또는 처리기 이외의으로 이름, 특성 값을 이스케이프 하는 되며 이러한 요구 사항은 특정 형식 또는 속성에 특성을 사용 하는 형식 변환기 보다 더 포괄적 때 일반적으로 구현 됩니다. XAML 용도에서 모든 마크업 확장의 `{` 및 `}` XAML 프로세서는 기준인 태그 확장 문자열 콘텐츠를 처리 해야 한다는 것을 인식 하는 규칙의 특성 구문에는 문자입니다. 자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
 `Binding`하는 예외적인 태그 확장은 <xref:System.Windows.Data.Binding> WPF의 XAML 구현에 대 한 확장 기능을 구현 하는 클래스는 다른 여러 메서드 및 XAML에 관련 되지 않은 속성에도 구현 합니다. 다른 멤버를 확인 하려고 <xref:System.Windows.Data.Binding> XAML 태그 확장으로 작동 하는 것 외에도 여러 데이터 바인딩 시나리오를 해결할 수 있는 하 게 자체 포함 된 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.Binding>  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
