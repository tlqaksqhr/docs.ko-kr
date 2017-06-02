---
title: "연결된 속성 개요 | Microsoft Docs"
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
  - "연결된 속성[WPF Designer]"
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# 연결된 속성 개요
연결 된 속성은 XAML로 정의 된 개념입니다.  연결된 속성은 모든 개체에서 설정할 수 있는 전역 속성 형식으로 사용하기 위한 개념입니다.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], 연결 된 속성을 기본 속성 "래퍼"가 없는 종속성 속성의 특수 한 형태로 일반적으로 정의 합니다.  
  
   
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스의 기존 종속성 속성 사용자의 관점에서 종속성 속성을 이해하고 있으며 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 읽었다고 가정합니다.  이 항목의 예제를 실행 하려면 합니다 또한 XAML 이해 하 고 작성 하는 방법을 알고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  
  
<a name="attached_properties_usage"></a>   
## 연결된 속성을 사용하는 이유  
 연결된 속성의 용도 중 하나는 실질적으로 부모 요소가 정의한 속성의 고유 값을 다른 자식 요소가 지정할 수 있도록 하는 것입니다.  이 시나리오의 특정한 용도는 자식 요소가 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 표시되는 방식을 부모 요소에 알리도록 하는 것입니다.  이에 대한 한 가지 예는 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> 속성입니다.  <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> 속성은 <xref:System.Windows.Controls.DockPanel> 자체가 아니라 <xref:System.Windows.Controls.DockPanel> 안에 포함되는 요소에 대해 설정하도록 디자인되었기 때문에 연결된 속성으로 만들어집니다.  <xref:System.Windows.Controls.DockPanel> 클래스는 <xref:System.Windows.Controls.DockPanel.DockProperty>라는 정적 <xref:System.Windows.DependencyProperty> 필드를 정의한 다음 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 및 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 메서드를 [연결된 속성](GTMT)에 대한 public 접근자로 제공합니다.  
  
<a name="attached_properties_xaml"></a>   
## XAML의 연결된 속성  
 XAML에서는 *AttachedPropertyProvider*.*PropertyName* 구문을 사용하여 연결된 속성을 설정합니다.  
  
 다음을 설정 하는 방법의 예입니다 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> XAML에서:  
  
 [!code-xml[PropertiesOvwSupport#APBasicUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]  
  
 사용법은 정적 속성과 비슷합니다. 즉, 지정된 인스턴스를 이름으로 참조하는 대신 항상 [연결된 속성](GTMT)을 소유하고 등록하는 형식 <xref:System.Windows.Controls.DockPanel>을 참조합니다.  
  
 또한 XAML의 연결 된 속성은 태그에서 설정 특성 이므로 설정 작업이 어떤 관련성이 있습니다.  스타일의 트리거와 같이 값을 비교 하는 것에 대 한 몇 가지 간접 메커니즘이 있지만 XAML에서 속성을 직접 가져올 수 없습니다 \(자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)\).  
  
### WPF의 연결된 속성 구현  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], 대부분의 존재는 연결 된 속성의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] UI 프리젠테이션에 관련 된 형식 종속성 속성으로 구현 됩니다.  연결 된 속성은 XAML 개념인 반면 종속성 속성은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개념.  때문에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결 된 속성은 종속성 속성, 속성 메타 데이터와 같은 종속성 속성 개념을 지원 하 고 기본 속성 메타 데이터의 값입니다.  
  
<a name="howused"></a>   
## 소유 형식에서 연결된 속성을 사용하는 방법  
 연결된 속성은 모든 개체에 대해 설정할 수 있지만 속성을 설정하면 명확한 결과가 생성된다거나 값이 항상 다른 개체에 의해 사용되는 것은 아닙니다.  일반적으로 연결된 속성은 다양한 클래스 계층 구조 또는 논리적 관계의 개체가 연결된 속성을 정의하는 형식에 공통 정보를 보고할 수 있도록 하기 위해 사용됩니다.  연결된 속성을 정의하는 형식은 일반적으로 다음 모델 중 하나를 따릅니다.  
  
-   연결된 속성을 정의하는 형식은 연결된 속성의 값을 설정하는 요소의 상위 요소일 수 있도록 디자인되었습니다.  그런 다음 형식은 일부 개체 트리 구조에 대해 내부 논리를 통해 자식 개체를 순환하여 값을 가져오고 해당 값에 대해 특정한 방식으로 작업을 수행합니다.  
  
-   연결된 속성을 정의하는 형식은 다양한 부모 요소 및 콘텐츠 모델의 자식 요소로 사용됩니다.  
  
-   연결된 속성을 정의하는 형식은 서비스를 나타냅니다.  다른 형식은 연결된 속성에 대한 값을 설정합니다.  그런 다음 속성을 설정하는 요소가 서비스의 컨텍스트에서 평가될 때, 서비스 클래스의 내부 논리에서 연결된 속성 값을 가져옵니다.  
  
### 부모 정의 연결된 속성에 대한 예제  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 연결된 속성을 정의하는 가장 일반적인 경우는 부모 요소가 자식 요소 컬렉션을 지원하며 동작의 세부 사항이 각 자식 요소에 대해 개별적으로 보고되는 동작도 구현할 때입니다.  
  
 <xref:System.Windows.Controls.DockPanel>은 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> 연결된 속성을 정의하며, <xref:System.Windows.Controls.DockPanel>에는 클래스 수준 코드가 렌더링 논리\(특히 <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> 및 <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>\)의 일부로 사용됩니다.  <xref:System.Windows.Controls.DockPanel> 인스턴스는 항상 바로 아래 자식 요소에 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>에 대한 값이 설정되었는지 여부를 검사합니다.  설정된 경우 해당 값은 해당 자식 요소에 적용되는 렌더링 논리에 대한 입력이 됩니다.  중첩된 <xref:System.Windows.Controls.DockPanel> 인스턴스는 각자의 바로 아래 자식 요소 컬렉션을 처리하지만 해당 동작은 <xref:System.Windows.Controls.DockPanel>에서 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> 값을 처리하는 방법에 대한 구현에 따라 다릅니다.  이론적으로는 바로 위 부모를 넘어서 요소에 영향을 주는 연결된 속성을 사용할 수 있습니다.  <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> 연결된 속성을 요소에 대해 작업을 수행할 <xref:System.Windows.Controls.DockPanel> 부모 요소가 없는 요소에 설정하면 오류 또는 예외가 발생하지 않습니다.  이는 전역 속성 값이 설정되었지만 정보를 사용할 수 있는 현재 <xref:System.Windows.Controls.DockPanel> 부모가 없음을 의미합니다.  
  
<a name="attached_properties_code"></a>   
## 코드의 연결된 속성  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 연결된 속성에는 손쉬운 get\/set 액세스를 위해 사용되는 일반적인 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] "래퍼" 메서드가 없습니다.  연결된 속성이 자신이 설정된 인스턴스에 대한 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 네임스페이스의 일부가 아닐 수 있기 때문입니다.  그러나 XAML 프로세서는 XAML이 구문 분석 될 때 해당 값을 설정할 수 있어야 합니다.  실제 연결 된 속성 사용법을 지원 하기 위해 연결 된 속성의 소유자 형식 전용된 접근자 메서드 형태로 구현 해야  `가져오기`*PropertyName* 및  `설정`*PropertyName*.  또한 이러한 전용 접근자 메서드는 코드에서 연결된 속성을 가져오거나 설정하는 데 유용합니다.  코드의 관점에서 연결된 속성은 속성 접근자 대신 메서드 접근자가 있는 지원 필드와 비슷하며 해당 지원 필드는 특별하게 정의할 필요 없이 개체에 존재할 수 있습니다.  
  
 다음 예제에서는 코드에서 연결된 속성을 설정하는 방법을 보여 줍니다.  이 예제에서 `myCheckBox`는 <xref:System.Windows.Controls.CheckBox> 클래스의 인스턴스입니다.  
  
 [!code-csharp[PropertiesOvwSupport#APCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
 [!code-vb[PropertiesOvwSupport#APCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]  
  
 경우 XAML 유사 사례 `myCheckBox` 의 자식 요소로 이미 추가 하지 않은 `myDockPanel` 코드의 셋째 줄에서 네 번째 줄의 코드는 예외를 발생 시키며 그러는 있지만 속성 값을와 상호 작용 하는 <xref:System.Windows.Controls.DockPanel> 부모와 따라서 아무 작업도 수행 하지 것입니다.  <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> 값이 자식 요소에 설정되고 <xref:System.Windows.Controls.DockPanel> 부모 요소가 있어야 렌더링된 응용 프로그램에서 효과적으로 동작합니다.  이 경우 연결된 속성을 설정한 다음 트리에 연결하거나,  또는 트리에 연결한 다음 연결된 속성을 설정할 수 있습니다.  어떤 순서로 작업을 수행하든 동일한 결과를 얻을 수 있습니다.  
  
<a name="attached_properties_metadata"></a>   
## 연결된 속성 메타데이터  
 속성을 등록할 때 <xref:System.Windows.FrameworkPropertyMetadata>가 설정되어 속성이 렌더링, 측정 등에 영향을 줄 것인지 여부와 같은 속성 특성을 지정합니다.  [연결된 속성](GTMT)에 대한 메타데이터는 일반적으로 [종속성 속성](GTMT)과 차이가 없습니다.  재정의에서 기본값을 연결된 속성 메타데이터로 지정하면 값은 재정의 클래스의 인스턴스에 대한 암시적 연결된 속성의 기본값이 됩니다.  프로세스가 메타데이터를 지정한 클래스의 인스턴스를 지정하는 연결된 속성에 대한 `Get` 메서드 접근자를 통해 연결된 속성의 값을 쿼리하고, 해당 연결된 속성의 값이 설정되지 않은 경우 기본값이 보고됩니다.  
  
 속성에 대해 속성 값 상속을 사용할 수 있게 하려면 연결되지 않은 종속성 속성이 아니라 연결된 속성을 사용해야 합니다.  자세한 내용은 [속성 값 상속](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)을 참조하십시오.  
  
<a name="custom"></a>   
## 사용자 지정 연결된 속성  
  
<a name="create_attached_properties"></a>   
### 연결된 속성을 만드는 시기  
 클래스 정의 이외에 클래스에 사용 가능한 속성 설정 메커니즘이 필요한 경우 [연결된 속성](GTMT)을 만들 수 있습니다.  이에 대한 가장 일반적인 시나리오는 레이아웃입니다.  기존 레이아웃 속성의 예로 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName> 및 <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=fullName>을 들 수 있습니다.  여기에서 사용 가능한 시나리오는 레이아웃 제어 요소에 대한 자식 요소로 존재하는 요소가 레이아웃 요구 사항을 레이아웃 상위 요소에 개별적으로\(각기 부모가 연결된 속성으로 정의된 속성 값 설정\) 표현할 수 있는 시나리오입니다.  
  
 연결된 속성을 사용하는 다른 시나리오는 클래스가 서비스를 나타낼 때 클래스가 서비스를 더 투명하게 통합하게 하려는 경우입니다.  
  
 다른 시나리오는 **속성** 창 편집과 같은 [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] 지원을 받기 위한 경우입니다.  자세한 내용은 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하십시오.  
  
 앞서 설명한 것처럼 속성 값 상속을 사용하려면 연결된 속성으로 등록해야 합니다.  
  
<a name="how_do_i_create_attached_properties"></a>   
### 연결된 속성을 만드는 방법  
 클래스가 엄격하게 다른 형식에 대해 사용할 [연결된 속성](GTMT)을 정의하는 경우 클래스는 <xref:System.Windows.DependencyObject>에서 파생될 필요가 없습니다.  하지만 파생 필요가 <xref:System.Windows.DependencyObject> 전체 수행 하는 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 모델의 연결 된 속성은 종속성 속성 될 수도 있습니다.  
  
 <xref:System.Windows.DependencyProperty> 형식의 `public` `static` `readonly` 필드를 선언하여 연결된 속성을 종속성 속성으로 정의합니다.  <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 메서드의 반환 값을 사용하여 이 필드를 정의합니다.  필드 이름은 필드 및 필드가 나타내는 속성의 이름을 지정하기 위해 만들어진 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 패턴을 따르기 위해, 연결된 속성 이름에 `Property` 문자열을 추가한 것과 일치해야 합니다.  연결 된 속성 공급자 고정도 제공 해야  `가져오기`*PropertyName* 및  `설정`*PropertyName* ; 연결 된 속성에 대 한 접근자 메서드 이렇게 하지 않으면 속성 시스템이 연결 된 속성을 사용할 수 없게 됩니다.  
  
> [!NOTE]
>  연결된 속성의 get 접근자를 생략하면 해당 속성에 대한 데이터 바인딩이 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 및 Expression Blend 등의 디자인 도구에서 작동하지 않습니다.  
  
#### Get 접근자  
 서명에  `가져오기`*PropertyName* 접근자가 있어야.  
  
 `public static object Get` *PropertyName* `(object`  `target` `)`  
  
-   `target` 개체는 구현에서 더 구체적인 형식으로 지정할 수 있습니다.  예를 들어 <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=fullName> 메서드의 경우에는 연결된 속성이 <xref:System.Windows.UIElement> 인스턴스에서만 설정되어야 하기 때문에 매개 변수 형식을 <xref:System.Windows.UIElement>로 지정합니다.  
  
-   반환 값은 각 구현에서 더 구체적인 형식으로 지정할 수 있습니다.  예를 들어 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 메서드는 값을 해당 열거형으로만 설정할 수 있기 때문에 <xref:System.Windows.Controls.Dock> 형식으로 지정합니다.  
  
#### Set 접근자  
 서명에  `설정`*PropertyName* 접근자가 있어야 합니다.  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
-   `target` 개체는 구현에서 더 구체적인 형식으로 지정할 수 있습니다.  예를 들어 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 메서드의 경우에는 연결된 속성이 <xref:System.Windows.UIElement> 인스턴스에서만 설정되어야 하기 때문에 <xref:System.Windows.UIElement> 형식으로 지정합니다.  
  
-   `value` 개체는 구현에서 더 구체적인 형식으로 지정할 수 있습니다.  예를 들어 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 메서드는 값을 해당 열거형으로만 설정할 수 있기 때문에 <xref:System.Windows.Controls.Dock> 형식으로 지정합니다.  기억의 값을이 메서드에 연결 된 속성은 태그에 연결 된 속성 사용을 발견 한 경우 해당 XAML 로더의 입력 값입니다.  해당 입력은 태그에서 XAML 특성 값으로 지정 된 값입니다.  따라서 적절한 형식을 특성 값\(결과적으로 문자열\)에서 만들 수 있도록 형식 변환, 값 serializer 또는 형식에 대한 태그 확장 지원이 있어야 합니다.  
  
 다음 예제에서는 종속성 속성 등록 \(사용 하는 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 메서드\),으로  `얻을`*PropertyName* 및  `설정`*PropertyName* 접근자입니다.  이 예제에서 연결된 속성 이름은 `IsBubbleSource`입니다.  따라서 접근자 이름은 `GetIsBubbleSource` 및 `SetIsBubbleSource`로 지정해야 합니다.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
#### 연결된 속성 특성  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 리플렉션 프로세스 및 리플렉션의 일반적인 사용자에 연결된 속성에 대한 정보와 디자이너와 같은 속성 정보를 제공하기 위한 몇 가지 [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)]을 정의합니다.  연결 된 속성에는 범위에 제한이 없는 형식이 있기 때문에 디자이너는 XAML를 사용 하는 특정 기술 구현에서 정의 된 모든 연결 된 속성의 전역 목록 사용자의 과부하를 피하는 방법을 해야 합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 연결된 속성에 대해 정의하는 [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)]을 사용하여 특정 연결된 속성이 속성 창에 표시되어야 하는 상황의 범위를 지정할 수 있습니다.  사용자가 지정한 연결된 속성에도 이러한 특성을 적용하는 것을 고려할 수 있습니다.  [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)]의 용도 및 구문은 적절한 참조 페이지에서 설명합니다.  
  
-   <xref:System.Windows.AttachedPropertyBrowsableAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>  
  
<a name="more"></a>   
## 연결된 속성에 대해 자세히 보기  
  
-   연결 된 속성 만들기에 대 한 자세한 내용은 [연결된 속성 등록](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md).  
  
-   종속성 속성 및 연결된 속성에 대한 고급 사용 시나리오에 대해서는 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 참조하십시오.  
  
-   속성을 연결된 속성과 종속성 속성으로 등록할 수도 있지만 "래퍼" 구현은 여전히 노출하게 됩니다.  이 경우 속성에서 해당 요소를 설정할 수 있습니다 또는 속성 구문을 통해 XAML 요소에 연결 합니다.  표준 및 연결된 사용에 대한 적절한 시나리오가 제공되는 속성의 예는 <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=fullName>입니다.  
  
## 참고 항목  
 <xref:System.Windows.DependencyProperty>   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [연결된 속성 등록](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)