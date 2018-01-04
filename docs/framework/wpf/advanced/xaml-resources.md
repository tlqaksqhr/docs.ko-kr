---
title: "XAML 리소스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reusing resources [WPF]
- resources [WPF], reusing
- reusing commonly defined objects [WPF]
- XAML [WPF], reusing resources
ms.assetid: 91580b89-a0a8-4889-aecb-fddf8e63175f
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2d58802bcdfa57bb7689e7406651fcc9829a7e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-resources"></a>XAML 리소스
리소스는 응용 프로그램의 여러 위치에서 다시 사용할 수 있는 개체입니다. 리소스의 예로는 브러시와 스타일이 있습니다. 이 개요에서는의 리소스를 사용 하는 방법을 설명 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다. 만들 수 있고 하거나 코드 서로 바꿔 코드를 사용 하 여 리소스에 액세스 하면 및 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다. 자세한 내용은 참조 [리소스와 코드가](../../../../docs/framework/wpf/advanced/resources-and-code.md)합니다.  
  
> [!NOTE]
>  이 항목에서 설명 하는 리소스 파일은 리소스 파일에 설명 된 다르지 [WPF 응용 프로그램 리소스, 내용 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md) 포함 또는 연결 된 리소스에 설명 된 다른 [ (.NET) 응용 프로그램 리소스 관리](http://msdn.microsoft.com/library/f2582734-8ada-4baa-8a7c-e2ef943ddf7e)합니다.  
  
  
<a name="usingresources"></a>   
## <a name="using-resources-in-xaml"></a>XAML의 리소스 사용  
 다음 예제에서는 정의 <xref:System.Windows.Media.SolidColorBrush> 페이지의 루트 요소에 대해 자원으로 합니다. 이 예제에서는 그런 다음 해당 리소스를 참조 하 고 사용 하 여 포함 하 여 여러 자식 요소의 속성을 설정 하는 <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Controls.TextBlock>, 및 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-xaml[FEResourceSH_snip#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]  
  
 모든 프레임 워크 수준 요소 (<xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>)에 <xref:System.Windows.FrameworkElement.Resources%2A> 하는 리소스를 포함 하는 속성에 해당 하는 속성이 (으로 <xref:System.Windows.ResourceDictionary>) 리소스를 정의 하는 합니다. 모든 요소에서 리소스를 정의할 수 있습니다. 그러나 리소스는 가장 자주 사용할 루트 요소에 정의 <xref:System.Windows.Controls.Page> 예제에서입니다.  
  
 리소스 디렉터리의 각 리소스에는 고유 키가 있어야 합니다. 통해 고유 키를 할당 하는 태그에 리소스를 정의 하는 경우는 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md)합니다. 일반적으로 키는 문자열이지만, 적절한 태그 확장을 사용하여 다른 개체 형식으로도 설정할 수 있습니다. 특정 기능 영역에서 비문자열 리소스의 키를 사용 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 스타일, 구성 요소 리소스 및 데이터 스타일 지정을 위해.  
  
 리소스를 정의한 다음 키 이름을 지정하는 리소스 태그 확장 구문을 사용하여 속성에 사용되도록 해당 리소스를 참조할 수 있습니다. 예를 들어 다음과 같습니다.  
  
 [!code-xaml[FEResourceSH_snip#KeyNameUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]  
  
 앞의 예제에서 때는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로더는 값을 처리 `{StaticResource MyBrush}` 에 대 한는 <xref:System.Windows.Controls.Control.Background%2A> 속성을 <xref:System.Windows.Controls.Button>, 리소스 사전에 대 한를 먼저 확인 하는 리소스 조회 논리는 <xref:System.Windows.Controls.Button> 요소입니다. 경우 <xref:System.Windows.Controls.Button> 리소스 키의 정의 없는 `MyBrush` (은 그렇지 않습니다; 해당 리소스 컬렉션이 비어) 조회의 부모 요소를 다음 확인 <xref:System.Windows.Controls.Button>, 변수인 <xref:System.Windows.Controls.Page>합니다. 따라서 정의 하는 경우 리소스에는 <xref:System.Windows.Controls.Page> 루트 요소의 논리적 트리에서 모든 요소는 <xref:System.Windows.Controls.Page> 허용 하는 모든 속성의 값을 설정에 대 한 동일한 리소스를 다시 사용할 수 있습니다 및 액세스할 수는 <xref:System.Type> 하는 리소스 이 옵션을 나타냅니다. 이전 예제에서는 동일한 `MyBrush` 서로 다른 두 속성을 설정 하는 리소스:는 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.Button>, 및 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle>합니다.  
  
<a name="staticdynamic"></a>   
## <a name="static-and-dynamic-resources"></a>정적 및 동적 리소스  
 리소스는 정적 리소스 또는 동적 리소스로 참조될 수 있습니다. 하나를 사용 하 여 수행 된 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) 또는 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)합니다. 태그 확장의 기능은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 확장 특성 문자열을 처리 하는 개체를 반환 하 여 개체 참조를 지정할 수는 그는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로더 합니다. 태그 확장 동작에 대 한 자세한 내용은 참조 [태그 확장명 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)합니다.  
  
 태그 확장을 사용하면 일반적으로 설정 중인 속성의 컨텍스트에서 평가되는 것이 아니라 특정 태그 확장을 통해 처리되는 문자열 형식으로 하나 이상의 매개 변수를 제공합니다. [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) 모든 사용 가능한 리소스 사전에서 해당 키에 대 한 값을 조회 하 여 키를 처리 합니다. 이 작업은 로드 프로세스에서 정적 리소스 참조를 사용하는 속성 값을 할당해야 하는 시점인 로드 시에 수행됩니다. [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) 대신 프로세스 응용 프로그램을 실제로 실행 될 때까지 키를 반환 하는 식 및 해당 식을 만들어 계산 되지 않은 남은, 될 때 식이 계산 되 고 값을 제공 합니다.  
  
 리소스를 참조할 때 정적 리소스 참조를 사용하는지 아니면 동적 리소스 참조를 사용하는지에 상관없이 영향을 미칠 수 있는 고려 사항은 다음과 같습니다.  
  
-   응용 프로그램에 대 한 리소스를 만드는 방법의 전체 디자인 (각 응용 프로그램에서는 페이지에 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 리소스 전용 어셈블리에).  
  
-   응용 프로그램 기능: 응용 프로그램 요구 사항의 일부로서 실시간으로 리소스 업데이트.  
  
-   해당 리소스 참조 형식의 각 조회 동작.  
  
-   특정 속성 또는 리소스 형식 및 해당 형식의 기본 동작.  
  
### <a name="static-resources"></a>정적 리소스  
 정적 리소스 참조는 다음 환경에 가장 적합합니다.  
  
-   응용 프로그램 디자인에서는 대부분의 리소스를 페이지나 응용 프로그램 수준 리소스 사전에 집중합니다. 정적 리소스 참조는 페이지 다시 로드와 같은 런타임 동작을 기반으로 다시 평가하지 않으므로, 리소스와 응용 프로그램 디자인별로 필요하지 않을 때 다수의 동적 리소스 참조를 사용하지 않을 수 있다는 성능상의 이점이 있습니다.  
  
-   에 있지 않은 속성의 값을 설정 하는 한 <xref:System.Windows.DependencyObject> 또는 <xref:System.Windows.Freezable>합니다.  
  
-   DLL로 컴파일되고 응용 프로그램의 일부로 컴파일되거나 응용 프로그램에 공유될 리소스 사전을 만듭니다.  
  
-   사용자 지정 컨트롤의 테마를 만들고 테마에서 사용되는 리소스를 정의합니다. 이 경우 일반적으로 동적 리소스 참조 조회 동작을 사용하지 않습니다. 대신, 조회가 예측 가능하고 테마에 자체 포함되도록 정적 리소스 참조 동작을 사용합니다. 동적 리소스 참조를 사용하면, 테마에 있는 참조까지도 런타임 시까지 평가되지 않은 상태로 남아 있게 되며, 테마를 적용할 때 일부 요소에서 테마가 참조하려는 키를 재정의하고 조회에서 로컬 요소가 테마 자체보다 앞에 옵니다. 이 경우 테마가 예상대로 작동하지 않습니다.  
  
-   리소스를 사용하여 다수의 종속성 속성을 설정합니다. 종속성 속성에는 속성 시스템에서 사용하게 설정한 유효 값이 캐싱이 있습니다. 따라서 로드 시 평가될 수 있는 종속성 속성의 값을 제공하는 경우, 종속성 속성에서 재평가된 식을 확인하지 않아도 되며 마지막 유효 값을 반환할 수 있습니다. 이 기술을 사용하면 성능상의 이점이 있습니다.  
  
-   모든 소비자에 대 한 기본 리소스를 변경 하려는 또는 사용 하 여 각 소비자에 대 한 별도 쓰기 가능한 인스턴스를 유지 하려는 [x: 공유 특성](../../../../docs/framework/xaml-services/x-shared-attribute.md)합니다.  
  
#### <a name="static-resource-lookup-behavior"></a>정적 리소스 조회 동작  
  
1.  조회 프로세스가 속성을 설정하는 요소를 통해 정의된 리소스 사전에서 요청된 키를 확인합니다.  
  
2.  그런 다음 조회 프로세스가 논리 트리를 상향식으로 통과하여 부모 요소와 해당 리소스 사전으로 이동합니다. 이 작업은 루트 요소에 도달할 때까지 계속됩니다.  
  
3.  다음으로 응용 프로그램 리소스를 확인합니다. 응용 프로그램 리소스는 리소스 사전에서 정의한 내에 있는 리소스는 <xref:System.Windows.Application> 개체에 대 한 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  
  
 리소스 사전 내의 정적 리소스 참조는 리소스 참조 전에 사전순으로 이미 정의된 리소스를 참조해야 합니다. 전방 참조는 정적 리소스 참조로 확인할 수 없습니다. 따라서 정적 리소스 참조를 사용하는 경우, 리소스별 용도에 맞게 리소스를 각 리소스 사전의 시작 부분에 정의하도록 리소스 사전 구조를 디자인해야 합니다.  
  
 정적 리소스 조회 테마 또는 시스템 리소스를 확장할 수 있지만 때문에이 기능이 지원는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로더에서 요청을 지연 합니다. 페이지가 로드될 때 런타임 테마가 응용 프로그램에 적절하게 적용되기 위해 지연이 필요합니다. 그러나 테마에만 존재하거나 시스템 리소스로 존재하는 것으로 알려진 키의 정적 리소스 참조는 사용하지 않는 것이 좋습니다. 사용자가 실시간으로 테마를 변경하는 경우 해당 참조가 다시 평가되지 않기 때문입니다. 동적 리소스 참조는 테마나 시스템 리소스를 요청할 때 더욱 안정적입니다. 테마 요소 자체가 다른 리소스를 요청할 때는 예외입니다. 이러한 참조는 앞서 설명한 이유때문에 정적 리소스 참조여야 합니다.  
  
 정적 리소스 참조가 없으면 다양한 예외 동작이 발생합니다. 리소스가 지연되면 런타임 시 예외가 발생합니다. 리소스가 지연되지 않으면 로드 시 예외가 발생합니다.  
  
### <a name="dynamic-resources"></a>동적 리소스  
 동적 리소스는 다음과 같은 환경에 가장 적합합니다.  
  
-   리소스 값은 런타임 시까지 알려지지 않은 조건에 따라 달라집니다. 여기에는 시스템 리소스 또는 사용자가 설정 가능한 리소스가 포함됩니다. 로 노출 시스템 속성을 참조 하는 setter 값을 만들 수는 예를 들어 <xref:System.Windows.SystemColors>, <xref:System.Windows.SystemFonts>, 또는 <xref:System.Windows.SystemParameters>합니다. 이러한 값은 궁극적으로 운영 체제와 사용자의 런타임 환경에서 오므로 정말로 동적입니다. 변경할 수 있는 응용 프로그램 수준 테마도 있습니다. 이 경우 페이지 수준 리소스 액세스를 통해서도 변경 사항을 캡처해야 합니다.  
  
-   사용자 지정 컨트롤의 테마 스타일을 만들거나 참조합니다.  
  
-   콘텐츠를 조정 하려는 <xref:System.Windows.ResourceDictionary> 응용 프로그램 수명 동안 합니다.  
  
-   상호 종속된 복잡한 리소스 구조체 가 있으며, 이 경우에는 전방 참조가 필요할 수 있습니다. 정적 리소스 참조를 지원 하지 않으므로 전방 참조 하지만 동적 리소스 참조에서는 이러한 리소스는 런타임까지, 평가 하지 않아도 되므로 전방 참조가 없는 관련 개념입니다.  
  
-   컴파일 또는 작업 집합 면에서 특히 큰 리소스를 참조하며, 페이지를 로드할 때 즉시 리소스를 사용하지 않을 수도 있습니다. 하지만 정적 리소스 참조에서 항상 로드 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 동적 리소스 참조를 로드 하지 않습니다는 실제로 사용 될 때까지; 페이지를 로드 합니다.  
  
-   setter 값이 테마나 다른 사용자 설정의 영향을 받는 다른 값에서 오는 스타일을 만듭니다.  
  
-   응용 프로그램 수명 중에 논리 트리에서 다시 부모가 지정될 수 있는 요소에 리소스를 적용합니다. 부모를 변경하면 리소스 조회 범위도 변경될 수 있으므로, 부모가 재지정된 요소의 리소스를 새 범위에 따라 재평가하려면 항상 동적 리소스 참조를 사용하세요.  
  
#### <a name="dynamic-resource-lookup-behavior"></a>동적 리소스 조회 동작  
 동적 리소스 참조에 대 한 리소스 조회 동작 호출 하는 경우 코드에서 조회 동작과 유사 <xref:System.Windows.FrameworkElement.FindResource%2A> 또는 <xref:System.Windows.FrameworkElement.SetResourceReference%2A>합니다.  
  
1.  조회 프로세스가 속성을 설정하는 요소를 통해 정의된 리소스 사전에서 요청된 키를 확인합니다.  
  
    -   요소를 정의 하는 경우는 <xref:System.Windows.FrameworkElement.Style%2A> 속성을는 <xref:System.Windows.Style.Resources%2A> 내에서 사전을 <xref:System.Windows.Style> 을 선택 합니다.  
  
    -   요소를 정의 하는 경우는 <xref:System.Windows.Controls.Control.Template%2A> 속성을는 <xref:System.Windows.FrameworkTemplate.Resources%2A> 내에서 사전을 <xref:System.Windows.FrameworkTemplate> 을 선택 합니다.  
  
2.  그런 다음 조회 프로세스가 논리 트리를 상향식으로 통과하여 부모 요소와 해당 리소스 사전으로 이동합니다. 이 작업은 루트 요소에 도달할 때까지 계속됩니다.  
  
3.  다음으로 응용 프로그램 리소스를 확인합니다. 응용 프로그램 리소스는 리소스 사전에서 정의한 내에 있는 리소스는 <xref:System.Windows.Application> 개체에 대 한 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  
  
4.  현재 활성 테마의 테마 리소스 사전을 확인합니다. 런타임 시 테마가 변경되면 값을 재평가합니다.  
  
5.  시스템 리소스를 확인합니다.  
  
 예외 동작이 있는 경우 다음과 같이 다양합니다.  
  
-   리소스에서 요청 된 경우는 <xref:System.Windows.FrameworkElement.FindResource%2A> 를 호출 하 고 찾을 수 없습니다, 예외가 발생 합니다.  
  
-   리소스에서 요청 된 경우는 <xref:System.Windows.FrameworkElement.TryFindResource%2A> 를 호출 하 고 찾을 수 없습니다, 예외가 발생 하지만 반환 된 값은 `null`합니다. 설정 되는 속성을 허용 하지 않는 경우 `null`, 것이 더 깊은 예외가 발생할 수 있습니다 (설정 되 고 개별 속성에 종속).  
  
-   동적 리소스 참조에 의해 리소스를 요청 했지만 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 및 찾을 수 없는 다음 동작 일반 속성 시스템에 따라 달라 지지만 일반적인 동작은 것 처럼 속성 설정은 작업이 발생 하지 않은 리소스가 있는 수준에서 합니다. 예를 들어, 평가할 수 없는 리소스를 사용하여 개별 단추 요소에서 배경을 설정하려고 하면 값 집합이 생기지 않지만, 속성 시스템 및 값 우선 순위의 다른 참가자로부터 유효 값을 여전히 가져올 수 있습니다. 예를 들어, 배경색은 로컬에 정의한 단추 스타일 또는 테마 스타일에서 여전히 가져올 수 있습니다. 테마 스타일이 정의하지 않은 속성의 경우, 실패한 리소스 평가 후 유효 값은 속성 메타데이터의 기본값에서 가져올 수 있습니다.  
  
#### <a name="restrictions"></a>제한  
 동적 리소스 참조에는 몇 가지 주목할 만한 제한 사항이 있습니다. 다음 중 하나 이상이 참이어야 합니다.  
  
-   설정 되는 속성에 속성 이어야 합니다는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>합니다. 속성으로 지원 되어야 합니다는 <xref:System.Windows.DependencyProperty>합니다.  
  
-   내에 있는 값에 대 한 참조는는 <xref:System.Windows.Style> <xref:System.Windows.Setter>합니다.  
  
-   설정 되는 속성에 속성 이어야 합니다는 <xref:System.Windows.Freezable> 중 하나의 값으로 제공 되는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 속성 또는 <xref:System.Windows.Setter> 값입니다.  
  
 설정 되는 속성 이어야 하므로 <xref:System.Windows.DependencyProperty> 또는 <xref:System.Windows.Freezable> 속성, 속성 변경 (동적 리소스 변경 된 값) 속성 시스템에 의해 승인 되었는지 때문에 UI에 대부분의 속성 변경 내용을 전파할 수 있습니다. 대부분의 컨트롤 경우 컨트롤의 다른 레이아웃을 강제로 있는 논리를 포함 한 <xref:System.Windows.DependencyProperty> 변경과 속성 레이아웃에 영향을 줄 수 있습니다. 그러나 일부 속성이 있는 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) 값을 기준으로 UI에 대 한 실시간에서 업데이트를 하는 방식에 대 한 값을 제공할 보장 됩니다. 이 기능은 속성 외에도 속성을 소유하는 형식, 심지어는 응용 프로그램의 논리 구조체에 따라서도 여전히 달라질 수 있습니다.  
  
<a name="stylesimplicitkeys"></a>   
## <a name="styles-datatemplates-and-implicit-keys"></a>스타일, DataTemplates 및 암시적 키  
 에 있는 모든 항목이 한다고 설명 했습니다 이전에 <xref:System.Windows.ResourceDictionary> 키가 있어야 합니다. 그러나 의미는 아닙니다 리소스를 모두 명시적 있어야 `x:Key`합니다. 리소스로 정의된 경우 여러 개체 형식에서 암시적 키를 지원하며, 이 경우 키 값이 다른 속성의 값과 연결됩니다. 로 알려져 암시적 키 반면는 `x:Key` 특성은 명시적 키입니다. 명시적 키를 지정하여 암시적 키를 덮어쓸 수 있습니다.  
  
 리소스에 대 한 매우 중요 한 한 가지 시나리오는 정의 하는 경우는 <xref:System.Windows.Style>합니다. 실제로 <xref:System.Windows.Style> 거의 항상 스타일은 다시 사용할 수 있도록 기본적으로 있으므로 리소스 사전에서 항목으로 정의 됩니다. 스타일에 대 한 자세한 내용은 참조 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)합니다.  
  
 컨트롤의 스타일은 암시적 키로 만들어 참조될 수 있습니다. 컨트롤의 기본 모양을 정의하는 테마 스타일은 이 암시적 키에 따라 달라집니다. 요청 하는 것의 관점에서 암시적 키는 <xref:System.Type> 컨트롤 자체입니다. 리소스 정의의 관점에서 암시적 키는 <xref:System.Windows.Style.TargetType%2A> 스타일의 합니다. 따라서 사용자 지정 컨트롤에 대 한 테마를 만드는 경우 기존 테마 스타일 상호 작용 하는 스타일을 만드는 않아도 지정 하는 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md) 해당 <xref:System.Windows.Style>합니다. 테마로 지정된 스타일을 사용하려면 스타일을 전혀 지정하지 않아도 됩니다. 예를 들어, 다음과 같은 스타일 정의 작동 하더라도 <xref:System.Windows.Style> 리소스 키가 같지 않습니다.  
  
 [!code-xaml[FEResourceSH_snip#ImplicitStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]  
  
 스타일 실제로 않았는지 키: 암시적 키 `typeof(` <xref:System.Windows.Controls.Button> `)`합니다. 태그를 지정할 수 있습니다는 <xref:System.Windows.Style.TargetType%2A> 이름을 형식으로 직접 (또는 필요에 따라 사용할 수 있습니다 [{X:type...}](../../../../docs/framework/xaml-services/x-type-markup-extension.md) 반환 하는 <xref:System.Type>합니다.  
  
 사용 하는 기본 테마 스타일 메커니즘을 통해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 스타일의 런타임 스타일으로 적용 되는 <xref:System.Windows.Controls.Button> 페이지에서 경우에는 <xref:System.Windows.Controls.Button> 지정 하려고 하지 않습니다 자체 해당 <xref:System.Windows.FrameworkElement.Style%2A> 속성 또는 특정 리소스 스타일에 대 한 참조입니다. 페이지에 정의된 스타일은 테마 사전 스타일에 있는 동일한 키를 사용하여 테마 사전 스타일보다 빠른 조회 순서를 통해 먼저 발견됩니다. 지정할 수 `<Button>Hello</Button>` 페이지 및으로 정의 된 스타일의 아무 곳 이나 <xref:System.Windows.Style.TargetType%2A> 의 `Button` 단추에 적용 됩니다. 원하는 경우 동일한 형식 값을 갖는 스타일 명시적으로 입력할 수 있습니다 <xref:System.Windows.Style.TargetType%2A>에서 태그는 하지만 포트는 선택 사항에 대 한 합니다.  
  
 스타일에 대 한 암시적 키 경우 컨트롤에 적용 되지 않습니다 <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> 은 `true` (또한 <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> 대신 명시적으로 컨트롤의 인스턴스 컨트롤 클래스에 대 한 기본 동작의 일부로 설정할 수 있습니다). 또한 암시적 키 파생된 클래스 시나리오를 지원 하려면 컨트롤 재정의 해야 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> (의 일부로 제공 되는 모든 기존 컨트롤 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이 작업을 수행). 스타일, 테마 및 컨트롤 디자인 하는 방법에 대 한 자세한 내용은 참조 [디자인 스타일 컨트롤에 대 한 지침이](../../../../docs/framework/wpf/controls/guidelines-for-designing-stylable-controls.md)합니다.  
  
 <xref:System.Windows.DataTemplate>암시적 키도 있습니다. 에 대 한 암시적 키는 <xref:System.Windows.DataTemplate> 는 <xref:System.Windows.DataTemplate.DataType%2A> 속성 값입니다. <xref:System.Windows.DataTemplate.DataType%2A>인수를 명시적으로 사용 하는 대신 형식의 이름으로 지정할 수도 있습니다 [{X:type...} ](../../../../docs/framework/xaml-services/x-type-markup-extension.md). 자세한 내용은 참조 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.ResourceDictionary>  
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [리소스 및 코드](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [리소스 정의 및 참조](../../../../docs/framework/wpf/advanced/how-to-define-and-reference-a-resource.md)  
 [응용 프로그램 관리 개요](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [x:Type 태그 확장](../../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
