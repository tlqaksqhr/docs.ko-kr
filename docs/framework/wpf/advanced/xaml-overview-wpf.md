---
title: "XAML 개요(WPF) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "특성 구문[XAML]"
  - "기본 클래스[XAML]"
  - "클래스[XAML]"
  - "코드 숨김 파일[WPF], XAML"
  - "컬렉션 속성[XAML]"
  - "콘텐츠 모델[XAML]"
  - "이벤트[XAML]"
  - "Extensible Application Markup Language(XAML 참조)"
  - "속성 요소[XAML]"
  - "루트 요소[XAML]"
  - "라우트된 이벤트"
  - "사용자 인터페이스[XAML]"
  - "XAML[WPF], XAML 정보"
ms.assetid: a80db4cd-dd0f-479f-a45f-3740017c22e4
caps.latest.revision: 57
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 50
---
# XAML 개요(WPF)
이 항목에서는 XAML 언어의 기능을 설명하고 XAML을 사용하여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 작성하는 방법을 보여 줍니다.  이 항목에서는 특히 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 구현된 XAML에 대해 자세히 설명합니다.  XAML 자체는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]보다 큰 언어 개념입니다.  
  
   
  
<a name="what_is_xaml"></a>   
## XAML이란?  
 XAML은 선언적 태그 언어입니다.  XAML은 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 프로그래밍 모델에 적용되어 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 쉽게 만들 수 있게 합니다.  선언적 XAML 태그에 표시되는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 만든 다음 코드 숨김 파일을 사용하여 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 정의를 런타임 논리와 구분할 수 있습니다. 이 정의는 partial 클래스 정의를 통해 태그에 연결됩니다.  XAML은 어셈블리에 정의된 특정 지원 형식 집합으로 개체의 인스턴스화를 직접 나타냅니다. 이는 지원 형식 시스템에 직접 연결되지 않고 해석되는 언어인 대부분의 다른 태그 언어와의 차이점입니다.  XAML은 개별 대상이 잠재적으로 서로 다른 도구를 사용하여 응용 프로그램의 논리와 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 대해 작업할 수 있는 워크플로를 가능하게 합니다.  
  
 텍스트로 나타내는 경우 XAML 파일은 일반적으로 확장명이 `.xaml`인 XML 파일입니다.  이 파일은 모든 XML 인코딩 방식으로 인코딩될 수 있지만 일반적으로 UTF\-8로 인코딩됩니다.  
  
 다음 예제에서는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 일부로 단추를 만드는 방법을 보여 줍니다.  이 예제는 XAML이 일반적인 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 프로그래밍 비유를 어떻게 나타내는지를 보여 주기 위한 것이며 전체 샘플이 아닙니다.  
  
 [!code-xml[XAMLOvwSupport#DirtSimple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]  
  
<a name="xaml_syntax_in_brief"></a>   
## XAML 구문 개요  
 다음 단원에서는 XAML 구문의 기본 형식에 대해 설명하고 간단한 태그 예제를 제공합니다.  각 구문 형식에 대해 자세하게 설명하지는 않습니다. 예를 들어, 지원 형식 시스템에서 이러한 구문을 어떻게 나타내는지에 대해서는 설명하지 않습니다.  이 항목에 소개된 각 구문 형식의 XAML 구문에 대한 자세한 내용은 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)를 참조하십시오.  
  
 XML 언어에 이미 익숙한 경우 다음 일부 단원에서 설명하는 내용 중 대부분은 초보적인 것일 수 있습니다.  이는 XAML의 기본적 설계 원칙 중 하나에 따른 결과입니다.  XAML 언어는 고유한 개념을 정의하고 있지만 이러한 개념은 XML 언어 및 태그 형식 내에서 적용됩니다.  
  
### XAML 개체 요소  
 일반적으로 개체 요소는 특정 형식의 인스턴스를 선언합니다.  이 형식은 XAML을 언어로 사용하는 기술에 지원 형식을 제공하는 어셈블리에 정의되어 있습니다.  
  
 개체 요소 구문은 항상 여는 꺾쇠 괄호\(\<\)로 시작합니다.  괄호 뒤에 인스턴스를 만들려는 형식의 이름이 나옵니다.  이름에는 접두사가 포함될 수 있으며, 이 개념에 대해서는 나중에 설명할 것입니다. 이름 뒤에는 개체 요소의 특성을 선택적으로 선언할 수 있습니다.  개체 요소 태그를 완료하려면 닫는 꺾쇠 괄호\(\>\)로 끝냅니다.  또는 슬래시와 닫는 꺾쇠 괄호를 연속해서 사용하여\(\/\>\) 태그를 완료하는 것과 같이 콘텐츠가 없는 자체 닫는 형식을 사용할 수도 있습니다.  예를 들어, 앞에서 나왔던 태그 조각을 다시 살펴보겠습니다.  
  
 [!code-xml[XAMLOvwSupport#DirtSimple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]  
  
 이 코드는 `<StackPanel>`\(콘텐츠 및 나중에 닫는 태그 있음\) 및 `<Button .../>`\(자체 닫는 형식, 여러 특성이 있음\)이라는 두 개의 개체 요소를 지정합니다.  개체 요소 `StackPanel`과 `Button`은 각각 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 정의된 클래스 이름으로 매핑되며 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리의 일부입니다.  개체 요소 태그를 지정할 때 새 인스턴스를 만드는 XAML 처리에 대한 명령을 만듭니다.  XAML을 로드 및 구문 분석할 때 기본 형식의 기본 생성자를 호출하여 각 인스턴스를 만듭니다.  
  
### 특성 구문\(속성\)  
 개체 속성은 개체 요소의 특성으로 표현되는 경우가 많습니다.  특성 구문은 특성 구문에서 설정되는 속성의 이름을 지정하며 뒤에 할당 연산자\(\=\)가 옵니다.  특성 값은 항상 따옴표 안에 포함된 문자열로 지정됩니다.  
  
 특성 구문은 가장 효율적인 속성 설정 구문이며 과거에 태그 언어를 사용한 적이 있는 개발자에게 가장 직관적인 구문입니다.  예를 들어, 다음 태그는 빨간색 텍스트와 파란색 배경이 있으며 `Content`로 지정된 표시 텍스트가 있는 단추를 만듭니다.  
  
 [!code-xml[XAMLOvwSupport#BlueRedButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]  
  
### 속성 요소 구문  
 개체 요소의 일부 속성의 경우에는 속성 값을 제공하기 위해 필요한 개체나 정보를 특성 구문의 문자열 제한에 맞춰 따옴표 안에 적절하게 표현할 수 없기 때문에 특성 구문을 사용할 수 없습니다.  이러한 경우에는 속성 요소 구문이라고 하는 다른 구문을 사용할 수 있습니다.  
  
 속성 요소 시작 태그의 구문은 `<`*typeName*`.`*propertyName*`>`입니다.  일반적으로 해당 태그의 콘텐츠는 속성이 해당 값으로 사용하는 형식의 개체 요소입니다.  콘텐츠를 지정한 후에는 끝 태그로 속성 요소를 닫아야 합니다.  끝 태그에 대한 구문은 `</`*typeName*`.`*propertyName*`>`입니다.  
  
 특성 구문이 지원되는 경우에는 특성 구문을 사용하는 것이 일반적으로 편리하며 태그를 간결하게 만들 수 있지만 이것은 기술적으로 제한이 있다는 것을 의미하는 것이 아니라 대체로 스타일의 문제입니다.  다음 예제에서는 앞의 특성 구문 예제에서와 같이 동일한 속성을 설정하는 것을 보여 주지만 이번에는 `Button`의 모든 속성에 대해 속성 요소 구문을 사용합니다.  
  
 [!code-xml[XAMLOvwSupport#BlueRedButtonPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]  
  
### 컬렉션 구문  
 XAML 언어에는 보다 읽기 쉬운 태그를 생성하는 몇 가지 최적화 기능이 포함되어 있습니다.  이러한 최적화 중 하나는 특정 속성이 컬렉션 형식을 사용하는 경우 태그에서 해당 속성 값 내에 자식 요소로 선언하는 항목이 컬렉션에 포함되는 것입니다.  이 경우 자식 개체 요소의 컬렉션이 컬렉션 속성에 설정되는 값입니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.GradientBrush.GradientStops%2A> 속성의 값을 설정하기 위한 컬렉션 구문을 보여 줍니다.  
  
```xaml  
<LinearGradientBrush>  
  <LinearGradientBrush.GradientStops>  
    <!-- no explicit new GradientStopCollection, parser knows how to find or create -->  
    <GradientStop Offset="0.0" Color="Red" />  
    <GradientStop Offset="1.0" Color="Blue" />  
  </LinearGradientBrush.GradientStops>  
</LinearGradientBrush>  
```  
  
### XAML 콘텐츠 속성  
 XAML은 클래스에서 해당 속성 중 하나를 XAML 콘텐츠 속성으로 정확하게 지정할 수 있는 언어 기능을 지정합니다.  개체 요소의 자식 요소가 해당 콘텐츠 속성의 값을 설정하는 데 사용됩니다.  즉, 콘텐츠 속성이 고유한 경우에는 XAML 태그에서 해당 속성을 설정할 때 속성 요소를 생략하고 태그 내에 보다 가시적인 부모\/자식 비유를 생성할 수 있습니다.  
  
 예를 들어, <xref:System.Windows.Controls.Border>는 <xref:System.Windows.Controls.Decorator.Child%2A>의 콘텐츠 속성을 지정합니다.  다음 두 개의 <xref:System.Windows.Controls.Border> 요소는 동일하게 처리됩니다.  첫 번째 요소는 콘텐츠 속성 구문을 이용하고 `Border.Child` 속성 요소를 생략합니다.  두 번째 요소는 명시적으로 `Border.Child`를 표시합니다.  
  
```xaml  
<Border>  
  <TextBox Width="300"/>  
</Border>  
<!--explicit equivalent-->  
<Border>  
  <Border.Child>  
    <TextBox Width="300"/>  
  </Border.Child>  
</Border>  
```  
  
 XAML 언어의 규칙에 따라 XAML 콘텐츠 속성의 값은 해당 개체 요소의 다른 모든 속성 요소의 맨 앞 또는 맨 뒤에 지정해야 합니다.  예를 들어, 다음 태그는 컴파일되지 않습니다.  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 XAML 콘텐츠 속성의 이러한 제한 사항에 대한 자세한 내용은 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)의 "XAML 콘텐츠 속성" 단원을 참조하십시오.  
  
### 텍스트 콘텐츠  
 일부 XAML 요소는 텍스트를 자신의 콘텐츠로 직접 처리할 수 있습니다.  이렇게 하려면 다음 경우 중 하나에 해당해야 합니다.  
  
-   클래스에서 콘텐츠 속성을 선언해야 하며, 이 콘텐츠 속성이 문자열에 할당할 수 있는 형식이어야 합니다. 형식은 <xref:System.Object>일 수 있습니다.  예를 들어, <xref:System.Windows.Controls.ContentControl>은 <xref:System.Windows.Controls.ContentControl.Content%2A>를 해당 콘텐츠 속성으로 사용하며 <xref:System.Object> 형식입니다. 이 형식은 실제 <xref:System.Windows.Controls.ContentControl>에 대해 <xref:System.Windows.Controls.Button>: `<Button>Hello</Button>`와 같은 사용을 지원합니다.  
  
-   형식에서 형식 변환기를 선언해야 합니다. 이 경우 텍스트 콘텐츠가 이 형식 변환기의 초기화 텍스트로 사용됩니다.  예를 들어, `<Brush>Blue</Brush>`입니다.  이러한 경우는 실제로 그다지 일반적이지 않습니다.  
  
-   형식은 알려진 XAML 언어 기본 형식이어야 합니다.  
  
### 콘텐츠 속성 및 컬렉션 구문 조합  
 다음 예제를 고려해 보십시오.  
  
```xaml  
<StackPanel>  
  <Button>First Button</Button>  
  <Button>Second Button</Button>  
</StackPanel>  
```  
  
 여기서 각 <xref:System.Windows.Controls.Button>은 <xref:System.Windows.Controls.StackPanel>의 자식 요소입니다.  이는 두 가지 서로 다른 이유로 두 태그를 생략하는 효율적이며 직관적인 태그입니다.  
  
-   **생략된 StackPanel.Children 속성 요소:** <xref:System.Windows.Controls.StackPanel>은 <xref:System.Windows.Controls.Panel>에서 파생됩니다.  <xref:System.Windows.Controls.Panel>은 <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=fullName>을 해당 XAML 콘텐츠 속성으로 정의합니다.  
  
-   **생략된 UIElementCollection 개체 요소:** <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=fullName> 속성은 <xref:System.Collections.IList>를 구현하는 <xref:System.Windows.Controls.UIElementCollection> 형식을 사용합니다.  컬렉션 처리에 대한 XAML 규칙\(예: <xref:System.Collections.IList>\)을 기반으로 컬렉션의 요소 태그를 생략할 수 있습니다.  이 경우 <xref:System.Windows.Controls.UIElementCollection>은 기본 생성자를 노출하지 않으므로 실제로 인스턴스화할 수 없으며, <xref:System.Windows.Controls.UIElementCollection> 개체 요소가 주석 처리되어 표시되는 것은 이런 이유 때문입니다.  
  
```xaml  
<StackPanel>  
  <StackPanel.Children>  
    <!--<UIElementCollection>-->  
    <Button>First Button</Button>  
    <Button>Second Button</Button>  
    <!--</UIElementCollection>-->  
  </StackPanel.Children>  
</StackPanel>  
```  
  
### 특성 구문\(이벤트\)  
 속성이 아니라 이벤트인 멤버에 대해서도 특성 구문을 사용할 수 있습니다.  이 경우 특성 이름은 이벤트의 이름입니다.  XAML 이벤트에 대한 WPF 구현에서 특성 값은 해당 이벤트의 대리자를 구현하는 처리기의 이름입니다.  예를 들어, 다음 태그는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대한 처리기를 태그에서 만든 <xref:System.Windows.Controls.Button>에 할당합니다.  
  
 [!code-xml[XAMLOvwSupport#ButtonWithCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]  
  
 WPF의 XAML 및 이벤트에는 이 특성 구문 예제보다 훨씬 더 많은 기능이 있습니다.  예를 들어, 여기서 참조된 `ClickHandler`가 무엇을 나타내며 어떻게 정의되는지가 궁금할 수 있습니다.  이 내용에 대해서는 이 항목의 뒷부분에 있는  단원에서 설명합니다.  
  
<a name="case_and_whitespace_in_xaml"></a>   
## XAML의 대\/소문자 및 공백  
 XAML은 일반적으로 대\/소문자를 구분합니다.  지원 형식을 확인하기 위해 WPF XAML은 CLR에서 대\/소문자를 구분하는 규칙에 따라 대\/소문자를 구분합니다.  개체 요소, 속성 요소 및 특성 이름은 모두 어셈블리의 기본 형식 또는 형식 멤버의 이름과 비교해 대\/소문자를 사용하여 지정해야 합니다.  XAML 언어 키워드 및 기본 형식 또한 대\/소문자를 구분합니다.  그러나 값은 대\/소문자를 항상 구분하지는 않습니다.  값의 대\/소문자 구분은 값 또는 속성 값 형식을 사용하는 속성과 연결된 형식 변환기의 동작에 따라 다릅니다.  예를 들어, <xref:System.Boolean> 형식을 사용하는 속성은 `true` 또는 `True`를 같은 값으로 처리할 수 있지만 이는 문자열을 <xref:System.Boolean>으로 변환하는 네이티브 WPF XAML 파서 형식 변환에서 이미 두 값이 같도록 허용했기 때문입니다.  
  
 WPF XAML 프로세서 및 serializer는 의미 없는 공백은 모두 무시하거나 삭제하고 의미 있는 공백은 모두 정규화합니다.  이는 XAML 사양에서 권장되는 기본 공백 동작과 일관됩니다.  이 동작은 일반적으로 XAML 콘텐츠 속성 안에서 문자열을 지정할 때만 영향을 줍니다.  간단히 말해 XAML은 공백, 줄 바꿈 및 탭 문자가 연속되는 문자열의 끝에 있는 경우 이를 공백으로 변환한 다음 하나의 공백을 유지합니다.  XAML 공백 처리에 대해서는 이 항목에서 자세히 다루지 않습니다.  자세한 내용은 [XAML의 공백 처리](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)를 참조하십시오.  
  
<a name="markup_extensions"></a>   
## 태그 확장  
 태그 확장은 XAML 언어 개념입니다.  특성 구문의 값을 제공하기 위해 사용할 때 중괄호\(`{` 및 `}`\)는 태그 확장 사용을 나타냅니다.  이 사용에서는 특성 값의 일반적인 처리를 리터럴 문자열이나 문자열 변환 가능 값으로 이스케이프하도록 XAML에 지시합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 프로그래밍에 가장 많이 사용되는 태그 확장은 데이터 바인딩 식에 사용되는 [바인딩](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)과 리소스 참조 [StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) 및 [DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)입니다.  태그 확장을 사용하면 일반적으로 속성이 특성 구문을 지원하지 않더라도 특성 구문을 사용하여 속성 값을 제공할 수 있으며,  중간 식 형식을 사용하여 값 지연이나 런타임에만 존재하는 다른 개체 참조와 같은 기능을 활성화할 수 있습니다.  
  
 예를 들어, 다음 태그에서는 특성 구문을 사용하여 <xref:System.Windows.FrameworkElement.Style%2A> 속성의 값을 설정합니다.  <xref:System.Windows.FrameworkElement.Style%2A> 속성은 기본적으로 특성 구문 문자열로 인스턴스화할 수 없는 <xref:System.Windows.Style> 클래스의 인스턴스를 사용합니다.  하지만 이 경우 특성은 특정 태그 확장인 [StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)를 참조합니다.  해당 태그 확장이 처리되면 이전에 리소스 사전에서 키가 지정된 리소스로 인스턴스화된 스타일에 대한 참조를 반환합니다.  
  
<!-- TODO: review snippet reference  [!CODE [FEResourceSH#XAMLOvwShortResources](FEResourceSH#XAMLOvwShortResources)]  -->  
<!-- TODO: review snippet reference [!CODE [FEResourceSH#XAMLOvwShortResources2](FEResourceSH#XAMLOvwShortResources2)]  -->  
<!-- TODO: review snippet reference [!CODE [FEResourceSH#XAMLOvwShortResources3](FEResourceSH#XAMLOvwShortResources3)]  -->  
  
 WPF에 구체적으로 구현된 XAML에 대한 모든 태그 확장의 참조 목록을 보려면 [WPF XAML 확장](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)을 참조하십시오.  System.Xaml에 정의되어 있고 .NET Framework XAML 구현에서 보다 광범위하게 사용 가능한 태그 확장의 참조 목록을 보려면 [XAML 네임스페이스\(x:\) 언어 기능](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)을 참조하십시오.  태그 확장 개념에 대한 자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하십시오.  
  
<a name="type_converters"></a>   
## 형식 변환기  
 단원에서는 문자열로 특성 값을 설정할 수 있어야 한다고 설명했습니다.  문자열이 다른 개체 형식이나 기본 값으로 변환되는 방법에 대한 기본 처리는 <xref:System.String> 형식 자체뿐 아니라 <xref:System.DateTime> 또는 <xref:System.Uri> 같은 특정 형식에 대한 기본 처리를 기반으로 합니다.  그러나 대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 형식 또는 이러한 형식의 멤버는 더 복잡한 개체 형식의 인스턴스를 문자열과 특성으로 지정할 수 있도록 기본 문자열 특성 처리 동작을 확장합니다.  
  
 <xref:System.Windows.Thickness> 구조체는 XAML 사용에 대해 형식 변환이 설정되는 형식의 예입니다.  <xref:System.Windows.Thickness>는 중첩된 사각형 내의 단위를 나타내며, <xref:System.Windows.FrameworkElement.Margin%2A>과 같은 속성의 값으로 사용됩니다.  <xref:System.Windows.Thickness>에 형식 변환기를 적용하면 <xref:System.Windows.Thickness>를 사용하는 모든 속성을 특성으로 지정할 수 있으므로 XAML에서 보다 쉽게 이러한 속성을 지정할 수 있습니다.  다음 예제에서는 형식 변환 및 특성 구문을 사용하여 <xref:System.Windows.FrameworkElement.Margin%2A>의 값을 제공합니다.  
  
 [!code-xml[XAMLOvwSupport#MarginTCE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]  
  
 앞의 특성 구문 예제는 다음의 더 자세한 구문 예제와 동일합니다. 이 예제에서는 <xref:System.Windows.FrameworkElement.Margin%2A>이 <xref:System.Windows.Thickness> 개체 요소를 포함하는 속성 요소 구문을 통해 설정되며,  <xref:System.Windows.Thickness>의 네 가지 주요 속성이 새 인스턴스에서 특성으로 설정됩니다.  
  
 [!code-xml[XAMLOvwSupport#MarginVerbose](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]  
  
> [!NOTE]
>  또한 형식 개체 자체에 기본 생성자가 없기 때문에 서브클래스 없이 형식 변환을 통해서만 해당 형식에 속성을 공개적으로 설정할 수 있는 제한된 개수의 개체가 있습니다.  예를 들면 <xref:System.Windows.Input.Cursor>입니다.  
  
 형식 변환 및 특성 구문에 대한 사용이 지원되는 방법에 대한 자세한 내용은 [TypeConverter 및 XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)을 참조하십시오.  
  
<a name="xaml_root_elements_and_xaml_namespaces"></a>   
## XAML 루트 요소 및 XAML 네임스페이스  
 XAML 파일에는 하나의 루트 요소만 있어야 올바른 형식의 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 파일이자 유효한 XAML 파일이 될 수 있습니다.  일반적인 WPF 시나리오의 경우 WPF 응용 프로그램 모델에서 특별한 의미가 있는 루트 요소를 사용합니다\(예: 페이지의 경우 <xref:System.Windows.Window> 또는 <xref:System.Windows.Controls.Page>, 외부 사전의 경우 <xref:System.Windows.ResourceDictionary>, 응용 프로그램 정의 루트의 경우 <xref:System.Windows.Application>\).  다음 예제에서는 루트 요소가 <xref:System.Windows.Controls.Page>인 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지에 대한 일반적인 XAML 파일의 루트 요소를 보여 줍니다.  
  
 [!code-xml[XAMLOvwSupport#RootOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]  
[!code-xml[XAMLOvwSupport#RootOnly2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]  
  
 루트 요소에는 특성 `xmlns`와 `xmlns:x`도 포함됩니다.  이러한 특성은 태그가 요소로 참조할 요소의 지원 형식에 대한 형식 정의가 포함된 XAML 네임스페이스를 XAML 프로세서에 나타냅니다.  `xmlns` 특성은 특히 기본 XAML 네임스페이스를 나타냅니다.  기본 XAML 네임스페이스 안에서는 태그의 개체 요소를 접두사 없이 지정할 수 있습니다.  대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 시나리오 및 [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 단원에 나오는 거의 모든 예제의 경우 기본 XAML 네임스페이스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 네임스페이스 [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]에 매핑됩니다.  `xmlns:x` 특성은 XAML 언어 네임스페이스 [!INCLUDE[TLA#tla_xamlxmlnsv1](../../../../includes/tlasharptla-xamlxmlnsv1-md.md)]를 매핑하는 추가적인 XAML 네임스페이스를 나타냅니다.  
  
 `xmlns`를 사용하여 이름 범위의 사용 및 매핑 범위를 정의하는 방식은 XML 1.0 사양과 일치합니다.  XAML 이름 범위는 형식 확인 및 XAML 구문 분석에 적용할 경우 형식이 이름 범위의 요소를 지원하는 방법도 암시한다는 점에서 XAML 이름 범위와는 다릅니다.  
  
 `xmlns` 특성은 각 XAML 파일의 루트 요소에서만 엄격하게 필요합니다.  `xmlns` 정의는 루트 요소의 모든 하위 요소에 적용됩니다\(이 동작은 `xmlns`에 대한 XML 1.0 사양과 일치함\). `xmlns` 특성은 루트 아래의 다른 요소에서도 허용되며, 정의 요소의 모든 하위 요소에 적용됩니다.  그러나 XAML 네임스페이스를 자주 정의하거나 재정의할 경우 XAML 태그 스타일을 읽기 어렵게 될 수 있습니다.  
  
 XAML 프로세서의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현에는 WPF 핵심 어셈블리를 인식하는 인프라가 포함되어 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 핵심 어셈블리는 기본 XAML 네임스페이스로의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 매핑을 지원하는 형식을 포함한다고 알려져 있습니다.  이 어셈블리는 프로젝트 빌드 파일과 WPF 빌드 및 프로젝트 시스템에 속하는 구성을 통해 사용할 수 있습니다.  따라서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리에서 제공된 XAML 요소를 참조하려는 경우 기본 XAML 네임스페이스를 기본 `xmlns`로 선언하기만 하면 됩니다.  
  
### x: 접두사  
 앞의 루트 요소 예제에서는 접두사 `x:`를 사용하여 XAML 언어 구문을 지원하는 전용 XAML 네임스페이스인 XAML 네임스페이스 [!INCLUDE[TLA#tla_xamlxmlnsv1](../../../../includes/tlasharptla-xamlxmlnsv1-md.md)]를 매핑했습니다.  이 `x:` 접두사는 이 [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] 전체의 설명서, 예제 및 프로젝트 템플릿에서 이 XAML 네임스페이스를 매핑하는 데 사용됩니다.  XAML 언어의 XAML 네임스페이스에는 XAML에서 자주 사용하게 될 몇 가지 프로그래밍 구문이 들어 있습니다.  다음은 가장 많이 사용하게 될 `x:` 접두사 네임스페이스 프로그래밍 구문의 목록입니다.  
  
-   [x:Key](../../../../docs/framework/xaml-services/x-key-directive.md): <xref:System.Windows.ResourceDictionary>\(또는 다른 프레임워크의 유사한 사전 개념\)의 각 리소스에 대한 고유한 키를 설정합니다.  `x:Key`는 일반적인 WPF 응용 프로그램 태그에서 보게 될 `x:` 사용의 90%를 차지할 것입니다.  
  
-   [x:Class](../../../../docs/framework/xaml-services/x-class-directive.md): [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 네임스페이스 및 XAML 페이지에 대한 코드 숨김을 제공하는 클래스의 클래스 이름을 지정합니다.  이러한 클래스가 WPF 프로그래밍 모델에 대해 코드 숨김을 지원하도록 해야 하므로 리소스가 없는 경우에도 `x:`가 매핑된 것을 자주 보게 됩니다.  
  
-   [x:Name](../../../../docs/framework/xaml-services/x-name-directive.md): 개체 요소가 처리된 후 런타임 코드에 있는 인스턴스에 대한 런타임 개체 이름을 지정합니다.  일반적으로는 [x:Name](../../../../docs/framework/xaml-services/x-name-directive.md)에 대응하여 WPF에 정의된 속성을 자주 사용하게 됩니다.  이러한 속성은 특히 CLR 지원 속성에 매핑되므로 초기화된 XAML에서 명명된 요소를 찾기 위해 런타임 코드를 자주 사용하는 응용 프로그램 작성에 보다 편리합니다.  이러한 속성 중 가장 널리 사용되는 속성은 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=fullName>입니다.  상응하는 [WPF 프레임워크 수준](GTMT) <xref:System.Windows.FrameworkElement.Name%2A> 속성이 특정 형식에서 지원되지 않으면 [x:Name](../../../../docs/framework/xaml-services/x-name-directive.md)을 계속 사용할 수 있습니다.  이는 특정 애니메이션 시나리오에서 볼 수 있는 상황입니다.  
  
-   [x:Static](../../../../docs/framework/xaml-services/x-static-markup-extension.md): XAML 호환 속성이 아닌 정적 값을 반환하는 참조를 사용할 수 있게 합니다.  
  
-   [x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md): 형식 이름을 기반으로 <xref:System.Type> 참조를 생성합니다.  <xref:System.Windows.Style.TargetType%2A?displayProperty=fullName>과 같은 <xref:System.Type>을 사용하는 특성을 지정하는 데 사용합니다. 하지만 대부분의 경우 속성에는 기본 문자열 대 <xref:System.Type> conversion in such a way that the [x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md) 태그 확장 사용은 선택 사항입니다.  
  
 `x:` 접두사\/XAML 네임스페이스에는 일반적으로는 사용되지 않는 추가적인 프로그래밍 구문이 있습니다.  자세한 내용은 [XAML 네임스페이스\(x:\) 언어 기능](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)을 참조하십시오.  
  
<a name="custom_prefixes_and_custom_types_in_xaml"></a>   
## XAML의 사용자 지정 접두사 및 사용자 지정 형식  
 사용자 지정 어셈블리 또는 PresentationCore, PresentationFramework 및 WindowsBase의 WPF 핵심 이외의 어셈블리에 대해 사용자 지정 `xmlns` 매핑의 일부로 어셈블리를 지정할 수 있습니다.  현재 시도 중인 XAML 사용을 지원하도록 해당 형식이 제대로 구현되어 있으면 XAML에서 해당 어셈블리의 형식을 참조할 수 있습니다.  
  
 다음은 사용자 지정 접두사가 XAML 태그에서 작동하는 방식을 보여 주는 기본 예제입니다.  접두사 `custom`은 루트 요소 태그에 정의되고, 응용 프로그램과 함께 패키지되고 사용 가능한 특정 어셈블리에 매핑됩니다.  이 어셈블리에는 일반적인 XAML 사용뿐 아니라 WPF XAML 콘텐츠 모델의 이 특정 시점에 삽입될 수 있는 클래스 상속 사용을 지원하도록 구현된 `NumericUpDown` 형식이 들어 있습니다.  이 `NumericUpDown` 컨트롤 인스턴스는 접두사를 사용하여 개체 요소로 선언되므로 XAML 파서에서 형식이 포함된 XAML 네임스페이스 및 형식 정의가 들어 있는 지원 어셈블리가 있는 위치를 알 수 있습니다.  
  
```  
<Page  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"   
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"   
    xmlns:custom="clr-namespace:NumericUpDownCustomControl;assembly=CustomLibrary"  
    >  
  <StackPanel Name="LayoutRoot">  
    <custom:NumericUpDown Name="numericCtrl1" Width="100" Height="60"/>  
...  
  </StackPanel>  
</Page>  
```  
  
 XAML의 사용자 지정 형식에 대한 자세한 내용은 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)를 참조하십시오.  
  
 XML 네임스페이스와 어셈블리 백업 코드의 네임스페이스가 어떻게 관련되는지에 대한 자세한 내용은 [WPF XAML을 위한 XAML 네임스페이스 및 네임스페이스 매핑](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)을 참조하십시오.  
  
<a name="events_and_xaml_codebehind"></a>   
## 이벤트 및 XAML 코드 숨김  
 대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 XAML 태그와 코드 숨김으로 구성됩니다.  프로젝트에서 XAML은 `.xaml` 파일로 작성되며 코드 숨김 파일은 [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] 또는 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 등의 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 언어를 사용하여 작성됩니다.  XAML 파일이 WPF 프로그래밍 및 응용 프로그램 모델의 일부로 태그 컴파일될 때 XAML 파일에 대한 XAML 코드 숨김 파일의 위치는 네임스페이스와 클래스를 XAML 루트 요소의 `x:Class` 특성으로 지정하여 식별합니다.  
  
 지금까지의 예제에서 몇 개의 단추를 살펴보았지만 아직 논리적 동작이 연결된 단추는 없었습니다.  개체 요소에 대한 동작을 추가하는 기본 응용 프로그램 수준 메커니즘은, 요소 클래스의 기존 이벤트를 사용하고 런타임에서 해당 이벤트가 발생할 때 호출되는 해당 이벤트에 대한 특정 처리기를 작성하는 것입니다.  사용할 이벤트 이름과 처리기 이름은 태그에서 지정하고 처리기를 구현하는 코드는 코드 숨김에서 정의합니다.  
  
 [!code-xml[XAMLOvwSupport#ButtonWithCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]  
  
 [!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
 [!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]  
  
 코드 숨김 파일은 CLR 네임스페이스 `ExampleNamespace`를 사용하며 `ExamplePage`를 해당 네임스페이스 안에서 partial 클래스로 선언합니다.  이는 태그 루트에 제공되는 `ExampleNamespace`.`ExamplePage`의 `x:Class` 특성 값과 비교됩니다.  WPF 태그 컴파일러는 루트 요소 형식에서 클래스를 파생하여 모든 컴파일된 XAML 파일에 대한 partial 클래스를 만듭니다.  같은 partial 클래스를 정의하는 코드 숨김을 제공하는 경우, 결과 코드는 컴파일된 응용 프로그램의 동일한 네임스페이스와 클래스 안에서 결합됩니다.  
  
 WPF에서의 코드 숨김 프로그래밍 요구 사항에 대한 자세한 내용은 [WPF의 코드 숨김 및 XAML](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)의 "코드 숨김, 이벤트 처리기 및 partial 클래스 요구 사항" 단원을 참조하십시오.  
  
 별도의 코드 숨김 파일을 만들지 않으려면 코드를 XAML 파일 안에 인라인으로 넣을 수도 있습니다.  하지만 인라인 코드는 제한이 많은 기술입니다.  자세한 내용은 [WPF의 코드 숨김 및 XAML](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)을 참조하십시오.  
  
### 라우트된 이벤트  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 기본이 되는 [라우트된 이벤트](GTMT)라는 기능이 있습니다.  라우트된 이벤트를 사용하면 요소가 다른 요소에 의해 발생한 이벤트를 처리할 수 있습니다. 단, 요소들이 트리 관계를 통해 연결되어 있어야 합니다.  XAML 특성을 사용하여 이벤트 처리를 지정할 때 라우트된 이벤트는 클래스 멤버 테이블에서 해당 이벤트를 나열하지 않는 요소를 포함하여 모든 요소에서 수신되고 처리될 수 있습니다.  이렇게 하려면 소유 클래스 이름으로 이벤트 이름 특성을 정규화합니다.  예를 들어, `StackPanel` \/ `Button` 예제의 부모 `StackPanel`은 처리기 이름을 특성 값으로 사용하고 `StackPanel` 개체 요소에 대해 `Button.Click` 특성을 지정하여 자식 요소 단추의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대한 처리기를 등록할 수 있습니다.  라우트된 이벤트의 작동 방식에 대한 자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하십시오.  
  
<a name="x_name_and_xaml_named_elements"></a>   
## XAML 명명된 요소  
 기본적으로 XAML 개체 요소 처리를 통해 개체 그래프에서 만들어진 개체 인스턴스는 고유한 식별자 또는 개체 참조를 가지지 않습니다.  이와 달리 코드에서 생성자를 호출할 때는 나중에 코드에서 인스턴스를 참조할 수 있도록 대개는 생성자 결과를 사용하여 변수를 생성된 인스턴스로 설정합니다.  태그 정의를 통해 만들어진 개체에 대한 표준화된 액세스를 제공하기 위해 XAML은 [x:Name 특성](../../../../docs/framework/xaml-services/x-name-directive.md)을 정의합니다.  모든 개체 요소에 대해 `x:Name` 특성의 값을 설정할 수 있습니다.  코드 숨김에서 선택한 식별자는 구성된 인스턴스를 참조하는 인스턴스 변수와 같습니다.  명명된 요소는 모든 측면에서 개체 인스턴스인 것처럼 작동하며\(이름은 해당 인스턴스를 참조함\) 코드 숨김은 명명된 요소를 참조하여 응용 프로그램 안에서 런타임 상호 작용을 처리할 수 있습니다.  인스턴스와 변수 간의 이 연결은 WPF XAML 태그 컴파일러에 의해 이루어지며, 보다 구체적으로는 <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A> 같은 기능 및 패턴이 관련됩니다. 이러한 기능 및 패턴에 대해서는 이 항목에서 자세히 설명하지 않습니다.  
  
 [WPF 프레임워크 수준](GTMT) XAML 요소는 XAML로 정의된 `x:Name` 특성과 동일한 <xref:System.Windows.FrameworkElement.Name%2A> 속성을 상속합니다.  다른 특정 클래스에서도 `x:Name`에 해당하는 속성 수준 속성을 제공하며 이것은 일반적으로 `Name` 속성으로도 정의됩니다.  일반적으로, 멤버 표에서 선택한 요소\/형식의 `Name` 속성을 찾을 수 없는 경우 `x:Name`을 대신 사용합니다.  `x:Name` 값은 XAML 요소에 대한 식별자를 제공하고, 이 식별자는 특정 하위 시스템 또는 <xref:System.Windows.FrameworkElement.FindName%2A> 같은 유틸리티 메서드에 의해 런타임에 사용될 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.StackPanel> 요소에 <xref:System.Windows.FrameworkElement.Name%2A>을 설정합니다.  그런 다음 해당 <xref:System.Windows.Controls.StackPanel> 내의 <xref:System.Windows.Controls.Button>에 대한 처리기가 <xref:System.Windows.FrameworkElement.Name%2A>에 설정된 대로 인스턴스 참조 `buttonContainer`를 통해 <xref:System.Windows.Controls.StackPanel>을 참조합니다.  
  
 [!code-xml[XAMLOvwSupport#NamedE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]  
[!code-xml[XAMLOvwSupport#NamedE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]  
  
 [!code-csharp[XAMLOvwSupport#NameCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
 [!code-vb[XAMLOvwSupport#NameCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]  
  
 변수와 마찬가지로 인스턴스의 XAML 이름도 범위라는 개념으로 제어됩니다. 즉, 예측 가능한 특정 범위 내에서 이름이 고유해야 합니다.  페이지를 정의하는 기본 태그는 해당 페이지의 루트 요소인 XAML 이름 범위 경계를 사용하여 하나의 고유한 XAML 이름 범위를 지정합니다.  하지만 다른 태그 소스는 런타임에 스타일 안의 템플릿 또는 스타일과 같은 페이지와 상호 작용할 수 있으며, 이러한 태그 소스에는 페이지의 XAML 이름 범위와 연결되지 않아도 되는 자체 XAML 이름 범위가 있는 경우가 많습니다.  `x:Name` 및 XAML 이름 범위에 대한 자세한 내용은 <xref:System.Windows.FrameworkElement.Name%2A>, [x:Name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md) 또는 [WPF XAML 이름 범위](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)를 참조하십시오.  
  
<a name="attached_properties_and_attached_events"></a>   
## 연결된 속성 및 연결된 이벤트  
 XAML에서는 속성이나 이벤트가 설정되는 요소의 형식 정의에 존재하는지 여부에 관계없이 임의의 요소에 특정 속성이나 이벤트를 지정할 수 있도록 하는 언어 기능을 지정합니다.  이 기능의 속성 버전을 [연결된 속성](GTMT)이라고 하고 이벤트 버전을 [연결된 이벤트](GTMT)라고 합니다.  개념적으로 볼 때 연결된 속성과 연결된 이벤트는 모든 XAML 요소\/개체 인스턴스에 설정할 수 있는 전역 멤버로 생각할 수 있습니다.  그러나 해당 요소\/클래스 또는 보다 큰 인프라는 연결된 값에 대해 지원 속성 저장소를 지원해야 합니다.  
  
 XAML의 연결된 속성은 일반적으로 특성 구문을 통해 사용합니다.  특성 구문에서는 연결된 속성을 *ownerType*.*propertyName* 형식으로 지정합니다.  
  
 이는 속성 요소 사용과 비슷해 보이지만 이 경우 지정하는 *ownerType*은 연결된 속성이 설정되는 개체 요소와 형식이 항상 다릅니다.  *ownerType*은 연결된 속성 값을 가져오거나 설정하기 위해 XAML 프로세서에 필요한 접근자 메서드를 제공하는 형식입니다.  
  
 연결된 속성에 대한 가장 일반적인 시나리오는 자식 요소가 부모 요소에 속성 값을 보고하도록 하는 것입니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> 연결된 속성을 보여 줍니다.  <xref:System.Windows.Controls.DockPanel> 클래스는 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>에 대한 접근자를 정의하며 따라서 연결된 속성을 소유합니다.  <xref:System.Windows.Controls.DockPanel> 클래스에는 자식 요소를 반복하고 각 요소에서 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>의 설정 값을 검사하는 논리도 포함됩니다.  값이 발견되면 레이아웃 도중 이 값을 사용하여 자식 요소를 배치합니다.  <xref:System.Windows.Controls.DockPanel> 클래스에 대한 시나리오도 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> 연결된 속성 및 이 위치 지정 기능을 사용하기 위해서입니다.  
  
 [!code-xml[XAMLOvwSupport#DockAP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 모든 연결된 속성은 거의 또는 모두 [종속성 속성](GTMT)으로도 구현됩니다.  자세한 내용은 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)를 참조하십시오.  
  
 연결된 이벤트는 비슷한 *ownerType*.*eventName* 특성 구문 형식을 사용합니다.  연결되지 않은 이벤트와 마찬가지로 XAML의 연결된 이벤트에 대한 특성 값은 이벤트가 요소에서 처리될 때 호출되는 처리기 메서드의 이름을 지정합니다.  WPF XAML에서 연결된 이벤트를 사용하는 것은 상대적으로 일반적이지 않습니다.  자세한 내용은 [연결된 이벤트 개요](../../../../docs/framework/wpf/advanced/attached-events-overview.md)를 참조하십시오.  
  
<a name="base_classes_and_xaml"></a>   
## 기본 형식 및 XAML  
 내부 WPF XAML 및 해당 XAML 네임스페이스는 XAML의 태그 요소이자 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체에 해당하는 형식의 컬렉션입니다.  하지만 모든 클래스를 요소에 매핑할 수 있는 것은 아닙니다.  <xref:System.Windows.Controls.Primitives.ButtonBase>와 같은 추상 클래스 및 특정 비추상 기본 클래스는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체 모델에서 상속에 사용됩니다.  각각의 구체적인 XAML 요소는 계층 구조의 일부 기본 클래스에서 멤버를 상속하기 때문에 추상 클래스를 포함한 기본 클래스는 여전히 XAML 개발에 있어서 중요합니다.  이러한 멤버에는 대개 요소에서 특성으로 설정할 수 있는 속성 또는 처리될 수 있는 이벤트가 포함됩니다.  <xref:System.Windows.FrameworkElement>는 [WPF 프레임워크 수준](GTMT)에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 구체적 기본 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 클래스입니다.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 디자인할 때는 모두 <xref:System.Windows.FrameworkElement>에서 파생되는 다양한 도형, 패널, 데코레이터 또는 컨트롤 클래스를 사용합니다.  관련 기본 클래스인 <xref:System.Windows.FrameworkContentElement>는 <xref:System.Windows.FrameworkElement>에서 의도적으로 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 미러링하는 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 사용하여, 유동 레이아웃 표현에 잘 작동하는 문서 지향적 요소를 지원합니다.  요소 수준 및 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체 모델에서 특성의 조합은 특정 요소 및 해당 기본 형식에 관계없이 대부분의 구체적 XAML 요소에 설정할 수 있는 공통 속성 집합을 제공합니다.  
  
<a name="xaml_security"></a>   
## XAML 보안  
 XAML은 개체 인스턴스화 및 실행을 직접적으로 나타내는 태그 언어입니다.  따라서 XAML에서 만든 요소에는 생성된 해당 코드가 수행하는 것과 마찬가지로 시스템 리소스\(예: 네트워크 액세스, 파일 시스템 IO\)와 상호 작용하는 동일한 기능이 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 보안 프레임워크인 [!INCLUDE[TLA#tla_cas](../../../../includes/tlasharptla-cas-md.md)]를 지원합니다.  즉, 인터넷 영역에서 실행되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠는 실행 권한이 줄어듭니다. 이때   "느슨한 XAML"\(컴파일되지 않은 XAML의 페이지가 로드 시 XAML 뷰어에 의해 해석됨\) 및 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]는 일반적으로 이 인터넷 영역에서 실행되며 같은 권한 집합을 사용합니다.  하지만 완전히 신뢰할 수 있는 응용 프로그램으로 로드된 XAML은 시스템 리소스에 대해 호스팅 응용 프로그램과 동일한 액세스 권한을 가집니다.  자세한 내용은 [WPF 부분 신뢰 보안](../../../../docs/framework/wpf/wpf-partial-trust-security.md)을 참조하십시오.  
  
<a name="loading_xaml_from_code"></a>   
## 코드에서 XAML 로드  
 XAML을 사용하여 전체 UI를 정의할 수 있지만 XAML에서 UI의 일부만 정의하는 것이 적합할 때도 있습니다.  이 기능을 통해 부분 사용자 지정, 정보의 로컬 저장, XAML을 사용한 비즈니스 개체 제공을 비롯한 가능한 다양한 시나리오를 지원할 수 있습니다.  이러한 시나리오에서 핵심 역할을 하는 것은 <xref:System.Windows.Markup.XamlReader> 클래스 및 해당 <xref:System.Windows.Markup.XamlReader.Load%2A> 메서드입니다.  입력은 XAML 파일이며 출력은 해당 태그에서 만들어진 개체의 전체 런타임 트리를 나타내는 개체입니다.  그런 다음 응용 프로그램에 이미 존재하는 다른 개체의 속성으로 개체를 삽입할 수 있습니다.  속성이 표시 기능을 가지고 있으며 응용 프로그램에 새 콘텐츠가 추가되었음을 실행 엔진에 알리는 콘텐츠 모델의 적절한 속성인 경우에는 XAML에 로드하여 실행 중인 응용 프로그램의 콘텐츠를 쉽게 수정할 수 있습니다.  하지만 이 기능은 실행되는 응용 프로그램에 파일을 로드함으로써 보안에 가져올 수 있는 영향을 감안하여 일반적으로 완전히 신뢰할 수 있는 응용 프로그램에서만 사용할 수 있게 되어 있습니다.  
  
<a name="whats_next"></a>   
## 새로운 기능  
 이 항목에서는 WPF에 적용되는 XAML 구문 개념과 용어에 대한 기본적인 내용을 소개했습니다.  이 항목에서 사용된 용어에 대한 자세한 내용은 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)를 참조하십시오.  
  
 자습서 항목 [연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)의 연습을 아직 수행하지 않은 경우 수행해 보십시오.  자습서에서 설명하는 태그 중심 응용 프로그램을 만들어보면 이 항목에서 설명하는 많은 개념을 더 확실하게 이해할 수 있을 것입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 <xref:System.Windows.Application> 클래스를 기반으로 하는 특정 응용 프로그램 모델을 사용합니다.  자세한 내용은 [응용 프로그램 관리 개요](../../../../docs/framework/wpf/app-development/application-management-overview.md)를 참조하십시오.  
  
 [WPF 응용 프로그램 만들기](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)에서는 명령줄에서 그리고 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]를 사용하여 XAML 포함 응용 프로그램을 만드는 방법에 대해 더 자세하게 설명합니다.  
  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 다양한 속성에 대해 자세히 설명하고 [종속성 속성](GTMT)의 개념을 소개합니다.  
  
## 참고 항목  
 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)   
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [XAML 네임스페이스\(x:\) 언어 기능](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)   
 [WPF XAML 확장](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)   
 [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)