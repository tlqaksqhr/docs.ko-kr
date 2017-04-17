---
title: "x:Name Directive | Microsoft Docs"
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
  - "x:Name"
  - "xName"
  - "Name"
helpviewer_keywords: 
  - "x:Name attribute [XAML Services]"
  - "XAML [XAML Services], x:Name attribute"
  - "Name attribute in XAML [XAML Services]"
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
caps.latest.revision: 27
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 27
---
# x:Name Directive
XAML 네임스페이스에서 XAML 정의 요소를 고유하게 식별합니다.  XAML 이름 범위와 그들의 고유성 모델은 프레임워크에서 API를 제공하거나 런타임 시 XAML에서 생성된 개체 그래프에 액세스하는 동작을 구현하는 경우 인스턴스화된 개체에 적용할 수 있습니다.  
  
## XAML 특성 사용  
  
```  
<object x:Name="XAMLNameValue".../>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`XAMLNameValue`|[XamlName 문법](../../../docs/framework/xaml-services/xamlname-grammar.md) 제한을 따르는 문자열입니다.|  
  
## 설명  
 프레임워크의 백업 프로그래밍 모델에 `x:Name`을 적용한 후에 이름은 생성자에서 반환한 개체 참조 또는 인스턴스를 보유하는 변수와 같습니다.  
  
 XAML 네임스페이스 내에서 사용한 `x:Name` 지시문 값은 고유해야 합니다.  기본적으로 .NET Framework XAML 서비스 API를 사용할 때 주 XAML 네임스페이스는 단일 XAML 프로덕션의 XAML 루트 요소에 정의되며 해당 XAML 프로덕션에 포함된 요소가 들어 있습니다.  단일 XAML 프로덕션 내에서 발생할 수 있는 추가의 개별 XAML 네임스페이스는 특정 시나리오를 해결하기 위해 프레임워크에 의해 정의될 수 있습니다.  예를 들어, WPF에서 새로운 XAML 네임스페이스는 해당 XAML 프로덕션에도 정의된 템플릿에 의해 정의되고 만들어집니다.  XAML 이름 범위\(WPF를 위해 작성되었지만 많은 XAML 이름 범위 개념과 관련\)에 대한 자세한 내용은 [WPF XAML 이름 범위](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)를 참조하십시오.  
  
 일반적으로 `x:Name`은 `x:Key`도 사용하는 상황에 적용해서는 안 됩니다.  기존의 특정 프레임워크에 의한 XAML 구현에서 `x:Key`와 `x:Name` 사이에 대체 개념을 도입했으나 이는 권장되는 사례는 아닙니다.  .NET Framework XAML 서비스는 <xref:System.Windows.Markup.INameScope> 또는 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>와 같은 이름\/키 정보를 처리할 때 이러한 대체 개념을 지원하지 않습니다.  
  
 `x:Name`는 물론 이름 고유성 적용의 허용 규칙은 특정 구현 프레임워크에 의해 정의될 수 있습니다.  그러나 .NET Framework XAML 서비스와 함께 사용하려면 XAML 네임스페이스 고유성의 프레임워크 정의는 본 문서에서  <xref:System.Windows.Markup.INameScope> 정보의 정의와 일관성이 있어야 하며 해당 정보가 적용되는 부분과 관련하여 동일한 규칙을 사용해야 합니다.  예를 들어, [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 구현은 다양한 태그 요소를 리소스 사전, 페이지 수준의 XAML에서 만든 논리 트리, 템플릿 및 기타 지연 콘텐츠 등과 같은 별도의 <xref:System.Windows.NameScope> 범위로 나눈 다음 각 XAML 네임스페이스 내에서 XAML 이름 고유성을 적용합니다.  
  
 .NET Framework XAML 서비스 XAML 개체 작성자가를 사용하는 사용자 지정 형식의 경우 해당 형식에 있는 `x:Name`에 매핑되는 속성은 설정하거나 변경할 수 있습니다.  이 형식 정의 코드에서는 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>와 함께 매핑할 속성의 이름을 참조하여 이 동작을 정의합니다.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>는 형식 수준 특성입니다.  
  
 .NET Framework XAML 서비스를 사용하여 XAML 네임스페이스 지원에 대한 지원 논리는 <xref:System.Windows.Markup.INameScope> 인터페이스를 구현하여 프레임워크에 중립적인 방법으로 정의할 수 있습니다.  
  
## WPF 사용 정보  
 XAML, partial 클래스 및 코드 숨김을 사용하는 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 대한 표준 빌드 구성에서 지정한 `x:Name`은 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]이 처리되면 기본 코드로 생성되는 필드의 이름이 되고 해당 필드는 개체에 대한 참조를 보유합니다. 생성된 필드는 기본적으로 내부입니다.  필드에 대한 액세스는 [x:FieldModifier 특성](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)을 지정하여 변경할 수 있습니다.  WPF 및 Silverlight에서 시퀀스는 태그 컴파일이 partial 클래스에서 필드를 정의하고 이름을 지정하지만 처음에 값은 비어 있음을 의미합니다.  그런 다음, `InitializeComponent`라는 생성된 메서드가 클래스 생성자 내에서 호출됩니다.  `InitializeComponent`는 partial 클래스의 XAML로 정의된 파트에 있는 각 `x:Name` 값을 입력 문자열로 사용함으로써 `FindName` 호출을 구성합니다.  그런 다음 반환 값은 비슷한 이름의 필드 참조에 할당되어 XAML 구문 분석에서 만든 개체로 필드 값을 입력합니다.  `InitializeComponent`를 실행하면 XAML로 정의되는 개체에 대한 참조를 필요로 할 때마다 `FindName`을 호출해야 하는 경우가 아닌 `x:Name`을 사용하여 런타임 개체 그래프를 직접 참조할 수 있습니다.  
  
 [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] 대상을 사용하고 `Page` 빌드 작업이 있는 XAML 파일을 포함하는 WPF 응용 프로그램의 경우에는 컴파일 시 별도의 참조 속성이 만들어지는데 이 참조 속성은 이벤트 처리기 대리자에 `Handles` 구문을 사용할 수 있도록 `x:Name`을 가진 모든 요소에 `WithEvents` 키워드를 추가합니다.  이 속성은 항상 public 속성입니다.  자세한 내용은 [Visual Basic 및 WPF 이벤트 처리](../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md)를 참조하십시오.  
  
 `x:Name`은 페이지가 빌드 작업을 통해 태그 컴파일되지 않은 경우\(예: 리소스 사전의 느슨한 XAML\)에도 로드 시 이름을 XAML 네임스페이스에 등록하기 위해 WPF XAML 프로세서에서 사용됩니다.  이러한 동작의 이유 중 하나는 <xref:System.Windows.Data.Binding.ElementName%2A> 바인딩에 `x:Name`이 필요하기 때문입니다.  자세한 내용은 [데이터 바인딩 개요](../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
 앞에서 설명한 것처럼 `x:Name`\(또는 `Name`\)은 `x:Key`도 사용하는 상황에 적용해서는 안 됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary>는 자체적으로 XAML 이름 범위로 정의되지만 이 동작을 시행하는 방법으로 <xref:System.Windows.Markup.INameScope> API에 대해서는 구현 안 됨 또는 null 값을 반환하는 특별한 동작을 가지고 있습니다.  WPF XAML 파서에서 XAML로 정의된 <xref:System.Windows.ResourceDictionary>에서 `Name` 또는 `x:Name`이 발견되면 해당 이름은 모든 XAML 네임스페이스에 추가되지 않습니다.  XAML 네임스페이스와 `FindName` 메서드에서 해당 이름을 찾으려고 하면 유효한 결과가 반환되지 않습니다.  
  
### x:이름 및 이름  
 많은 WPF 응용 프로그램 시나리오는 <xref:System.Windows.FrameworkElement> 및 <xref:System.Windows.FrameworkContentElement>와 같은 몇 가지 중요한 기본 클래스의 기본 XAML 네임스페이스에 지정된 `Name` 종속성 속성을 동일한 용도로 사용할 수 있기 때문에 `x:Name` 특성을 사용하지 않을 수도 있습니다.  프레임워크 수준에서 `Name` 속성이 없는 요소에 대한 코드 액세스가 중요한 일반적인 XAML 및 WPF 시나리오도 있습니다.  예를 들어, 특정 애니메이션과 스토리보드 지원 클래스는 `Name` 속성을 지원하지 않지만 애니메이션을 제어하려면 코드에서 참조해야 합니다.  이후 코드에서 참조하려면 XAML에서 생성되는 시간 표시 및 변환의 속성으로 `x:Name`을 지정해야 합니다.  
  
 <xref:System.Windows.FrameworkElement.Name%2A>을 클래스의 속성으로 사용할 수 있으면 <xref:System.Windows.FrameworkElement.Name%2A> 및 `x:Name`을 특성으로 번갈아 사용할 수 있지만 같은 요소에 둘 다 지정하면 구문 분석 예외가 발생합니다.  XAML이 태그 컴파일된 경우 태그 컴파일에 예외가 발생하며, 그렇지 않은 경우 로드가 발생합니다.  
  
 <xref:System.Windows.FrameworkElement.Name%2A>은 XAML 특성 구문을 사용하거나 코드에서 <xref:System.Windows.DependencyObject.SetValue%2A>를 사용하여 설정할 수 있습니다. 그러나 <xref:System.Windows.FrameworkElement.Name%2A> 속성을 코드에서 설정하면 XAML이 이미 로드된 대부분의 환경에서는 XAML 이름 범위에 해당 필드 참조가 만들어지지 않는 경우도 있습니다.  <xref:System.Windows.FrameworkElement.Name%2A>을 코드에서 설정하는 대신 코드에서 적절한 이름 범위에 대해 <xref:System.Windows.NameScope> 메서드를 사용하는 것이 좋습니다.  
  
 <xref:System.Windows.FrameworkElement.Name%2A>은 내부 텍스트로 속성 요소 구문을 사용하여 또한 설정할 수 있지만 일반적이지 않은 것입니다.  이와 대조적으로 `x:Name`은 XAML 속성 요소 구문 또는 <xref:System.Windows.DependencyObject.SetValue%2A>를 사용하는 코드로 설정할 수 없습니다. 지시문이므로 오직 개체의 특성 구문을 사용하여 설정할 수 있습니다.  
  
## Silverlight 사용 정보  
 Silverlight용 `x:Name`는 별도로 문서화되어 있습니다.  자세한 내용은 [XAML Namespace \(x:\) Language Features \(Silverlight\)](http://go.microsoft.com/fwlink/?LinkId=199081)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=fullName>   
 <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=fullName>   
 [WPF의 트리](../../../docs/framework/wpf/advanced/trees-in-wpf.md)