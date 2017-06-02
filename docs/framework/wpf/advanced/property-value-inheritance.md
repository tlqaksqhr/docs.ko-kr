---
title: "속성 값 상속 | Microsoft Docs"
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
  - "상속, 속성 값"
  - "속성, 값 상속"
  - "값 상속"
ms.assetid: d7c338f9-f2bf-48ed-832c-7be58ac390e4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 속성 값 상속
속성 값 상속은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템의 한 기능입니다.  속성 값 상속을 사용하면 요소 트리의 자식 요소가 가장 가까운 부모 요소에 설정된 값을 상속하여 부모 요소로부터 특정 속성 값을 가져올 수 있습니다.  부모 요소도 속성 값 상속을 통해 속성 값을 가져올 수 있으므로 속성 시스템이 페이지 루트로 가는 모든 경로를 재귀적으로 사용할 수 있습니다.  속성 값 상속은 속성 시스템의 기본 동작이 아닙니다. 따라서 자식 요소에서 속성 값 상속이 시작되게 하려면 특정 메타데이터 설정을 사용하여 속성을 설정해야 합니다.  
  
   
  
<a name="Property_Value_Inheritance_is_Containment_Inheritance"></a>   
## 포함 상속으로서의 속성 값 상속  
 여기서 "상속"이라는 용어는 형식 및 일반 개체 지향 프로그래밍의 컨텍스트에서 사용하는 상속의 개념과는 약간 다릅니다. 형식 및 일반 개체 지향 프로그래밍의 컨텍스트에서 상속은 파생 클래스가 기본 클래스에서 멤버 정의를 상속하는 것을 말합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서도 이러한 상속의 개념이 사용됩니다. 즉, 다양한 기본 클래스에 정의된 속성은 요소로 사용되는 파생 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 클래스의 특성으로 노출되고 코드에서 멤버로 노출됩니다.  속성 값 상속은 특히 요소 트리 내의 부모\/자식 관계를 기반으로, 한 요소에서 다른 요소로 속성 값이 상속되는 방식과 관련된 개념입니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그로 응용 프로그램을 정의하는 경우와 같이 다른 요소 내에 요소를 중첩할 때 가장 직접적으로 요소 트리가 표시됩니다.  지정한 다른 개체 컬렉션에 개체를 추가하여 프로그래밍 방식으로 개체 트리를 만들 수도 있으며 이 경우 속성 값 상속은 완성된 트리에서 런타임에 작동하는 것과 동일하게 작동합니다.  
  
<a name="Practical_Applications_of_Property_Value_Inheritance"></a>   
## 속성 값 상속의 실제 적용  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]에는 속성 상속을 사용하는 여러 속성이 포함되어 있습니다.  대개 이러한 속성을 사용하는 시나리오에서는 페이지 당 속성을 한 번만 설정하는 것이 적합하지만 해당 속성이 기본 요소 클래스 중 하나의 멤버이기도 하므로 대부분의 자식 요소에서도 속성이 존재하게 됩니다.  예를 들어 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성은 흐르는 콘텐츠가 페이지에 표시 및 정렬되는 방향을 제어합니다.  텍스트 흐름 개념은 모든 자식 요소에서 일관된 방식으로 처리하는 것이 일반적입니다.  즉, 몇 가지 이유로 사용자 또는 환경에 의해 요소 트리 수준에서 흐름 방향이 다시 설정된 경우 흐름 방향이 전체적으로 다시 설정되어야 합니다.  하지만 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을 상속하도록 설정된 경우에는 응용 프로그램 내 각 페이지의 표시 요구 사항을 포괄하는 요소 트리 내의 특정 수준에서 한 번만 이 속성 값을 설정하거나 다시 설정하면 됩니다.  초기 기본값까지 이런 식으로 상속됩니다.  속성 값 상속 모델을 사용하더라도 흐름 방향을 의도적으로 혼합하는 것과 같은 드문 경우에 한해서는 개별 요소가 속성 값을 다시 설정할 수 있습니다.  
  
<a name="Making_a_Custom_Property_Inheritable"></a>   
## 사용자 지정 속성을 상속 가능 속성으로 설정  
 사용자 지정 속성의 메타데이터를 변경하여 고유한 사용자 지정 속성을 상속 가능하게 설정할 수 있습니다.  하지만 속성을 상속 가능하게 지정하면 성능 면에서 몇 가지 고려해야 할 사항이 발생합니다.  속성에 설정된 로컬 값이 없거나 스타일, 템플릿 또는 데이터 바인딩을 통해 얻은 값이 없는 경우에는 상속 가능한 속성이 자신에게 할당된 속성 값을 논리적 트리의 모든 자식 요소에 제공합니다.  
  
 속성이 값 상속에 참가하도록 하려면 [연결된 속성 등록](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)의 설명에 따라 사용자 지정 연결된 속성을 만듭니다.  이 속성을 메타데이터\(<xref:System.Windows.FrameworkPropertyMetadata>\)에 등록하고 해당 메타데이터 내의 옵션 설정에서 "Inherits" 옵션을 지정합니다.  또한 속성에 기본값을 설정하여 지금부터 이 값이 상속되도록 만들어야 합니다.  속성을 연결된 속성으로 등록했더라도 "연결되지 않은" [종속성 속성](GTMT)과 마찬가지로 소유자 형식의 get\/set 액세스에 대한 속성 "래퍼"를 만들 수 있습니다.  이렇게 한 다음 소유자 형식 또는 파생 형식에 직접 속성 래퍼를 사용하여 상속 가능 속성을 설정하거나 <xref:System.Windows.DependencyObject>의 연결된 속성 구문을 사용하여 설정할 수 있습니다.  
  
 연결된 속성은 개념적으로 전역 속성과 비슷합니다. 즉, 모든 <xref:System.Windows.DependencyObject>의 값을 확인하고 유효한 결과를 가져올 수 있습니다.  연결된 속성을 사용하는 일반적인 시나리오에서는 자식 요소에 속성 값을 설정합니다. 이 시나리오는 해당 속성이 트리의 각 요소\(<xref:System.Windows.DependencyObject>\)에 항상 암시적으로 존재하는 연결된 속성인 경우 보다 효과적입니다.  
  
> [!NOTE]
>  연결되지 않은 종속성 속성에도 속성 값 상속이 작동하는 것처럼 보일 수 있지만, 연결되지 않은 속성이 런타임 트리의 특정 요소 경계를 통해 상속될 때의 동작은 정의되어 있지 않습니다.  메타데이터에 <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>를 지정할 때는 항상 <xref:System.Windows.DependencyProperty.RegisterAttached%2A>를 사용하여 속성을 등록합니다.  
  
<a name="InheritanceContext"></a>   
## 트리 경계를 넘어 속성 값 상속  
 속성 상속은 요소 트리를 이동하는 방식으로 작동합니다.  이 트리는 많은 경우 논리적 트리와 나란히 존재합니다.  하지만 <xref:System.Windows.Media.Brush>와 같이 요소 트리를 정의하는 [WPF 핵심 수준](GTMT) 개체를 태그에 포함하는 경우에는 불연속적인 논리적 트리가 만들어집니다.  진정한 논리적 트리는 개념적으로 <xref:System.Windows.Media.Brush>를 통해 확장되지 않는데 이는 논리적 트리가 [WPF 프레임워크 수준](GTMT) 개념이기 때문입니다.  <xref:System.Windows.LogicalTreeHelper>의 메서드를 사용하는 경우 반환되는 결과에 이러한 사실이 반영되는 것을 볼 수 있습니다.  하지만 속성 값 상속을 사용하면 논리적 트리에서 발생하는 이러한 간격을 메울 수 있으며 상속된 값을 경계를 넘어 전달할 수 있습니다. 단, 상속 가능한 속성이 연결된 속성으로 등록되어 있어야 하고 의도적 상속 차단 경계\(예: <xref:System.Windows.Controls.Frame>\)를 만나지 않아야 합니다.  
  
## 참고 항목  
 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)   
 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)