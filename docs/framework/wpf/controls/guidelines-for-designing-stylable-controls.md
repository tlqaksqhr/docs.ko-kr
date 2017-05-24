---
title: "스타일을 지정할 수 있는 컨트롤을 디자인하기 위한 지침 | Microsoft Docs"
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
  - "컨트롤, 스타일 디자인"
  - "컨트롤에 대한 스타일 디자인"
ms.assetid: c52dde45-a311-4531-af4c-853371c4d5f4
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 스타일을 지정할 수 있는 컨트롤을 디자인하기 위한 지침
이 문서에서는 스타일 및 템플릿을 지정할 수 있는 컨트롤을 디자인할 때 고려할 일련의 최선의 구현 방법을 요약합니다.  기본 제공 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 집합의 테마 컨트롤 스타일을 작업하면서 수많은 시행 착오를 통해 이러한 최적의 구현 방법을 얻게 되었습니다.  이러한 과정을 통해 성공적인 스타일은 스타일 자체만큼이나 잘 디자인된 개체 모델의 결과임을 알게 되었습니다.  이 문서는 스타일 제작자가 아니라 컨트롤 제작자를 위해 작성되었습니다.  
  
   
  
<a name="Terminology"></a>   
## 용어  
 "스타일 및 템플릿"은 컨트롤 제작자가 컨트롤의 시각적 측면을 컨트롤의 스타일과 템플릿에 맡길 수 있는 기술의 모음을 가리킵니다.  이러한 기술 모음에는 다음이 포함됩니다.  
  
-   스타일\(속성 setter, 트리거 및 스토리보드 포함\)  
  
-   리소스  
  
-   컨트롤 템플릿  
  
-   데이터 템플릿  
  
 스타일 및 템플릿에 대한 소개를 보려면 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하십시오.  
  
<a name="Before_You_Start__Understanding_Your_Control"></a>   
## 시작하기 전에: 컨트롤 이해  
 이 지침에 대해 알아보기 전에 컨트롤의 일반적인 사용에 대해 이해하고 정의하는 것이 중요합니다.  스타일은 제어하기 어려운 경우가 많은 일련의 가능성을 노출합니다.  많은 응용 프로그램에서 또는 많은 개발자가 폭넓게 사용하도록 작성된 컨트롤에서는 스타일을 사용하여 컨트롤의 시각적 모양을 광범위하게 변경할 수 있다는 문제가 있습니다.  실제로 스타일이 지정된 컨트롤은 심지어 컨트롤 제작자가 의도한 것과도 유사하지 않을 수 있습니다.  스타일이 제공하는 유연성은 기본적으로 한계가 없다는 데 있으므로 일반적인 사용에 대해 이해하면 결정 사항을 세심히 검토하는 데 도움이 될 수 있습니다.  
  
 컨트롤의 일반적인 사용에 대해 이해하려면 컨트롤의 값 제공에 대해 생각해 보는 것이 좋습니다.  테이블에서 다른 컨트롤은 제공할 수 없는 컨트롤만이 제공할 수 있는 값은 무엇일까요?  일반적인 사용에서는 특정한 시각적 모양을 제안하는 것이 아니라 컨트롤의 개발 개념과 그 사용에 대한 합리적인 예측 모음을 암시합니다.  이러한 이해를 통해 일반적인 경우의 컴퍼지션 모델과 스타일로 정의한 스타일 동작에 대해 몇 가지 가정을 세울 수 있습니다.  예를 들어 <xref:System.Windows.Controls.ComboBox>의 경우 일반적인 사용에 대해 이해하면 특정 <xref:System.Windows.Controls.ComboBox>의 모퉁이가 둥근지는 알 수 없으나 <xref:System.Windows.Controls.ComboBox>에 팝업 창과 이 상자가 열려 있는지 여부를 설정\/해제하는 방법이 필요할 수 있다는 점은 알 수 있습니다.  
  
<a name="General_Guidelines"></a>   
## 일반 지침  
  
-   **템플릿 계약을 엄격하게 적용하지 마십시오.** 컨트롤의 템플릿 계약은 컨트롤이 올바로 작동하기 위해 필요한 요소, 명령, 트리거 또는 속성 설정으로 구성될 수 있습니다.  
  
    -   계약을 가능한 한 최소화합니다.  
  
    -   디자인하는 동안 즉, 디자인 도구를 사용할 때 컨트롤 템플릿이 불완전한 상태에 있는 것이 일반적이라는 예상에 대해 디자인합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 "작성" 상태 인프라를 제공하지 않으므로 이러한 상태가 유효할 수 있다는 예상하에 컨트롤을 빌드해야 합니다.  
  
    -   템플릿 계약의 항목이 준수되지 않을 경우 예외를 throw하지 마십시오.  마찬가지로 패널의 자식이 너무 많거나 적을 경우 패널에서 예외를 throw하지 않아야 합니다.  
  
-   **주변 기능을 템플릿 도우미 요소에 포함시킵니다.** 각 컨트롤은 핵심 기능과 실제 값 제공에 중점을 두고 컨트롤의 일반적인 사용에 따라 디자인해야 합니다.  이를 위해 템플릿 내의 컴퍼지션 및 도우미 요소를 통해 주변 동작 및 시각화 즉, 컨트롤의 핵심 기능에 영향을 주지 않는 동작 및 시각화를 사용할 수 있도록 설정합니다.  도우미 요소는 다음 세 가지 범주로 구분됩니다.  
  
    -   **독립 실행형** 도우미 형식 \- 템플릿에서 "익명으로" 사용되는 다시 사용 가능한 public 컨트롤 또는 기본 형식입니다. 즉, 도우미 요소도 스타일 지정된 컨트롤도 다른 요소를 인식하지 못합니다.  기술적으로 모든 요소는 익명 형식이 될 수 있지만 본 컨텍스트에서 이 용어는 대상 시나리오를 사용하는 데 필요한 특수화된 기능을 캡슐화하는 형식을 나타냅니다.  
  
    -   **형식 기반** 도우미 요소 \- 특수화된 기능을 캡슐화하는 새 형식입니다.  일반적으로 이러한 요소는 일반 컨트롤이나 기본 형식보다 더 좁은 범위의 기능을 갖도록 디자인되었습니다.  독립 실행형 도우미 요소와 달리 형식 기반 도우미 요소는 사용되는 컨텍스트를 인식하며 일반적으로 해당 템플릿에 요소가 속한 컨트롤과 데이터를 공유해야 합니다.  
  
    -   **이름 지정** 도우미 요소 \- 컨트롤이 해당 템플릿 내에서 이름으로 찾아야 하는 예상하는 일반 컨트롤 또는 기본 형식입니다. 이러한 요소에는 템플릿 내에서 잘 알려진 이름이 지정되므로 컨트롤이 요소를 찾고 해당 요소와 프로그래밍 방식으로 상호 작용할 수 있습니다.  템플릿에는 지정한 이름의 요소가 하나만 있을 수 있습니다.  
  
     다음 표에서는 현재 컨트롤 스타일에서 사용되는 도우미 요소를 보여 줍니다. 모든 요소가 나열된 것은 아닙니다.  
  
    |요소|형식|다음 리소스에서 사용|  
    |--------|--------|-----------------|  
    |<xref:System.Windows.Controls.ContentPresenter>|형식 기반|<xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.Frame> 등\(모든 <xref:System.Windows.Controls.ContentControl> 형식\)|  
    |<xref:System.Windows.Controls.ItemsPresenter>|형식 기반|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu> 등\(모든 <xref:System.Windows.Controls.ItemsControl> 형식\)|  
    |<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|이름 지정|<xref:System.Windows.Controls.ToolBar>|  
    |<xref:System.Windows.Controls.Primitives.Popup>|독립 실행형|<xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ToolBar>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolTip> 등|  
    |<xref:System.Windows.Controls.Primitives.RepeatButton>|이름 지정|<xref:System.Windows.Controls.Slider>, <xref:System.Windows.Controls.Primitives.ScrollBar> 등|  
    |<xref:System.Windows.Controls.Primitives.ScrollBar>|이름 지정|<xref:System.Windows.Controls.ScrollViewer>|  
    |<xref:System.Windows.Controls.ScrollViewer>|독립 실행형|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.Frame> 등|  
    |<xref:System.Windows.Controls.Primitives.TabPanel>|독립 실행형|<xref:System.Windows.Controls.TabControl>|  
    |<xref:System.Windows.Controls.TextBox>|이름 지정|<xref:System.Windows.Controls.ComboBox>|  
    |<xref:System.Windows.Controls.Primitives.TickBar>|형식 기반|<xref:System.Windows.Controls.Slider>|  
  
-   **도우미 요소에 대해 필요한 사용자 지정 바인딩이나 속성 설정을 최소화합니다.** 도우미 요소가 컨트롤 템플릿 내에서 올바로 작동하려면 특정 바인딩이나 속성 설정이 필요한 것이 일반적입니다.  가능한 한 도우미 요소 및 템플릿 기반 컨트롤에서 이러한 설정을 지정해야 합니다.  속성이나 바인딩을 설정할 때는 사용자가 설정한 값을 재정의하지 않도록 주의해야 합니다.  자세한 최선의 구현 방법은 다음과 같습니다.  
  
    -   이름 지정 도우미 요소는 부모가 식별해야 하며 부모가 도우미 요소에 필요한 설정을 지정해야 합니다.  
  
    -   형식 기반 도우미 요소는 요소 자체에서 필요한 설정을 직접 지정해야 합니다.  이렇게 하려면 도우미 요소에서 해당 `TemplatedParent`\(요소가 사용되는 템플릿의 컨트롤 형식\)를 포함하여 요소가 사용되는 정보 컨텍스트를 쿼리할 수 있어야 합니다.  예를 들어 <xref:System.Windows.Controls.ContentPresenter>는 <xref:System.Windows.Controls.ContentControl> 파생 형식에서 사용되는 경우 자동으로 `TemplatedParent`의 `Content` 속성을 <xref:System.Windows.Controls.ContentPresenter.Content%2A> 속성에 바인딩합니다.  
  
    -   독립 실행형 도우미 요소는 정의상 도우미 요소와 부모 요소 모두 다른 요소를 인식하지 못하므로 이와 같은 방법으로 최적화할 수 없습니다.  
  
-   **Name 속성을 사용하여 템플릿 내의 요소에 플래그를 지정합니다.** 요소에 프로그래밍 방식으로 액세스하기 위해 요소를 찾아야 하는 컨트롤에서는 `Name` 속성 및 `FindName` 패러다임을 사용하여 이렇게 해야 합니다.  컨트롤에서는 요소를 찾지 못하는 경우 예외를 throw하진 않지만 해당 요소를 필요로 하는 기능을 자동으로 사용하지 않도록 설정해야 합니다.  
  
-   **스타일에서 컨트롤 상태와 동작을 표시하기 위한 최선의 구현 방법을 사용합니다.** 다음은 스타일에서 컨트롤 상태 변경 사항 및 동작을 표시하기 위한 최선의 구현 방법을 순서대로 나열한 목록입니다.  목록에서 시나리오를 사용 가능하게 하는 첫 번째 항목을 사용해야 합니다.  
  
    1.  속성 바인딩.  예제: <xref:System.Windows.Controls.ComboBox.IsDropDownOpen%2A?displayProperty=fullName> 및 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A?displayProperty=fullName> 간의 바인딩  
  
    2.  트리거된 속성 변경 사항 또는 속성 애니메이션.  예제: <xref:System.Windows.Controls.Button>의 호버 상태  
  
    3.  명령.  예제: <xref:System.Windows.Controls.Primitives.ScrollBar>의 <xref:System.Windows.Controls.Primitives.ScrollBar.LineUpCommand>\/<xref:System.Windows.Controls.Primitives.ScrollBar.LineDownCommand>  
  
    4.  독립 실행형 도우미 요소.  예제: <xref:System.Windows.Controls.TabControl>의 <xref:System.Windows.Controls.Primitives.TabPanel>  
  
    5.  형식 기반 도우미 형식.  예제:<xref:System.Windows.Controls.Button>의  <xref:System.Windows.Controls.ContentPresenter>, <xref:System.Windows.Controls.Slider>의 <xref:System.Windows.Controls.Primitives.TickBar>  
  
    6.  이름 지정 도우미 요소  예제: <xref:System.Windows.Controls.ComboBox>의 <xref:System.Windows.Controls.TextBox>  
  
    7.  이름 지정 도우미 형식의 버블링된 이벤트.  스타일 요소에서 버블링된 이벤트를 수신하면 이벤트를 생성하는 요소를 고유하게 식별할 수 있어야 합니다.  예제: <xref:System.Windows.Controls.ToolBar>의 <xref:System.Windows.Controls.Primitives.Thumb>  
  
    8.  사용자 지정 `OnRender` 동작.  예제: <xref:System.Windows.Controls.Button>의 <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   **템플릿 트리거와는 반대로 스타일 트리거를 최소한으로 사용합니다.** 템플릿에 있는 요소의 속성에 영향을 주는 트리거는 템플릿에서 선택해야 합니다.  컨트롤의 속성에 영향을 주는 트리거\(`TargetName` 없음\)는 템플릿을 변경하면 트리거도 삭제해야 한다는 것을 알고 있는 경우를 제외하고 스타일에서 선언할 수 있습니다.  
  
-   **기존 스타일 패턴과 일관성을 유지합니다.** 대부분의 경우 문제를 해결하는 여러 방법이 있습니다.  가능한 한 기존 컨트롤 스타일 패턴과 일관성을 유지해야 합니다.  동일한 기본 형식에서 파생되는 컨트롤\(예: <xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.Primitives.RangeBase> 등\)의 경우 이 점은 특히 중요합니다.  
  
-   **템플릿을 다시 지정하지 않고도 일반적인 사용자 지정 시나리오를 사용할 수 있도록 만드는 속성을 노출합니다.** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 사용자 지정 가능한 플러그형 파트를 지원하지 않으므로 컨트롤 사용자는 속성을 직접 설정하거나 스타일을 사용하여 속성을 설정하는 두 가지 사용자 지정 방법만 사용할 수 있습니다.  이 점을 염두에 두고 매우 일반적이고 우선 순위가 높은 사용자 지정 시나리오를 대상으로 하는 제한된 수의 속성만 표시하여 템플릿을 다시 지정할 필요가 없도록 하는 것이 좋습니다.  다음은 사용자 지정 시나리오를 사용하는 시기와 그 방법에 대한 유용한 정보입니다.  
  
    -   매우 일반적인 사용자 지정은 컨트롤의 속성으로 노출하고 템플릿에서 사용해야 합니다.  
  
    -   덜 일반적이지만 자주 사용하는 사용자 지정은 연결된 속성으로 노출해야 하며 템플릿에서 사용해야 합니다.  
  
    -   알려져 있지만 드문 사용자 지정은 템플릿 다시 지정이 필요하도록 할 수 있습니다.  
  
<a name="Theme_Considerations"></a>   
## 테마 고려 사항  
  
-   **테마 스타일에서는 모든 테마에서 속성 의미 체계의 일관성을 유지하려 해야 하지만 이를 보장할 수는 없습니다.** 컨트롤에는 컨트롤 문서의 일부로 컨트롤의 속성 의미 체계 즉, 컨트롤의 속성에 대한 "의미"를 설명하는 문서가 있어야 합니다.  예를 들어 <xref:System.Windows.Controls.ComboBox> 컨트롤에서는 <xref:System.Windows.Controls.ComboBox> 내의 <xref:System.Windows.Controls.Control.Background%2A> 속성에 대한 의미를 정의해야 합니다.  컨트롤의 기본 스타일에서는 해당 문서에 정의된 의미 체계를 모든 테마에서 따라야 합니다.  반면 컨트롤 사용자는 속성 의미 체계가 테마에 따라 변경될 수 있음을 알아야 합니다.  경우에 따라 특정 테마에 필요한 시각적 제약 조건하에서 지정한 속성을 표시할 수 없을 수도 있습니다.  예를 들어 클래식 테마에는 많은 컨트롤에 대해 `Thickness`를 적용할 수 있는 단일 테두리가 없습니다.  
  
-   **테마 스타일에서는 모든 테마에서 트리거 의미 체계를 일관성 있게 유지할 필요가 없습니다.** 컨트롤 스타일에서 트리거나 애니메이션을 통해 노출하는 동작은 테마에 따라 다를 수 있습니다.  컨트롤 사용자는 모든 테마에서 특정 동작을 얻기 위해 컨트롤에서 동일한 메커니즘을 사용할 필요는 없다는 것을 알아야 합니다.  예를 들어 한 테마에서는 애니메이션을 사용하여 호버 동작을 표현하는 데 반해 다른 테마에서는 트리거를 사용할 수 있습니다.  이 때문에 사용자 지정된 컨트롤의 동작 유지에서 불일치가 발생할 수 있습니다.  예를 들어 컨트롤의 호버 상태가 트리거를 사용하여 표현된 경우 배경 속성을 변경해도 이 상태에 영향을 주지 않을 수 있습니다.  그러나 호버 상태가 애니메이션을 사용하여 구현된 경우 배경을 변경하면 애니메이션이 복구할 수 없게 중단되어 상태가 전환될 수 있습니다.  
  
-   **테마 스타일에서는 모든 테마에서 "레이아웃" 의미 체계를 일관성 있게 유지할 필요가 없습니다.** 예를 들어 기본 스타일에서는 모든 테마에서 컨트롤이 같은 크기를 차지할 필요가 없으며 모든 테마에서 내용의 여백 또는 안쪽 여백이 동일할 필요가 없습니다.  
  
## 참고 항목  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)