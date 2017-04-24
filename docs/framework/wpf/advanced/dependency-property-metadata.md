---
title: "종속성 속성 메타데이터 | Microsoft Docs"
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
  - "API, 메타데이터"
  - "종속성 속성, 메타데이터"
  - "메타데이터, 종속성 속성에 대해"
  - "메타데이터 재정의"
ms.assetid: d01ed009-b722-41bf-b82f-fe1a8cdc50dd
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# 종속성 속성 메타데이터
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템에는 리플렉션이나 일반적인 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 특성을 통해 속성에 대해 보고할 수 있는 것보다 많은 정보를 제공하는 메타데이터 보고 시스템이 있습니다.  [종속성 속성](GTMT)의 메타데이터는 [종속성 속성](GTMT)을 정의하는 클래스를 통해 고유하게 할당할 수 있으며, [종속성 속성](GTMT)을 다른 클래스에 추가할 때 변경할 수 있고, 속성을 정의하는 기본 클래스에서 [종속성 속성](GTMT)을 상속하는 모든 파생 클래스를 통해 재정의할 수 있습니다.  
  
   
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스의 기존 종속성 속성 사용자의 관점에서 종속성 속성을 이해하고 있으며 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 읽었다고 가정합니다.  이 항목의 예제를 실행하려면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 이해하고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 작성 방법을 알고 있어야 합니다.  
  
<a name="dp_metadata_contents"></a>   
## 종속성 속성 메타데이터 사용 방법  
 종속성 속성 메타데이터는 종속성 속성의 특성을 검사하기 위해 쿼리할 수 있는 개체 형식으로 존재합니다.  또한 이러한 메타데이터는 속성 시스템에서 특정 종속성 속성을 처리할 때 속성 시스템에 의해 자주 액세스됩니다.  종속성 속성의 메타데이터 개체는 다음과 같은 형식의 정보를 포함할 수 있습니다.  
  
-   종속성 속성의 기본값\(로컬 값, 스타일, 상속 등을 통해 종속성 속성의 다른 값을 결정할 수 없는 경우\).  종속성 속성의 값을 할당할 때 속성 시스템에서 기본값에 적용하는 우선 순위에 대한 자세한 내용은 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)를 참조하십시오.  
  
-   소유자 형식별 강제 변환 또는 변경 알림 동작에 영향을 주는 콜백 구현에 대한 참조.  이러한 콜백은 주로 비공용 액세스 수준으로 정의되기 때문에 허용된 액세스 범위에 포함된 참조만 실제로 메타데이터에서 참조할 수 있습니다.  종속성 속성 콜백에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)를 참조하십시오.  
  
-   종속성 속성이 [WPF 프레임워크 수준](GTMT) 속성인 경우에는 [WPF 프레임워크 수준](GTMT) 레이아웃 엔진 및 속성 상속 논리와 같은 서비스에 대한 정보와 상태를 보고하는 [WPF 프레임워크 수준](GTMT) 종속성 속성 특성이 메타데이터에 포함될 수 있습니다.  종속성 속성 메타데이터의 이러한 측면에 대한 자세한 내용은 [프레임워크 속성 메타데이터](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)를 참조하십시오.  
  
<a name="APIs"></a>   
## 메타데이터 API  
 속성 시스템에서 사용하는 대부분의 메타데이터 정보는 <xref:System.Windows.PropertyMetadata> 클래스 형식을 통해 보고됩니다.  메타데이터 인스턴스는 속성 시스템에 종속성 속성을 등록할 때 선택적으로 지정할 수 있으며, 기본 클래스 종속성 속성 정의에서 상속한 메타데이터를 재정의하거나 자신을 소유자로 추가하는 다른 형식에 대해 다시 지정할 수 있습니다.  속성을 등록할 때 메타데이터를 지정하지 않으면 해당 클래스의 기본값을 사용하여 기본 <xref:System.Windows.PropertyMetadata>가 생성됩니다. 등록된 메타데이터는 <xref:System.Windows.DependencyObject> 인스턴스의 종속성 속성에서 메타데이터를 가져오는 다양한 <xref:System.Windows.DependencyProperty.GetMetadata%2A> 오버로드를 호출할 때 <xref:System.Windows.PropertyMetadata>로 반환됩니다.  
  
 그런 다음 [WPF 프레임워크 수준](GTMT) 클래스와 같은 세부 아키텍처에 사용할 구체적인 메타데이터를 제공하기 위해 기본 <xref:System.Windows.PropertyMetadata> 클래스에서 다른 클래스가 파생됩니다.  예를 들어 <xref:System.Windows.UIPropertyMetadata>는 애니메이션 보고를 추가하고, <xref:System.Windows.FrameworkPropertyMetadata>는 이전 단원에서 설명한 [WPF 프레임워크 수준](GTMT) 속성을 제공합니다.  종속성 속성은 다음과 같은 <xref:System.Windows.PropertyMetadata> 파생 클래스에 등록할 수 있습니다.  메타데이터를 검사할 때는 기본 <xref:System.Windows.PropertyMetadata> 형식을 파생된 클래스에 캐스팅하여 보다 구체적인 속성을 검사할 수 있습니다.  
  
> [!NOTE]
>  이 문서에서는 <xref:System.Windows.FrameworkPropertyMetadata>에 지정할 수 있는 속성 특성을 "플래그"라고도 합니다.  종속성 속성을 등록하거나 메타데이터를 재정의하는 데 사용할 새 메타데이터 인스턴스를 만들 때는 플래그 열거형 <xref:System.Windows.FrameworkPropertyMetadataOptions>를 사용하여 이러한 값을 지정한 다음 열거형의 연결된 값을 <xref:System.Windows.FrameworkPropertyMetadata> 생성자에 제공합니다.  그러나 이렇게 만든 옵션 특성은 <xref:System.Windows.FrameworkPropertyMetadata> 안에 생성 열거형 값이 아니라 일련의 부울 속성으로 노출됩니다.  부울 속성을 사용하면 플래그 열거형 값에 마스크를 적용할 필요 없이 각 조건을 확인하여 원하는 정보를 가져올 수 있습니다.  생성자는 생성자 시그니처를 적절한 길이로 유지하기 위해 연결된 <xref:System.Windows.FrameworkPropertyMetadataOptions>를 사용하지만 생성된 실제 메타데이터는 메타데이터를 더 쉽게 쿼리할 수 있도록 각 속성을 개별적으로 노출합니다.  
  
<a name="override_or_subclass"></a>   
## 메타데이터 재정의 및 클래스 파생 시기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템에서는 종속성 속성 전체를 다시 구현하지 않고도 종속성 속성의 일부 특성을 변경할 수 있는 기능을 제공합니다.  이 기능은 특정 형식의 종속성 속성에 대해 서로 다른 속성 메타데이터 인스턴스를 생성하여 구현됩니다.  대부분의 기존 종속성 속성은 가상 속성이 아니므로 엄밀하게 말하자면 상속된 클래스에서 종속성 속성을 "다시 구현"하려면 기존 멤버를 숨기는 방법밖에 없습니다.  
  
 기존 종속성 속성의 특성을 수정하여 특정 형식의 종속성 속성을 구현할 수 없는 경우에는 파생 클래스를 만든 후 이 클래스에 사용자 지정 종속성 속성을 선언해야 할 수 있습니다.  사용자 지정 종속성 속성은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]에 정의된 종속성 속성과 동일하게 동작합니다.  사용자 지정 종속성 속성에 대한 자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 참조하십시오.  
  
 종속성 속성에서 재정의할 수 없는 한 가지 중요한 특성은 해당 값 형식입니다.  상속하려는 종속성 속성이 필요한 동작을 수행하지만 형식이 맞지 않는 경우에는 사용자 지정 종속성 속성을 구현한 후 형식 변환 또는 사용자 지정 클래스에 대한 다른 구현을 통해 속성을 연결해야 할 수 있습니다.  기존 <xref:System.Windows.ValidateValueCallback>은 메타데이터가 아니라 등록 필드 자체에 존재하기 때문에 이 콜백도 바꿀 수 없습니다.  
  
<a name="scenarios"></a>   
## 기존 메타데이터 변경 시나리오  
 기존 종속성 속성의 메타데이터로 작업할 때 종속성 속성의 메타데이터를 변경하는 가장 일반적인 방법은 기본값을 변경하는 것입니다.  속성 시스템 콜백을 변경하거나 추가하는 방법은 고급 시나리오에 해당합니다.  이러한 고급 작업은 파생 클래스 구현에서 종속성 속성 간 관계가 서로 다른 경우에 수행하는 것이 좋습니다.  코드와 선언 모두를 지원하는 프로그래밍 모델을 구현하기 위한 조건 중 하나는 순서에 관계없이 속성을 설정할 수 있어야 한다는 것입니다.  즉, 모든 종속성 속성은 컨텍스트에 상관없이 just\-in\-time 방식으로 설정해야 하며 생성자에서의 일반적인 경우와 달리 설정 순서 정보에 의존할 수 없습니다.  속성 시스템의 이러한 측면에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)를 참조하십시오.  참고로 유효성 검사 콜백은 메타데이터의 일부가 아니라 종속성 속성 식별자의 일부이므로  유효성 검사 콜백은 메타데이터를 재정의하여 변경할 수 없습니다.  
  
 기존 종속성 속성에서 [WPF 프레임워크 수준](GTMT) 속성 메타데이터 옵션을 변경해야 하는 경우도 있습니다.  이러한 옵션은 [WPF 프레임워크 수준](GTMT) 속성에 대한 알려진 조건 일부를 레이아웃 시스템 같은 다른 [WPF 프레임워크 수준](GTMT) 프로세스와 통신합니다.  일반적으로 옵션은 새 종속성 속성을 등록할 때만 설정하지만 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 또는 <xref:System.Windows.DependencyProperty.AddOwner%2A> 호출에서 [WPF 프레임워크 수준](GTMT) 속성 메타데이터를 변경할 수도 있습니다.  사용할 구체적인 값 및 자세한 내용은 [프레임워크 속성 메타데이터](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)를 참조하십시오.  새로 등록하는 종속성 속성에 대해 이러한 옵션을 설정하는 방법에 대한 자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 참조하십시오.  
  
<a name="dp_override_metadata"></a>   
### 메타데이터 재정의  
 메타데이터를 재정의하는 가장 기본적인 목적은 메타데이터에서 파생되어 현재 형식의 종속성 속성에 적용된 다양한 동작을 변경하는 것입니다.  자세한 내용은 [메타데이터](#dp_metadata_contents) 단원에서 설명합니다.  자세한 내용 및 코드 예제를 보려면 [종속성 속성의 메타데이터 재정의](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md)를 참조하십시오.  
  
 속성 메타데이터는 등록 호출\(<xref:System.Windows.DependencyProperty.Register%2A>\) 시 종속성 속성에 대해 제공할 수 있습니다.  그러나 일반적으로는 클래스가 종속성 속성을 상속할 때 형식별 메타데이터를 제공하는 것이 좋습니다.  이 작업은 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 메서드를 호출하여 수행할 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]에서 예를 들자면 <xref:System.Windows.FrameworkElement> 클래스는 <xref:System.Windows.UIElement.Focusable%2A> 종속성 속성을 가장 처음 등록하는 형식입니다.  그러나 <xref:System.Windows.Controls.Control> 클래스는 이 종속성 속성의 값을 `false`에서 `true`로 변경하여 메타데이터를 재정의함으로써 고유한 초기 기본값을 지정합니다. 그 외의 클래스는 원래 구현된 <xref:System.Windows.UIElement.Focusable%2A>을 재사용합니다.  
  
 메타데이터를 재정의하면 여러 메타데이터 특성이 병합되거나 바뀝니다.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>이 병합됩니다.  새 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>을 추가하면 해당 콜백이 메타데이터에 저장됩니다.  재정의에 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>을 지정하지 않으면 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>의 값이 메타데이터에서 해당 값을 지정한 가장 가까운 상위에서의 참조로 승격됩니다.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>에 대한 실제 속성 시스템 동작은 계층 구조의 모든 메타데이터 소유자에 대한 구현이 가장 깊게 파생된 클래스의 콜백이 먼저 호출되는 속성 시스템 실행 순서대로 테이블에 유지되고 추가되는 것입니다.  
  
-   <xref:System.Windows.PropertyMetadata.DefaultValue%2A>가 바뀝니다.  재정의에 <xref:System.Windows.PropertyMetadata.DefaultValue%2A>을 지정하지 않으면 <xref:System.Windows.PropertyMetadata.DefaultValue%2A>의 값은 메타데이터에서 해당 값을 지정한 가장 가까운 상위에서 가져옵니다.  
  
-   <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 구현이 바뀝니다.  새 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>을 추가하면 해당 콜백이 메타데이터에 저장됩니다.  재정의에 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>을 지정하지 않으면 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>의 값이 메타데이터에서 해당 값을 지정한 가장 가까운 상위에서의 참조로 승격됩니다.  
  
-   속성 시스템 동작은 직접적인 메타데이터의 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>만 호출되는 방식으로 수행됩니다.  계층 구조의 다른 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 구현에 대한 참조는 유지되지 않습니다.  
  
 이 동작은 <xref:System.Windows.PropertyMetadata.Merge%2A>에 의해 구현되며 파생된 메타데이터 클래스에서 재정의될 수 있습니다.  
  
#### 연결된 속성 메타데이터 재정의  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 [연결된 속성](GTMT)은 종속성 속성으로 구현됩니다.  이는 연결된 속성에도 개별 클래스에서 재정의할 수 있는 속성 메타데이터가 있음을 의미합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 연결된 속성의 범위를 지정할 때는 일반적으로 모든 <xref:System.Windows.DependencyObject>에 연결된 속성을 설정할 수 있다는 사실을 고려해야 합니다.  따라서 <xref:System.Windows.DependencyObject>에서 파생된 모든 클래스는 클래스의 인스턴스에 설정되어 있는 연결된 속성의 메타데이터를 재정의할 수 있습니다.  예를 들면 기본값, 콜백 또는 [WPF 프레임워크 수준](GTMT) 특성 보고 속성을 재정의할 수 있습니다.  연결된 속성이 클래스의 인스턴스에 설정되어 있으면 해당 재정의 속성 메타데이터 특성이 적용됩니다.  예를 들어 속성을 설정하지 않은 경우에는 클래스의 인스턴스에서 재정의 값이 연결된 속성의 값으로 보고되도록 기본값을 재정의할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> 속성은 연결된 속성에 사용하는 데는 적합하지 않습니다.  
  
<a name="dp_add_owner"></a>   
### 클래스를 기존 종속성 속성의 소유자로 추가  
 클래스는 <xref:System.Windows.DependencyProperty.AddOwner%2A> 메서드를 사용하여 이미 등록되어 있는 종속성 속성의 소유자로 자체 추가될 수 있습니다.  이렇게 하면 클래스에서는 원래 다른 형식에 대해 등록된 종속성 속성을 사용할 수 있습니다.  이 경우 추가된 클래스는 대개 종속성 속성의 소유자로 처음 등록된 형식에서 파생된 클래스가 아닙니다.  이렇게 하면 원래 소유자 클래스와 추가되는 클래스가 실제로 같은 클래스 계층 구조에 있지 않아도 클래스와 해당 클래스에서 파생된 클래스가 [종속성 속성](GTMT) 구현을 "상속"할 수 있습니다.  또한 추가되는 클래스 및 이 클래스에서 파생되는 모든 클래스는 원래 종속성 속성에 대한 형식별 메타데이터를 제공할 수 있습니다.  
  
 추가되는 클래스는 속성 시스템 유틸리티 메서드를 통해 자신을 소유자로 추가해야 할 뿐만 아니라 [종속성 속성](GTMT)을 속성 시스템에서 활용하고 코드와 태그 모두에 노출할 수 있도록 몇 가지 추가적인 공용 멤버를 자체적으로 선언해야 합니다.  기존 종속성 속성을 추가하는 클래스는 종속성 속성의 개체 모델을 노출하는 것과 관련하여 새 사용자 지정 종속성 속성을 정의하는 클래스와 동일한 작업을 수행합니다.  먼저 종속성 속성 식별자 필드를 노출합니다.  이 필드는 <xref:System.Windows.DependencyProperty.AddOwner%2A> 호출의 반환 값에 할당되는 <xref:System.Windows.DependencyProperty> 형식의 `public static readonly` 필드여야 합니다.  그런 다음 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] "래퍼" 속성을 정의합니다.  래퍼를 사용하면 <xref:System.Windows.DependencyObject.SetValue%2A>를 매번 호출할 필요 없이 래퍼 자체에서 한 번만 호출하면 되기 때문에 코드에서 종속성 속성을 보다 편리하게 조작할 수 있습니다.  래퍼는 사용자 지정 [종속성 속성](GTMT)을 등록할 때와 동일한 방법으로 구현됩니다.  [종속성 속성](GTMT)을 구현하는 방법에 대한 자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) 및 [종속성 속성의 소유자 형식 추가](../../../../docs/framework/wpf/advanced/how-to-add-an-owner-type-for-a-dependency-property.md)를 참조하십시오.  
  
#### AddOwner 및 연결된 속성  
 소유자 클래스에 의해 연결된 속성으로 정의된 종속성 속성에 대해 <xref:System.Windows.DependencyProperty.AddOwner%2A>를 호출할 수 있습니다.  일반적으로 이 방법은 연결된 속성을 연결되지 않은 종속성 속성으로 노출하기 위해 사용합니다.  그런 다음 <xref:System.Windows.DependencyProperty.AddOwner%2A> 반환 값을 `public static readonly` 필드로 노출하여 종속성 속성 식별자로 사용하고, 속성이 멤버 테이블에 표시되고 클래스에서 연결되지 않은 속성을 사용할 수 있도록 적절한 "래퍼" 속성을 정의합니다.  
  
## 참고 항목  
 <xref:System.Windows.PropertyMetadata>   
 <xref:System.Windows.DependencyObject>   
 <xref:System.Windows.DependencyProperty>   
 <xref:System.Windows.DependencyProperty.GetMetadata%2A>   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [프레임워크 속성 메타데이터](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)