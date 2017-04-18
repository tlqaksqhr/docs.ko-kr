---
title: "XAML 리소스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "리소스 다시 사용"
  - "리소스를 다시 사용"
  - "일반적으로 정의된 개체 다시 사용"
  - "XAML, 리소스를 다시 사용"
ms.assetid: 91580b89-a0a8-4889-aecb-fddf8e63175f
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# XAML 리소스
리소스는 응용 프로그램의 여러 위치에 다시 사용할 수 있는 개체입니다. 리소스의 예로 브러시 및 스타일. 이 개요의 리소스를 사용 하는 방법에 설명 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다. 만들 수 있고 하거나 코드 서로 바꿔 코드를 사용 하 여 리소스에 액세스 하면 및 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다. 자세한 내용은 참조 [리소스 및 코드](../../../../docs/framework/wpf/advanced/resources-and-code.md)합니다.  
  
> [!NOTE]
>  이 항목에서 설명 하는 리소스 파일은 리소스 파일에 설명 된 다르지 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md) 포함 또는 연결 된 리소스에 설명 된 다른 [응용 프로그램 리소스 관리 (.NET)](../Topic/Managing%20Application%20Resources%20\(.NET\).md)합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="usingresources"></a>   
## <a name="using-resources-in-xaml"></a>XAML의 리소스 사용  
 다음 예제에서는 정의 <xref:System.Windows.Media.SolidColorBrush> 페이지의 루트 요소에 있습니다. 예제에서는 그런 다음 해당 리소스를 참조 하 고 사용 하 여의 여러 자식 요소를 포함 하 여 속성을 설정 하는 <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Controls.TextBlock>, 및 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-xml[FEResourceSH_snip#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]  
  
 모든 프레임 워크 수준 요소 ( <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>)에 <xref:System.Windows.FrameworkElement.Resources%2A> 속성에는 리소스를 포함 하는 속성 (으로 <xref:System.Windows.ResourceDictionary>) 리소스를 정의 하 합니다. 모든 요소에 리소스를 정의할 수 있습니다. 리소스는 루트 요소에 가장 자주 정의 되는 반면 <xref:System.Windows.Controls.Page> 예제에서입니다.  
  
 각 리소스는 리소스 사전에 고유 키를 있어야 합니다. 통해 고유 키를 할당 하는 태그에 리소스를 정의 하는 경우는 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md)합니다. 일반적으로 키가 문자열입니다. 그러나 설정할 수 있습니다 또한 다른 개체 형식에 적절 한 태그 확장을 사용 하 여 합니다. 리소스에 대 한 문자열이 아닌 키의 특정 기능 영역에서 사용 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 스타일, 구성 요소 리소스 및 데이터 스타일 지정을 위해.  
  
 리소스를 정의한 후에 예를 들어 키 이름을 지정 하는 리소스 태그 확장 구문을 사용 하 여 속성 값에 사용할 리소스를 참조할 수 있습니다.  
  
 [!code-xml[FEResourceSH_snip#KeyNameUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]  
  
 앞의 예제에서 때는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로더는 값을 처리 `{StaticResource MyBrush}` 에 대 한는 <xref:System.Windows.Controls.Control.Background%2A> 속성을 <xref:System.Windows.Controls.Button>, 리소스 사전에 대 한를 먼저 확인 하는 리소스 조회 논리는 <xref:System.Windows.Controls.Button> 요소입니다. 경우 <xref:System.Windows.Controls.Button> 리소스 키에 대 한 정의 맺지 않은 `MyBrush` (그렇지 않으면, 해당 리소스 컬렉션은 비어), 조회의 부모 요소를 다음 확인 <xref:System.Windows.Controls.Button>, 변수인 <xref:System.Windows.Controls.Page>합니다. 따라서 정의 하는 경우 리소스에는 <xref:System.Windows.Controls.Page> 루트 요소, 논리적 트리는에 있는 모든 요소는 <xref:System.Windows.Controls.Page> 에 액세스할 수 있는지 및 허용 하는 모든 속성의 값을 설정에 대 한 동일한 리소스를 다시 사용할 수는 <xref:System.Type> 리소스가 나타내는 합니다. 이전 예제에서는 동일한 `MyBrush` 서로 다른 두 속성을 설정 하는 리소스:는 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.Button>, 및 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle>합니다.  
  
<a name="staticdynamic"></a>   
## <a name="static-and-dynamic-resources"></a>정적 및 동적 리소스  
 정적 리소스 또는 동적 리소스는 리소스를 참조할 수 있습니다. 이 중 하나를 사용 하 여 작업 수행은 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) 또는 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)합니다. 태그 확장의 기능입니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 확장 특성 문자열을 처리 하는 개체를 반환 하 여 개체 참조를 지정할 수는 그는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로더. 태그 확장 동작에 대 한 자세한 내용은 참조 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)합니다.  
  
 태그 확장을 사용 하면 일반적으로 제공한 설정 되는 속성의 컨텍스트에서 평가 되지 않고 하나 이상의 매개 변수가 문자열 양식에서 해당 특정 태그 확장에 의해 처리 됩니다. [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) 모든 사용 가능한 리소스 사전에서 해당 키에 대 한 값을 조회 하 여 키를 처리 합니다. 이 로드 프로세스를 정적 리소스 참조를 사용 하는 속성 값을 할당 해야 하는 경우에 지점 로드 시 발생 합니다. [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) 대신 프로세스는 응용 프로그램이 실제로 실행 될 때까지 식 및 해당 식을 만들어 키 확인 되지 않은 남은, 이때 식이 계산 되 고 값을 제공 합니다.  
  
 리소스를 참조 하는 경우 다음 고려 사항은 영향을 줄 수는 정적 리소스 참조 또는 동적 리소스 참조:  
  
-   응용 프로그램에 대 한 리소스를 만드는 방법의 전체 디자인 (응용 프로그램에서 페이지당에 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 리소스 전용 어셈블리에).  
  
-   응용 프로그램 기능: 실시간으로 응용 프로그램 요구 사항 부분에서는 리소스를 업데이트 하는?  
  
-   각 조회 동작 해당 리소스 참조 형식입니다.  
  
-   특정 속성 또는 리소스 형식 및 해당 형식의 기본 동작입니다.  
  
### <a name="static-resources"></a>정적 리소스  
 정적 리소스에 따라 다음과 같은 경우에 대 한 작업을 참조 하는 가장 적합 합니다.  
  
-   응용 프로그램 디자인 중점적으로 설명 가장 모든 해당 리소스를 페이지 또는 응용 프로그램 수준의 리소스의 사전입니다. 리소스 및 응용 프로그램 디자인 필요 하지 않는 많은 수의 동적 리소스 참조를 방지 하는 데 몇 가지 성능상의 이점을 수 따라서 있으며 정적 리소스 참조는 페이지를 다시 로드 등의 런타임 동작에 따라 다시 평가 하지 않습니다.  
  
-   에 있지 않은 속성의 값을 설정 하는 한 <xref:System.Windows.DependencyObject> 또는 <xref:System.Windows.Freezable>합니다.  
  
-   DLL로 컴파일 및 응용 프로그램의 일부로 패키지 또는 응용 프로그램 간에 공유 될 리소스 사전을 만듭니다.  
  
-   사용자 지정 컨트롤에 대 한 테마를 만들고 테마 내에서 사용 되는 리소스를 정의 하는 합니다. 이 경우 일반적으로 원하지 않는 동적 리소스 참조 조회 동작을 대신 정적 리소스 참조 동작 조회는 예측 가능 하 고 테마를 자체 포함 되도록 합니다. 동적 리소스 참조에도 테마 내의 참조는 남아 평가 되지 않은 런타임 전에 이며 기회가 테마를 적용 하면 일부 로컬 요소가 테마를 참조 하려고 하는 키를 다시 정의 됩니다 및 로컬 요소 조회에서 자체는 테마를 이전 대체 됩니다. 이런 경우, 테마에 예상 되는 방식에서 작동 하지 않습니다.  
  
-   리소스를 사용 하는 많은 수의 종속성 속성을 설정할 수 있습니다. 종속성 속성은 유효 값 캐싱이 속성 시스템에 의해 활성화 된 이므로 될 수 있는 종속성 속성의 값을 제공 하는 경우 로드 시간에 계산 되는 종속성 속성 다시 계산 된 식을 확인 하지 않아도 및 마지막 유효 값을 반환할 수 있습니다. 이 기술은 성능상의 이점을 수 있습니다.  
  
-   모든 소비자에 대 한 기본 리소스를 변경 하려면 또는 사용 하 여 각 소비자에 대 한 별도 쓰기 가능한 인스턴스를 유지 하려는 [x: 공유 특성](../../../../docs/framework/xaml-services/x-shared-attribute.md)합니다.  
  
#### <a name="static-resource-lookup-behavior"></a>정적 리소스 조회 동작  
  
1.  속성을 설정 하는 요소에 정의 된 리소스 사전 내에서 요청된 된 키에 대 한 조회 프로세스를 확인 합니다.  
  
2.  다음 조회 프로세스는 부모 요소와 해당 리소스 사전에 위로 논리적 트리를 이동 합니다. 이 루트 요소에 도달할 때까지 계속 됩니다.  
  
3.  다음으로, 응용 프로그램 리소스를 검사 합니다. 응용 프로그램 리소스에서 정의 된 리소스 사전 내에 있는 리소스는는 <xref:System.Windows.Application> 개체에 대 한 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  
  
 리소스 사전 내에서 정적 리소스 참조는 이미 정의 되어 있는 어휘 적으로 리소스 참조 하기 전에 리소스를 참조 해야 합니다. 전방 참조는 정적 리소스 참조로 확인할 수 없습니다. 이러한 이유로 정적 리소스 참조를 사용 하는 경우 디자인 해야 되도록 리소스 사전 구조에 또는 각 해당 리소스 사전의 시작 부분에 리소스에서 사용 하기 위한 리소스가 정의 됩니다.  
  
 정적 리소스 조회 테마 또는 시스템 리소스를 확장할 수 있지만 때문에이 기능이 지원는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로더에서 요청을 지연 합니다. 지연이는 런타임 테마 페이지 로드 시간에 응용 프로그램에 올바로 적용 되도록 해야만 됩니다. 그러나 정적 리소스 리소스 권장 되지 않는 시스템 또는 테마에만 있을 것으로 알려진 키에 대 한 참조입니다. 이러한 참조는 테마 실시간에 사용자에에서 의해 변경 되 면 다시 평가 되지 않기 때문입니다. 동적 리소스 참조 테마 또는 시스템 리소스를 요청 하는 경우 더 안정적입니다. 테마 요소 자체는 다른 리소스를 요청 하는 경우는 예외가입니다. 이러한 참조에는 앞에서 언급 한 이유 때문에 정적 리소스 참조 해야 합니다.  
  
 정적 리소스 참조는 없는 경우 예외 동작이 달라 집니다. 리소스 연기 된 경우 런타임에 예외가 발생 합니다. 리소스를 연기 되지 않으면 로드 시에는 예외가 발생 합니다.  
  
### <a name="dynamic-resources"></a>동적 리소스  
 동적 리소스는 다음과 같은 경우에 가장 적합 합니다.  
  
-   리소스의 값은 런타임 전에 알 수 없는 조건에 따라 달라 집니다. 시스템 리소스 또는 리소스를 설정할 수 있는 다른 경우 사용자가 포함 됩니다. 에 의해 노출 되는 대로 시스템 등록 정보를 참조 하는 setter 값을 만들 수는 예를 들어 <xref:System.Windows.SystemColors>, <xref:System.Windows.SystemFonts>, 또는 <xref:System.Windows.SystemParameters>합니다. 이러한 값은 궁극적으로 사용자 및 운영 체제의 런타임 환경에서 가져온 있기 때문에 진정으로 동적입니다. 페이지 수준의 리소스 액세스 해야 변경 내용을 캡처할 수도 변경 될 수 있는 응용 프로그램 수준 테마를 할 수 있습니다.  
  
-   만드는 지 아니면 테마 스타일 사용자 지정 컨트롤에 대 한 참조입니다.  
  
-   콘텐츠를 조정 하려는 <xref:System.Windows.ResourceDictionary> 응용 프로그램 수명 동안.  
  
-   전방 참조 필요할 수 있습니다 상호 종속성이 있는 복잡 한 리소스 구조가 해야 합니다. 정적 리소스 참조 전방 참조를 지원 하지 않는 동적 리소스 참조에서는 이러한 리소스 런타임 전에 평가할 필요가 없기 때문에 있고 전방 참조 되지 않으므로 관련 개념을 합니다.  
  
-   컴파일 또는 작업 집합의 관점에서 매우 큰 리소스를 참조 하 고 리소스 페이지가 로드 될 때 즉시 사용할 수 없습니다. 그러나 정적 리소스 참조에서 항상 로드 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지가 로드 될 때, 동적 리소스 참조를 로드 하지 않습니다는 실제로 사용 될 때까지 합니다.  
  
-   Setter 값으로 테마 또는 다른 사용자 설정에 영향을 받는 다른 값에서 수행할 수 있는 스타일을 만들게 됩니다.  
  
-   리소스를 적용 하는 응용 프로그램 수명 동안 논리적 트리에 부모가 재지정 될 수 있는 요소에 있습니다. 리소스 조회 범위를 변경 하는 부모를 잠재적으로 변경 되므로 새 범위를 기반으로 다시 평가 부모가 재지정된 된 요소에 대 한 리소스 하려면, 항상 사용 하세요 동적 리소스 참조.  
  
#### <a name="dynamic-resource-lookup-behavior"></a>동적 리소스 조회 동작  
 동적 리소스 참조에 대 한 리소스 조회 동작 호출 하는 경우 코드에서 조회 동작 기능과 유사한 <xref:System.Windows.FrameworkElement.FindResource%2A> 또는 <xref:System.Windows.FrameworkElement.SetResourceReference%2A>합니다.  
  
1.  속성을 설정 하는 요소에 정의 된 리소스 사전 내에서 요청된 된 키에 대 한 조회 프로세스를 확인 합니다.  
  
    -   요소를 정의 하는 경우는 <xref:System.Windows.FrameworkElement.Style%2A> 속성을는 <xref:System.Windows.Style.Resources%2A> 내에서 사전을 <xref:System.Windows.Style> 확인 됩니다.  
  
    -   요소를 정의 하는 경우는 <xref:System.Windows.Controls.Control.Template%2A> 속성을는 <xref:System.Windows.FrameworkTemplate.Resources%2A> 내에서 사전을 <xref:System.Windows.FrameworkTemplate> 확인 됩니다.  
  
2.  다음 조회 프로세스는 부모 요소와 해당 리소스 사전에 위로 논리적 트리를 이동 합니다. 이 루트 요소에 도달할 때까지 계속 됩니다.  
  
3.  다음으로, 응용 프로그램 리소스를 검사 합니다. 응용 프로그램 리소스에서 정의 된 리소스 사전 내에 있는 리소스는는 <xref:System.Windows.Application> 개체에 대 한 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  
  
4.  현재 테마에 대 한 테마 리소스 사전 확인 됩니다. 런타임 시 테마 변경 되 면 값이 다시 평가 합니다.  
  
5.  시스템 리소스를 검사 합니다.  
  
 예외 동작 (있는 경우)에 다음이 달라 집니다.  
  
-   리소스에서 요청한 경우는 <xref:System.Windows.FrameworkElement.FindResource%2A> 를 호출 하 고 찾을 수 없습니다, 예외가 발생 합니다.  
  
-   리소스에서 요청한 경우는 <xref:System.Windows.FrameworkElement.TryFindResource%2A> 를 호출 하 고 찾을 수 없습니다, 예외가 발생 하지만 반환된 된 값은 `null`합니다. 설정 되는 속성을 허용 하지 않는 경우 `null`, 것이 더 깊은 예외가 발생할 수 있습니다 (이에 따라 달라 집니다 설정 되는 개별 속성).  
  
-   동적 리소스 참조에 의해 리소스를 요청한 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 찾을 수 없는 다음 동작은 일반 속성 시스템에 따라 있으며 일반적인 동작은 것 처럼 속성 설정 작업이 발생 하지 않은 리소스가 있는 수준입니다. 예를 들어, 백그라운드에 설정 하려는 경우는 계산 될 수 있는 리소스를 사용 하 여 개별 단추 요소를 다음 값을 설정 하지 결과 얻으려면 하지만 유효 값은 계속 속성 시스템 및 값 우선 순위에 따라 다른 참가자 로부터 가져올 수 있습니다. 예를 들어, 배경 값 로컬로 정의 된 단추 스타일, 또는 테마 스타일에서에 여전히 가져올 수 있습니다. 테마 스타일에 의해 정의 되지 않은 속성에 대해 실패 한 리소스 평가 이후의 유효 값의 속성 메타 데이터의 기본 값에서 가져올 수 있습니다.  
  
#### <a name="restrictions"></a>제한 사항  
 동적 리소스 참조 몇 가지 주목할 만한 제한이 적용 됩니다. 다음 중 하나 이상 되어야 합니다.  
  
-   설정 되는 속성에 속성 이어야는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>합니다. 속성으로 백업 해야 하는 <xref:System.Windows.DependencyProperty>합니다.  
  
-   포함 된 값에 대 한 참조는는 <xref:System.Windows.Style><xref:System.Windows.Setter>합니다.  
  
-   설정 되는 속성에 속성 이어야 합니다는 <xref:System.Windows.Freezable> 의 값으로 제공 되는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 속성 또는 <xref:System.Windows.Setter> 값입니다.  
  
 설정 되는 속성 수 있어야 하므로 <xref:System.Windows.DependencyProperty> 또는 <xref:System.Windows.Freezable> 속성을 속성 시스템에서 속성 변경 (동적 리소스 변경 된 값)는 승인 하기 때문에 UI에 대부분의 속성 변경 내용을 전파할 수 있습니다. 대부분의 컨트롤을 컨트롤의 또 다른 레이아웃 하는 경우 강제로 논리를 포함 한 <xref:System.Windows.DependencyProperty> 변경 내용 및 속성 레이아웃에 영향을 줄 수 있습니다. 그러나 일부 속성이 있는 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) 값으로 UI에 실시간으로 업데이트 하는 방식으로 값을 제공 하도록 보장 합니다. 아직 해당 기능, 속성 또는 응용 프로그램의 논리 구조를 소유 하는 형식에 따라 뿐만 아니라 속성에 따라 달라질 수 있습니다.  
  
<a name="stylesimplicitkeys"></a>   
## <a name="styles-datatemplates-and-implicit-keys"></a>스타일, Datatemplate, 및 암시적 키  
 에 있는 모든 항목이 한다고 설명 했습니다 이전에 <xref:System.Windows.ResourceDictionary> 키가 있어야 합니다. 그러나 그렇다고 모든 리소스를 명시적가 있어야 `x:Key`합니다. 여러 개체 유형은 다른 속성 값의 키 값은 관련이 리소스로 정의 하는 경우 암시적 키를 지원 합니다. 로 알려져 암시적 키 반면는 `x:Key` 특성은 명시적 키입니다. 명시적 키를 지정 하 여 암시적 키를 덮어쓸 수 있습니다.  
  
 리소스에 대 한 매우 중요 한 시나리오는 정의 하는 경우는 <xref:System.Windows.Style>합니다. 실제로 <xref:System.Windows.Style> 거의 항상 스타일은 기본적으로 다시 사용할 수 있도록 만들어졌으므로 리소스 사전에 항목으로 정의 됩니다. 스타일에 대 한 자세한 내용은 참조 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)합니다.  
  
 컨트롤에 대 한 스타일 사용 하 여 만든와 암시적 키를 사용 하 여 참조 될 수 있습니다. 컨트롤의 기본 모양을 정의 하는 테마 스타일 암시적이 키에 의존 합니다. 요청 하의 관점에서 암시적 키는 <xref:System.Type> 컨트롤 자체의입니다. 리소스 정의의 관점에서 암시적 키는 <xref:System.Windows.Style.TargetType%2A> 스타일입니다. 따라서 사용자 지정 컨트롤에 대 한 테마를 만드는 경우 기존 테마 스타일과 상호 작용 하는 스타일을 만드는 필요가 없습니다 지정 하는 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md) 해당 <xref:System.Windows.Style>합니다. 및 테마가 지정 된 스타일을 사용 하려는 경우 필요가 없습니다 스타일을 지정 합니다. 예를 들어, 다음과 같은 스타일 정의 작동 하더라도 <xref:System.Windows.Style> 리소스 키가 같지 않습니다.  
  
 [!code-xml[FEResourceSH_snip#ImplicitStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]  
  
 스타일을가지고 키: 암시적 키 `typeof(` <xref:System.Windows.Controls.Button>`)`합니다. 태그를 지정할 수 있습니다는 <xref:System.Windows.Style.TargetType%2A> 형식으로 직접 이름을 (또는 선택적으로 사용할 수 있습니다 [{X:type...}](../../../../docs/framework/xaml-services/x-type-markup-extension.md) 반환 하는 <xref:System.Type>합니다.  
  
 사용 하는 기본 테마 스타일 메커니즘을 통해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 런타임 스타일의 스타일을 적용 하는 <xref:System.Windows.Controls.Button> 페이지에서 경우에는 <xref:System.Windows.Controls.Button> 지정 하려고 하지 않습니다 자체 해당 <xref:System.Windows.FrameworkElement.Style%2A> 속성 또는 스타일에 대 한 특정 리소스 참조 합니다. 페이지에 정의 된 스타일 테마 사전 스타일에 동일한 키를 사용 하 여 테마 사전 스타일 보다 이전 조회 시퀀스에서 먼저 발견 됩니다. 지정할 수 `<Button>Hello</Button>` 페이지 및으로 정의한 스타일의 모든 위치에서 <xref:System.Windows.Style.TargetType%2A> 의 `Button` 단추에 적용 됩니다. 동일한 형식 값을 갖는 스타일을 명시적으로 키를 <xref:System.Windows.Style.TargetType%2A>의 명확도 있지만 태그는 선택 사항에 대 한 합니다.  
  
 스타일에 대 한 암시적 키 하면 컨트롤에 적용 되지 않습니다 <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> 는 `true` (또한 <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> 대신 명시적으로 컨트롤의 인스턴스는 컨트롤 클래스에 대 한 기본 동작의 일부로 설정 될 수 있습니다). 또한 파생 된 클래스 시나리오에 대 한 암시적 키를 지원 하기 위해 컨트롤 재정의 해야 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> (의 일부로 제공 되는 모든 기존 컨트롤 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이렇게). 스타일, 테마 및 컨트롤 디자인에 대 한 자세한 내용은 참조 [디자인 스타일 컨트롤에 대 한 지침](../../../../docs/framework/wpf/controls/guidelines-for-designing-stylable-controls.md)합니다.  
  
 <xref:System.Windows.DataTemplate> 는 암시적 키도 있습니다. 에 대 한 암시적 키는 <xref:System.Windows.DataTemplate> 는 <xref:System.Windows.DataTemplate.DataType%2A> 속성 값입니다.                  <xref:System.Windows.DataTemplate.DataType%2A> 명시적으로 사용 하지 않고 형식의 이름으로 지정할 수도 있습니다 [{X:type...} ](../../../../docs/framework/xaml-services/x-type-markup-extension.md). 자세한 내용은 다음을 참조 하십시오. [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.ResourceDictionary>   
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [리소스 및 코드](../../../../docs/framework/wpf/advanced/resources-and-code.md)   
 [정의 및 리소스를 참조 합니다.](../../../../docs/framework/wpf/advanced/how-to-define-and-reference-a-resource.md)   
 [응용 프로그램 관리 개요](../../../../docs/framework/wpf/app-development/application-management-overview.md)   
 [X:type 태그 확장](../../../../docs/framework/xaml-services/x-type-markup-extension.md)   
 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)   
 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)