---
title: 프레임워크 속성 메타데이터
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: d968bc7a3033bd994590520c5cd5062d3c212b4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547464"
---
# <a name="framework-property-metadata"></a>프레임워크 속성 메타데이터
프레임워크 속성 메타데이터는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 아키텍처의 WPF 프레임워크 수준에 있는 것으로 간주되는 개체 요소의 속성용으로 보고됩니다. 일반적으로 WPF 프레임워크 수준 지정에서는 렌더링, 데이터 바인딩 및 속성 시스템 미세 조정과 같은 기능이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레젠테이션 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 및 실행 파일을 통해 처리됩니다. 이러한 시스템에서 프레임워크 속성 메타데이터를 쿼리하여 특정 요소 속성의 기능별 특성을 결정합니다.  
  
 
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스에서 기존 종속성 속성의 소비자 관점에서 종속성 속성을 이해하고 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 읽었다고 가정합니다. [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)도 읽어야 합니다.  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>프레임워크 속성 메타데이터로 통신하는 내용  
 프레임워크 속성 메타데이터는 다음 범주로 구분할 수 있습니다.  
  
-   레이아웃 속성 요소에 영향을 주는 보고 (<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>). 속성에 해당 측면을 적용 하 고 구현 하는 경우 메타 데이터에서 이러한 플래그를 설정할 수는 <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 특정 렌더링 동작 및 레이아웃 정보를 제공 하기 위해 클래스의 메서드 시스템입니다. 일반적으로 이러한 구현에서는 해당 레이아웃 속성이 속성 메타데이터에서 참인 종속성 속성의 속성 무효화를 확인하고 해당 무효화만 새로운 레이아웃 전달을 요청해야 합니다.  
  
-   요소의 부모 요소에 영향을 주는 레이아웃 속성을 보고 (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>). 기본적으로이 플래그를 설정 하는 몇 가지 예는 <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>합니다.  
  
-   <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. 기본적으로 종속성 속성은 값을 상속하지 않습니다. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> 상속도 일부 제어 합성 시나리오에 필요한 시각적 트리로 이동 하는 경로가 있습니다.  
  
    > [!NOTE]
    >  속성 값 컨텍스트에서 “상속”이라는 용어는 종속성 속성에 특정한 것입니다. 즉, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템의 WPF 프레임워크 수준 기능때문에 자식 요소가 부모 요소에서 실제 종속성 속성 값을 상속할 수 있습니다. 파생된 유형을 통한 멤버 상속 및 관리된 코드 유형과는 직접적인 관련이 없습니다. 자세한 내용은 [속성 값 상속](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)을 참조하십시오.  
  
-   데이터 바인딩 특성을 보고 (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>). 기본적으로 프레임워크의 종속성 속성은 단방향 바인딩 동작을 통한 데이터 바인딩을 지원합니다. 시나리오가 전혀 없는 경우 데이터 바인딩을 사용하지 않게 설정할 수 있습니다(유연하고 확장 가능해야 하므로 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]에는 이러한 속성의 예가 많지 않음). 구성 요소 간에 컨트롤의 동작을 함께 연결 하는 속성에 대 한 기본값은 양방향 바인딩을 설정할 수 있습니다 (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> 은 예제) 또는 양방향 바인딩을 사용자에 대 한 일반적이 고 예상 시나리오 (<xref:System.Windows.Controls.TextBox.Text%2A> 은 예). 데이터 바인딩 관련 메타데이터를 변경하면 기본값에만 영향을 미칩니다. 바인딩별 변경에서는 해당 기본값을 항상 변경할 수 있습니다. 바인딩 모드와 일반적인 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요.  
  
-   속성에서 응용 프로그램 또는 서비스를 지 원하는 저널링 저널링 되어야 하는지 여부를 보고 (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>). 일반 요소에는 기본적으로 저널링을 사용하지 않지만, 특정 사용자 입력 컨트롤에 대해서는 선택적으로 사용합니다. 이 속성은 저널링의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현을 포함하여 저널링 서비스를 통해 읽어야 하며, 일반적으로 탐색 단계 간에 지속되어야 하는 목록의 사용자 선택 항목과 같은 사용자 컨트롤에 설정됩니다. 저널에 대한 자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하세요.  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>FrameworkPropertyMetadata 읽기  
 각 위에 링크 된 속성은 특정 속성이 있는 <xref:System.Windows.FrameworkPropertyMetadata> 이름과 기본 클래스에 추가 <xref:System.Windows.UIPropertyMetadata>합니다. 이러한 각 속성은 기본적으로 `false`입니다. 이러한 속성의 값을 아는 것이 중요 한 속성에 대 한 메타 데이터를 요청에 반환된 된 메타 데이터를 캐스팅 하려고 해야 <xref:System.Windows.FrameworkPropertyMetadata>, 한 다음 필요에 따라 개별 속성 값을 확인 합니다.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>메타데이터 지정  
 메타 데이터를 새 종속성 속성 등록 적용의 목적에 대 한 새 메타 데이터 인스턴스를 만들 때는의 메타 데이터 클래스를 사용 하 여 선택할 수 있습니다: 기본 <xref:System.Windows.PropertyMetadata> 와 같은 일부 파생 클래스 또는 <xref:System.Windows.FrameworkPropertyMetadata>합니다. 일반적으로 사용 해야 <xref:System.Windows.FrameworkPropertyMetadata>속성이 속성 시스템와의 상호 작용 하는 경우에 특히, 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 및 데이터 바인딩과 같은 함수입니다. 파생 되도록 더 복잡 한 시나리오에 대 한 또 다른 옵션은 <xref:System.Windows.FrameworkPropertyMetadata> 의 멤버에 전달 추가 정보를 사용 하 여 클래스를 보고 직접 메타 데이터를 만듭니다. 사용할 수도 있습니다 <xref:System.Windows.PropertyMetadata> 또는 <xref:System.Windows.UIPropertyMetadata> 기능 구현에 대 한 지원 수준을 통신할 수 있습니다.  
  
 기존 속성에 대 한 (<xref:System.Windows.DependencyProperty.AddOwner%2A> 또는 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 호출)를 재정의 해야 하는 항상 원본 등록에 사용 된 메타 데이터 유형을 사용 합니다.  
  
 만드는 경우는 <xref:System.Windows.FrameworkPropertyMetadata> 인스턴스를 두 가지 방법으로 프레임 워크 속성 특성에 전달 하는 특정 속성에 대 한 값으로 해당 메타 데이터를 채우는 데:  
  
1.  사용 하 여는 <xref:System.Windows.FrameworkPropertyMetadata> 허용 하는 생성자 시그니처는 `flags` 매개 변수입니다. 이 매개 변수 값의 조합이 원하는 모든으로 채워야는 <xref:System.Windows.FrameworkPropertyMetadataOptions> 열거형 플래그입니다.  
  
2.  없이 서명 중 하나를 사용 하 여 한 `flags` 매개 변수를 다음에 보고 하는 부울 속성을 설정 하 고 <xref:System.Windows.FrameworkPropertyMetadata> 를 `true` 원하는 각 특성 변경에 대 한 합니다. 이 작업을 수행하는 경우 이 종속성 속성이 있는 요소를 생성하기 전에 이러한 속성을 설정해야 합니다. `flags` 매개 변수를 방지하는 동작을 허용하기 위해 부울 속성은 읽기-쓰기가 되며 여전히 메타데이터를 채우지만, 속성을 사용하기 전에 메타데이터를 적절하게 봉인해야 합니다. 따라서 메타데이터를 요청한 후에 속성을 설정하려는 것은 올바른 작업이 아닙니다.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>프레임워크 속성 메타데이터 병합 동작  
 프레임워크 속성 메타데이터를 재정의할 때, 여러 다른 메타데이터 특성을 병합하거나 대체합니다.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 병합 됩니다. 새 추가 하는 경우 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, 해당 콜백 메타 데이터에 저장 됩니다. 지정 하지 않는 경우는 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 재정의 값에 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 메타 데이터에 지정 하는 가장 가까운 상위 항목에서 참조로 승격 됩니다.  
  
-   에 대 한 실제 속성 시스템 동작 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 사용 되는 구현을 계층의 모든 메타 데이터 소유자 유지 되 고 테이블에 추가 대 한 가장 많이 파생된 된 클래스의 콜백 하 되 속성 시스템에 의해 실행 순서 대로 먼저 호출 됩니다. 상속된 콜백은 한 번만 실행되며, 메타데이터에 해당 콜백을 둔 클래스가 소유하는 것으로 계산됩니다.  
  
-   <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 대체 됩니다. 지정 하지 않는 경우는 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 재정의 값에 <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 메타 데이터에 지정 하는 가장 가까운 상위 항목에서 제공 합니다.  
  
-   <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 구현이 바뀝니다. 새 추가 하는 경우 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, 해당 콜백 메타 데이터에 저장 됩니다. 지정 하지 않는 경우는 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 재정의 값에 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 메타 데이터에 지정 하는 가장 가까운 상위 항목에서 참조로 승격 됩니다.  
  
-   속성 시스템 동작은는 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 즉시 메타 데이터에 호출 됩니다. 다른에 참조가 없는 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 구현 계층 구조에서 유지 됩니다.  
  
-   플래그 <xref:System.Windows.FrameworkPropertyMetadataOptions> 열거형을 비트 OR 연산으로 결합 됩니다.  지정 하는 경우 <xref:System.Windows.FrameworkPropertyMetadataOptions>, 원래 옵션을 덮어쓰지 않습니다.  옵션을 변경 하려면 해당 속성을 설정 <xref:System.Windows.FrameworkPropertyMetadata>합니다. 예를 들어 경우 원래 <xref:System.Windows.FrameworkPropertyMetadata> 개체 집합이 <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> 플래그를 설정 하 여 변경할 수 있습니다 <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> 를 `false`합니다.  
  
 이 동작을 구현 하 여 <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>, 파생 된 메타 데이터 클래스에서 재정의 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.DependencyProperty.GetMetadata%2A>  
 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
