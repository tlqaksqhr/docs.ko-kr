---
title: "종속성 속성 값 우선 순위 | Microsoft Docs"
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
  - "클래스, 종속성 속성의 소유자"
  - "종속성 속성, 소유자인 클래스"
  - "종속성 속성, 메타데이터"
  - "메타데이터, 종속성 속성"
ms.assetid: 1fbada8e-4867-4ed1-8d97-62c07dad7ebc
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# 종속성 속성 값 우선 순위
<a name="introduction"></a> 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템의 동작이 [종속성 속성](GTMT) 값에 어떤 영향을 줄 수 있는지에 대해 설명하고 속성 시스템의 특성이 속성의 유효 값에 적용되는 우선 순위에 대해 설명합니다.  
  
   
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 사용자가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스의 기존 종속성 속성 사용자의 관점에서 종속성 속성을 이해하고 있으며 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 읽었다고 가정합니다.  이 항목의 예제를 실행하려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 이해하고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 작성 방법을 알고 있어야 합니다.  
  
<a name="intro"></a>   
## WPF 속성 시스템  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템을 사용하면 다양한 요소에 따라 종속성 속성 값을 결정할 수 있으므로 실시간 속성 유효성 검사, 런타임에 바인딩, 다른 속성 값에 관련 속성 값 변경 내용 알림 등의 기능을 사용할 수 있습니다.  종속성 속성 값을 결정하는 데 사용되는 정확한 순서와 논리는 상당히 복잡합니다.  하지만 이 순서를 알면 불필요한 속성 설정을 피할 수 있고, 종속성 속성 값을 변경하려는 일부 시도가 예상과 다른 결과 값을 나타내는 정확한 이유를 설명할 수 있습니다.  
  
<a name="multiple_sets"></a>   
## 여러 위치에서 "설정"할 수 있는 종속성 속성  
 다음은 하나의 속성\(<xref:System.Windows.Controls.Control.Background%2A>\) 안에 값에 영향을 줄 수 있는 세 가지 "설정" 작업이 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제입니다.  
  
 [!code-xml[PropertiesOvwSupport#DPPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#dpprecedence)]  
  
 이 경우 적용되는 색은 빨강, 녹색, 파랑 중 어떤 색입니까?  
  
 애니메이션 값과 강제 변환을 제외하면 로컬 속성 집합이 가장 높은 우선 순위로 설정됩니다.  로컬에서 값을 설정하면 어떤 스타일이나 컨트롤 템플릿에서도 값이 적용될 것으로 예상할 수 있습니다.  이 예제에서 <xref:System.Windows.Controls.Control.Background%2A>는 로컬에서 Red로 설정됩니다.  따라서 이 범위 내에서 정의된 스타일은 설사 그것이 다른 경우라면 이 범위 내에서 이 형식을 가진 모든 요소에 적용될 암시적 스타일일지라도 <xref:System.Windows.Controls.Control.Background%2A> 속성에 값을 지정하는 가장 높은 우선 순위가 아닙니다.  Button 인스턴스에서 로컬 값 Red를 제거하면 스타일이 우선 순위를 갖고 단추는 스타일의 Background 값을 갖게 됩니다.  스타일 내에서는 트리거가 우선적으로 적용되므로 마우스가 단추 위에 있으면 단추 색이 파랑이 되고 그렇지 않으면 녹색이 됩니다.  
  
<a name="listing"></a>   
## 종속성 속성 설정 우선 순위 목록  
 다음은 속성 시스템에서 종속성 속성의 런타임 값을 할당할 때 사용되는 최종적인 순서입니다.  우선 순위가 높은 항목이 먼저 나열됩니다.  이 목록은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)에서 수행된 몇 가지 일반화를 바탕으로 확장됩니다.  
  
1.  **속성 시스템 강제 변환.** 강제 변환에 대한 자세한 내용은 이 항목 뒷부분에 나오는 [강제 변환, 애니메이션 및 기준 값](#animations)을 참조하십시오.  
  
2.  **활성 애니메이션 또는 Hold 동작이 있는 애니메이션.** 실제적인 효과를 내려면 속성 애니메이션이 로컬로 설정된 기준 값\(애니메이션 효과가 적용되지 않은 값\)보다 우선 순위를 가질 수 있어야 합니다.  자세한 내용은 이 항목 뒷부분에 나오는 [강제 변환, 애니메이션 및 기준 값](#animations)을 참조하십시오.  
  
3.  **로컬 값.** 로컬 값은 편리한 "래퍼" 속성을 통해 설정할 수 있습니다. 이는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 특성 또는 속성 요소로 설정하거나 특정 인스턴스의 속성을 사용하여 <xref:System.Windows.DependencyObject.SetValue%2A> [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]를 호출하는 것과 동일합니다.  바인딩이나 리소스를 사용하여 로컬 값을 설정하면 각각의 바인딩이나 리소스가 직접 값이 설정된 것처럼 우선 순위에 따라 작용합니다.  
  
4.  **TemplatedParent 템플릿 속성.** 템플릿\(<xref:System.Windows.Controls.ControlTemplate> 또는 <xref:System.Windows.DataTemplate>\)의 일부로 생성된 요소에는 <xref:System.Windows.FrameworkElement.TemplatedParent%2A>가 있습니다.  이 속성을 적용하는 시기에 대한 자세한 내용은 이 항목의 뒷부분에 나오는 [TemplatedParent](#templatedparent)를 참조하십시오.  템플릿 내에서는 다음과 같은 우선 순위가 적용됩니다.  
  
    1.  <xref:System.Windows.FrameworkElement.TemplatedParent%2A> 템플릿의 트리거  
  
    2.  <xref:System.Windows.FrameworkElement.TemplatedParent%2A> 템플릿의 속성 집합\(대개 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성을 통해 설정\)  
  
5.  **암시적 스타일.** `Style` 속성에만 적용됩니다.  `Style` 속성은 해당 요소의 형식과 일치하는 키가 있는 스타일 리소스로 채워집니다.  해당 스타일 리소스는 페이지 또는 응용 프로그램에 있어야 합니다. 암시적 스타일 리소스에 대한 조회는 테마까지 진행되지 않습니다.  
  
6.  **스타일 트리거.** 페이지 또는 응용 프로그램의 스타일 내에 있는 트리거입니다. 이 경우 스타일은 암시적 스타일이거나 명시적 스타일일 수 있지만 우선 순위가 낮은 기본 스타일에서 가져온 스타일은 아닙니다.  
  
7.  **템플릿 트리거.** 스타일 내에 있는 템플릿의 트리거이거나 직접 적용되는 템플릿의 트리거입니다.  
  
8.  **스타일 setter.** 페이지 또는 응용 프로그램의 스타일 내에 있는 <xref:System.Windows.Setter> 값입니다.  
  
9. **기본\(테마\) 스타일.** 이 스타일을 적용하는 시기와 테마 스타일과 테마 스타일 내 템플릿과의 관계에 대한 자세한 내용은 이 항목 뒷부분에 나오는 [기본\(테마\) 스타일](#themestyles)을 참조하십시오.  기본 스타일 내에서는 다음과 같은 우선 순위가 적용됩니다.  
  
    1.  테마 스타일의 활성 트리거  
  
    2.  테마 스타일의 Setter  
  
10. **상속.** 몇 가지 종속성 속성은 부모 요소의 값을 자식 요소에 상속하므로 응용 프로그램의 각 요소에서 이러한 종속성 속성을 따로 설정할 필요가 없습니다.  자세한 내용은 [속성 값 상속](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)을 참조하십시오.  
  
11. **종속성 속성 메타데이터의 기본값.** 지정된 모든 종속성 속성에는 해당 속성의 속성 시스템 등록 과정에서 설정된 기본값이 있을 수 있습니다.  또한 종속성 속성을 상속하는 파생 클래스에는 형식을 기준으로 기본값을 비롯한 메타데이터를 재정의하는 옵션이 있습니다.  자세한 내용은 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)를 참조하십시오.  상속은 기본값보다 먼저 확인되므로 상속된 속성의 경우 부모 요소 기본값이 자식 요소보다 우선 순위가 높습니다.  결과적으로, 상속 가능한 속성이 설정되지 않으면 자식 요소 기본값 대신 루트 또는 부모에 지정된 기본값이 사용됩니다.  
  
<a name="templatedparent"></a>   
## TemplatedParent  
 표준 응용 프로그램 태그에서 직접 선언하는 요소의 속성에는 우선 순위 항목인 TemplatedParent가 적용되지 않습니다.  TemplatedParent 개념은 템플릿의 응용 프로그램을 통해 존재하게 되는 시각적 트리 내의 자식 항목을 위해서만 존재합니다.  속성 시스템이 <xref:System.Windows.FrameworkElement.TemplatedParent%2A> 템플릿에서 값을 검색할 때는 해당 요소를 생성한 템플릿을 검색하는 것입니다.  일반적으로 <xref:System.Windows.FrameworkElement.TemplatedParent%2A> 템플릿의 속성 값은 자식 요소에 로컬 값으로 설정된 것처럼 동작하지만 차후 템플릿이 공유되는 경우가 있기 때문에 로컬 값보다는 우선 순위가 낮은 것입니다.  자세한 내용은 <xref:System.Windows.FrameworkElement.TemplatedParent%2A>를 참조하십시오.  
  
<a name="style_property"></a>   
## 스타일 속성  
 앞서 설명한 조회 순서는 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 제외한 모든 가능한 종속성 속성에 적용됩니다.  <xref:System.Windows.FrameworkElement.Style%2A> 속성은 그 자체에 스타일을 지정할 수 없어 우선 순위 항목이 5에서 8까지 적용되지 않는다는 점에서 다른 속성과 다릅니다.  또한 <xref:System.Windows.FrameworkElement.Style%2A>의 애니메이션이나 강제 변환은 권장되지 않습니다. <xref:System.Windows.FrameworkElement.Style%2A>에 애니메이션 효과를 적용하려면 사용자 지정 애니메이션 클래스가 필요합니다.  이 때문에 <xref:System.Windows.FrameworkElement.Style%2A> 속성은 다음 세 가지 방식으로 설정할 수 있습니다.  
  
-   **명시적 스타일.** <xref:System.Windows.FrameworkElement.Style%2A> 속성이 직접 설정됩니다.  대부분의 시나리오에서 스타일은 인라인으로 정의되는 것이 아니라 명시적 키에 의해 리소스로 참조됩니다.  이 경우에는 Style 속성 자체가 로컬 값, 다시 말해 우선 순위 항목 3처럼 동작합니다.  
  
-   **암시적 스타일.** <xref:System.Windows.FrameworkElement.Style%2A> 속성이 직접 설정되지 않습니다.  하지만 <xref:System.Windows.FrameworkElement.Style%2A>은 리소스 조회 시퀀스\(페이지, 응용 프로그램\)의 특정 수준에 존재하며 스타일이 적용될 형식과 일치하는 리소스 키를 사용하여 입력됩니다.  이 경우에는 <xref:System.Windows.FrameworkElement.Style%2A> 속성 자체는 시퀀스에서 항목 5로 식별되는 우선 순위에 따라 동작합니다.  이 상태를 검사하려면 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 기준으로 <xref:System.Windows.DependencyPropertyHelper>를 사용하고 결과에서 <xref:System.Windows.BaseValueSource>를 찾습니다.  
  
-   **기본 스타일** 또는 **테마 스타일**. <xref:System.Windows.FrameworkElement.Style%2A> 속성이 직접 설정되지 않으며 런타임 전까지 실제로 `null` 값으로 읽힙니다.  이 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레젠테이션 엔진의 일부인 런타임 테마 평가에서 스타일을 가져옵니다.  
  
 암시적 스타일이 테마에 없는 경우 형식이 정확히 일치해야 합니다. `MyButton` `Button` 파생 클래스는 `Button`에 대해 암시적으로 스타일을 사용하지 않습니다.  
  
<a name="themestyles"></a>   
## 기본\(테마\) 스타일  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 제공되는 모든 컨트롤에는 기본 스타일이 있습니다.  이 기본 스타일은 테마에 따라 달라질 수 있기 때문에 테마 스타일이라고도 합니다.  
  
 기본 스타일 내에서 발견되는 가장 중요한 컨트롤 정보는 테마 스타일에서 <xref:System.Windows.Controls.Control.Template%2A> 속성의 setter로 존재하는 컨트롤 템플릿입니다.  기본 스타일에서 가져온 템플릿이 없는 경우 사용자 지정 스타일의 일부인 사용자 지정 템플릿이 없는 컨트롤은 시각적인 모양이 없습니다.  기본 스타일의 템플릿은 각 컨트롤의 시각적 모양에 기본 구조를 제공하며 템플릿의 시각적 트리에 정의된 속성과 해당 컨트롤 클래스 간의 연결을 정의합니다.  각 컨트롤은 템플릿 전체를 대체하지 않고도 컨트롤의 시각적 모양을 바꿀 수 있는 속성 집합을 노출합니다.  예를 들어 <xref:System.Windows.Controls.Primitives.ScrollBar>의 구성 요소인 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤의 기본 시각적 모양을 살펴보겠습니다.  
  
 <xref:System.Windows.Controls.Primitives.Thumb>에는 사용자 지정 가능한 특정 속성이 있습니다.  <xref:System.Windows.Controls.Primitives.Thumb>의 기본 템플릿은 여러 <xref:System.Windows.Controls.Border> 구성 요소가 중첩되어 있는 기본 구조 \/ 시각적 트리를 생성하여 3D 효과를 만듭니다.  템플릿의 일부인 속성을 <xref:System.Windows.Controls.Primitives.Thumb> 클래스를 통해 사용자 지정할 수 있도록 노출하려는 경우 해당 속성을 템플릿 내에서 [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)으로 노출해야 합니다.  <xref:System.Windows.Controls.Primitives.Thumb>의 경우에는 테두리의 다양한 속성이 <xref:System.Windows.Controls.Border.Background%2A> 또는 <xref:System.Windows.Controls.Border.BorderThickness%2A> 같은 속성에 대한 템플릿 바인딩을 공유합니다.  하지만 다른 특정 속성이나 시각적 배치는 컨트롤 템플릿으로 하드 코드되거나 테마에서 직접 가져오는 값에 바인딩되므로 전체 템플릿을 대체하지 않는 한 변경할 수 없습니다.  일반적으로, 템플릿 부모에서 가져오는 속성이 템플릿 바인딩으로 노출되지 않는 경우 속성을 쉽게 대상으로 지정할 수 있는 방법이 없기 때문에 스타일을 통해 조정할 수 없습니다.  하지만 이 경우에도 적용된 템플릿의 속성 값 상속이나 기본값을 사용하면 속성을 조정할 수 있습니다.  
  
 테마 스타일 정의에서는 형식이 키로 사용됩니다.  하지만 지정된 요소 인스턴스에 테마를 적용하면 컨트롤의 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> 속성을 검사하여 테마에서 이 형식을 조회합니다.  이 동작은 암시적 스타일처럼 리터럴 형식을 사용하는 것과 다릅니다.  <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> 값은 구현자가 해당 값을 변경하지 않은 경우에도 파생 클래스에 상속됩니다. 이 경우 정상적인 속성 변경 방법은 속성 수준에서 값을 재정의하는 것이 아니라 속성 메타데이터에서 기본값을 변경하는 것입니다.  이러한 간접 방법을 사용하면 기본 클래스에서 다른 방법으로라면 스타일을 갖지 못했을 파생 요소에 테마 스타일을 정의할 수 있습니다. 여기서 중요한 점은 스타일을 갖지 못하면 그 스타일 내의 템플릿을 갖지 못하므로 결과적으로 기본적인 시각적 모양을 전혀 가질 수 없다는 것입니다.  따라서 <xref:System.Windows.Controls.Button>에서 `MyButton`을 파생시킬 수 있으며 <xref:System.Windows.Controls.Button> 기본 템플릿을 계속 가져올 수 있습니다.  다른 동작이 필요한 `MyButton` 컨트롤 제작자라면 `MyButton`에서 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>의 종속성 속성 메타데이터를 재정의하여 다른 키를 반환하게 한 다음, `MyButton` 컨트롤을 포함시켜야 하는 `MyButton` 템플릿을 비롯한 관련 테마 스타일을 정의할 수도 있습니다.  테마, 스타일 및 컨트롤 제작에 대한 자세한 내용은 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하십시오.  
  
<a name="resources"></a>   
## 동적 리소스 참조 및 바인딩  
 동적 리소스 참조 및 바인딩 작업은 해당 작업이 설정된 위치의 우선 순위를 고려합니다.  예를 들어 로컬 값에 적용되는 동적 리소스는 우선 순위 항목 3으로 동작하고 테마 스타일 내의 속성 setter에 대한 바인딩은 우선 순위 항목 9에 적용되는 식으로 동작합니다.  동적 리소스 참조와 바인딩은 모두 응용 프로그램의 런타임 상태에서 값을 가져올 수 있어야 하므로 지정된 속성에 대한 속성 값 우선 순위를 결정하는 실제 프로세스가 런타임으로도 확장됩니다.  
  
 엄밀하게 말하면 동적 리소스 참조는 속성 시스템의 일부가 아니며 위에 나열된 순서로 상호 작용하는 고유한 조회 순서를 가지고 있습니다.  이 우선 순위는 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)에 자세히 설명되어 있습니다.  이 우선 순위를 간단하게 요약하면 요소에서 페이지 루트, 응용 프로그램, 테마, 시스템의 순서입니다.  
  
 동적 리소스 및 바인딩에는 해당 작업이 설정된 위치의 우선 순위가 적용되지만 값은 지연됩니다.  이 때문에 로컬 값에 동적 리소스나 바인딩을 설정한 경우 로컬 값이 변경되면 변경된 값이 동적 리소스나 바인딩을 완전히 대체하는 경우가 발생하기도 합니다.  이 경우 <xref:System.Windows.DependencyObject.ClearValue%2A> 메서드를 호출하여 로컬에서 설정한 값을 지워도 동적 리소스나 바인딩이 복원되지 않습니다.  실제로, 리터럴 로컬 값이 없는 상태에서 동적 리소스나 바인딩이 배치된 속성에 대해 <xref:System.Windows.DependencyObject.ClearValue%2A>를 호출하면 <xref:System.Windows.DependencyObject.ClearValue%2A> 호출을 통해서도 이러한 동적 리소스나 바인딩이 지워집니다.  
  
<a name="setcurrentvalue"></a>   
## SetCurrentValue  
 <xref:System.Windows.DependencyObject.SetCurrentValue%2A> 메서드는 속성을 설정하는 또 다른 방법이지만 우선 순위는 지정되어 있지 않습니다.  대신 <xref:System.Windows.DependencyObject.SetCurrentValue%2A>를 사용하면 이전 값의 소스를 덮어쓰지 않고 속성 값을 변경할 수 있습니다.  값을 설정하면서 해당 값에 로컬 값의 우선 순위를 부여하지 않으려는 경우 항상 <xref:System.Windows.DependencyObject.SetCurrentValue%2A>를 사용할 수 있습니다.  예를 들어 속성이 트리거에 의해 설정된 다음 <xref:System.Windows.DependencyObject.SetCurrentValue%2A>를 통해 다른 값을 할당 받은 경우, 속성 시스템에서는 여전히 트리거를 유지하므로 트리거 작업이 발생하면 속성이 변경됩니다.  <xref:System.Windows.DependencyObject.SetCurrentValue%2A>를 사용하면 우선 순위가 더 높은 소스를 제공하지 않고도 속성 값을 변경할 수 있습니다.  마찬가지로 <xref:System.Windows.DependencyObject.SetCurrentValue%2A>를 사용하면 바인딩을 덮어쓰지 않고 속성 값을 변경할 수 있습니다.  
  
<a name="animations"></a>   
## 강제 변환, 애니메이션 및 기준 값  
 강제 변환 및 애니메이션은 모두 이 [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]에서 "기준 값"으로 표현되는 값에 작용합니다.  따라서 항목 2에 도달할 때까지 항목을 위쪽으로 평가하여 결정되는 값이 기준 값이 됩니다.  
  
 애니메이션의 경우 애니메이션에서 특정 동작에 대해 "From" 및 "To"를 모두 지정하지 않는 경우나 완료 시 애니메이션을 고의로 기준 값으로 되돌리는 경우에는 기준 값이 애니메이션 값에 영향을 줄 수 있습니다.  이 효과를 실제로 확인하려면 [From, To, and By Animation Target Values 샘플](http://go.microsoft.com/fwlink/?LinkID=159988)을 실행하십시오.  그런 다음, 예제에서 직사각형 높이의 로컬 값을 애니메이션의 "From"과 다른 초기 로컬 값을 갖도록 설정합니다.  그러면 애니메이션이 "From" 값을 사용하여 시작된 후에 기준 값으로 대체되는 것을 확인할 수 있습니다.  애니메이션에서 Stop <xref:System.Windows.Media.Animation.FillBehavior>를 지정하면 애니메이션이 완료된 후 애니메이션 전에 찾은 값으로 되돌아가도록 지정할 수 있습니다.  이후에는 기준 값 결정에 정상적인 우선 순위가 사용됩니다.  
  
 값 우선 순위의 서로 다른 위치에서 정의되었을 수 있는 여러 애니메이션을 하나의 속성에 적용할 수도 있습니다.  하지만 이러한 애니메이션은 단순히 높은 우선 순위의 애니메이션을 적용하는 게 아니라 값을 혼합하게 됩니다.  이는 애니메이션이 정의된 방식과 애니메이션 효과를 적용할 값의 형식에 따라 달라집니다.  속성에 애니메이션 효과를 주는 방법에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
 강제 변환은 가장 높은 수준에서 적용됩니다.  이것은 이미 실행 중인 애니메이션에 값 강제 변환이 적용되는 경우에도 마찬가지입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 특정 기존 종속성 속성에는 강제 변환이 기본으로 제공됩니다.  사용자 지정 종속성 속성의 경우에는 <xref:System.Windows.CoerceValueCallback>을 작성하고 속성을 생성할 때 메타데이터의 일부로 콜백을 전달하여 사용자 지정 종속성 속성에 대한 강제 변환 동작을 정의합니다.  또한 파생 클래스에서 기존 속성에 대한 메타데이터를 재정의하여 해당 속성의 강제 변환 동작을 재정의할 수도 있습니다.  강제 변환은 해당 시점에서 강제 변환에 대한 제약 조건이 존재할 때 적용되는 방식으로 기준 값을 사용하지만 이 경우에도 기준 값은 그대로 유지됩니다.  따라서 강제 변환의 제약 조건이 나중에 리프트되면 강제 변환은 해당 기준 값과 가장 가까운 값을 반환하고 강제 변환이 속성에 미치는 영향은 모든 제약 조건이 리프트되는 즉시 중지됩니다.  강제 변환 동작에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)를 참조하십시오.  
  
<a name="triggers"></a>   
## 트리거 동작  
 컨트롤에서 테마 기본 스타일의 일부로 트리거 동작을 정의하는 경우가 많습니다.  컨트롤에 로컬 속성을 설정하면 트리거가 시각적인 측면에서나 동작과 관련된 측면에서나 사용자 기반 이벤트에 반응하는 것을 방지할 수 있습니다.  속성 트리거의 가장 일반적인 용도는 <xref:System.Windows.Controls.Primitives.Selector.IsSelected%2A> 같은 상태 속성이나 컨트롤에 사용하는 것입니다.  예를 들어 <xref:System.Windows.Controls.Button>을 비활성화한 경우\(<xref:System.Windows.UIElement.IsEnabled%2A>에 대한 트리거가 `false`인 경우\) 기본적으로 테마 스타일의 <xref:System.Windows.Controls.Control.Foreground%2A> 값은 컨트롤을 "회색 음영"으로 나타나게 만듭니다.  하지만 이 속성 트리거 시나리오에서도 로컬 <xref:System.Windows.Controls.Control.Foreground%2A> 값을 설정한 경우에는 로컬 속성 설정에 따라 우선 순위에서 일반적인 회색 음영 색이 무시됩니다.  따라서 테마 수준 트리거 동작이 있는 속성에 대한 값을 설정할 때는 주의를 기울여야 하며 해당 컨트롤의 의도된 사용자 환경을 간섭하지 않는지 확인해야 합니다.  
  
<a name="clearvalue"></a>   
## ClearValue 및 값 우선 순위  
 <xref:System.Windows.DependencyObject.ClearValue%2A> 메서드를 사용하면 요소에 설정된 [종속성 속성](GTMT)에서 로컬로 적용된 모든 값을 손쉽게 지울 수 있습니다.  하지만 <xref:System.Windows.DependencyObject.ClearValue%2A>를 호출해도 속성 등록 중에 메타데이터에 설정된 기본값이 새로운 유효 값이 된다고 보장할 수는 없습니다.  값 우선 순위의 다른 모든 참가 요소는 그대로 활성 상태로 유지됩니다.  로컬로 설정된 값만 우선 순위 시퀀스에서 제거됩니다.  예를 들어 역시 테마 스타일로 설정된 속성에 대해 <xref:System.Windows.DependencyObject.ClearValue%2A>를 호출하면 메타데이터 기반 기본값 대신 테마 값이 새 값으로 적용됩니다.  프로세스에서 모든 속성 값 참가 요소를 가져와 해당 값을 등록된 메타데이터 기본값으로 설정하려는 경우 종속성 속성 메타데이터를 쿼리하여 기본값을 가져온 다음 해당 기본값으로 <xref:System.Windows.DependencyObject.SetValue%2A>를 호출하여 로컬로 속성을 설정할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.DependencyObject>   
 <xref:System.Windows.DependencyProperty>   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [종속성 속성 콜백 및 유효성 검사](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)