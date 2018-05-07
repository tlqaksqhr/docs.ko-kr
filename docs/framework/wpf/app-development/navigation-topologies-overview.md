---
title: 탐색 토폴로지 개요
ms.date: 03/30/2017
helpviewer_keywords:
- linear topology [WPF]
- fixed hierarchical topology [WPF]
- fixed linear topology [WPF]
- topologies [WPF]
- navigation topologies [WPF]
- dynamically-generated topology
ms.assetid: 5d5ee837-629a-4933-869a-186dc22ac43d
ms.openlocfilehash: 8976ba7973e4f53022846b98c47d5613fd6ba158
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="navigation-topologies-overview"></a>탐색 토폴로지 개요
<a name="introduction"></a> 이 개요에서는의 탐색 토폴로지 소개 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]합니다. 세 가지 일반적인 탐색 토폴로지를 샘플과 함께 차례로 설명합니다.  
  
> [!NOTE]
>  이 항목을 읽기 전에 구조적된 탐색에 대 한 개념을 잘 알고 있어야 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 페이지 함수를 사용 하 여 합니다. 이 항목에 대 한 자세한 내용은 참조 하십시오. [구조적 탐색 개요](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [탐색 토폴로지](#Navigation_Topologies)  
  
-   [구조적 탐색 토폴로지](#Structured_Navigation_Topologies)  
  
-   [고정 선형 토폴로지 탐색](#Navigation_over_a_Fixed_Linear_Topology)  
  
-   [고정 계층적 토폴로지 동적 탐색](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
-   [동적으로 생성된 토폴로지 탐색](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>   
## <a name="navigation-topologies"></a>탐색 토폴로지  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 탐색 페이지의 일반적으로 구성 됩니다 (<xref:System.Windows.Controls.Page>)를 하이퍼링크로 (<xref:System.Windows.Documents.Hyperlink>) 클릭 하면 다른 페이지로 이동 하는 합니다. 페이지를 탐색 하 여 식별 됩니다 [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] (참조 [WPF의 Pack Uri](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)). 페이지, 하이퍼링크를 보여 주는 다음의 간단한 예제를 고려해 야 하 고 [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]:  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 이러한 페이지에 정렬 되는 *탐색 토폴로지* 토폴로지 구조 페이지 간에 탐색 방법에 의해 결정 됩니다. 이 특정 탐색 토폴로지는 간단한 시나리오에 적합하지만 탐색은 더 복잡한 토폴로지를 필요로 하며 그중 일부는 응용 프로그램이 실행 중일 때만 정의할 수 있습니다.  
  
 이 항목에서는 일반적인 세 가지 탐색 토폴로지: *고정 선형*, *고정 된 계층적*, 및 *동적으로 생성 된*합니다. 각 탐색 토폴로지 나와 있는 샘플에는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 다음 그림과 같이:  
  
 ![데이터 항목이 있는 작업 페이지](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure6.png "NavigationTopologyFigure6")  
  
<a name="Structured_Navigation_Topologies"></a>   
## <a name="structured-navigation-topologies"></a>구조적 탐색 토폴로지  
 탐색 토폴로지는 광범위하게 두 가지로 구분됩니다.  
  
-   **고정 토폴로지**: 컴파일 시 정의되며 런타임 시 변경되지 않습니다. 고정 토폴로지는 선형 순서 또는 계층적 순서로 고정된 페이지 시퀀스를 탐색하는 데 유용합니다.  
  
-   **동적 토폴로지**: 사용자, 응용 프로그램 또는 시스템에서 수집한 입력을 기반으로 런타임 시 정의됩니다. 동적 토폴로지는 페이지를 다른 시퀀스로 탐색할 수 있을 때 유용합니다.  
  
 페이지를 사용하여 탐색 토폴로지를 만들 수도 있지만 샘플에서는 페이지 함수를 사용하는데 이 기능이 토폴로지의 페이지를 통해 데이터를 전달하고 반환하는 지원을 단순화하는 추가 지원을 제공하기 때문입니다.  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>   
## <a name="navigation-over-a-fixed-linear-topology"></a>고정 선형 토폴로지 탐색  
 고정 선형 토폴로지는 고정된 시퀀스로 탐색되는 하나 이상의 마법사 페이지가 있는 마법사의 구조와 유사합니다. 다음 그림에서는 고정 선형 토폴로지를 사용하는 마법사의 상위 수준 구조와 흐름을 보여 줍니다.  
  
 ![탐색 토폴로지 다이어그램](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure1.png "NavigationTopologyFigure1")  
  
 고정 선형 토폴로지를 탐색하는 일반적인 동작은 다음과 같습니다.  
  
-   호출 페이지에서 마법사를 초기화하고 첫 번째 마법사 페이지로 이동하는 시작 프로그램 페이지로 이동합니다. 시작 관리자 페이지 (한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-덜 <xref:System.Windows.Navigation.PageFunction%601>) 호출 페이지는 마법사의 첫 번째 페이지를 직접 호출할 수 있으므로, 필요 하지 않습니다. 그러나 시작 페이지를 사용하면 특히 초기화가 복잡한 경우 마법사 초기화를 단순화할 수 있습니다.  
  
-   사용자는 뒤로 및 앞으로 단추(또는 하이퍼링크)를 사용하여 페이지 사이를 탐색할 수 있습니다.  
  
-   사용자는 저널을 사용하여 페이지 간을 이동할 수 있습니다.  
  
-   사용자는 [취소] 단추를 눌러 마법사 페이지에서 마법사를 취소할 수 있습니다.  
  
-   사용자는 [마침] 단추를 눌러 마지막 마법사 페이지에서 마법사를 승인할 수 있습니다.  
  
-   마법사가 취소되면 적절한 결과를 반환하며 데이터는 반환하지 않습니다.  
  
-   사용자가 마법사를 승인하면 마법사가 적절한 결과와 수집한 데이터를 반환합니다.  
  
-   마법사가 완료되면(승인 또는 취소) 마법사가 구성하는 페이지가 저널에서 제거됩니다. 이렇게 하면 마법사의 각 인스턴스가 격리되어 잠재적인 데이터 또는 비정상 상태를 피할 수 있습니다.  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>   
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a>고정 계층적 토폴로지 동적 탐색  
 일부 응용 프로그램에서는 다음 그림과 같이 페이지에서 두 개 이상의 다른 페이지를 탐색할 수 있습니다.  
  
 ![여러 페이지를 탐색할 수 있는 페이지](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure2.png "NavigationTopologyFigure2")  
  
 이 구조는 고정 계층적 토폴로지로 알려져 있으며 계층 구조가 통과되는 시퀀스는 종종 응용 프로그램이나 사용자에 의해 런타임 시 결정됩니다. 런타임 시 두 개 이상의 다른 페이지를 탐색할 수 있는 계층 구조의 각 페이지는 탐색할 페이지를 결정하는 데 필요한 데이터를 수집합니다. 다음 그림은 앞의 그림을 기반으로 몇 가지 가능한 탐색 시퀀스 중 하나를 보여 줍니다.  
  
 ![탐색 토폴로지 다이어그램](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure3.png "NavigationTopologyFigure3")  
  
 고정 계층적 구조의 페이지를 탐색하는 시퀀스가 런타임에 결정되더라도 사용자 환경은 고정 선형 토폴로지의 사용자 환경과 동일합니다.  
  
-   호출 페이지에서 마법사를 초기화하고 첫 번째 마법사 페이지로 이동하는 시작 프로그램 페이지로 이동합니다. 시작 관리자 페이지 (한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-덜 <xref:System.Windows.Navigation.PageFunction%601>) 호출 페이지는 마법사의 첫 번째 페이지를 직접 호출할 수 있으므로, 필요 하지 않습니다. 그러나 시작 페이지를 사용하면 특히 초기화가 복잡한 경우 마법사 초기화를 단순화할 수 있습니다.  
  
-   사용자는 뒤로 및 앞으로 단추(또는 하이퍼링크)를 사용하여 페이지 사이를 탐색할 수 있습니다.  
  
-   사용자는 저널을 사용하여 페이지 간을 이동할 수 있습니다.  
  
-   사용자는 저널을 탐색할 때 탐색 시퀀스를 변경할 수 있습니다.  
  
-   사용자는 [취소] 단추를 눌러 마법사 페이지에서 마법사를 취소할 수 있습니다.  
  
-   사용자는 [마침] 단추를 눌러 마지막 마법사 페이지에서 마법사를 승인할 수 있습니다.  
  
-   마법사가 취소되면 적절한 결과를 반환하며 데이터는 반환하지 않습니다.  
  
-   사용자가 마법사를 승인하면 마법사가 적절한 결과와 수집한 데이터를 반환합니다.  
  
-   마법사가 완료되면(승인 또는 취소) 마법사가 구성하는 페이지가 저널에서 제거됩니다. 이렇게 하면 마법사의 각 인스턴스가 격리되어 잠재적인 데이터 또는 비정상 상태를 피할 수 있습니다.  
  
<a name="Navigation_over_a_Dynamically_Generated_Topology"></a>   
## <a name="navigation-over-a-dynamically-generated-topology"></a>동적으로 생성된 토폴로지 탐색  
 일부 응용 프로그램에서 두 개 이상의 페이지를 탐색하는 시퀀스는 런타임 시 사용자, 응용 프로그램 또는 외부 데이터에 의해서만 결정될 수 있습니다. 다음 그림은 탐색 시퀀스가 결정되지 않은 페이지 집합을 보여 줍니다.  
  
 ![탐색 토폴로지 다이어그램](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure4.png "NavigationTopologyFigure4")  
  
 다음 그림은 런타임 시 사용자가 선택한 탐색 시퀀스를 보여 줍니다.  
  
 ![탐색 다이어그램](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure5.png "NavigationTopologyFigure5")  
  
 탐색 시퀀스를 동적으로 생성된 토폴로지라고 합니다. 다른 탐색 토폴로지와 마찬가지로 사용자의 환경은 이전 토폴로지의 경우와 같습니다.  
  
-   호출 페이지에서 마법사를 초기화하고 첫 번째 마법사 페이지로 이동하는 시작 프로그램 페이지로 이동합니다. 시작 관리자 페이지 (한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-덜 <xref:System.Windows.Navigation.PageFunction%601>) 호출 페이지는 마법사의 첫 번째 페이지를 직접 호출할 수 있으므로, 필요 하지 않습니다. 그러나 시작 페이지를 사용하면 특히 초기화가 복잡한 경우 마법사 초기화를 단순화할 수 있습니다.  
  
-   사용자는 뒤로 및 앞으로 단추(또는 하이퍼링크)를 사용하여 페이지 사이를 탐색할 수 있습니다.  
  
-   사용자는 저널을 사용하여 페이지 간을 이동할 수 있습니다.  
  
-   사용자는 [취소] 단추를 눌러 마법사 페이지에서 마법사를 취소할 수 있습니다.  
  
-   사용자는 [마침] 단추를 눌러 마지막 마법사 페이지에서 마법사를 승인할 수 있습니다.  
  
-   마법사가 취소되면 적절한 결과를 반환하며 데이터는 반환하지 않습니다.  
  
-   사용자가 마법사를 승인하면 마법사가 적절한 결과와 수집한 데이터를 반환합니다.  
  
-   마법사가 완료되면(승인 또는 취소) 마법사가 구성하는 페이지가 저널에서 제거됩니다. 이렇게 하면 마법사의 각 인스턴스가 격리되어 잠재적인 데이터 또는 비정상 상태를 피할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Navigation.PageFunction%601>  
 <xref:System.Windows.Navigation.NavigationService>  
 [구조적 탐색 개요](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)
