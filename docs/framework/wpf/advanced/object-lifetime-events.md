---
title: 개체 수명 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- events [WPF], ContentRendered
- events [WPF], Deactivated
- events [WPF], Unloaded
- Activated events [WPF]
- events [WPF], Loaded
- Application objects [WPF], lifetime events
- events [WPF], Activated
- ContentRendered events [WPF]
- Deactivated events [WPF]
- events [WPF], Initialized
- events [WPF], Closing
- Unloaded events [WPF]
- exit events [WPF]
- objects' lifetime events [WPF]
- Loaded events [WPF]
- Closing events [WPF]
- events [WPF], Closed
- Initialized events [WPF]
- Closed events [WPF]
- startup events [WPF]
- lifetime events of objects [WPF]
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
ms.openlocfilehash: 02a6736fe54be4683044f648e9d5ed5e8a3d95dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="object-lifetime-events"></a>개체 수명 이벤트
이 항목에서는 생성, 사용 및 소멸 등의 개체 수명 단계를 나타내는 특정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트에 대해 설명합니다.  
  

  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스의 기존 종속성 속성의 소비자 관점에서 종속성 속성을 이해하고 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) 항목을 읽었다고 가정합니다. 이 항목의 예제를 따르려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ([XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) 참조)과 함께 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 작성하는 방법을 알아야 합니다.  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>개체 수명 이벤트  
 Microsoft.NET Framework 관리 코드의 모든 개체는 유사한 여러 수명, 생성, 사용 및 소멸의 단계를 통해 이동합니다. 또한 많은 개체에는 소멸 단계의 일부로 발생하는 종료 단계가 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개체, 특히 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 요소로 식별하는 시각적 개체에는 개체 수명의 공통 단계 집합이 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그래밍 및 응용 프로그램 모델은 이러한 단계를 일련의 이벤트로 노출합니다. 수명 이벤트와 관련하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 일반적인 요소, 창 요소, 탐색 호스트 및 응용 프로그램 개체 등 네 가지 기본 유형의 개체가 있습니다. Windows 및 탐색 호스트도 시각적 개체(요소)의 더 큰 그룹에 속합니다. 이 항목에서는 모든 요소에 공통적으로 적용되는 수명 이벤트에 대해 설명한 다음 응용 프로그램 정의, 창 또는 탐색 호스트에 적용되는 특정 이벤트를 소개합니다.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>요소에 대한 공통 수명 이벤트  
 모든 WPF 프레임 워크 수준 요소 (해당 개체에서 파생 되 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>)에 세 가지 일반적인 수명을 이벤트가: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>, 및 <xref:System.Windows.FrameworkElement.Unloaded>합니다.  
  
### <a name="initialized"></a>초기화됨  
 <xref:System.Windows.FrameworkElement.Initialized> 먼저 발생 하 고 해당 생성자를 호출 하 여 개체의 초기화에 해당 합니다. 이 이벤트는 초기화에 응답하여 발생하므로 이 이벤트가 발생하면 개체의 모든 속성이 설정되어 있음을 알 수 있습니다 동적 리소스나 바인딩과 같은 식 사용의 경우는 예외입니다. 이러한 식은 평가되지 않은 식이 됩니다. 요구 사항이 모든 속성을 설정 하는 순서에 따라 <xref:System.Windows.FrameworkElement.Initialized> 먼저, 가장 깊은 요소 요소 트리에 있는 순서 대로 발생가 태그에 정의 된 중첩 된 요소에 의해 발생 하는 루트를 향해 부모 요소의 합니다. 순서가 이와 같은 이유는 부모/자식 관계와 포함이 속성이고 따라서 부모는 속성을 채우는 자식 요소 또한 완전히 초기화되기 전에는 초기화를 보고할 수 없기 때문입니다.  
  
 처리기에 대 한 응답에서에 작성 하는 경우는 <xref:System.Windows.FrameworkElement.Initialized> 이벤트를 고려해 야 하는 처리기가 연결 된 주위 요소 트리 (논리적 트리 또는 시각적 트리)의 다른 모든 요소를 만든 특히 하지 않을 수도 있다는 것 부모 요소입니다. 멤버 변수가 null일 수 있거나 식 수준에서도 데이터 소스가 기본 바인딩으로 채워지지 않을 수도 있습니다.  
  
### <a name="loaded"></a>로드됨  
 <xref:System.Windows.FrameworkElement.Loaded> 다음 발생 합니다. <xref:System.Windows.FrameworkElement.Loaded> 최종 렌더링 되기 전에 되지만 레이아웃 시스템 렌더링에 필요한 모든 값에서 계산 된 후 발생 합니다. <xref:System.Windows.FrameworkElement.Loaded> 요소 내에 포함 된 논리적 트리에서 완료 되며 HWND 및 표면 렌더링을 제공 하는 프레젠테이션 소스에 연결 하는 과정이 수반 됩니다. 표준 데이터 바인딩 (다른 속성 또는 직접 정의 된 데이터 원본 등의 로컬 소스에 바인딩) 이전에 발생 됩니다 <xref:System.Windows.FrameworkElement.Loaded>합니다. 비동기 데이터 바인딩(외부 또는 동적 소스)이 발생할 수도 있지만 비동기라는 용어에서 유추할 수 있듯이 그 발생 여부를 보장할 수는 없습니다.  
  
 메커니즘은는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트는 다른 <xref:System.Windows.FrameworkElement.Initialized>합니다. <xref:System.Windows.FrameworkElement.Initialized> 이벤트는 전체 요소 트리의 하 여 직접 조정 하지 않는 요소에 의해 발생된 요소입니다. 반면,는 <xref:System.Windows.FrameworkElement.Loaded> 트리 전체에서 전체 요소 (특히, 논리 트리) 중재 이벤트가 발생 합니다. 고려 되는 상태 로드 하는 트리의 모든 요소는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트는 루트 요소에서 먼저 발생 합니다. <xref:System.Windows.FrameworkElement.Loaded> 각 자식 요소에 대해 이벤트가 연속 해 서 발생 합니다.  
  
> [!NOTE]
>  이 동작은 표면적으로 볼 때 라우트된 이벤트의 터널링과 유사할 수 있습니다. 그러나 이벤트 간에 정보가 전달되지 않습니다. 각 요소에는 항상 처리 하는 해당 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 및 이벤트 데이터를 처리 된 것으로 표시에 해당 요소가 아닌 영향을 주지 않습니다.  
  
### <a name="unloaded"></a>언로드됨  
 <xref:System.Windows.FrameworkElement.Unloaded> 마지막 발생 하 고 프레젠테이션 소스 또는 제거 하 고 시각적 부모 중 하나에 의해 시작 됩니다. 때 <xref:System.Windows.FrameworkElement.Unloaded> 발생 하 고 처리 된 이벤트 소스 부모 요소의 (기준으로 <xref:System.Windows.FrameworkElement.Parent%2A> 속성) 또는 논리 또는 시각적 트리 위쪽에 있는 지정 된 요소가 이미 했을 수 있습니다 설정, 리소스 참조 데이터 바인딩을 지를 의미 합니다. 스타일 또는 마지막 알려진된 실행 시간 값으로 설정할 수 있습니다.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>수명 이벤트 응용 프로그램 모델 요소  
 요소는 다음과 같은 응용 프로그램 모델 요소에 대 한 일반적인 수명 이벤트에서 빌드: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, 및 <xref:System.Windows.Controls.Frame>합니다. 이러한 요소는 특정 목적과 관련된 추가 이벤트를 사용하여 공통 개체 수명 이벤트를 확장합니다. 다음 항목에서 이에 대해 자세히 설명합니다.  
  
-   <xref:System.Windows.Application>: [응용 프로그램 관리 개요](../../../../docs/framework/wpf/app-development/application-management-overview.md)합니다.  
  
-   <xref:System.Windows.Window>: [WPF Windows 개요](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)합니다.  
  
-   <xref:System.Windows.Controls.Page><xref:System.Windows.Navigation.NavigationWindow>, 및 <xref:System.Windows.Controls.Frame>: [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
