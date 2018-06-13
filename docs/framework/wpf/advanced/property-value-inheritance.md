---
title: 속성 값 상속
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [WPF], property values
- value inheritance [WPF]
- properties [WPF], value inheritance
ms.assetid: d7c338f9-f2bf-48ed-832c-7be58ac390e4
ms.openlocfilehash: 6af356d1c6325714fbc98cd5fe8c3ebc1825fcb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547396"
---
# <a name="property-value-inheritance"></a>속성 값 상속
속성 값 상속은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템의 기능입니다. 속성 값 상속을 통해 요소 트리의 자식 요소가 부모 요소에서 특정 속성 값을 얻어 가장 근접한 부모 요소의 아무 곳에서나 설정되었을 때 해당 값을 상속합니다. 부모 요소는 속성 값 상속을 통해 값을 얻었을 수 있으므로 시스템이 완전히 페이지 루트로 되돌아갈 수 있습니다. 속성 값 상속은 기본 속성 시스템 동작이 아닙니다. 속성이 자식 요소에서 속성 값 상속을 시작하게 하려면 특정 메타데이터 설정을 사용하여 속성을 설정해야 합니다.  
  

  
<a name="Property_Value_Inheritance_is_Containment_Inheritance"></a>   
## <a name="property-value-inheritance-is-containment-inheritance"></a>속성 값 상속은 포함 상속임  
 여기서 "상속"이라는 용어는 파생 클래스가 기본 클래스에서 멤버 정의를 상속하는 형식 및 일반적인 개체 지향 프로그램의 컨텍스트에서 사용하는 상속과 완전히 같은 개념은 아닙니다. 해당 상속의 의미는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서도 유효합니다. 다양한 기본 클래스에 정의되는 속성은 요소로 사용될 때 파생 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 클래스의 특성으로 표시되고 코드의 멤버로 표시됩니다. 속성 값 상속의 경우 특히 요소 트리 내의 부모-자식 관계에 따라 요소 간에 속성 값을 상속하는 방식이 영향을 미칩니다. 해당 요소 트리는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그에서 응용 프로그램을 정의할 때 요소 내부에 다른 요소를 중첩할 경우 대부분 직접 표시됩니다. 다른 개체의 지정된 컬렉션에 개체를 추가하여 개체 트리를 프로그래밍 방식으로 만들 수도 있고 속성 값 상속은 런타임에 완료된 트리에서 동일한 방식으로 수행됩니다.  
  
<a name="Practical_Applications_of_Property_Value_Inheritance"></a>   
## <a name="practical-applications-of-property-value-inheritance"></a>속성 값 상속의 실제 응용 프로그램  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]에는 속성 상속을 가능하게 하는 여러 속성이 포함됩니다. 일반적으로 이러한 속성은 페이지당 한 번만 속성을 설정하는 것이 적절하지만 해당 속성이 기본 요소 클래스 중 하나의 멤버이기도 하므로 대부분의 자식 요소에도 존재하는 속성을 포함합니다. 예를 들어는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성 컨트롤은 방향 이동 콘텐츠 표시 및 페이지에 정렬 합니다. 일반적으로 모든 자식 요소에서 텍스트 흐름 개념을 일관성 있게 처리하려고 합니다. 어떤 이유로 사용자 또는 환경 작업에 의해 요소 트리의 몇몇 수준에서 다시 설정된 흐름 방향은 일반적으로 전체적으로 다시 설정되어야 합니다. 경우는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 상속 하려고 속성, 값을 설정 또는 응용 프로그램의 각 페이지의 표시 요구를 포함 하는 요소 트리에 있는 수준에서 한 번 다시 설정만 필요 합니다. 초기 기본값도 이 방식으로 상속됩니다. 속성 값 상속 모델에서는 드물지만 다양한 흐름 방향을 의도적으로 포함하는 경우 개별 요소가 값을 다시 설정할 수 있습니다.  
  
<a name="Making_a_Custom_Property_Inheritable"></a>   
## <a name="making-a-custom-property-inheritable"></a>사용자 지정 속성을 상속 가능으로 설정  
 사용자 지정 속성의 메타데이터를 변경하여 자체 사용자 지정 속성을 상속 가능으로 설정할 수도 있습니다. 하지만 속성을 상속 가능으로 지정할 경우 성능상 몇 가지 사항을 고려해야 합니다. 속성에 설정된 로컬 값이 없거나 스타일, 템플릿 또는 데이터 바인딩을 통해 얻은 값이 없는 경우 상속 가능 속성은 논리 트리에서 모든 자식 요소에 할당된 속성 값을 제공합니다.  
  
 속성을 값 상속에 참여하도록 설정하려면 [연결된 속성 등록](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)에 설명된 대로 사용자 지정 연결된 속성을 만듭니다. 메타 데이터와 속성을 등록 (<xref:System.Windows.FrameworkPropertyMetadata>) 해당 메타 데이터 내에서 옵션 설정에 "Inherits" 옵션을 지정 합니다. 또한 속성에 설정된 기본값이 있는지 확인합니다. 이제 이 값이 상속되기 때문입니다. 속성을 연결된 속성으로 등록하더라도 "연결되지 않은" 종속성 속성의 경우처럼 소유자 형식에서 get/set 액세스에 대한 속성 “래퍼”를 만들어야 할 수 있습니다. 이렇게 하면 상속 가능한 속성 설정할 수 있습니다 소유자 형식 또는 파생된 형식에 직접 속성 래퍼를 사용 하 여에 연결 된 속성 구문을 사용 하 여 설정할 수 있습니다 또는 <xref:System.Windows.DependencyObject>합니다.  
  
 연결 된 속성은 전역 속성; 개념적으로 비슷합니다. 값을 확인할 수 있습니다 <xref:System.Windows.DependencyObject> 유효한 결과입니다. 연결 된 속성에 대 한 일반적인 시나리오는 자식 요소에 속성 값을 설정 하 고 해당 시나리오는 해당 속성에는 항상 각 요소에 대해 연결된 된 속성을 사용 하는 경우 보다 효과적인 (<xref:System.Windows.DependencyObject>) 트리에서 합니다.  
  
> [!NOTE]
>  속성 값 상속은 연결된 종속성 속성에도 적용되는 것처럼 보일 수 있지만 런타임 트리의 특정 요소 경계를 통한 연결되지 않은 속성에 대한 상속 동작은 정의되지 않습니다. 항상 사용 하 여 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 지정 하는 속성을 등록 하려면 <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> 메타 데이터에 있습니다.  
  
<a name="InheritanceContext"></a>   
## <a name="inheriting-property-values-across-tree-boundaries"></a>트리 경계를 넘어 속성 값 상속  
 속성 상속은 요소 트리를 통과하는 방식으로 수행됩니다. 이 트리는 일반적으로 논리 트리와 비슷합니다. 하지만 포함 하는 경우 WPF 핵심 수준 개체와 같은 요소 트리를 정의 하는 태그에는 <xref:System.Windows.Media.Brush>, 연속 되지 않은 논리 트리를 만들었습니다. 진정한 논리적 트리를 통해 개념적으로 확장 되지 않습니다는 <xref:System.Windows.Media.Brush>논리적 트리 WPF 프레임 워크 수준 개념 이므로, 합니다. 메서드를 사용 하는 경우 결과에 반영 볼 수 있습니다 <xref:System.Windows.LogicalTreeHelper>합니다. 그러나 속성 값 상속 논리적 트리에서이 간격을 연결 수 있으며 연결된 된 속성 및 없는 의도적인 상속 경계로 등록 된 상속 가능한 속성으로 상속 된 값을 통해 전달할 수 있습니다 (한 같은<xref:System.Windows.Controls.Frame>) 발생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)  
 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)
