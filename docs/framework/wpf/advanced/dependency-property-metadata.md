---
title: 종속성 속성 메타데이터
ms.date: 03/30/2017
helpviewer_keywords:
- APIs [WPF], metadata
- dependency properties [WPF], metadata
- metadata [WPF], for dependency properties
- overriding metadata [WPF]
ms.assetid: d01ed009-b722-41bf-b82f-fe1a8cdc50dd
ms.openlocfilehash: f0aa1d2962b0bccea7a0901877b29550319aaa3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541699"
---
# <a name="dependency-property-metadata"></a>종속성 속성 메타데이터
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템에는 리플렉션이나 일반적인 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 특성을 통해 속성에 대해 보고할 수 있는 수준을 넘어서는 메타데이터 보고 시스템이 포함됩니다. 또한 종속성 속성에 대한 메타데이터는 종속성 속성을 정의하는 클래스에서 고유하게 할당하고, 종속성 속성이 다른 클래스에 추가될 때 변경하며, 정의하는 기본 클래스에서 종속성 속성을 상속하는 모든 파생 클래스에서 구체적으로 재정의할 수 있습니다.  
  
 
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스에서 기존 종속성 속성의 소비자 관점에서 종속성 속성을 이해하고 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 읽었다고 가정합니다. 이 항목의 예제를 따르려면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 이해하고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 작성하는 방법도 알아야 합니다.  
  
<a name="dp_metadata_contents"></a>   
## <a name="how-dependency-property-metadata-is-used"></a>종속성 속성 메타데이터를 사용하는 방법  
 종속성 속성 메타데이터는 종속성 속성의 특성을 검사하기 위해 쿼리할 수 있는 개체로 존재합니다. 또한 이 메타데이터는 속성 시스템에서 제공된 종속성 속성을 처리할 때 자주 액세스합니다. 종속성 속성에 대한 메타데이터 개체에는 다음과 같은 유형의 정보가 포함될 수 있습니다.  
  
-   로컬 값, 스타일, 상속 등으로 종속성 속성에 대한 다른 값을 확인할 수 없는 경우 종속성 속성에 대한 기본값. 기본값이 종속성 속성에 대한 값을 할당할 때 속성 시스템에서 사용되는 우선 순위에 참여하는 방법에 대한 자세한 내용은 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)를 참조하세요.  
  
-   소유자 유형별로 강제 변환 또는 변경 알림 동작에 영향을 주는 콜백 구현에 대한 참조. 이러한 콜백은 종종 public이 아닌 액세스 수준으로 정의되므로 일반적으로 참조가 허용된 액세스 범위 내에 있지 않으면 메타데이터에서 실제 참조를 가져올 수 없습니다. 종속성 속성 콜백에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)를 참조하세요.  
  
-   해당 종속성 속성이 WPF 프레임워크 수준 속성으로 간주되는 경우 메타데이터에는 WPF 프레임워크 수준 레이아웃 엔진 및 속성 상속 논리 같은 서비스에 대한 정보 및 상태를 보고하는 WPF 프레임워크 수준 종속성 속성 특성이 포함될 수 있습니다. 이러한 측면의 종속성 속성 메타데이터에 대한 자세한 내용은 [프레임워크 속성 메타데이터](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)를 참조하세요.  
  
<a name="APIs"></a>   
## <a name="metadata-apis"></a>메타데이터 API  
 대부분의 속성 시스템에서 사용 하는 메타 데이터 정보를 보고 된 형식이 고 <xref:System.Windows.PropertyMetadata> 클래스입니다. 메타데이터 인스턴스는 종속성 속성이 속성 시스템에 등록될 때 필요에 따라 지정되며 소유자로 자신을 추가하거나 기본 클래스 종속성 속성 정의에서 상속되는 메타데이터를 재정의하는 추가 형식에 대해 다시 지정할 수 있습니다. (속성을 등록 하는 기본 메타 데이터를 지정 하지 않는 경우 <xref:System.Windows.PropertyMetadata> 해당 클래스에 대 한 기본값을 사용 하 여 만들어집니다.) 로 등록 된 메타 데이터가 반환 되는지 <xref:System.Windows.PropertyMetadata> 다양 한 호출 하는 경우 <xref:System.Windows.DependencyProperty.GetMetadata%2A> 에서 종속성 속성에서 메타 데이터를 가져오기 하는 오버 로드는 <xref:System.Windows.DependencyObject> 인스턴스.  
  
 <xref:System.Windows.PropertyMetadata> 클래스는 다음 아키텍처와 같은 WPF 프레임 워크 수준 클래스에 대 한 보다 구체적인 메타 데이터를 제공 하에서 파생 됩니다. <xref:System.Windows.UIPropertyMetadata> 애니메이션을 보고, 추가 및 <xref:System.Windows.FrameworkPropertyMetadata> 이전 섹션에서 언급 한 WPF 프레임 워크 수준 속성을 제공 합니다. 종속성 속성을 등록 하는 경우 이러한에 등록할 수 있습니다 이러한 <xref:System.Windows.PropertyMetadata> 파생 클래스입니다. 메타 데이터를 검사 하는 경우, 기본 <xref:System.Windows.PropertyMetadata> 보다 구체적인 속성을 확인할 수 있도록 유형은 파생된 클래스에 캐스팅 될 수 있습니다.  
  
> [!NOTE]
>  에 지정할 수 있는 속성의 특징 <xref:System.Windows.FrameworkPropertyMetadata> "flags"를 사용 하 여이 설명서에서에 라고도 합니다. 플래그 열거형을 사용 하 여 이러한 값을 지정 만들면 사용 하기 위해 새 메타 데이터 인스턴스가 종속성에서 속성을 등록 하거나 메타 데이터 재정의 <xref:System.Windows.FrameworkPropertyMetadataOptions> 는 열거형의연결된값을제공합니다<xref:System.Windows.FrameworkPropertyMetadata> 생성자입니다. 그러나 생성 된 해당 옵션 특성은 표시 내에서 한 <xref:System.Windows.FrameworkPropertyMetadata> 일련의 생성 하는 열거형 값 보다는 부울 속성입니다. 부울 속성을 사용하면 플래그 열거형 값에 마스크를 적용하여 관심 있는 정보를 가져오는 대신 각 조건을 확인할 수 있습니다. 생성자를 사용 하 여 연결 된 <xref:System.Windows.FrameworkPropertyMetadataOptions> 실제 생성 된 메타 데이터는 보다 직관적인 메타 데이터를 쿼리할 수 있도록 개별 속성을 표시 하는 반면, 적절 한 생성자 서명의 길이 유지 하기 위해.  
  
<a name="override_or_subclass"></a>   
## <a name="when-to-override-metadata-when-to-derive-a-class"></a>메타데이터를 재정의하는 경우, 클래스를 파생시키는 경우  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템은 종속성 속성의 일부 특성을 완전히 다시 구현할 필요 없이 변경하는 기능을 설정했습니다. 이 기능은 특정 형식에 있는 종속성 속성에 대한 속성 메타데이터의 다른 인스턴스를 생성하여 수행합니다. 대부분의 기존 종속성 속성은 가상 속성이 아닙니다. 따라서 엄밀히 말해 상속된 클래스에서 "다시 구현"하려면 기존 멤버를 숨겨야만 합니다.  
  
 특정 형식에 있는 종속성 속성에 대해 사용하려는 시나리오를 기존 종속성 속성의 특성을 수정하여 수행할 수 없는 경우 파생 클래스를 만든 다음 해당 파생 클래스에서 사용자 지정 종속성 속성을 선언해야 할 수 있습니다. 사용자 지정 종속성 속성은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]에서 정의된 종속성 속성과 동일하게 동작합니다. 사용자 지정 종속성 속성에 대한 자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 참조하세요.  
  
 재정의할 수 없는 종속성 속성의 주요 특성 한 가지는 해당 값 형식입니다. 필요한 유사한 동작을 수행하는 종속성 속성을 상속하려고 하는데 다른 형식이 필요한 경우 사용자 지정 종속성 속성을 구현하고 사용자 지정 클래스에서 형식 변환이나 다른 구현을 통해 속성을 연결해야 합니다. 또한 바꿀 수 없지만 기존 <xref:System.Windows.ValidateValueCallback>이 콜백을 등록 필드 자체 및 해당 메타 데이터 내에 있지 있으므로, 합니다.  
  
<a name="scenarios"></a>   
## <a name="scenarios-for-changing-existing-metadata"></a>기존 메타데이터 변경 시나리오  
 기존 종속성 속성의 메타데이터를 사용하여 작업하는 경우 종속성 속성 메타데이터를 변경하는 한 가지 일반적인 시나리오는 기본값을 변경하는 것입니다. 속성 시스템 콜백 변경 또는 추가는 고급 시나리오입니다. 파생 클래스의 구현이 종속성 속성 간에 다른 상관 관계를 갖는 경우 이 작업을 수행하는 것이 좋습니다. 코드와 선언적 사용을 모두 지원하는 프로그래밍 모델의 조건 중 하나는 순서에 관계없이 속성을 설정할 수 있어야 하는 것입니다. 따라서 모든 종속 속성은 컨텍스트 없이 적시에 설정해야 하며 생성자에서 찾을 수 있는 설정 순서를 사용할 필요가 없습니다. 속성 시스템의 이러한 측면에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)를 참조하세요. 유효성 검사 콜백은 메타데이터의 일부가 아니라 종속성 속성 식별자의 일부입니다. 따라서 유효성 검사 콜백은 메타데이터를 재정의하여 변경할 수 없습니다.  
  
 경우에 따라 기존 종속성 속성에서 WPF 프레임워크 수준 속성 메타데이터 옵션을 변경하려고 할 수도 있습니다. 이러한 옵션은 WPF 프레임워크 수준 속성에 대한 알려진 특정 조건을 레이아웃 시스템 같은 다른 WPF 프레임워크 수준 프로세스에 전달합니다.  새 종속성 속성을 등록 하는 경우에 일반적으로 수행에서 옵션을 설정 되지만 WPF 프레임 워크 수준 속성 메타 데이터의 일환으로 변경할 수 이기도 한 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 또는 <xref:System.Windows.DependencyProperty.AddOwner%2A> 호출 합니다. 사용할 특정 값 및 자세한 내용은 [프레임워크 속성 메타데이터](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)를 참조하세요. 새로 등록된 종속성 속성에 대해 이러한 옵션을 설정하는 방법과 관련된 자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 참조하세요.  
  
<a name="dp_override_metadata"></a>   
### <a name="overriding-metadata"></a>메타데이터 재정의  
 메타데이터 재정의의 용도는 특정 형식에 있는 종속성 속성에 적용되는 다양한 메타데이터 파생 동작을 변경할 수 있도록 하는 것입니다. 그 이유는 [메타데이터](#dp_metadata_contents) 섹션에 자세히 설명되어 있습니다. 몇 가지 코드 예제를 비롯한 자세한 내용은 [종속성 속성의 메타데이터 재정의](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md)를 참조하세요.  
  
 등록 호출 하는 동안 종속성 속성에 대 한 속성 메타 데이터를 제공할 수 있습니다 (<xref:System.Windows.DependencyProperty.Register%2A>). 그러나 대부분의 경우 해당 종속성 속성을 상속하는 클래스에 대해 형식별 메타데이터를 제공하려고 합니다. 호출 하 여이 작업을 수행할 수는 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 메서드.  예제를 보려면는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], <xref:System.Windows.FrameworkElement> 클래스는 먼저을 등록 하는 형식을 <xref:System.Windows.UIElement.Focusable%2A> 종속성 속성입니다. 하지만 <xref:System.Windows.Controls.Control> 클래스는 코드를 자체 초기 기본 값을 제공 하는 종속성 속성에 대 한 메타 데이터 재정의 `false` 를 `true`, 하 여 원래 <xref:System.Windows.UIElement.Focusable%2A> 구현 합니다.  
  
 메타데이터를 재정의하는 경우 서로 다른 메타데이터 특성이 병합되거나 대체됩니다.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 병합 됩니다. 새 추가 하는 경우 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, 해당 콜백 메타 데이터에 저장 됩니다. 지정 하지 않는 경우는 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 재정의 값에 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 메타 데이터에 지정 하는 가장 가까운 상위 항목에서 참조로 승격 됩니다.  
  
-   에 대 한 실제 속성 시스템 동작 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 계층의 모든 메타 데이터 소유자에 대 한 구현을 유지 되며 가장 많이 파생 된 클래스의 콜백이 먼저 호출 된 속성 시스템에 의해 실행 순서 대로 테이블에 추가 됩니다.  
  
-   <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 대체 됩니다. 지정 하지 않는 경우는 <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 재정의 값에 <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 메타 데이터에 지정 하는 가장 가까운 상위 항목에서 제공 합니다.  
  
-   <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 구현이 바뀝니다. 새 추가 하는 경우 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, 해당 콜백 메타 데이터에 저장 됩니다. 지정 하지 않는 경우는 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 재정의 값에 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 메타 데이터에 지정 하는 가장 가까운 상위 항목에서 참조로 승격 됩니다.  
  
-   속성 시스템 동작은는 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 즉시 메타 데이터에 호출 됩니다. 다른에 참조가 없는 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 구현 계층 구조에서 유지 됩니다.  
  
 이 동작을 구현 하 여 <xref:System.Windows.PropertyMetadata.Merge%2A>, 파생 된 메타 데이터 클래스에서 재정의 될 수 있습니다.  
  
#### <a name="overriding-attached-property-metadata"></a>연결된 속성 메타데이터 재정의  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 연결된 속성은 종속성 속성으로 구현됩니다. 즉, 이러한 속성에는 개별 클래스에서 재정의할 수 있는 속성 메타데이터도 있습니다. 에 연결된 된 속성에 대 한 범위 지정 고려 사항 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 는 일반적으로 모든 <xref:System.Windows.DependencyObject> 설정 하는 연결된 된 속성을 가질 수 있습니다. 따라서 <xref:System.Windows.DependencyObject> 파생된 클래스 클래스의 인스턴스에서 설정할 수 있는 연결 된 속성에 대 한 메타 데이터를 재정의할 수 있습니다. 기본값, 콜백 또는 WPF 프레임워크 수준 특성 보고 속성을 재정의할 수 있습니다. 연결된 속성이 클래스의 인스턴스에서 설정된 경우 해당 속성 메타데이터 재정의 특성이 적용됩니다. 예를 들어 재정의 값이 클래스의 인스턴스에서 연결된 속성의 값으로 보고되도록 속성이 다르게 설정되지 않을 때마다 기본값을 재정의할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> 속성은 연결 된 속성의 관련이 없습니다.  
  
<a name="dp_add_owner"></a>   
### <a name="adding-a-class-as-an-owner-of-an-existing-dependency-property"></a>기존 종속성 속성의 소유자로 클래스 추가  
 클래스를 사용 하 여 이미 등록 되어 있는 종속성 속성의 소유자로 추가할 수는 <xref:System.Windows.DependencyProperty.AddOwner%2A> 메서드. 이렇게 하면 클래스에서 처음에 다른 형식으로 등록된 종속성 속성을 사용할 수 있습니다. 일반적으로 추가하는 클래스는 해당 종속성 속성을 소유자로 처음 등록한 형식의 파생 클래스가 아닙니다. 효과적으로 이렇게 하면 동일한 실제 클래스 계층 구조에 원래 소유자 클래스와 추가하는 클래스가 없어도 클래스와 해당 파생 클래스에서 종속성 속성 구현을 "상속"할 수 있습니다. 또한 추가하는 클래스와 모든 파생 클래스도 원래 종속성 속성에 대해 형식별 메타데이터를 제공할 수 있습니다.  
  
 추가하는 클래스는 코드와 태그에 모두 노출하여 종속성 속성을 속성 시스템의 전체 참가자로 만들려면 속성 시스템 유틸리티 메서드를 통해 자신을 소유자로 추가할 뿐만 아니라 클래스 자체에 추가 public 멤버를 선언해야 합니다. 새 사용자 지정 종속성 속성을 정의하는 클래스와 마찬가지로 기존 종속성 속성을 추가하는 클래스는 해당 종속성 속성에 대한 개체 모델을 노출하는 한 동일한 책임이 있습니다. 첫 번째로 노출할 멤버는 종속성 속성 식별자 필드입니다. 이 필드는 `public static readonly` 형식의 필드 <xref:System.Windows.DependencyProperty>의 반환 값에 할당 되는 <xref:System.Windows.DependencyProperty.AddOwner%2A> 호출 합니다. 두 번째로 정의할 멤버는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] "래퍼" 속성입니다. 래퍼를 사용 하면 코드에서 종속성 속성을 조작 하는 것이 더 편리 (호출 하지 마십시오. <xref:System.Windows.DependencyObject.SetValue%2A> 시간, 각 및 래퍼 자체에서 해당 호출을 한 번만 가능). 래퍼는 사용자 지정 종속성 속성을 등록할 때의 구현 방법과 동일하게 구현됩니다. 종속성 속성 구현에 대한 자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) 및 [종속성 속성의 소유자 형식 추가](../../../../docs/framework/wpf/advanced/how-to-add-an-owner-type-for-a-dependency-property.md)를 참조하세요.  
  
#### <a name="addowner-and-attached-properties"></a>AddOwner 및 연결된 속성  
 호출할 수 있습니다 <xref:System.Windows.DependencyProperty.AddOwner%2A> 소유자 클래스에 의해 연결된 된 속성으로 정의 된 종속성 속성에 대 한 합니다. 일반적으로 이 작업은 이전에 연결된 속성을 연결되지 않은 종속성 속성으로 노출하기 위해 수행합니다. 그런 다음 제공 됩니다는 <xref:System.Windows.DependencyProperty.AddOwner%2A> 반환 값으로는 `public static readonly` 종속성 속성의 식별자로 사용 하기 위해 필드 및 속성 멤버 테이블에 표시 되 고 연결 되지 않은 속성을 원하는 수 있도록 적절 한 "래퍼" 속성을 정의 클래스에서 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.PropertyMetadata>  
 <xref:System.Windows.DependencyObject>  
 <xref:System.Windows.DependencyProperty>  
 <xref:System.Windows.DependencyProperty.GetMetadata%2A>  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [프레임워크 속성 메타데이터](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)
