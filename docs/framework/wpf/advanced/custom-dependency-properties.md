---
title: "사용자 지정 종속성 속성 | Microsoft Docs"
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
  - "사용자 지정 종속성 속성"
  - "종속성 속성, 사용자 지정"
  - "구현, 래퍼"
  - "메타데이터, 속성의 경우"
  - "속성, 메타데이터"
  - "속성, 등록"
  - "속성 등록"
  - "래퍼, 구현"
ms.assetid: e6bfcfac-b10d-4f58-9f77-a864c2a2938f
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# 사용자 지정 종속성 속성
이 항목에서는 먼저 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램 개발자와 구성 요소 작성자가 사용자 지정 [종속성 속성](GTMT)을 만드는 이유에 대해 설명한 다음 종속성 속성을 구현하는 단계 및 속성의 성능, 유용성 또는 다양성을 향상시키는 구현 옵션에 대해 설명합니다.  
  
   
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 독자가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스의 기존 종속성 속성 사용자로서 종속성 속성을 이해하고 있으며 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) 항목을 읽었다고 가정합니다.  이 항목의 예제를 실행하려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에 대해서도 이해하고 있어야 하며 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 작성 방법을 알고 있어야 합니다.  
  
<a name="whatis"></a>   
## 종속성 속성의 정의  
 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성을 [종속성 속성](GTMT)으로 구현하면 스타일 지정, 데이터 바인딩, 상속, 애니메이션, 기본값을 지원하는 속성을 만들 수 있습니다.  종속성 속성은 <xref:System.Windows.DependencyProperty.Register%2A> 메서드\(또는 <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>\)를 호출하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템에 등록되었으며 <xref:System.Windows.DependencyProperty> 식별자 필드의 지원을 받는 속성입니다.  종속성 속성은 <xref:System.Windows.DependencyObject> 형식에만 사용할 수 있지만 <xref:System.Windows.DependencyObject>는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스 계층 구조의 상위에 있으므로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 사용할 수 있는 대부분의 클래스는 종속성 속성을 지원할 수 있습니다.  종속성 속성에 대한 자세한 내용 및 이 [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]의 종속성 속성을 설명하는 데 사용되는 몇 가지 용어 및 규칙을 보려면 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하십시오.  
  
<a name="example_dp"></a>   
## 종속성 속성의 예제  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스에 구현된 종속성 속성의 예로는 <xref:System.Windows.Controls.Control.Background%2A> 속성, <xref:System.Windows.FrameworkElement.Width%2A> 속성 및 <xref:System.Windows.Controls.TextBox.Text%2A> 속성이 있습니다.  클래스가 노출하는 각 종속성 속성에는 동일한 클래스에 노출되는 <xref:System.Windows.DependencyProperty> 형식의 해당 공용 정적 필드가 있습니다. 이 필드는 종속성 속성의 식별자입니다.  이 식별자의 이름은 [종속성 속성](GTMT) 이름 뒤에 `Property`라는 문자열을 추가하여 지정됩니다.  예를 들어 <xref:System.Windows.Controls.Control.Background%2A> 속성의 해당 <xref:System.Windows.DependencyProperty> 식별자 필드는 <xref:System.Windows.Controls.Control.BackgroundProperty>입니다.  식별자에는 등록된 [종속성 속성](GTMT)에 대한 정보가 저장됩니다. 식별자는 나중에 <xref:System.Windows.DependencyObject.SetValue%2A> 호출 등 [종속성 속성](GTMT)과 관련된 다른 작업에 사용됩니다.  
  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)에서 설명하는 것처럼 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 모든 종속성 속성\(대부분의 [연결된 속성](GTMT)은 제외\)은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성도 되는데 이는 종속성 속성이 "래퍼" 구현이기 때문입니다.  따라서 코드에서는 다른 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성을 사용할 때와 동일하게 래퍼를 정의하는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 접근자를 호출하여 종속성 속성을 가져오거나 설정할 수 있습니다.  설정된 종속성 속성의 사용자는 기본 속성 시스템에 대한 연결 지점에 해당하는 <xref:System.Windows.DependencyObject> 메서드 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A>를 일반적으로 사용하지 않습니다.  그보다는 기존 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성 구현에서 식별자 필드를 적절히 사용하여 `get` 및 `set` 래퍼 구현 내에서 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A>을 호출합니다.  사용자 지정 종속성 속성을 직접 구현하는 경우에도 이와 비슷하게 래퍼를 정의합니다.  
  
<a name="backing_with_dp"></a>   
## 종속성 속성을 구현하기에 적합한 경우  
 <xref:System.Windows.DependencyObject>에서 파생된 클래스에 속성을 구현할 때 속성에 <xref:System.Windows.DependencyProperty> 식별자를 지원하여 종속성 속성으로 만들 수 있습니다.  속성을 항상 종속성 속성으로 만들 필요는 없으며 시나리오에 맞게 결정하면 됩니다.  때로는 속성에 전용 필드를 지원하는 일반적인 방법이 적합한 경우도 있습니다.  하지만 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능 중 하나 이상을 지원하는 속성을 만들려면 속성을 항상 [종속성 속성](GTMT)으로 구현해야 합니다.  
  
-   스타일에 속성을 설정하려는 경우.  자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하십시오.  
  
-   데이터 바인딩을 지원하는 속성을 만들려는 경우.  종속성 속성의 데이터 바인딩에 대한 자세한 내용은 [두 컨트롤의 속성 바인딩](../../../../docs/framework/wpf/data/how-to-bind-the-properties-of-two-controls.md)을 참조하십시오.  
  
-   동적 리소스 참조를 사용하여 속성을 설정하려는 경우.  자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
-   요소 트리의 부모 요소에서 속성 값을 자동으로 상속하려는 경우.  이 경우 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 메서드로 등록합니다. 이는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 액세스를 위한 속성 래퍼를 만드는 경우에도 해당합니다.  자세한 내용은 [속성 값 상속](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)을 참조하십시오.  
  
-   속성에 애니메이션을 적용하려는 경우.  자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
-   속성 시스템, 환경, 사용자 작업에 의해 또는 스타일을 읽고 사용하는 것으로 인해 이전 속성 값이 변경될 때 속성 시스템에서 이를 보고하도록 하려는 경우.  속성 메타데이터를 사용하면 속성 값이 확실히 변경되었다고 속성 시스템이 판단할 때마다 호출되는 콜백 메서드를 속성에 지정할 수 있습니다.  이와 관련된 개념이 바로 속성 값 강제 변환입니다.  자세한 내용은 [종속성 속성 콜백 및 유효성 검사](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)를 참조하십시오.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로세스에도 사용되는 이미 설정된 메타데이터 규칙을 사용하려는 경우\(예: 속성 값 변경 시 레이아웃 시스템에서 각 요소에 대한 표시를 다시 구성해야 하는지 여부 보고\).  또는 메타데이터 재정의를 사용함으로써 파생된 클래스가 기본값과 같은 메타데이터 기반 특성을 변경할 수 있도록 하려는 경우  
  
-   사용자 지정 컨트롤의 속성이 **속성** 창 편집과 같은 [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] 지원을 받도록 하려는 경우.  자세한 내용은 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하십시오.  
  
 위의 시나리오를 검토할 때는 완전히 새로운 속성을 구현하는 대신 기존 [종속성 속성](GTMT)의 메타데이터를 재정의하여 시나리오를 실현할 수 있는지도 함께 고려해야 합니다.  메타데이터 재정의가 유용한지 여부나 시나리오가 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 종속성 속성 및 클래스의 구현과 유사한 점이 있는지 등은 모두 해당 시나리오에 따라 다릅니다.  기존 속성의 메타데이터 재정의에 대한 자세한 내용은 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)를 참조하십시오.  
  
<a name="checklist"></a>   
## 종속성 속성 정의를 위한 검사 목록  
 종속성 속성을 정의하는 작업은 다음과 같은 네 가지 단계로 이루어집니다.  이 중 몇 가지는 구현 시 하나의 코드 줄로 결합되므로 반드시 순서대로 실행해야 하는 단계는 아닙니다.  
  
-   \(선택 사항\) 종속성 속성의 속성 메타데이터를 만듭니다.  
  
-   소유자 유형과 속성 값 형식을 지정하여 속성 시스템에 속성 이름을 등록합니다.  속성 메타데이터도 지정합니다\(사용된 경우\).  
  
-   소유자 유형에 `public` `static` `readonly` 필드로 <xref:System.Windows.DependencyProperty> 식별자를 정의합니다.  
  
-   종속성 속성 이름과 동일한 이름을 지정하여 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] "래퍼" 속성을 정의합니다.  [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] "래퍼" 속성의 `get` 및 `set` 접근자를 구현합니다. 이 두 접근자는 래퍼 속성을 지원하는 종속성 속성에 연결하는 데 사용됩니다.  
  
<a name="registering"></a>   
### 속성 시스템에 속성 등록  
 속성을 [종속성 속성](GTMT)으로 만들려면 속성 시스템에서 유지 관리하는 테이블에 속성을 등록하고 이후 속성 시스템 작업에서 한정자로 사용되는 고유 식별자를 속성에 제공해야 합니다.  이러한 작업은 내부 작업일 수도 있고 속성 시스템 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 호출하는 사용자 코드일 수도 있습니다.  속성을 등록하려면 클래스 본문 내에서\(클래스의 내부이며 멤버 정의의 외부\) <xref:System.Windows.DependencyProperty.Register%2A> 메서드를 호출합니다.  식별자 필드는 <xref:System.Windows.DependencyProperty.Register%2A> 메서드 호출을 통해 메서드의 반환 값으로도 제공됩니다.  <xref:System.Windows.DependencyProperty.Register%2A> 호출을 다른 멤버 정의의 외부에서 수행하는 이유는 이 반환 값을 사용하여 <xref:System.Windows.DependencyProperty> 형식의 `public` `static` `readonly` 필드를 할당하고 이를 클래스의 일부로 만들기 때문입니다.  이 필드가 종속성 속성의 식별자가 됩니다.  
  
 [!code-csharp[WPFAquariumSln#RegisterAG](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
 [!code-vb[WPFAquariumSln#RegisterAG](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]  
  
<a name="nameconventions"></a>   
### 종속성 속성 이름 규칙  
 종속성 속성과 관련된 명명 규칙은 이미 정해져 있으며 몇 가지 예외적인 경우를 제외하고는 이 규칙을 따라야 합니다.  
  
 다음 예제와 같이 종속성 속성 자체에는 <xref:System.Windows.DependencyProperty.Register%2A>의 첫 번째 매개 변수로 제공된 "AquariumGraphic"이라는 기본 이름이 지정되어 있습니다.  이 이름은 각 등록 형식 내에서 고유해야 합니다.  기본 형식을 통해 상속된 종속성 속성은 이미 등록 형식의 일부인 것으로 간주되므로 상속된 속성의 이름은 다시 등록할 수 없습니다.  하지만 종속성 속성이 상속되지 않은 경우에도 해당 종속성 속성의 소유자로 클래스를 추가할 수 있는 방법이 있습니다. 자세한 내용은 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)를 참조하십시오.  
  
 식별자 필드를 만들 때는 등록한 속성의 이름을 지정하고 뒤에 `Property`라는 접미사를 추가하여 식별자 필드 이름을 지정합니다.  이 필드는 종속성 속성의 식별자이며, 나중에 래퍼에서 구현할 <xref:System.Windows.DependencyObject.SetValue%2A> 및 <xref:System.Windows.DependencyObject.GetValue%2A> 호출의 입력으로 사용자 코드를 통한 속성 코드 액세스, 허용되는 외부 코드 액세스, 속성 시스템 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 사용됩니다.  
  
> [!NOTE]
>  종속성 속성은 클래스 본문에서 정의하는 것이 일반적인 구현 방법이지만 클래스의 정적 생성자에서 정의할 수도 있습니다.  이 방법은 종속성 속성을 초기화하는 데 두 줄 이상의 코드가 필요한 경우에 적합합니다.  
  
<a name="wrapper1"></a>   
### "래퍼" 구현  
 래퍼를 구현하는 경우 `get` 구현에서 <xref:System.Windows.DependencyObject.GetValue%2A>를 호출하고 `set` 구현에서 <xref:System.Windows.DependencyObject.SetValue%2A>를 호출해야 합니다. 여기에서는 명확성을 위해 원래 등록 호출 및 필드를 보여 줍니다.  
  
 예외적인 경우를 제외한 모든 경우에 래퍼 구현은 각각 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 작업만 수행해야 합니다.  그 이유에 대해서는 [XAML 로드 및 종속성 속성](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md) 항목에 설명되어 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스에 제공되는 기존의 모든 공용 종속성 속성은 이러한 단순한 래퍼 구현 모델을 사용합니다. 종속성 속성의 작동 방법에 내재된 가장 복잡한 문제는 종속성 속성의 작동 방법이 속성 시스템의 본래 동작인지 또는 속성 메타데이터를 통한 속성 변경 콜백 또는 강제 변환과 같은 다른 개념을 통해 구현된 것인지 여부입니다.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
 다시 말해 규칙에 따르면 래퍼 속성의 이름은 속성을 등록한 <xref:System.Windows.DependencyProperty.Register%2A> 호출의 첫 번째 매개 변수로 선택 및 지정된 이름과 같아야 합니다.  이 규칙을 따르지 않았다고 해서 속성의 모든 용도를 사용할 수 없는 것은 아니지만 다음과 같은 몇 가지 중대한 문제에 직면할 수 있습니다.  
  
-   스타일 및 템플릿의 특정 기능이 작동하지 않습니다.  
  
-   대부분의 도구와 디자이너는 이러한 명명 규칙을 사용하여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 적절히 serialize하거나 속성별 수준에서 디자이너 환경에 대한 지원을 제공해야 합니다.  
  
-   현재 구현된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로더는 특성 값을 처리할 때 래퍼를 완전히 무시하고 명명 규칙을 사용합니다.  자세한 내용은 [XAML 로드 및 종속성 속성](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)을 참조하십시오.  
  
<a name="metadata"></a>   
### 새 종속성 속성의 속성 메타데이터  
 종속성 속성을 등록할 때 속성 시스템을 통해 등록하면 속성 특성이 저장된 메타데이터 개체가 만들어집니다.  이러한 특성 중 대부분에는 단순한 <xref:System.Windows.DependencyProperty.Register%2A> 시그니처를 사용하여 속성을 등록하는 경우 설정되는 기본값이 있습니다.  다른 <xref:System.Windows.DependencyProperty.Register%2A> 시그니처를 사용하면 속성을 등록할 때 원하는 메타데이터를 지정할 수 있습니다.  종속성 속성에 지정되는 가장 일반적인 메타데이터는 해당 속성을 사용하는 새 인스턴스에 적용되는 기본값을 제공합니다.  
  
 <xref:System.Windows.FrameworkElement>의 파생 클래스에 존재하는 종속성 속성을 만드는 경우 기본 <xref:System.Windows.PropertyMetadata> 클래스 대신 <xref:System.Windows.FrameworkPropertyMetadata>라는 좀 더 특수한 메타데이터 클래스를 사용할 수 있습니다.  <xref:System.Windows.FrameworkPropertyMetadata> 클래스의 생성자에는 다양한 메타데이터 특성을 조합하여 지정할 수 있는 여러 개의 시그니처가 있습니다.  기본값만 지정하려면 <xref:System.Object> 형식의 단일 매개 변수를 사용하는 시그니처를 사용합니다.  이 개체 매개 변수를 속성의 형식별 기본값으로 전달합니다. 여기서 제공하는 기본값은 <xref:System.Windows.DependencyProperty.Register%2A> 호출에서 `propertyType` 매개 변수로 제공한 형식이어야 합니다.  
  
 <xref:System.Windows.FrameworkPropertyMetadata> 클래스를 사용하는 경우 속성에 메타데이터 옵션 플래그도 지정할 수 있습니다.  이러한 플래그는 속성 등록 후 속성 메타데이터에서 별개의 속성으로 변환되어 레이아웃 엔진과 같은 다른 프로세스에 특정 조건을 전달하는 데 사용됩니다.  
  
#### 적절한 메타데이터 플래그 설정  
  
-   속성 또는 속성 값의 변경이 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 영향을 주거나 레이아웃 시스템이 페이지에서 요소 크기를 조정하거나 렌더링하는 데 영향을 주는 경우에는 <xref:System.Windows.FrameworkPropertyMetadataOptions>, <xref:System.Windows.FrameworkPropertyMetadataOptions>, <xref:System.Windows.FrameworkPropertyMetadataOptions> 플래그 중 하나 이상을 설정합니다.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions>는 속성이 변경되면 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 렌더링이 변경되어야 함을 나타냅니다. 이 경우 포함하는 개체가 해당 부모 내에서 공간을 더 많거나 적게 사용할 수 있습니다.  예를 들어 이 플래그는 "Width" 속성에 설정해야 합니다.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions>는 속성이 변경되면 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 렌더링이 변경되어야 함을 나타냅니다. 이는 일반적으로 전용 공간은 변경할 필요가 없지만 해당 공간 내에서의 배치는 변경됨을 나타냅니다.  예를 들어 이 플래그는 "Alignment" 속성에 설정해야 합니다.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions>는 레이아웃과 치수에는 영향을 주지 않지만 다른 렌더링이 필요한 변경이 발생했음을 나타냅니다.  기존 요소의 색을 변경하는 속성\(예: "Background"\)을 예로 들 수 있습니다.  
  
    -   이러한 플래그는 대개 속성 시스템이나 레이아웃 콜백에 대한 고유의 재정의 구현을 위해 메타데이터에서 프로토콜로 사용됩니다.  인스턴스 속성 중 하나가 값 변경을 보고하면 <xref:System.Windows.UIElement.InvalidateArrange%2A>를 호출하고 해당 메타데이터에서 <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>가 `true`로 설정된 <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> 콜백을 사용하는 경우를 예로 들 수 있습니다.  
  
-   일부 속성은 앞에서 설명한 크기 변경뿐만 아니라 포함하는 부모 요소의 렌더링 특성에도 영향을 줄 수 있습니다.  유동 문서 모델에서 사용되는 <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A> 속성을 예로 들 수 있습니다. 이 속성이 변경되면 해당 단락이 포함된 유동 문서의 전반적인 렌더링이 변경될 수 있습니다.  직접 만든 속성에서 이와 비슷한 경우를 확인하려면 <xref:System.Windows.FrameworkPropertyMetadataOptions> 또는 <xref:System.Windows.FrameworkPropertyMetadataOptions>를 사용합니다.  
  
-   종속성 속성은 기본적으로 데이터 바인딩을 지원합니다.  데이터 바인딩을 실제로 사용할 시나리오가 없거나 대형 개체에 대해 데이터 바인딩 성능이 문제가 되는 경우에는 데이터 바인딩을 의도적으로 사용하지 않을 수 있습니다.  
  
-   기본적으로 종속성 속성에 대한 데이터 바인딩 <xref:System.Windows.Data.Binding.Mode%2A>는 기본값인 <xref:System.Windows.Data.BindingMode>로 설정되어 있지만  바인딩 인스턴스별로 바인딩을 <xref:System.Windows.Data.BindingMode>로 변경할 수 있습니다. 자세한 내용은 [바인딩 방향 지정](../../../../docs/framework/wpf/data/how-to-specify-the-direction-of-the-binding.md)을 참조하십시오.  종속성 속성 작성자는 속성에 <xref:System.Windows.Data.BindingMode> 바인딩 모드가 기본적으로 사용되도록 선택할 수 있습니다.  이 바인딩 모드를 사용하는 기존 종속성 속성으로는 <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=fullName>이 있습니다. 이 속성에 대한 시나리오에서는 <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> 설정 논리와 <xref:System.Windows.Controls.MenuItem>의 작성이 기본 테마 스타일과 상호 작용합니다.  <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> 속성 논리는 다른 상태 속성 및 메서드 호출에 따라 속성 상태를 유지 관리하기 위해 기본적으로 데이터 바인딩을 사용합니다.  기본적으로 <xref:System.Windows.Data.BindingMode>로 바인딩하는 다른 속성으로는 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName>가 있습니다.  
  
-   <xref:System.Windows.FrameworkPropertyMetadataOptions> 플래그를 설정하여 사용자 지정 종속성 속성에서 속성 상속을 사용할 수도 있습니다.  속성 상속은 부모 요소와 자식 요소에 공통 속성이 있으며 자식 요소의 특정 속성 값을 부모 요소의 해당 속성에 설정된 값과 동일한 값으로 설정하는 것이 적합한 시나리오에서 유용합니다.  상속 가능한 속성의 예로 데이터 표현의 마스터\-세부 시나리오를 가능하게 하는 바인딩 작업에 사용되는 <xref:System.Windows.FrameworkElement.DataContext%2A>를 들 수 있습니다.  <xref:System.Windows.FrameworkElement.DataContext%2A>를 상속 가능한 속성으로 설정하면 모든 자식 요소가 해당 데이터 컨텍스트를 상속합니다.  속성 값이 상속되므로 데이터 컨텍스트를 페이지 루트 또는 응용 프로그램 루트에서 지정하면 됩니다. 따라서 속성이 상속될 수 있는 모든 자식 요소에서 바인딩을 위해 데이터 컨텍스트를 다시 지정할 필요가 없습니다.  <xref:System.Windows.FrameworkElement.DataContext%2A>도 상속으로 기본값을 재정의하는 것을 보여 주는 좋은 예입니다. 하지만 이 속성은 항상 특정 자식 요소에서 로컬로 설정할 수 있습니다. 자세한 내용은 [계층적 데이터에 마스터\-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)을 참조하십시오.  속성 값 상속을 사용하면 성능이 저하될 수 있으므로 꼭 필요한 경우에만 사용하는 것이 좋습니다. 자세한 내용은 [속성 값 상속](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)을 참조하십시오.  
  
-   <xref:System.Windows.FrameworkPropertyMetadataOptions> 플래그를 설정하여 탐색 업무 일지 서비스에서 종속성 속성을 사용하거나 검색해야 하는지 여부를 나타냅니다.  이러한 속성의 예로는 <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A> 속성이 있습니다. 이 속성은 업무 일지 기록을 탐색할 때 선택 컨트롤의 선택된 항목이 유지되도록 합니다.  
  
<a name="RODP"></a>   
## 읽기 전용 종속성 속성  
 읽기 전용 종속성 속성을 정의할 수 있습니다.  읽기 전용 속성의 경우 속성을 속성 시스템에 등록하고 식별자를 노출하는 절차와 마찬가지로 속성을 읽기 전용으로 정의하는 이유에 대한 시나리오는 다소 다를 수 있습니다.  자세한 내용은 [읽기 전용 종속성 속성](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)을 참조하십시오.  
  
<a name="CTDP"></a>   
## 컬렉션 형식 종속성 속성  
 컬렉션 형식 종속성 속성을 구현하는 경우 고려해야 할 추가적인 문제가 있습니다.  자세한 내용은 [컬렉션 형식 종속성 속성](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)을 참조하십시오.  
  
<a name="SecurityC"></a>   
## 종속성 속성 보안 고려 사항  
 종속성 속성은 공용 속성으로 선언하고  종속성 속성 식별자 필드는 공용 정적 필드로 선언해야 합니다.  다른 액세스 수준\(예: protected\)을 선언하려는 경우에도 속성 시스템 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]와 함께 식별자를 통해 항상 종속성 속성에 액세스할 수 있습니다.  보호된 식별자 필드에도 액세스할 수 있는데 이는 속성 시스템의 일부인 메타데이터 보고 또는 값 결정 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]\(예: <xref:System.Windows.LocalValueEnumerator>\) 덕분입니다.  자세한 내용은 [종속성 속성 보안](../../../../docs/framework/wpf/advanced/dependency-property-security.md)을 참조하십시오.  
  
<a name="DPCtor"></a>   
## 종속성 속성 및 클래스 생성자  
 관리 코드 프로그래밍에는 클래스 생성자가 가상 메서드를 호출하지 않아야 한다는 일반적인 원칙이 적용되며 대부분의 경우 이러한 원칙은 FxCop 등의 코드 분석 도구를 통해 적용됩니다.  이는 파생 클래스 생성자의 기본 초기화로서 생성자가 호출될 수 있으며 생성 중인 개체 인스턴스의 초기화가 완료되지 않은 상태에서 생성자를 통한 가상 메서드 입력이 발생할 수 있기 때문입니다.  이미 <xref:System.Windows.DependencyObject>에서 파생된 클래스에서 다시 클래스를 파생하는 경우 속성 시스템 자체에서 내부적으로 가상 메서드를 호출하고 노출한다는 점에 유의하십시오.  이러한 가상 메서드는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템 서비스의 일부입니다.  메서드를 재정의하면 파생 클래스가 값 결정에 참가할 수 있습니다.  런타임 초기화 시 발생할 수 있는 문제를 방지하려면 매우 구체적인 생성자 패턴을 따르지 않는 경우 종속성 속성 값을 클래스 생성자 내에 설정하지 않아야 합니다.  자세한 내용은 [DependencyObject의 안전한 생성자 패턴](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)을 참조하십시오.  
  
## 참고 항목  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [컬렉션 형식 종속성 속성](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)   
 [종속성 속성 보안](../../../../docs/framework/wpf/advanced/dependency-property-security.md)   
 [XAML 로드 및 종속성 속성](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)   
 [DependencyObject의 안전한 생성자 패턴](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)