---
title: "태그 확장 및 WPF XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "*Extension 클래스"
  - "태그 확장 바인딩"
  - "중괄호 문자"
  - "문자, 중괄호"
  - "클래스, MarkupExtension"
  - "중괄호 문자({})"
  - "DynamicResource 태그 확장"
  - "리터럴 중괄호 문자({})"
  - "태그 확장"
  - "MarkupExtension 클래스"
  - "확장 구문 중첩"
  - "RelativeSource 태그 확장"
  - "StaticResource 태그 확장"
  - "TemplateBinding 태그 확장"
  - "XAML, 태그 확장"
ms.assetid: 618dc745-8b14-4886-833f-486d2254bb78
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# 태그 확장 및 WPF XAML
이 항목에서는 XAML 태그 확장의 구문 규칙, 용도, 기반이 되는 클래스 개체 모델 등을 비롯한 개념에 대해 소개합니다.  태그 확장은 XAML 언어의 일반적 기능이며 XAML 서비스에 대한 .NET 구현의 일반적 기능입니다.  이 항목에서는 WPF XAML에서 사용할 태그 확장에 대해 자세히 설명합니다.  
  
   
  
<a name="XAML_Processors_and_Markup_Extensions"></a>   
## XAML 프로세서와 태그 확장  
 일반적으로 파서는 특성 값을 기본 형식으로 변환 가능한 리터럴 문자열로 해석하거나 특정 방법에 따라 개체로 변환할 수 있습니다.  이러한 방법 중 하나는 형식 변환기를 참조하는 것이며, 이에 대한 설명은 [TypeConverter 및 XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md) 항목에 나와 있습니다.  하지만 이와 다른 동작이 필요한 경우도 있습니다.  예를 들어 특성 값 때문에 개체 그래프에 새 개체가 나타나지 않도록 XAML 프로세서에 지시할 수 있습니다.  이 경우 해당 특성은 개체 그래프의 다른 부분에 있는 이미 만들어진 개체 또는 정적 개체에 대한 참조를 만드는 개체 그래프가 나타나게 해야 합니다.  또 다른 예로 기본값이 아닌 인수를 개체 생성자에 제공하는 구문을 사용하도록 XAML 프로세서에 지시할 수도 있습니다. 이러한 경우에는 태그 확장을 통해 해결책을 찾을 수 있습니다.  
  
<a name="Basic_Markup_Extension_Syntax"></a>   
## 기본 태그 확장 구문  
 태그 확장은 특성에서 사용되는 속성, 속성 요소에서 사용되는 속성 또는 두 속성 모두의 값을 제공하도록 구현할 수 있습니다.  
  
 특성 값을 제공하는 데 사용되는 경우 XAML 프로세서는 구문에서 여는 중괄호와 닫는 중괄호\({ 및 }\)를 통해 태그 확장 시퀀스를 구분합니다.  태그 확장 형식은 여는 중괄호 바로 다음에 오는 문자열 토큰으로 식별됩니다.  
  
 속성 요소 구문에 사용되는 경우 태그 확장은 속성 요소 값을 제공하는 데 사용되는 다른 요소와 시각적으로 동일합니다. 즉, 태그 확장 클래스를 요소로 참조하는 XAML 요소 선언을 꺾쇠괄호\(\<\>\)로 묶습니다.  
  
<a name="XAML_Defined_Markup_Extensions"></a>   
## XAML 정의 태그 확장  
 XAML의 WPF 구현과 관련되지 않고 대신 XAML의 내장 형식 또는 기능 구현에서 언어로 사용되는 몇 가지 태그 확장도 있습니다.  이러한 태그 확장은 System.Xaml 어셈블리에 일반적인 .NET Framework XAML 서비스의 일부로 정의되어 있으며, XAML 언어 XAML 네임스페이스 내에 있습니다.  일반적인 태그 사용 방법에서 볼 수 있는 것처럼 이러한 태그 확장은 대개 구문에서 `x:` 접두사로 식별됩니다.  <xref:System.Windows.Markup.MarkupExtension> 기본 클래스\(System.Xaml에 정의됨\)에서는 WPF XAML 등의 XAML 판독기 및 XAML 작성기에서 지원되기 위해 모든 태그 확장이 사용해야 하는 패턴을 제공합니다.  
  
-   `x:Type`은 명명된 형식에 대한 <xref:System.Type> 개체를 제공합니다.  이 기능은 스타일 및 템플릿에서 가장 많이 사용됩니다.  자세한 내용은 [x:Type 태그 확장](../../../../docs/framework/xaml-services/x-type-markup-extension.md)을 참조하십시오.  
  
-   `x:Static`은 정적 값을 생성합니다.  이 값은 직접적으로 대상 속성 값의 형식은 아니지만 해당 형식으로 확인될 수 있는 값 형식 코드 엔터티에서 가져옵니다.  자세한 내용은 [x:Static 태그 확장](../../../../docs/framework/xaml-services/x-static-markup-extension.md)을 참조하십시오.  
  
-   `x:Null`은 속성 값으로 `null`을 지정하며 특성 또는 속성 요소 값에 사용될 수 있습니다.  자세한 내용은 [x:Null 태그 확장](../../../../docs/framework/xaml-services/x-null-markup-extension.md)을 참조하십시오.  
  
-   `x:Array`를 사용하면 WPF 기본 요소 및 컨트롤 모델에서 제공하는 컬렉션 지원 기능을 의도적으로 사용하지 않는 경우에 XAML 구문에서 일반적인 배열을 생성할 수 있습니다.  자세한 내용은 [x:Array 태그 확장](../../../../docs/framework/xaml-services/x-array-markup-extension.md)을 참조하십시오.  
  
> [!NOTE]
>  `x:` 접두사는 XAML 파일 또는 프로덕션의 루트 요소에서 XAML 언어 내장 형식의 대표적인 XAML 네임스페이스 매핑에 사용됩니다.  예를 들어 WPF 응용 프로그램용 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 템플릿은 이 `x:` 매핑을 사용하여 XAML 파일을 초기화합니다.  사용자 지정 XAML 네임스페이스 매핑에는 다른 접두사 토큰을 선택할 수 있지만 이 설명서에서는 WPF 기본 네임스페이스나 특정 프레임워크와 관련되지 않은 기타 XAML 네임스페이스와는 달리 XAML 언어의 XAML 네임스페이스의 일부로 정의된 엔터티를 식별하는 데 기본 `x:` 매핑을 사용합니다.  
  
<a name="WPF_Specific_Markup_Extensions"></a>   
## WPF 관련 태그 확장  
 WPF 프로그래밍에서 사용되는 가장 일반적인 태그 확장은 리소스 참조\(`StaticResource` 및 `DynamicResource`\)를 지원하는 태그 확장과 데이터 바인딩\(`Binding`\)을 지원하는 태그 확장입니다.  
  
-   `StaticResource`는 이미 정의된 리소스의 값을 대체하여 속성 값을 제공합니다.  `StaticResource` 평가는 궁극적으로 XAML 로드 시간에 수행되고 런타임에는 개체 그래프에 액세스하지 못합니다. 자세한 내용은 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)을 참조하십시오.  
  
-   `DynamicResource`는 값이 리소스에 대한 런타임 참조가 되도록 지연하여 속성 값을 제공합니다.  동적 리소스 참조는 리소스가 액세스될 때마다 새로 조회하도록 하고 런타임에 개체 그래프에 액세스합니다.  이 액세스를 얻기 위해 속성 시스템의 종속성 속성 및 계산된 식에 의해 `DynamicResource` 개념이 지원됩니다.  따라서 종속성 속성 대상에는 `DynamicResource`만 사용할 수 있습니다.  자세한 내용은 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)을 참조하십시오.  
  
-   `Binding`은 런타임에 부모 개체에 적용되는 데이터 컨텍스트를 사용하여 속성에 대한 데이터 바인딩된 값을 제공합니다.  이 태그 확장은 데이터 바인딩을 지정하는 인라인 구문을 사용하기 때문에 비교적 복잡합니다.  자세한 내용은 [Binding 태그 확장](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)을 참조하십시오.  
  
-   `RelativeSource`는 런타임 요소 개체 트리에서 가능한 여러 관계를 탐색할 수 있는 <xref:System.Windows.Data.Binding>에 대한 소스 정보를 제공합니다.  즉, 주변 개체 트리에 대한 완전한 지식 없이 코드에 생성되거나 다용도 템플릿에 생성되는 바인딩에 대한 특수한 소스를 제공합니다.  자세한 내용은 [RelativeSource MarkupExtension](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)을 참조하십시오.  
  
-   `TemplateBinding`을 사용하면 컨트롤 템플릿에서 템플릿을 사용할 클래스의 개체\-모델 정의 속성에서 가져온 템플릿 기반 속성 값을 사용할 수 있습니다.  즉, 템플릿 정의 내의 속성은 템플릿이 적용된 후의 컨텍스트에만 액세스할 수 있습니다.  자세한 내용은 [TemplateBinding 태그 확장](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)을 참조하십시오.  `TemplateBinding`의 실질적인 사용 방법에 자세한 내용은 [Styling with ControlTemplates 샘플](http://go.microsoft.com/fwlink/?LinkID=160041)을 참조하십시오.  
  
-   `ColorConvertedBitmap`에서는 비교적 고급 이미징 시나리오를 지원합니다.  자세한 내용은 [ColorConvertedBitmap 태그 확장](../../../../docs/framework/wpf/advanced/colorconvertedbitmap-markup-extension.md)을 참조하십시오.  
  
-   특히 사용자 지정 컨트롤과 패키지되어 있는 리소스 및 테마와 관련된 리소스 조회의 `ComponentResourceKey` 및 `ThemeDictionary` 지원.  자세한 내용은 [ComponentResourceKey 태그 확장](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md), [ThemeDictionary 태그 확장](../../../../docs/framework/wpf/advanced/themedictionary-markup-extension.md) 또는 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하십시오.  
  
<a name="StarExtension"></a>   
## \*Extension 클래스  
 일반적인 XAML 언어 및 WPF 관련 태그 확장의 경우 XAML 프로세서에서 각 태그 확장의 동작은 <xref:System.Windows.Markup.MarkupExtension>에서 파생되고 <xref:System.Windows.Markup.StaticExtension.ProvideValue%2A> 메서드 구현을 제공하는 `*Extension` 클래스를 통해 식별됩니다.  각 확장에서 이 메서드는 태그 확장이 실행될 때 반환되는 개체를 제공합니다.  반환되는 개체는 대개 태그 확장에 전달된 다양한 문자열 토큰을 기반으로 평가됩니다.  
  
 예를 들어 <xref:System.Windows.StaticResourceExtension> 클래스는 해당 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> 구현이 요청된 개체를 반환하도록 실제 리소스 조회의 표면적인 구현을 제공합니다. 이때 이 구현의 입력은 `x:Key`를 기준으로 리소스를 조회하는 데 사용되는 문자열입니다.  기존 태그 확장을 사용할 때에는 이러한 구현 세부 사항이 중요하지 않습니다.  
  
 일부 태그 확장에는 문자열 토큰 인수가 사용되지 않습니다.  이는 태그 확장이 정적 값 또는 일정한 값을 반환하기 때문이거나, 반환해야 하는 값의 컨텍스트가 `serviceProvider` 매개 변수로 전달된 서비스 중 하나를 통해 사용 가능하기 때문입니다.  
  
 `*Extension` 이름 지정 패턴은 편의성과 일관성을 고려한 것입니다.  XAML 프로세서가 해당 클래스를 태그 확장에 대한 지원으로 식별하는 데 필요한 것은 아닙니다.  코드베이스에 System.Xaml이 포함되어 있고 .NET Framework XAML 서비스 구현이 사용되는 경우 클래스는 <xref:System.Windows.Markup.MarkupExtension>에서 파생되고 생성 구문을 지원하기만 하면 XAML 태그 확장으로 인식됩니다.  WPF에서는 <xref:System.Windows.Data.Binding>과 같이 `*Extension` 명명 패턴을 따르지 않는 태그 확장 사용 클래스를 정의합니다.  이와 같은 일반적인 이유는 클래스 지원 시나리오가 순수한 태그 확장 지원의 범위를 벗어나기 때문입니다.  <xref:System.Windows.Data.Binding>의 경우, 이 클래스는 런타임에 XAML과 관련이 없는 시나리오에 사용되는 개체의 메서드 및 속성에 액세스할 수 있게 해 줍니다.  
  
### 초기화 텍스트의 확장 클래스 해석  
 XAML 프로세서는 중괄호 안에서 태그 확장 이름 다음에 나오는 문자열 토큰을 다음 방법 중 하나로 해석합니다.  
  
-   쉼표는 항상 개별 토큰의 분리 기호나 구분 기호를 나타냅니다.  
  
-   구분된 개별 토큰에 등호가 포함되지 않은 경우 각 토큰은 생성자 인수로 처리됩니다.  각 생성자 매개 변수는 해당 시그니처에 필요한 형식과 순서로 지정되어야 합니다.  
  
    > [!NOTE]
    >  XAML 프로세서는 여러 쌍 중 인수 수가 일치하는 생성자를 호출해야 합니다.  이러한 이유 때문에 사용자 지정 태그 확장을 구현할 경우 인수 수가 동일한 매개 변수를 여러 개 제공하지 않습니다.  매개 변수 수가 동일한 태그 확장 생성자 경로가 둘 이상 있을 때의 XAML 프로세서 동작은 정의되어 있지 않지만, 태그 확장 형식 정의에 이 상황이 있는 경우 XAML 프로세서에서 사용에 대한 예외를 throw할 수 있다고 예상해야 합니다.  
  
-   구분된 개별 토큰에 등호가 있으면 XAML 프로세서는 먼저 태그 확장의 기본 생성자를 호출합니다.  그런 다음 각 이름\=값 쌍이 태그 확장에 존재하는 속성 이름과 해당 속성에 할당할 값으로 해석됩니다.  
  
-   태그 확장에서 생성자 동작과 속성 설정 동작이 동일한 경우에는 어떤 동작을 사용해도 관계가 없습니다.  설정 가능한 속성이 둘 이상 있는 태그 확장에서는 *property*`=`*value* 쌍을 사용하는 것이 보다 일반적입니다. 그 이유는 태그의 의도를 더욱 명확하게 지정할 수 있고, property\=value 쌍을 지정할 경우 속성 순서가 중요하지 않으므로 실수로 생성자 매개 변수 순서가 바뀌는 일을 방지할 수 있기  때문입니다. 또한 태그 확장이 설정 가능한 속성을 모두 설정하는 생성자 매개 변수를 제공한다는 보장이 없습니다.  예를 들어 <xref:System.Windows.Data.Binding>은 확장에서 *property*`=`*value* 형태로 설정할 수 있는 많은 속성이 있는 태그 확장이지만 <xref:System.Windows.Data.Binding>은 두 가지 생성자, 즉 기본 생성자와 초기 경로를 설정하는 생성자만 지원합니다.  
  
-   리터럴 쉼표는 이스케이프 없이 태그 확장에 전달할 수 없습니다.  
  
<a name="EscapeSequences"></a>   
## 이스케이프 시퀀스 및 태그 확장  
 XAML 프로세서의 특성 처리에서는 중괄호를 태그 확장 시퀀스의 표시기로 사용합니다.  또한 필요한 경우에는 리터럴 중괄호 다음에 비어 있는 중괄호 쌍을 사용하여 이스케이프 시퀀스를 입력함으로써 리터럴 중괄호 문자 특성을 생성할 수 있습니다.  [{} 이스케이프 시퀀스 \/ 태그 확장](../../../../docs/framework/xaml-services/escape-sequence-markup-extension.md)를 참조하십시오.  
  
<a name="Nesting"></a>   
## XAML에서 중첩 태그 확장 사용법  
 여러 태그 확장을 중첩할 수 있으며 각 태그 확장은 가장 깊은 수준부터 사용됩니다.  예를 들어 다음을 사용해 봅니다.  
  
```  
<Setter Property="Background"  
  Value="{DynamicResource {x:Static SystemColors.ControlBrushKey}}" />  
  
```  
  
 이 사용에서 `x:Static` 문이 먼저 계산되고 문자열이 반환됩니다.  그런 다음 해당 문자열은 `DynamicResource`의 인수로 사용됩니다.  
  
## 태그 확장 및 속성 요소 구문  
 속성 요소 값을 채우는 개체 요소로 사용된 경우에는 태그 확장 클래스를 XAML에서 사용할 수 있는 일반적인 형식 기반 개체 요소와 시각적으로 구분할 수 없습니다.  이 경우 일반적인 개체 요소와 태그 확장 간의 실질적인 차이는 태그 확장이 형식화된 값으로 계산되거나 식으로 지연된다는 점입니다.  따라서 다른 프로그래밍 모델에서 런타임에 바인딩되는 속성이 처리되는 방식과 마찬가지로 태그 확장의 속성 값에서 발생할 수 있는 형식 오류에 대한 메커니즘이 달라집니다.  일반적인 개체 요소는 XAML이 구문 분석될 때 해당 요소가 설정하고 있는 대상 속성을 기준으로 형식 일치 여부가 확인됩니다.  
  
 속성 요소를 채우는 개체 요소 구문에 사용되는 대부분의 태그 확장에는 콘텐츠나 추가 속성 요소 구문이 없으므로  개체 요소 태그를 닫고 자식 요소를 제공하지 않을 수 있습니다.  XAML 프로세서에서 개체 요소를 발견할 때마다 해당 클래스의 생성자가 호출되어 구문 분석된 요소에서 생성되는 개체를 인스턴스화합니다.  태그 확장 클래스의 경우에도 마찬가지입니다. 따라서 개체 요소 구문에서 태그 확장을 사용할 수 있으려면 기본 생성자를 제공해야 합니다.  일부 기존 태그 확장에는 효율적인 초기화를 위해 지정해야 하는 필수 속성 값이 적어도 하나는 있습니다.  이런 경우 해당 속성 값은 대개 개체 요소에 속성 특성으로 지정됩니다.  [XAML 네임스페이스\(x:\) 언어 기능](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md) 및 [WPF XAML 확장](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md) 참조 페이지에는 필수 속성이 있는 태그 확장 및 필수 속성의 이름이 나와 있습니다.  또한 참조 페이지에는 특정 태그 확장에서 개체 요소 구문이나 특성 구문을 사용할 수 없는지 여부도 나와 있습니다.  예를 들어 [x:Array 태그 확장](../../../../docs/framework/xaml-services/x-array-markup-extension.md)의 경우에는 배열의 내용을 태그에서 콘텐츠로 지정해야 하기 때문에 특성 구문을 사용할 수 없습니다.  배열 내용은 일반 개체로 처리되므로 특성에 대한 기본 형식 변환기를 사용할 수 없습니다.  [x:Array 태그 확장](../../../../docs/framework/xaml-services/x-array-markup-extension.md)에는 `type` 매개 변수도 필요합니다.  
  
## 참고 항목  
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [XAML 네임스페이스\(x:\) 언어 기능](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)   
 [WPF XAML 확장](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)   
 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)   
 [Binding 태그 확장](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)   
 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)   
 [x:Type 태그 확장](../../../../docs/framework/xaml-services/x-type-markup-extension.md)