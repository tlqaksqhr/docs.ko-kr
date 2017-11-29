---
title: "WPF 추가 기능 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add-ins and XAML browser applications [WPF]
- add-ins overview [WPF]
- add-ins [WPF], performance
- add-ins [WPF], benefits
- .NET Framework add-in model [WPF]
- add-ins [WPF], user interface
- add-ins and the user interface [WPF]
- add-ins [WPF], architecture
- add-ins [WPF], limitations
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 290682542a0accaf38408127f7358625abca14af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="wpf-add-ins-overview"></a>WPF 추가 기능 개요
<a name="Introduction"></a> [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에는 개발자가 추가 기능 확장성을 지원하는 응용 프로그램을 만드는 데 사용할 수 있는 추가 기능 모델이 포함되어 있습니다. 이 추가 기능 모델을 사용하면 응용 프로그램 기능과 통합하고 이 기능을 확장하는 추가 기능을 만들 수 있습니다. 일부 시나리오에서는 응용 프로그램에서 추가 기능을 통해 제공되는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]도 표시해야 합니다. 이 항목에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]가 이러한 시나리오를 가능하게 하는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델을 보강하는 방법, 그 기반이 되는 아키텍처, 해당 이점 및 한계를 보여줍니다.  
  

  
<a name="Requirements"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델에 대해 잘 알고 있어야 합니다. 자세한 내용은 [추가 기능 및 확장성](../../../../docs/framework/add-ins/index.md)을 참조하세요.  
  
<a name="AddInsOverview"></a>   
## <a name="add-ins-overview"></a>추가 기능 개요  
 응용 프로그램에서는 새 기능을 통합하기 위해 응용 프로그램을 다시 컴파일하여 배포하는 복잡한 작업을 방지하도록 확장성 메커니즘을 구현하여 개발자(자사 및 타사)가 새 기능을 통합하는 다른 응용 프로그램을 만들 수 있도록 합니다. 이러한 형식의 확장성을 지원하는 가장 일반적인 방법은 추가 기능(“추가 기능” 및 “플러그 인”이라고도 함)을 사용하는 것입니다. 추가 기능으로 확장성을 노출하는 실제 응용 프로그램의 예에는 다음이 있습니다.  
  
-   Internet Explorer 추가 기능.  
  
-   Windows Media Player 플러그 인.  
  
-   Visual Studio 추가 기능.  
  
 예를 들어, Windows Media Player 추가 기능 모델을 사용하면 타사 개발자가 다양한 방식으로 Windows Media Player를 확장하는 “플러그 인”을 구현할 수 있습니다. 이러한 방식에는 Windows Media Player에서 기본적으로 지원하지 않는 미디어 형식(예: DVD, MP3)의 디코더와 인코더, 오디오 효과 및 스킨이 포함됩니다. 모든 추가 기능 모델에 공통인 동작과 엔터티가 여러 개 있지만, 각 추가 기능 모델은 응용 프로그램에 고유한 기능을 노출하도록 빌드되어 있습니다.  
  
 일반적인 추가 기능 확장성 솔루션의 세 가지 기본 엔터티는 *계약*, *추가 기능* 및 *호스트 응용 프로그램*입니다. 계약은 추가 기능이 다음 두 방법으로 호스트 응용 프로그램과 통합하는 방법을 정의합니다.  
  
-   추가 기능은 호스트 응용 프로그램으로 구현된 기능과 통합됩니다.  
  
-   호스트 응용 프로그램에서 추가 기능과 통합될 기능을 노출합니다.  
  
 추가 기능을 사용하려면 호스트 응용 프로그램에서 해당 기능을 찾아 런타임 시 로드해야 합니다. 따라서 추가 기능을 지원하는 응용 프로그램에서는 다음과 같은 추가 작업을 담당합니다.  
  
-   **검색**: 호스트 응용 프로그램에서 지원하는 계약을 준수하는 추가 기능 찾기.  
  
-   **활성화**: 추가 기능과의 통신을 로드, 실행 및 설정.  
  
-   **격리**: 응용 프로그램 도메인 또는 프로세스를 사용하여 추가 기능의 잠재적인 보안 및 실행 문제로부터 응용 프로그램을 보호하는 격리 경계 설정.  
  
-   **통신**: 추가 기능과 호스트 응용 프로그램을 통해 메서드를 호출하고 데이터를 전달하여 격리 경계를 넘어 서로 통신할 수 있도록 허용.  
  
-   **수명 관리**: 예측 가능하고 정리된 방식으로 응용 프로그램 도메인과 프로세스를 로드 및 언로드( [응용 프로그램 도메인](../../../../docs/framework/app-domains/application-domains.md) 참조).  
  
-   **버전 관리**: 호스트 응용 프로그램과 추가 기능 중 하나의 새 버전이 만들어진 경우에도 계속 통신 가능한지 확인.  
  
 근본적으로, 강력한 추가 기능 모델을 개발하는 것은 쉬운 작업이 아닙니다. 따라서 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 추가 기능 모델을 빌드하는 인프라를 제공합니다.  
  
> [!NOTE]
>  추가 기능에 대한 자세한 내용은 [추가 기능 및 확장성](../../../../docs/framework/add-ins/index.md)을 참조하세요.  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## <a name="net-framework-add-in-model-overview"></a>.NET Framework 추가 기능 모델 개요  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델에는 <xref:System.AddIn> 네임 스페이스를 추가 기능에서 확장성의 배포를 단순화 하도록 설계 된 형식 집합을 포함 합니다. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델의 기본 단위는 호스트 응용 프로그램과 추가 기능이 서로 통신하는 방법을 정의하는 *계약*입니다. 계약은 계약의 호스트-응용 프로그램별 *보기*를 사용하여 호스트 응용 프로그램에 노출됩니다. 마찬가지로 계약의 추가 기능별 *보기*가 추가 기능에 노출됩니다. 호스트 응용 프로그램과 추가 기능이 계약의 각 보기 간에 통신할 수 있도록 *어댑터*가 사용됩니다. 계약, 보기 및 어댑터를 세그먼트라고 하며, 관련 세그먼트 집합이 *파이프라인*을 구성합니다. 파이프라인은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델이 검색, 활성화, 보안 격리, 실행 격리(응용 프로그램 도메인과 프로세스를 모두 사용), 통신, 수명 관리 및 버전 관리를 지원하는 기반입니다.  
  
 개발자는 이러한 지원을 모두 활용하여 호스트 응용 프로그램의 기능과 통합하는 추가 기능을 빌드할 수 있습니다. 그러나 일부 시나리오에서는 호스트 응용 프로그램이 추가 기능에서 제공하는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 표시해야 합니다. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 각 프레젠테이션 기술에는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 구현하는 고유 모델이 있으므로 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델에서는 어떠한 특정 프레젠테이션 기술도 지원하지 않습니다. 대신 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 추가 기능에 대한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 지원을 사용하여 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델을 확장합니다.  
  
<a name="WPFAddInModel"></a>   
## <a name="wpf-add-ins"></a>WPF 추가 기능  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델과 함께 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 사용하면 호스트 응용 프로그램이 추가 기능의 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 표시해야 하는 다양한 시나리오를 처리할 수 있습니다. 특히 다음 두 프로그래밍 모델을 사용하면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]로 이러한 시나리오를 처리할 수 있습니다.  
  
1.  **추가 기능이 UI를 반환함**. 추가 기능에서 계약에 정의된 대로 메서드 호출을 통해 호스트 응용 프로그램에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 반환합니다. 이 시나리오는 다음과 같은 경우에 사용됩니다.  
  
    -   추가 기능에서 반환하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 모양은 동적으로 생성되는 보고서와 같이 런타임 시에만 존재하는 조건 또는 데이터에 따라 달라집니다.  
  
    -   추가 기능에서 제공하는 서비스의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 추가 기능을 사용할 수 있는 호스트 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와 다릅니다.  
  
    -   추가 기능은 주로 호스트 응용 프로그램의 서비스를 수행하며, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 사용하여 호스트 응용 프로그램에 상태를 보고합니다.  
  
2.  **추가 기능이 UI임**. 추가 기능은 계약에 정의된 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]입니다. 이 시나리오는 다음과 같은 경우에 사용됩니다.  
  
    -   추가 기능에서 광고와 같이 표시되고 있지 않은 서비스를 제공하지 않는 경우.  
  
    -   추가 기능에서 제공하는 서비스의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 계산기 또는 색 선택과 같은 추가 기능을 사용할 수 있는 모든 호스트 응용 프로그램에 공통적으로 나타나는 경우.  
  
 이러한 시나리오에서는 호스트 응용 프로그램과 추가 기능 응용 프로그램 도메인 간에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 개체를 전달할 수 있어야 합니다. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델은 원격을 이용하여 응용 프로그램 도메인 간에 통신하므로, 두 도메인 간에 전달되는 개체는 원격으로 사용 가능해야 합니다.  
  
 원격으로 사용 가능한 개체는 다음 중 하나 이상을 수행하는 클래스의 인스턴스입니다.  
  
-   파생 되는 <xref:System.MarshalByRefObject> 클래스입니다.  
  
-   <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현합니다.  
  
-   에 <xref:System.SerializableAttribute> 특성이 적용 합니다.  
  
> [!NOTE]
>  원격으로 사용 가능한 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 개체 만들기에 대한 자세한 내용은 [개체를 원격으로 사용 가능하도록 설정](http://msdn.microsoft.com/en-us/01197253-3f13-43b7-894d-9683e431192a)을 참조하세요.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 형식은 원격으로 사용할 수 없습니다. 문제점을 해결하기 위해 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델을 확장하여 추가 기능을 통해 만들어진 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 호스트 응용 프로그램에서 표시할 수 있게 합니다. 이 지원은가 제공 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 두 유형을 통해:는 <xref:System.AddIn.Contract.INativeHandleContract> 인터페이스 및 두 개의 정적 메서드를 구현한는 <xref:System.AddIn.Pipeline.FrameworkElementAdapters> 클래스: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 및 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>합니다. 상위 수준에서는 대략적으로 이러한 형식과 메서드가 다음과 같은 방식으로 사용됩니다.  
  
1.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]사용 하려면 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 제공한 추가 기능에서 직접 또는 간접적으로 파생 된 클래스는 <xref:System.Windows.FrameworkElement>, 셰이프, 컨트롤, 사용자 정의 컨트롤, 레이아웃 패널 및 페이지 등.  
  
2.  UI를 추가 하 고 호스트 응용 프로그램 간에 전달 되는 선언 하는 계약, 때마다로 선언 되어야 합니다는 <xref:System.AddIn.Contract.INativeHandleContract> (하지는 <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> 추가 기능에 대 한 원격 가능 표현인 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 격리 경계를 넘어 전달할 수 있습니다.  
  
3.  응용 프로그램 도메인에 대 한 추가 기능에서 전달 되기 전에 <xref:System.Windows.FrameworkElement> 로 패키지 한 <xref:System.AddIn.Contract.INativeHandleContract> 호출 하 여 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>합니다.  
  
4.  호스트 응용 프로그램의 응용 프로그램 도메인에 전달 된 후의 <xref:System.AddIn.Contract.INativeHandleContract> 로 다시 패키지는 <xref:System.Windows.FrameworkElement> 호출 하 여 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>합니다.  
  
 어떻게 <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, 및 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 사용 되는 특정 시나리오에 따라 달라 집니다. 다음 섹션에서는 각 프로그래밍 모델의 자세한 내용을 제공합니다.  
  
<a name="ReturnUIFromAddInContract"></a>   
## <a name="add-in-returns-a-user-interface"></a>추가 기능이 사용자 인터페이스를 반환함  
 추가 기능이 호스트 응용 프로그램에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 반환하려면 다음이 필요합니다.  
  
1.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [추가 기능 및 확장성](../../../../docs/framework/add-ins/index.md) 문서에 설명된 대로 호스트 응용 프로그램, 추가 기능 및 파이프라인을 만들어야 합니다.  
  
2.  계약을 구현 해야 <xref:System.AddIn.Contract.IContract> 고 반환 하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 계약 형식의 반환 값을 사용 하 여 메서드를 선언 해야 <xref:System.AddIn.Contract.INativeHandleContract>합니다.  
  
3.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 전달 되는 추가 기능과 호스트 간의 응용 프로그램 직접 또는 간접적으로에서 파생 되어야 <xref:System.Windows.FrameworkElement>합니다.  
  
4.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 에서 반환 하는 추가 기능에서 변환 해야는 <xref:System.Windows.FrameworkElement> 에 <xref:System.AddIn.Contract.INativeHandleContract> 격리 경계를 통과 하기 전에.  
  
5.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 에서 변환 해야 반환 되는 프로그램 <xref:System.AddIn.Contract.INativeHandleContract> 에 <xref:System.Windows.FrameworkElement> 격리 경계를 통과 한 후 합니다.  
  
6.  호스트 응용 프로그램은 반환 된 표시 <xref:System.Windows.FrameworkElement>합니다.  
  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 반환하는 추가 기능을 구현하는 방법을 설명하는 예는 [UI를 반환하는 추가 기능 만들기](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)를 참조하세요.  
  
<a name="AddInIsAUI"></a>   
## <a name="add-in-is-a-user-interface"></a>추가 기능이 사용자 인터페이스임  
 추가 기능이 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]이면 다음이 필요합니다.  
  
1.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [추가 기능 및 확장성](../../../../docs/framework/add-ins/index.md) 문서에 설명된 대로 호스트 응용 프로그램, 추가 기능 및 파이프라인을 만들어야 합니다.  
  
2.  추가 기능에 대 한 계약 인터페이스를 구현 해야 <xref:System.AddIn.Contract.INativeHandleContract>합니다.  
  
3.  호스트 응용 프로그램에 전달 되는 추가 기능에 직접 또는 간접적으로에서 파생 되어야 <xref:System.Windows.FrameworkElement>합니다.  
  
4.  추가 기능에서 변환 해야는 <xref:System.Windows.FrameworkElement> 에 <xref:System.AddIn.Contract.INativeHandleContract> 격리 경계를 통과 하기 전에.  
  
5.  추가 기능에서 변환 해야는 <xref:System.AddIn.Contract.INativeHandleContract> 에 <xref:System.Windows.FrameworkElement> 격리 경계를 통과 한 후 합니다.  
  
6.  호스트 응용 프로그램은 반환 된 표시 <xref:System.Windows.FrameworkElement>합니다.  
  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]인 추가 기능을 구현하는 방법을 설명하는 예는 [UI인 추가 기능 만들기](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-is-a-ui.md)를 참조하세요.  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## <a name="returning-multiple-uis-from-an-add-in"></a>추가 기능에서 여러 UI 반환  
 추가 기능에서 표시할 호스트 응용 프로그램을 위해 여러 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 제공하는 경우가 많습니다. 예를 들어, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]인 추가 기능이 호스트 응용 프로그램에 상태 정보도 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]로 제공하는 경우가 있습니다. 이와 같은 추가 기능은 [추가 기능이 사용자 인터페이스를 반환함](#ReturnUIFromAddInContract) 및 [추가 기능이 사용자 인터페이스임](#AddInIsAUI) 모델의 기술을 조합하여 구현할 수 있습니다.  
  
<a name="AddInsAndXBAPs"></a>   
## <a name="add-ins-and-xaml-browser-applications"></a>추가 기능 및 XAML 브라우저 응용 프로그램  
 지금까지의 예에서는 호스트 응용 프로그램이 독립형 응용 프로그램으로 설치되었습니다. 다음과 같은 추가 빌드 및 구현 요구 사항이 있긴 하지만 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]에서도 추가 기능을 호스팅할 수 있습니다.  
  
-   클라이언트 컴퓨터에서 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]와 동일한 폴더의 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] 응용 프로그램 캐시에 파이프라인(폴더 및 어셈블리) 및 추가 기능 어셈블리를 다운로드하도록 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 응용 프로그램 매니페스트를 특별히 구성해야 합니다.  
  
-   추가 기능을 검색하고 로드하는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 코드가 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]의 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 응용 프로그램 캐시를 파이프라인과 추가 기능 위치로 사용해야 합니다.  
  
-   추가 기능이 원본 사이트에 있는 느슨한 파일을 참조하는 경우 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]는 특수 보안 컨텍스트에 추가 기능을 로드해야 합니다. 추가 기능이 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]에서 호스팅된 경우 이러한 추가 기능은 호스트 응용 프로그램의 원본 사이트에 있는 느슨한 파일만 참조할 수 있습니다.  
  
 이러한 작업은 다음 하위 섹션에 자세히 설명되어 있습니다.  
  
### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>ClickOnce 배포를 위한 파이프라인 및 추가 기능 구성  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]는 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 배포 캐시의 안전한 폴더로 다운로드되고 이 폴더에서 실행됩니다. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]가 추가 기능을 호스트하려면 파이프라인과 추가 기능 어셈블리도 안전한 폴더에 다운로드해야 합니다. 이 작업을 수행하려면 다운로드할 파이프라인과 추가 기능 어셈블리를 모두 포함하도록 응용 프로그램 매니페스트를 구성해야 합니다. [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]에서 파이프라인 어셈블리를 검색하려면 파이프라인과 추가 기능 어셈블리가 호스트 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 프로젝트의 루트 폴더에 있어야 하지만, 이 작업은 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]에서 가장 쉽게 수행됩니다.  
  
 결과적으로 첫 번째 단계에서는 각 파이프라인 어셈블리의 빌드 출력과 추가 기능 어셈블리 프로젝트를 설정하여 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 프로젝트의 루트에 파이프라인 및 추가 기능 어셈블리를 빌드합니다. 다음 표에서는 호스트 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 프로젝트와 동일한 솔루션 및 루트 폴더에 있는 파이프라인 어셈블리 프로젝트와 추가 기능 어셈블리 프로젝트의 빌드 출력 경로를 보여줍니다.  
  
 표 1: XBAP로 호스팅되는 파이프라인 어셈블리의 출력 경로 빌드  
  
|파이프라인 어셈블리 프로젝트|빌드 출력 경로|  
|-------------------------------|-----------------------|  
|계약|`..\HostXBAP\Contracts\`|  
|추가 기능 뷰|`..\HostXBAP\AddInViews\`|  
|추가 기능측 어댑터|`..\HostXBAP\AddInSideAdapters\`|  
|호스트측 어댑터|`..\HostXBAP\HostSideAdapters\`|  
|추가 기능|`..\HostXBAP\AddIns\WPFAddIn1`|  
  
 다음 단계에서는 다음을 수행하여 파이프라인 어셈블리와 추가 기능 어셈블리를 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]의 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 콘텐츠 파일로 지정합니다.  
  
1.  솔루션 탐색기에서 각 파이프라인 폴더를 마우스 오른쪽 단추로 클릭하고 **프로젝트에 포함**을 선택하여 프로젝트에 파이프라인 및 추가 기능 어셈블리 포함.  
  
2.  **속성** 창에서 각 파이프라인 어셈블리 및 추가 기능 어셈블리의 **빌드 작업**을 **콘텐츠**로 설정.  
  
 마지막 단계에서는 다운로드할 파이프라인 어셈블리 파일과 추가 기능 어셈블리 파일을 포함하도록 응용 프로그램 매니페스트를 구성합니다. 파일은 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 응용 프로그램이 차지하는 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 캐시의 폴더 루트에 있는 폴더에 있어야 합니다. 구성은 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]에서 다음을 수행하여 구현할 수 있습니다.  
  
1.  [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 프로젝트를 마우스 오른쪽 단추로 클릭하고, **속성**, **게시** 순으로 클릭한 다음 **응용 프로그램 파일** 단추를 클릭합니다.  
  
2.  **응용 프로그램 파일** 대화 상자에서 각 파이프라인과 추가 기능 DLL의 **게시 상태**를 **포함(자동)**으로 설정하고 각 파이프라인과 추가 기능 DLL에 대해 **그룹 다운로드**을 **(필수)**로 설정합니다.  
  
### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>응용 프로그램 기준 위치에서 파이프라인과 추가 기능 사용  
 파이프라인 및 추가 기능이 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 배포용으로 구성되면 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]와 동일한 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 캐시 폴더에 다운로드됩니다. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]의 파이프라인과 추가 기능을 사용하려면 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 코드를 통해 응용 프로그램 기준 위치에서 가져와야 합니다. 파이프라인과 추가 기능을 사용하기 위한 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델의 다양한 형식과 멤버에서 이 시나리오를 위한 특수 지원을 제공합니다. 경로으로 식별 되는 첫째, 고 <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> 열거형 값입니다. 다음을 포함하는 파이프라인을 사용하기 위해 관련 추가 기능 멤버의 오버로드와 함께 이 값을 사용합니다.  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
### <a name="accessing-the-hosts-site-of-origin"></a>호스트의 원본 사이트에 액세스  
 추가 기능이 원본 사이트의 파일을 참조할 수 있도록 호스트 응용 프로그램과 동일한 수준의 보안 격리로 추가 기능을 로드해야 합니다. 이 보안 수준으로 식별 되는 <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> 열거형 값에 전달 하 고는 <xref:System.AddIn.Hosting.AddInToken.Activate%2A> 메서드 추가 기능이 활성화 됩니다.  
  
<a name="WPFAddInModelArchitecture"></a>   
## <a name="wpf-add-in-architecture"></a>WPF 추가 기능 아키텍처  
 가장 높은 수준에서 앞서 설명한 것 처럼 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 수 있도록 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 구현 하는 추가 기능 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] (에서 직접 또는 간접적으로 파생 된 <xref:System.Windows.FrameworkElement>)를 사용 하 여 <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 및 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>합니다. 결과 호스트 응용 프로그램 반환 되는 <xref:System.Windows.FrameworkElement> 에서 표시 되는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 호스트 응용 프로그램에서입니다.  
  
 간단한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 추가 기능 시나리오의 경우 개발자는 이 내용만 알면 충분합니다. 더 복잡한 시나리오의 경우, 특히 레이아웃, 리소스 및 데이터 바인딩과 같이 추가 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 서비스를 활용하려는 시나리오에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]가 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 지원하는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델을 확장하는 방법에 대해 자세히 알아야 이 방법의 이점과 한계를 이해할 수 있습니다.  
  
 근본적으로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 추가 기능에서 호스트 응용 프로그램으로 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 전달하지 않습니다. 대신 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]가 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 상호 운용성을 사용하여 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 대한 Win32 창 핸들을 전달합니다. 이와 같이 추가 기능의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 호스트 응용 프로그램에 전달되면 다음이 발생합니다.  
  
-   추가 기능 쪽에서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]가 호스트 응용 프로그램이 표시할 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 창 핸들을 획득합니다. 창 핸들은 내부에 의해 캡슐화 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 에서 파생 된 클래스 <xref:System.Windows.Interop.HwndSource> 구현 <xref:System.AddIn.Contract.INativeHandleContract>합니다. 이 클래스의 인스턴스 반환한 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 호스트 응용 프로그램의 응용 프로그램 도메인에 추가 기능의 응용 프로그램 도메인 마샬링됩니다.  
  
-   호스트 응용 프로그램 쪽에서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 가져오며는 <xref:System.Windows.Interop.HwndSource> 는 내부 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 에서 파생 된 클래스 <xref:System.Windows.Interop.HwndHost> 소비 및 <xref:System.AddIn.Contract.INativeHandleContract>합니다. 이 클래스의 인스턴스 반환한 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 호스트 응용 프로그램입니다.  
  
 <xref:System.Windows.Interop.HwndHost>표시 하기 위해 존재 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], 창 핸들에서 공백과 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]합니다. 자세한 내용은 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)을 참조하세요.  
  
 요약 하자면, <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, 및 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 에 대 한 창 핸들을 허용 하기 위해 존재는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 로 캡슐화 되는 호스트 응용 프로그램에 전달할 추가 기능에서 <xref:System.Windows.Interop.HwndHost> 호스트를 표시 합니다. 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다.  
  
> [!NOTE]
>  호스트 응용 프로그램 가져오기 때문에 <xref:System.Windows.Interop.HwndHost>, 호스트 응용 프로그램에서 반환 되는 개체를 변환할 수 없습니다 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 형식에 의해 구현 되며으로에서 추가 기능 (예를 들어 한 <xref:System.Windows.Controls.UserControl>).  
  
 기본적으로 <xref:System.Windows.Interop.HwndHost> 호스트 응용 프로그램 수 사용 하는 방법에 영향을 주는 특정 제한 사항이 있습니다. 그러나 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 확장 <xref:System.Windows.Interop.HwndHost> 추가 시나리오에 대 한 몇 가지 기능을 사용 합니다. 이러한 이점과 한계는 아래에 설명되어 있습니다.  
  
<a name="WPFAddInModelBenefits"></a>   
## <a name="wpf-add-in-benefits"></a>WPF 추가 기능의 이점  
 때문에 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 추가 기능에서 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 에서 파생 되는 내부 클래스를 사용 하 여 호스트 응용 프로그램에서 표시 <xref:System.Windows.Interop.HwndHost>, those [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 의 기능에 의해 제한 <xref:System.Windows.Interop.HwndHost> 와 관련 하 여 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 레이아웃, 렌더링, 데이터 바인딩, 스타일, 템플릿 및 리소스 등의 서비스입니다. 그러나 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 내부 확대 <xref:System.Windows.Interop.HwndHost> 하위 클래스에 다음을 포함 하는 추가 기능:  
  
-   호스트 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와 추가 기능의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 간 탭 이동. "인 추가 기능 한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" 프로그래밍 모델에서는 재정의를 추가 기능 측 어댑터 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 탭 이동, 추가 기능에 완벽 하 게 신뢰 되지 않거나 부분적으로 신뢰할 수 있는 여부를 사용 하도록 설정 하려면.  
  
-   호스트 응용 프로그램 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]에서 표시된 추가 기능 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]의 접근성 요구 사항 준수.  
  
-   여러 응용 프로그램 도메인 시나리오에서 안전하게 실행되도록 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 사용.  
  
-   추가 기능이 보안 격리(즉, 부분적으로 신뢰되는 보안 샌드박스) 상태에서 실행되는 경우 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 창 핸들에 대한 무단 액세스 방지. 호출 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 이 보안을 위해:  
  
    -   에 대 한는 "반환 추가 기능을 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" 프로그래밍 모델, 추가 기능에 대 한 창 핸들을 전달 하는 유일한 방법은 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 간에 격리 경계를 호출 하는 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>합니다.  
  
    -   에 대 한는 "인 추가 기능 한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" 프로그래밍 모델을 재정의 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 호출 되며 추가 기능 측 어댑터 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (이전 예제에서와 같이) 이므로 필요한 경우 추가 기능 측 어댑터를 호출 하는 대로 `QueryContract` 구현 호스트 측 어댑터.  
  
-   여러 응용 프로그램 도메인 실행 보호 제공. 응용 프로그램 도메인의 한계로 인해 추가 기능 응용 프로그램 도메인에서 throw된 처리되지 않은 예외가 발생하면 격리 경계가 있는 경우에도 전체 응용 프로그램이 중단됩니다. 그러나 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]와 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델은 이 문제에 대한 간단한 해결 방법을 제공하고 응용 프로그램 안정성을 향상시킵니다. A [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 추가 기능을 표시 하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 만듭니다는 <xref:System.Windows.Threading.Dispatcher> 호스트 응용 프로그램은 응용 프로그램 도메인을 실행 하는 스레드는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램입니다. 처리 하 여 응용 프로그램 도메인에서 발생 하는 처리 되지 않은 모든 예외를 검색할 수 있습니다는 <xref:System.Windows.Threading.Dispatcher.UnhandledException> 의 이벤트는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 추가 기능에 해당 <xref:System.Windows.Threading.Dispatcher>합니다. 가져올 수는 <xref:System.Windows.Threading.Dispatcher> 에서 <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> 속성입니다.  
  
<a name="WPFAddInModelLimitations"></a>   
## <a name="wpf-add-in-limitations"></a>WPF 추가 기능 한계  
 이점 외 하 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 에서 제공 하는 기본 동작에 추가 <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost>, 창 핸들 및 추가 기능에 대 한 제한도 있습니다. [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 호스트 응용 프로그램에서 표시 되는:  
  
-   호스트 응용 프로그램에서 표시되는 추가 기능 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]은 호스트 응용 프로그램의 클리핑 동작을 준수하지 않습니다.  
  
-   상호 운용성 시나리오의 *에어스페이스* 개념도 추가 기능에 적용됩니다([기술 영역 개요](../../../../docs/framework/wpf/advanced/technology-regions-overview.md) 참조).  
  
-   리소스 상속, 데이터 바인딩 및 명령과 같은 호스트 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 서비스를 추가 기능 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]에서 자동으로 사용할 수 있는 것은 아닙니다. 추가 기능에 이러한 서비스를 제공하려면 파이프라인을 업데이트해야 합니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 회전하거나, 배율을 조정하거나 기울일 수 없으며 변환을 통해 달리 변경할 수 없습니다([변환 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md) 참조).  
  
-   추가 기능에서 내부 콘텐츠 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 그리기 작업에서으로 렌더링 되는 <xref:System.Drawing> 알파 혼합 네임 스페이스를 포함할 수 있습니다. 그러나 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와 이를 포함하는 호스트 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 모두 100% 불투명한 상태여야 합니다. 즉, 두 가지 모두 `Opacity` 속성이 1로 설정되어 있어야 합니다.  
  
-   경우는 <xref:System.Windows.Window.AllowsTransparency%2A> 추가 기능을 포함 하는 호스트 응용 프로그램에서 창의 속성 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 로 설정 된 `true`, 추가 기능에 보이지 않습니다. 이는 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 100% 불투명한 경우(즉, `Opacity` 속성의 값이 1임)에도 마찬가지입니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 동일한 최상위 창의 다른 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 요소 위에 표시되어야 합니다.  
  
-   추가 기능에서 부분 없습니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 를 사용 하 여 렌더링할 수는 <xref:System.Windows.Media.VisualBrush>합니다. 대신 추가 기능은 생성된 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 스냅숏을 사용하여 계약에 정의된 메서드를 통해 호스트 응용 프로그램에 전달할 수 있는 비트맵을 만들 수 있습니다.  
  
-   미디어 파일을 재생할 수 없습니다는 <xref:System.Windows.Controls.MediaElement> 추가 기능에서 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]용으로 생성된 마우스 이벤트는 호스트 응용 프로그램을 통해 생성되거나 발생되지 않으며 호스트 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 `IsMouseOver`의 속성 값이 `false`입니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 컨트롤 간에 포커스가 이동할 때 호스트 응용 프로그램에서 `GotFocus` 및 `LostFocus` 이벤트를 받거나 발생시키지 않습니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 포함하는 호스트 응용 프로그램의 부분은 인쇄 시 흰색으로 표시됩니다.  
  
-   모든 디스패처 (참조 <xref:System.Windows.Threading.Dispatcher>) 추가 기능에서 만든 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 종료 해야 수동으로 소유자 추가 기능 언로드되기 전에 호스트 응용 프로그램 실행을 계속 하는 경우. 계약에서 추가 기능이 언로드되기 전에 호스트 응용 프로그램에서 추가 기능에 신호를 보낼 수 있도록 하는 메서드를 구현할 수 있으므로 이를 통해 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 디스패처를 종료할 수 있습니다.  
  
-   추가 기능을 하는 경우 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 은 <xref:System.Windows.Controls.InkCanvas> 같거나는 <xref:System.Windows.Controls.InkCanvas>, 추가 기능을 언로드할 수 없습니다.  
  
<a name="PerformanceOptimization"></a>   
## <a name="performance-optimization"></a>성능 최적화  
 기본적으로 여러 응용 프로그램 도메인을 사용할 경우 각 응용 프로그램에 필요한 다양한 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 어셈블리가 응용 프로그램의 도메인에 모두 로드됩니다. 결과적으로 새 응용 프로그램 도메인을 만들고 이 도메인의 응용 프로그램을 시작하는 데 필요한 시간이 성능에 영향을 미칠 수 있습니다. 그러나 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 응용 프로그램이 이미 로드된 경우 응용 프로그램 도메인 전체에서 어셈블리를 공유하도록 응용 프로그램에 지시하여 시작 시간을 줄이는 방법을 제공합니다. 사용 하 여이 작업을 수행 된 <xref:System.LoaderOptimizationAttribute> 진입점 메서드에 적용 해야 하는 특성 (`Main`). 이 경우, 응용 프로그램 정의를 구현하는 코드만 사용해야 합니다([응용 프로그램 관리 개요](../../../../docs/framework/wpf/app-development/application-management-overview.md) 참조).  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.LoaderOptimizationAttribute>  
 [추가 기능 및 확장성](../../../../docs/framework/add-ins/index.md)  
 [응용 프로그램 도메인](../../../../docs/framework/app-domains/application-domains.md)  
 [.NET framework Remoting 개요](http://msdn.microsoft.com/en-us/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)  
 [원격 가능 개체 만들기](http://msdn.microsoft.com/en-us/01197253-3f13-43b7-894d-9683e431192a)  
 [방법 항목](../../../../docs/framework/wpf/app-development/how-to-topics.md)
