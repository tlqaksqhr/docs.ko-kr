---
title: "프레임워크 속성 메타데이터 | Microsoft Docs"
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
  - "프레임워크 속성 메타데이터"
  - "메타데이터, 프레임워크 속성"
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 프레임워크 속성 메타데이터
프레임워크 속성 메타데이터 옵션은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 아키텍처의 [WPF 프레임워크 수준](GTMT)에 있는 것으로 간주되는 개체 요소의 속성에 대해 보고됩니다.  일반적으로 [WPF 프레임워크 수준](GTMT) 지정의 경우 렌더링, 데이터 바인딩 및 속성 시스템 조정 등과 같은 기능이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 표시 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 및 실행 파일에 의해 처리됩니다.  이러한 시스템은 프레임워크 속성 메타데이터를 쿼리하여 특정 요소 속성의 기능별 특성을 결정합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 사용자가 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스의 기존 종속성 속성에 대한 소비자의 관점에서 [종속성 속성](GTMT)을 이해하고 있으며 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 읽었다고 가정합니다.  또한 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)를 읽어야 합니다.  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## 프레임워크 속성 메타데이터가 전달하는 내용  
 프레임워크 속성 메타데이터는 다음 범주로 나눌 수 있습니다.  
  
-   요소에 영향을 주는 레이아웃 속성 보고\(<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>\).  속성이 해당 측면에 영향을 주고 레이아웃 시스템에 특정 렌더링 동작과 정보를 제공하기 위해 클래스에 <xref:System.Windows.FrameworkElement.MeasureOverride%2A>\/<xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드를 구현하는 경우 메타데이터에 이러한 플래그를 설정할 수 있습니다.  일반적으로 이러한 구현은 이러한 레이아웃 속성이 속성 메타데이터에서 true인 종속성 속성에서 속성 무효화를 검사하며 이러한 무효화에만 새 레이아웃 과정 요청이 필요합니다.  
  
-   요소의 부모 요소에 영향을 주는 레이아웃 속성 보고\(<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>\).  이러한 플래그가 기본적으로 설정되는 몇 가지 예는 <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=fullName> 및 <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=fullName>입니다.  
  
-   <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>.  기본적으로 종속성 속성은 값을 상속하지 않습니다.  <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A>를 사용하면 상속 경로가 시각적 트리를 통해 이동합니다. 이는 시나리오를 구성하는 일부 컨트롤에 필요합니다.  
  
    > [!NOTE]
    >  속성 값의 측면에서 "상속"이라는 용어는 종속성 속성에 한정된 무엇인가를 의미합니다. 즉, 자식 요소는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템의 [WPF 프레임워크 수준](GTMT) 기능 때문에 부모 요소에서 실제 종속성 속성 값을 상속할 수 있음을 의미합니다.  파생 형식을 통한 관리 코드 형식 및 멤버 상속에 대해서는 직접적으로 수행되는 작업이 없습니다.  자세한 내용은 [속성 값 상속](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)을 참조하십시오.  
  
-   데이터 바인딩 특징 보고\(<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>\).  기본적으로 프레임워크의 종속성 속성은 단방향 바인딩 동작을 사용한 데이터 바인딩을 지원합니다.  해당 시나리오가 없는 경우 데이터 바인딩을 사용할 수 없도록 지정할 수 있습니다\(유연성과 확장성이 높게 설계되었기 때문에 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]에는 해당 속성의 예제가 많지 않기 때문\).  구성 요소 간에 컨트롤의 동작을 함께 묶는 속성\(예: <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A>\) 또는 양방향 바인딩이 일반적이며 사용자에게 필요한 시나리오\(예: <xref:System.Windows.Controls.TextBox.Text%2A>\)에 대해서는 양방향 기본값을 사용하도록 바인딩을 설정할 수 있습니다.  데이터 바인딩 관련 메타데이터를 변경하면 기본값에만 영향이 미칩니다. 이러한 기본값은 바인딩별로 언제든지 변경할 수 있습니다.  바인딩 모드 및 일반적인 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
-   저널링을 지원하는 응용 프로그램 또는 서비스에서 속성을 저널링해야 하는지 여부 보고\(<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>\).  일반 요소의 경우 저널링이 기본적으로 설정되지 않지만 특정 사용자 입력 컨트롤에 대해 선택적으로 설정됩니다.  이 속성은 저널링의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현을 포함한 저널링 서비스가 읽기 위한 것이며, 일반적으로 탐색 단계 내내 지속되어야 하는 목록 안의 사용자 선택 항목과 같은 사용자 컨트롤에서 설정됩니다.  저널에 대한 자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하십시오.  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## FrameworkPropertyMetadata 읽기  
 위에 링크된 각 속성은 <xref:System.Windows.FrameworkPropertyMetadata>가 직접적인 기본 클래스 <xref:System.Windows.UIPropertyMetadata>에 추가하는 특정 속성입니다.  이러한 각 속성은 기본적으로 `false`가 됩니다.  이러한 속성 값을 아는 것이 필요한 속성에 대한 메타데이터 요청은 반환된 데이터를 <xref:System.Windows.FrameworkPropertyMetadata>로 캐스팅하려고 시도한 후 필요에 따라 개별 속성 값을 검사해야 합니다.  
  
<a name="Specifying_Metadata"></a>   
## 메타데이터 지정  
 메타데이터를 새 종속성 속성 등록에 적용하기 위한 용도로 새 메타데이터 인스턴스를 만드는 경우에는 사용할 메타데이터 클래스를 기본 <xref:System.Windows.PropertyMetadata> 또는 <xref:System.Windows.FrameworkPropertyMetadata>와 같은 파생 클래스 중에서 선택할 수 있습니다.  일반적으로, 특히 속성이 속성 시스템 및 레이아웃과 데이터 바인딩 같은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능과 상호 작용할 때는 <xref:System.Windows.FrameworkPropertyMetadata>를 사용해야 합니다.  더 복잡한 시나리오에 대해 사용할 수 있는 다른 옵션은 <xref:System.Windows.FrameworkPropertyMetadata>에서 파생하여 멤버에서 전달되는 추가 정보가 있는 고유한 메타데이터 보고 클래스를 만드는 것입니다.  또는 <xref:System.Windows.PropertyMetadata>나 <xref:System.Windows.UIPropertyMetadata>를 사용하여 구현 기능에 대한 지원 수준을 전달할 수 있습니다.  
  
 기존 속성\(<xref:System.Windows.DependencyProperty.AddOwner%2A> 또는 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 호출\)의 경우에는 항상 원래 등록에서 사용하는 메타데이터 형식으로 재정의해야 합니다.  
  
 <xref:System.Windows.FrameworkPropertyMetadata> 인스턴스를 만들 때 프레임워크 속성 특징을 전달하는 특정 속성에 대한 값으로 해당 메타데이터를 채우는 방법에는 두 가지가 있습니다.  
  
1.  `flags` 매개 변수를 허용하는 <xref:System.Windows.FrameworkPropertyMetadata> 생성자 시그니처를 사용합니다.  이 매개 변수는 <xref:System.Windows.FrameworkPropertyMetadataOptions> 열거형 플래그를 원하는 대로 조합한 값으로 채워야 합니다.  
  
2.  `flags` 매개 변수 없이 시그니처 중 하나를 사용한 다음 원하는 각 특성 변경에 대해 <xref:System.Windows.FrameworkPropertyMetadata>의 보고 부울 속성을 `true`로 설정합니다.  이렇게 하는 경우에는 이 종속성 속성을 가진 모든 요소가 생성되기 전에 이 속성을 설정해야 합니다. 부울 속성은 `flags` 매개 변수를 피하는 동작을 허용하면서 메타데이터를 채우도록 하기 위해 읽기\-쓰기로 설정되어 있지만 메타데이터는 속성 사용 전에 봉인되어야 합니다.  따라서 메타데이터 요청 후 속성을 설정하려는 시도는 올바르지 않은 작업입니다.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## 프레임워크 속성 메타데이터 병합 동작  
 프레임워크 속성 메타데이터를 재정의할 때 여러 메타데이터 특성이 병합되거나 바뀝니다.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>이 병합됩니다.  새 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>을 추가하면 해당 콜백이 메타데이터에 저장됩니다.  재정의에 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>을 지정하지 않으면 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>의 값이 메타데이터에서 해당 값을 지정한 가장 가까운 상위에서의 참조로 승격됩니다.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>에 대한 실제 속성 시스템 동작은 계층 구조의 모든 메타데이터 소유자에 대한 구현이 가장 깊게 파생된 클래스의 콜백이 먼저 호출되는 속성 시스템 실행 순서대로 테이블에 유지되고 추가되는 것입니다.  상속된 콜백은 해당 콜백을 메타데이터에 배치한 클래스가 소유한 것으로 간주되어 한 번만 실행됩니다.  
  
-   <xref:System.Windows.PropertyMetadata.DefaultValue%2A>가 바뀝니다.  재정의에 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>을 지정하지 않으면 <xref:System.Windows.PropertyMetadata.DefaultValue%2A>의 값은 메타데이터에서 해당 값을 지정한 가장 가까운 상위에서 가져옵니다.  
  
-   <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 구현이 바뀝니다.  새 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>을 추가하면 해당 콜백이 메타데이터에 저장됩니다.  재정의에 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>을 지정하지 않으면 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>의 값이 메타데이터에서 해당 값을 지정한 가장 가까운 상위에서의 참조로 승격됩니다.  
  
-   속성 시스템 동작은 직접적인 메타데이터의 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>만 호출되는 방식으로 수행됩니다.  계층 구조의 다른 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 구현에 대한 참조는 유지되지 않습니다.  
  
-   <xref:System.Windows.FrameworkPropertyMetadataOptions> 열거형의 플래그는 비트 OR 연산으로 결합됩니다.  <xref:System.Windows.FrameworkPropertyMetadataOptions>를 지정하면 원래 옵션을 덮어쓰지 않게 됩니다.  옵션을 변경하려면 <xref:System.Windows.FrameworkPropertyMetadata>에 대해 해당 속성을 설정합니다.  예를 들어 원래 <xref:System.Windows.FrameworkPropertyMetadata> 개체가 <xref:System.Windows.FrameworkPropertyMetadataOptions?displayProperty=fullName> 플래그를 설정하는 경우 <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=fullName>을 `false`로 설정하여 이를 변경할 수 있습니다.  
  
 이 동작은 <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>에 의해 구현되며 파생된 메타데이터 클래스에서 재정의될 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.DependencyProperty.GetMetadata%2A>   
 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)