---
title: "사용자 지정 종속성 속성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- implementing [WPF], wrappers
- registering properties [WPF]
- properties [WPF], metadata
- metadata [WPF], for properties
- custom dependency properties [WPF]
- properties [WPF], registering
- wrappers [WPF], implementing
- dependency properties [WPF], custom
ms.assetid: e6bfcfac-b10d-4f58-9f77-a864c2a2938f
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 588ab00d61a701dc43e2af5978a6023a93f367f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="custom-dependency-properties"></a>사용자 지정 종속성 속성
이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램 개발자와 구성 요소 작성자가 사용자 지정 종속성 속성을 만들려고 하는 이유와 구현 단계 및 속성의 성능, 유용성 또는 유연성을 향상시킬 수 있는 일부 구현 옵션에 대해 설명합니다.  
  

  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스에서 기존 종속성 속성의 소비자 관점에서 종속성 속성을 이해하고 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) 항목을 읽었다고 가정합니다. 이 항목의 예제를 따르려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 이해하고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 작성하는 방법도 알아야 합니다.  
  
<a name="whatis"></a>   
## <a name="what-is-a-dependency-property"></a>종속성 속성이란?  
 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성을 종속성 속성으로 구현하여 스타일 지정, 데이터 바인딩, 애니메이션 및 기본값을 지원하도록 할 수 있습니다. 종속성 속성은 등록 된 속성의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 호출 하 여 속성 시스템의 <xref:System.Windows.DependencyProperty.Register%2A> 메서드 (또는 <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>), 뒷받침 하 고는 <xref:System.Windows.DependencyProperty> 식별자 필드입니다. 종속성 속성을 에서만 사용할 수 있습니다. <xref:System.Windows.DependencyObject> 형식, 하지만 <xref:System.Windows.DependencyObject> 에서 매우 높은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스 계층 구조, 대부분의 클래스에서 사용할 수 있도록 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 종속성 속성을 지원할 수 있습니다. 종속성 속성 및 이 [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]에서 종속성 속성을 설명하는 데 사용된 일부 용어 및 규칙에 대한 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하세요.  
  
<a name="example_dp"></a>   
## <a name="examples-of-dependency-properties"></a>종속성 속성의 예  
 구현 되는 종속성 속성의 예로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스에는 <xref:System.Windows.Controls.Control.Background%2A> 속성을는 <xref:System.Windows.FrameworkElement.Width%2A> 속성, 및 <xref:System.Windows.Controls.TextBox.Text%2A> 다양 한 기타 속성입니다. 클래스에 의해 노출 된 각 종속성 속성에는 해당 공용 정적 필드 형식의 <xref:System.Windows.DependencyProperty> 는 동일한 클래스에 노출 합니다. 이는 종속성 속성의 식별자입니다. 식별자는 규칙을 사용하여 이름이 지정됩니다. 종속성 속성의 이름에는 문자열 `Property`가 추가됩니다. 해당 예를 들어 <xref:System.Windows.DependencyProperty> 에 대 한 식별자 필드는 <xref:System.Windows.Controls.Control.Background%2A> 속성은 <xref:System.Windows.Controls.Control.BackgroundProperty>합니다. 식별자에는 등록 된와 같은 종속성 속성을 포함 하는 다른 작업에는 식별자가 나중에 사용 됩니다 종속성 속성에 대 한 정보를 저장 <xref:System.Windows.DependencyObject.SetValue%2A>합니다.  
  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)에서 언급했듯이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 모든 종속성 속성(대부분의 연결된 속성 제외)은 "래퍼" 구현으로 인해 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성이기도 합니다. 따라서 코드에서 다른 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성을 사용하는 것과 같은 방식으로 래퍼를 정의하는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 접근자를 호출하여 종속성 속성을 가져오거나 설정할 수 있습니다. 설정 된 종속성 속성의 소비자로 사용 하지 않으면 일반적으로 <xref:System.Windows.DependencyObject> 메서드 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A>, 하는 속성 시스템에서 연결 지점입니다. 대신, 기존 구현을 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성 호출 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 내에서 `get` 및 `set` 래퍼 식별자 필드를 적절 하 게 사용 하 여 속성을 구현 . 사용자 지정 종속성 속성을 직접 구현하는 경우 유사한 방법으로 래퍼를 정의하게 됩니다.  
  
<a name="backing_with_dp"></a>   
## <a name="when-should-you-implement-a-dependency-property"></a>종속성 속성의 구현 시기  
 구현 하는 경우 속성을 클래스에서 클래스에서 파생으로 <xref:System.Windows.DependencyObject>, 사용 하 여 속성을 백업 하는 옵션이 있습니다는 <xref:System.Windows.DependencyProperty> 식별자 이므로 하는 종속성 속성을 만듭니다. 속성을 종속성 속성으로 만드는 것이 항상 필요하거나 적절한 것은 아니며 시나리오 요구에 따라 달라집니다. 때로는 개인 필드로 속성을 지원하는 일반적인 기술이 적합합니다. 그러나 속성에서 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능 중 하나 이상을 지원하기를 원할 때마다 속성을 종속성 속성으로 구현해야 합니다.  
  
-   스타일에 속성을 설정하려고 합니다. 자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하세요.  
  
-   속성에서 데이터 바인딩을 지원하게 하려고 합니다. 데이터 바인딩 종속성 속성에 대한 자세한 내용은 [두 컨트롤의 속성 바인딩](../../../../docs/framework/wpf/data/how-to-bind-the-properties-of-two-controls.md)을 참조하세요.  
  
-   동적 리소스 참조를 사용하여 속성을 설정하려고 합니다. 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하세요.  
  
-   요소 트리의 부모 요소에서 속성 값을 자동으로 상속받도록 하려고 합니다. 이 경우 등록은 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 메서드, 속성에 대 한 래퍼를 만들 수도 있는 경우에 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 액세스 합니다. 자세한 내용은 [속성 값 상속](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)을 참조하세요.  
  
-   속성에 애니메이션 효과를 주려고 합니다. 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하세요.  
  
-   속성 시스템, 환경 또는 사용자가 수행한 작업을 통해 또는 스타일을 읽고 사용하여 이전 속성 값이 변경되었을 때 속성 시스템에서 보고하도록 하려고 합니다. 속성 메타데이터를 사용하여 속성 시스템에서 속성 값이 명확하게 변경되었다는 것을 확인할 때마다 호출되는 콜백 메서드를 속성이 지정할 수 있습니다. 관련 개념은 속성 값 강제 변환입니다. 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)를 참조하세요.  
  
-   속성 값 변경 시 레이아웃 시스템에서 요소의 시각적 개체를 재구성해야 하는지 여부를 보고하는 것과 같이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로세스에서도 사용되는 설정된 메타데이터 규칙을 사용하려고 합니다. 또는 파생 클래스가 기본값과 같은 메타데이터 기반 특성을 변경할 수 있도록 메타데이터 재정의를 사용할 수 있도록 하려고 합니다.  
  
-   사용자 지정 컨트롤 속성이 **속성** 창 편집과 같은 [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] 지원을 받도록 하려고 합니다. 자세한 내용은 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하십시오.  
  
 이러한 시나리오를 검토할 때는 완전히 새로운 속성을 구현하는 대신 기존 종속성 속성의 메타데이터를 재정의하여 시나리오를 얻을 수 있는지 여부도 고려해야 합니다. 메타데이터 재정의가 실용적인지 여부는 시나리오 유형과 해당 시나리오가 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 종속성 속성 및 클래스의 구현과 얼마나 유사한지에 따라 다릅니다. 기존 속성에서 메타데이터 재정의에 대한 자세한 내용은 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)를 참조하세요.  
  
<a name="checklist"></a>   
## <a name="checklist-for-defining-a-dependency-property"></a>종속성 속성 정의를 위한 검사 목록  
 종속성 속성 정의는 4가지 고유한 개념으로 구성됩니다. 이러한 개념은 반드시 엄격한 절차적 단계는 아니며, 그중 일부는 구현 시 단일 코드 줄로 결합됩니다.  
  
-   (선택 사항) 종속성 속성의 속성 메타데이터를 만듭니다.  
  
-   속성 시스템에 속성 이름을 등록하여 소유자 유형과 속성 값의 유형을 지정합니다. 또한 사용되는 경우 속성 메타데이터를 지정합니다.  
  
-   정의 <xref:System.Windows.DependencyProperty> 식별자로는 `public` `static` `readonly` 필드에 소유자 유형입니다.  
  
-   이름이 종속성 속성의 이름과 일치하는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] "래퍼" 속성을 정의합니다. [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] "래퍼" 속성의 `get` 및 `set` 접근자는 해당 속성을 지원하는 종속성 속성과 연결하도록 구현합니다.  
  
<a name="registering"></a>   
### <a name="registering-the-property-with-the-property-system"></a>속성 시스템에 속성 등록  
 속성이 종속성 속성이 되게 하려면 속성 시스템에서 유지하는 테이블에 해당 속성을 등록한 다음 나중에 속성 시스템 작업의 한정자로 사용되는 고유 식별자를 지정해야 합니다. 이러한 작업은 내부 작업이거나 속성 시스템 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 호출하는 자체 코드일 수 있습니다. 속성을 등록 하려면 호출는 <xref:System.Windows.DependencyProperty.Register%2A> 클래스 (클래스, 하지만 다른 모든 멤버 정의 외부)의 본문 내 합니다. 식별자 필드 여도 제공 됩니다는 <xref:System.Windows.DependencyProperty.Register%2A> 메서드 호출의 반환 값입니다. 이유는는 <xref:System.Windows.DependencyProperty.Register%2A> 호출이 완료 될 다른 멤버 외부 정의 할당을 만들려면이 반환 값을 사용 하기 때문에 `public` `static` `readonly` 형식의 필드 <xref:System.Windows.DependencyProperty> 클래스의 일환으로 합니다. 이 필드는 종속성 속성의 식별자가 됩니다.  
  
 [!code-csharp[WPFAquariumSln#RegisterAG](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
 [!code-vb[WPFAquariumSln#RegisterAG](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]  
  
<a name="nameconventions"></a>   
### <a name="dependency-property-name-conventions"></a>종속성 속성 이름 규칙  
 예외적인 상황을 제외하고 모든 상황에서 따라야 하는 종속성 속성과 관련하여 설정된 명명 규칙이 있습니다.  
  
 종속성 속성 자체의 첫 번째 매개 변수로 제공 된이 예제와 같이 "AquariumGraphic" 이라는 기본 이름이 갖습니다 <xref:System.Windows.DependencyProperty.Register%2A>합니다. 그 이름은 각 등록 형식 내에서 고유해야 합니다. 기본 형식을 통해 상속된 종속성 속성은 이미 등록 형식의 일부로 간주되어 상속된 속성의 이름을 다시 등록할 수 없습니다. 그러나 종속성 속성이 상속되지 않는 경우에도 클래스를 종속성 속성의 소유자로 추가하는 기술이 있습니다. 자세한 내용은 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)를 참조하세요.  
  
 식별자 필드를 만들 때 이 필드의 이름을 등록할 때의 속성 이름과 접미사 `Property`로 지정합니다. 이 필드는 종속성 속성의 식별자 이며 나중에 대 한 입력으로 사용 되는 <xref:System.Windows.DependencyObject.SetValue%2A> 및 <xref:System.Windows.DependencyObject.GetValue%2A> 호출 하면이 실현 된다 코드 액세스 사용자 고유의 코드에서 속성에는 외부 코드 액세스 하 여 여 래퍼에 허용 를 속성 시스템에 의해 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서.  
  
> [!NOTE]
>  클래스 본문에서 종속성 속성을 정의하는 것이 일반적인 구현이지만 클래스 정적 생성자에서 종속성 속성을 정의할 수도 있습니다. 이 접근 방식은 종속성 속성을 초기화하기 위해 두 줄 이상의 코드가 필요한 경우에 유용할 수 있습니다.  
  
<a name="wrapper1"></a>   
### <a name="implementing-the-wrapper"></a>"래퍼" 구현  
 래퍼 구현을 호출 해야 <xref:System.Windows.DependencyObject.GetValue%2A> 에 `get` 구현 및 <xref:System.Windows.DependencyObject.SetValue%2A> 에 `set` 구현 (원래 등록 호출 및 필드는 표시 너무 명확성).  
  
 제외한 모든 예외적인 경우 래퍼 구현은 수행 해야는 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 작업을 각각. 그 이유는 [XAML로드 및 종속성 속성](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md) 항목에서 설명합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스에서 제공되는 모든 기존의 공용 종속성 속성은 이 간단한 래퍼 구현 모델을 사용합니다. 종속성 속성의 작동 방식의 대부분은 본질적으로 속성 시스템의 동작이거나 속성 메타데이터를 통한 속성 변경 콜백 또는 강제 변환과 같은 다른 개념을 통해 구현됩니다.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
 다시, 규칙에 따라 래퍼 속성의 이름이 동일 해야 선택 및의 첫 번째 매개 변수로 지정 된 이름으로는 <xref:System.Windows.DependencyProperty.Register%2A> 호출 속성을 등록 합니다. 속성이 규칙을 따르지 않는다고 해서 가능한 모든 용도에 사용하지 못한다는 것은 아니지만 몇 가지 주목할 만한 문제가 발생하게 됩니다.  
  
-   스타일과 템플릿의 특정 측면이 작동하지 않습니다.  
  
-   대부분의 도구와 디자이너는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 제대로 serialize하거나 속성별 수준에서 디자이너 환경 지원을 제공하기 위해 명명 규칙을 사용해야 합니다.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로더의 현재 구현은 래퍼를 완전히 무시하고 특성 값을 처리할 때 명명 규칙을 사용합니다. 자세한 내용은 [XAML로드 및 종속성 속성](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)을 참조하세요.  
  
<a name="metadata"></a>   
### <a name="property-metadata-for-a-new-dependency-property"></a>새 종속성 속성의 속성 메타데이터  
 종속성 속성을 등록할 때 속성 시스템을 통한 등록은 속성 특성을 저장하는 메타데이터 개체를 만듭니다. 이러한 특성 중 대부분에 속성의 간단한 서명을 사용 하 여 등록 하는 경우 설정 된 기본값이 있는 <xref:System.Windows.DependencyProperty.Register%2A>합니다. 다른 서명이 <xref:System.Windows.DependencyProperty.Register%2A> 원하는 대로 속성을 등록 하는 메타 데이터를 지정할 수 있습니다. 종속성 속성에 대해 지정된 가장 일반적인 메타데이터는 속성을 사용하는 새 인스턴스에 적용되는 기본값을 속성에 제공하는 것입니다.  
  
 파생된 클래스에 존재 하는 종속성 속성을 만드는 경우 <xref:System.Windows.FrameworkElement>, 더 특수 한 메타 데이터 클래스를 사용할 수 있습니다 <xref:System.Windows.FrameworkPropertyMetadata> 기본 대신 <xref:System.Windows.PropertyMetadata> 클래스입니다. 에 대 한 생성자는 <xref:System.Windows.FrameworkPropertyMetadata> 클래스 여러 개의 시그니처가 조합 하 여 다양 한 메타 데이터 특성을 지정할 수 있습니다. 형식의 단일 매개 변수를 사용 하는 서명을 사용 하 여 기본값만 지정 하려는 경우 <xref:System.Object>합니다. 개체 매개 변수 속성에 대 한 특정 형식의 기본 값으로 전달 (제공 되는 기본 값으로 제공 되는 형식 이어야 합니다는 `propertyType` 에서 매개 변수는 <xref:System.Windows.DependencyProperty.Register%2A> 호출).  
  
 에 대 한 <xref:System.Windows.FrameworkPropertyMetadata>, 프로그램 속성에 대 한 메타 데이터 옵션 플래그를 지정할 수도 있습니다. 이러한 플래그는 등록 후에 속성 메타데이터에서 불연속 속성으로 변환되며 특정 조건을 레이아웃 엔진과 같은 다른 프로세스와 통신하는 데 사용됩니다.  
  
#### <a name="setting-appropriate-metadata-flags"></a>적절한 메타데이터 플래그 설정  
  
-   속성 (또는 해당 값의 변경 사항이) 적용 하는 경우는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], 특히 영향을 줌 레이아웃 시스템 크기를 조정 하거나 페이지에서 요소를 렌더링 하는 방법 설정 플래그 중 하나 이상을: <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>, <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>, <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>합니다.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>이 속성에 대 한 변경에 대 한 변경 해야 함을 의미 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 를 포함 하는 개체 공간이 필요할 수 있습니다 더 많거나 적게 부모 내에서 렌더링 합니다. 예를 들어 "Width" 속성은 이 플래그를 설정해야 합니다.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>이 속성에 대 한 변경에 대 한 변경 해야 함을 의미 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 렌더링이에서 변경 된 전용된 공간 필요 하지 않지만 공간 내에서 위치 지정이 변경 되었음을 나타내는지 않습니다. 예를 들어 "Alignment" 속성은 이 플래그를 설정해야 합니다.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>나타냅니다 레이아웃 및 측정값에 영향을 주지 것입니다 되지만 다른 렌더링이 필요한 다른 변경 사항이 있는 발생 했습니다. 예를 들어 기존 요소의 색상을 변경하는 "Background"와 같은 속성이 있습니다.  
  
    -   이러한 플래그는 종종 속성 시스템 또는 레이아웃 콜백의 자체 재정의 구현에 대한 메타데이터의 프로토콜로 사용됩니다. 예를 들어, 할 수 있습니다는 <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> 호출 하는 콜백 <xref:System.Windows.UIElement.InvalidateArrange%2A> 인스턴스 속성 값 변경 사항을 보고 및 <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> 으로 `true` 는 메타 데이터에 있습니다.  
  
-   일부 속성은 위에 언급된 필수 크기의 변경 이상으로, 포함하는 부모 요소의 렌더링 특성에 영향을 줄 수 있습니다. 예로 <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A> 해당 속성에 대 한 변경 내용을 단락을 포함 하는 흐름 문서의의 전체 렌더링을 변경할 수 있는 흐름 문서 모델에서 사용 되는 속성입니다. 사용 하 여 <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentArrange> 또는 <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentMeasure> 사용자 고유의 속성에서 비슷한 경우를 파악할 수 있습니다.  
  
-   기본적으로 종속성 속성은 데이터 바인딩을 지원합니다. 데이터 바인딩에 대한 현실적인 시나리오가 없거나 큰 개체에 대한 데이터 바인딩의 성능이 문제로 인식되는 경우 데이터 바인딩을 의도적으로 사용하지 않도록 설정할 수 있습니다.  
  
-   기본적으로 데이터 바인딩 <xref:System.Windows.Data.Binding.Mode%2A> 종속성 속성이 기본적으로에 대 한 <xref:System.Windows.Data.BindingMode.OneWay>합니다. 바인딩의 언제 든 변경할 수 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩 인스턴스별로; 대 한 자세한 내용은 참조 [바인딩의 방향을 지정](../../../../docs/framework/wpf/data/how-to-specify-the-direction-of-the-binding.md)합니다. 종속성 속성 작성자는 속성 사용 하도록 선택할 수 있지만 <xref:System.Windows.Data.BindingMode.TwoWay> 기본적으로 바인딩 모드입니다. 기존 종속성 속성의 예로 <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=nameWithType>;은이 속성에 대 한 시나리오는 <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> 설정 논리와의 합성 <xref:System.Windows.Controls.MenuItem> 기본 테마 스타일와 상호 작용 합니다. <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> 속성 논리를 사용 하 여 데이터 바인딩을 고유 하 게 다른 상태 속성 및 메서드 호출에 따라에서 속성의 상태를 유지 합니다. 바인딩하는 다른 속성으로 <xref:System.Windows.Data.BindingMode.TwoWay> 은 기본적으로 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>합니다.  
  
-   설정 하 여 사용자 지정 종속성 속성의 속성 상속을 사용할 수도 있습니다는 <xref:System.Windows.FrameworkPropertyMetadataOptions.Inherits> 플래그입니다. 속성 상속은 부모 요소와 자식 요소가 공통된 속성을 갖는 시나리오에 유용하며 자식 요소가 해당 특정 속성 값을 부모가 설정한 값과 동일한 값으로 설정하는 것이 적합합니다. 예제에서는 상속 가능한 속성은 <xref:System.Windows.FrameworkElement.DataContext%2A>, 바인딩 데이터 표시에 대 한 중요 한 마스터-세부 정보 시나리오를 사용 하는 작업에 사용 됩니다. 함으로써 <xref:System.Windows.FrameworkElement.DataContext%2A> , 상속 가능한 모든 자식 요소는 데이터 컨텍스트를 상속도 합니다. 속성 값 상속으로 인해 페이지 또는 응용 프로그램 루트에서 데이터 컨텍스트를 지정할 수 있으며 가능한 모든 하위 요소의 바인딩에 대해 다시 지정할 필요가 없습니다. <xref:System.Windows.FrameworkElement.DataContext%2A>또한 상속 된 기본값을 무시 하지만 항상 설정할 수 있습니다 로컬로; 특정 자식 요소에 설명 하기 위해 좋은 예 자세한 내용은 참조 [마스터-세부 패턴을 사용 하 여 계층적 데이터로](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)합니다. 속성 값 상속을 사용하면 성능이 저하될 수 있으므로 꼭 필요할 때만 사용해야 합니다. 자세한 내용은 [속성 값 상속](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)을 참조하세요.  
  
-   설정의 <xref:System.Windows.FrameworkPropertyMetadataOptions.Journal> 종속성 속성을 검색 또는 탐색 저널링 services에서 사용 하는 경우를 나타내는 플래그입니다. 예로 <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A> 속성, 선택 영역에서 선택 된 항목이 저널링 기록을 탐색할 때 컨트롤을 유지 해야 합니다.  
  
<a name="RODP"></a>   
## <a name="read-only-dependency-properties"></a>읽기 전용 종속성 속성  
 읽기 전용인 종속성 속성을 정의할 수 있습니다. 그러나 속성을 읽기 전용으로 정의하는 이유에 대한 시나리오는 속성 시스템에 속성을 등록하고 식별자를 노출하는 절차와 약간 다릅니다. 자세한 내용은 [읽기 전용 종속성 속성](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)을 참조하세요.  
  
<a name="CTDP"></a>   
## <a name="collection-type-dependency-properties"></a>컬렉션 형식 종속성 속성  
 컬렉션 형식 종속성 속성에는 고려할 몇 가지 추가 구현의 문제점이 있습니다. 자세한 내용은 [컬렉션 형식 종속성 속성](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)을 참조하세요.  
  
<a name="SecurityC"></a>   
## <a name="dependency-property-security-considerations"></a>종속성 속성 보안 고려 사항  
 종속성 속성은 공용 속성으로 선언해야 합니다. 종속성 속성 식별자 필드는 공용 정적 필드로 선언해야 합니다. 다른 액세스 수준(예: 보호됨)을 선언하려고 시도하더라도 속성 시스템 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]와 함께 식별자를 통해 종속성 속성에 항상 액세스할 수 있습니다. 보호 된 식별자 필드도 되어이 잠재적으로 액세스할 수 있는 메타 데이터 보고 또는 값 결정 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 의 일부인 속성 시스템에 같은 <xref:System.Windows.LocalValueEnumerator>합니다. 자세한 내용은 [종속성 속성 보안](../../../../docs/framework/wpf/advanced/dependency-property-security.md)을 참조하세요.  
  
<a name="DPCtor"></a>   
## <a name="dependency-properties-and-class-constructors"></a>종속성 속성 및 클래스 생성자  
 클래스 생성자가 가상 ​​메서드를 호출해서는 안 되는 관리 코드 프로그래밍(종종 FxCop와 같은 코드 분석 도구로 시행)에 일반적인 원칙이 있습니다. 이는 생성자가 파생 클래스 생성자의 기본 초기화로 호출될 수 있고 생성자를 통한 가상 메서드 입력이 생성 중인 개체 인스턴스의 불완전 초기화 상태에서 발생할 수 있기 때문입니다. 이미에서 파생 되는 모든 클래스에서 파생 시키는 경우 <xref:System.Windows.DependencyObject>, 속성 시스템 자체를 호출 하 고 가상 메서드를 내부적으로 노출 알고 있어야 합니다. 이러한 가상 메서드는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템 서비스의 일부입니다. 메서드를 재정의하면 파생 클래스가 값 결정에 참여할 수 있습니다. 런타임 초기화 시 발생할 수 있는 문제를 방지하려면 매우 구체적인 생성자 패턴을 따라 클래스의 생성자 내에서 종속성 속성 값을 설정해야 합니다. 자세한 내용은 [DependencyObjects의 안전한 생성자 패턴](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [컬렉션 형식 종속성 속성](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)  
 [종속성 속성 보안](../../../../docs/framework/wpf/advanced/dependency-property-security.md)  
 [XAML 로드 및 종속성 속성](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)  
 [DependencyObjects의 안전한 생성자 패턴](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)
