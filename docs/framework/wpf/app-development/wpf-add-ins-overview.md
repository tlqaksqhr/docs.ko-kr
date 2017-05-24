---
title: "WPF 추가 기능 개요 | Microsoft Docs"
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
  - ".NET Framework 추가 기능 모델[WPF]"
  - "추가 기능[WPF], 아키텍처"
  - "추가 기능[WPF], 장점"
  - "추가 기능[WPF], 제한 사항"
  - "추가 기능[WPF], 성능"
  - "추가 기능[WPF], 사용자 인터페이스"
  - "추가 기능 및 사용자 인터페이스[WPF]"
  - "추가 기능 및 XAML 브라우저 응용 프로그램[WPF]"
  - "추가 기능 개요[WPF]"
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
caps.latest.revision: 36
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 35
---
# WPF 추가 기능 개요
<a name="Introduction"></a> [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에는 개발자가 추가 기능 확장성을 지원하는 응용 프로그램을 만드는 데 사용할 수 있는 추가 기능 모델이 포함되어 있습니다.  이 추가 기능 모델을 사용하면 응용 프로그램 기능을 통합하고 확장하는 추가 기능을 만들 수 있습니다.  어떤 경우에는 응용 프로그램에서 추가 기능으로 제공되는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 표시해야 합니다.  이 항목에서는 이러한 경우에 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 사용하여 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델을 보완하는 방법과 그 바탕을 이루는 아키텍처, 이점, 한계 등에 대해 설명합니다.  
  
   
  
<a name="Requirements"></a>   
## 사전 요구 사항  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델에 대해 잘 알고 있어야 합니다.  자세한 내용은 [추가 기능 및 확장성](../../../../ml/index.xml)를 참조하십시오.  
  
<a name="AddInsOverview"></a>   
## 추가 기능 개요  
 새 기능을 통합하기 위해 응용 프로그램을 다시 컴파일하여 배포하는 복잡한 일을 방지할 수 있도록 응용 프로그램에서는 자사나 타사의 개발자가 새 기능을 통합하는 다른 응용 프로그램을 만들 수 있는 확장성 메커니즘을 구현합니다.  이러한 종류의 확장성을 지원하는 가장 일반적인 방법은 "플러그 인"이라고도 하는 추가 기능을 사용하는 것입니다.  다음은 추가 기능을 통해 확장성을 노출하는 실제 응용 프로그램의 예입니다.  
  
-   Internet Explorer 추가 기능  
  
-   Windows Media Player 플러그 인  
  
-   Visual Studio 추가 기능  
  
 Windows Media Player 추가 기능 모델을 사용하면 타사 개발자가 다양한 방식으로 Windows Media Player를 확장하는 "플러그 인"을 구현할 수 있습니다. 예를 들어 Windows Media Player가 기본적으로 지원하지 않는 미디어 형식\(예: DVD, MP3\)에 대한 디코더와 인코더, 오디오 효과, 스킨 등을 만들 수 있습니다.  모든 추가 기능 모델에는 공통적으로 포함된 여러 엔터티와 동작이 있지만 각 추가 기능 모델은 응용 프로그램에 고유한 기능을 노출하도록 구성됩니다.  
  
 일반적인 추가 기능 확장성 솔루션의 세 가지 기본 엔터티는 *계약*, *추가 기능* 및 *호스트 응용 프로그램*입니다.  계약은 추가 기능과 호스트 응용 프로그램의 통합 방법을 두 가지 방식으로 정의합니다.  
  
-   추가 기능은 호스트 응용 프로그램으로 구현된 기능과 통합됩니다.  
  
-   호스트 응용 프로그램은 추가 기능과 통합할 기능을 노출합니다.  
  
 추가 기능을 사용하려면 호스트 응용 프로그램이 런타임에 추가 기능을 찾아 로드해야 합니다.  따라서 추가 기능을 지원하는 응용 프로그램에서는 다음과 같은 추가 작업이 필요합니다.  
  
-   **검색**: 호스트 응용 프로그램에서 지원되는 계약을 준수하는 추가 기능 찾기  
  
-   **활성화**: 추가 기능 로드, 실행 및 통신 설정  
  
-   **격리**: 응용 프로그램 도메인이나 프로세스를 사용하여 추가 기능의 잠재적인 보안 및 실행 문제로부터 응용 프로그램을 보호하는 격리 경계 설정  
  
-   **통신**: 추가 기능 및 호스트 응용 프로그램이 메서드를 호출하고 데이터를 전달하여 격리 경계를 넘어 서로 통신할 수 있도록 허용  
  
-   **수명 관리**: 명확하고 예측 가능한 방식으로 응용 프로그램 도메인과 프로세스 로드 및 언로드\([응용 프로그램 도메인](../../../../docs/framework/app-domains/application-domains.md) 참조\)  
  
-   **버전 관리**: 호스트 응용 프로그램과 추가 기능의 새 버전이 만들어진 경우에도 계속 통신할 수 있게 함  
  
 강력한 추가 기능 모델을 개발하는 것은 쉬운 작업이 아닙니다.  따라서 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 추가 기능 모델을 빌드하는 인프라를 제공합니다.  
  
> [!NOTE]
>  추가 기능에 대한 자세한 내용은 [추가 기능 및 확장성](../../../../ml/index.xml)를 참조하십시오.  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## .NET Framework 추가 기능 모델 개요  
 <xref:System.AddIn> 네임스페이스에서 찾을 수 있는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델은 추가 기능 확장을 쉽게 개발할 수 있도록 디자인된 형식 집합을 포함하고 있습니다.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델의 기본 단위는 호스트 응용 프로그램과 추가 기능의 통신 방법을 정의하는 *계약*입니다.  계약은 계약의 호스트 응용 프로그램별 *보기*를 사용하여 호스트 응용 프로그램에 노출됩니다.  마찬가지로 계약의 추가 기능별 *보기*는 추가 기능에 노출됩니다.  호스트 응용 프로그램과 추가 기능이 해당 계약 보기 간에 통신할 수 있도록 *어댑터*가 사용됩니다.  계약, 보기 및 어댑터를 세그먼트라고 하며 관련 세그먼트 집합은 *파이프라인*을 구성합니다.  파이프라인은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델이 검색, 활성화, 보안 격리, 실행 격리\(응용 프로그램 도메인 및 프로세스 사용\), 통신, 수명 관리 및 버전 관리를 지원하는 기반입니다.  
  
 개발자는 이러한 지원을 모두 활용하여 호스트 응용 프로그램의 기능을 통합하는 추가 기능을 빌드할 수 있습니다.  하지만 호스트 응용 프로그램이 추가 기능으로 제공되는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 표시해야 하는 경우도 있습니다.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 각 프레젠테이션 기술에는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 구현하는 고유한 모델이 있기 때문에 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델은 어떠한 특정 프레젠테이션 기술도 지원하지 않습니다.  그 대신 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]가 추가 기능에 대한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 지원을 사용하여 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델을 확장합니다.  
  
<a name="WPFAddInModel"></a>   
## WPF 추가 기능  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델과 함께 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 사용하면 추가 기능의 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 표시해야 하는 다양한 호스트 응용 프로그램 시나리오를 처리할 수 있습니다.  특히 다음 두 프로그래밍 모델을 사용하면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]로 이러한 시나리오를 처리할 수 있습니다.  
  
1.  **UI를 반환하는 추가 기능**.  추가 기능은 계약으로 정의된 메서드 호출을 통해 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 응용 프로그램에 반환합니다.  이 시나리오는 다음과 같은 경우에 사용됩니다.  
  
    -   추가 기능이 반환하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 모양은 동적으로 생성된 보고서와 같이 런타임에만 존재하는 데이터나 조건에 종속됩니다.  
  
    -   추가 기능으로 제공되는 서비스의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 추가 기능을 사용할 수 있는 호스트 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와 다릅니다.  
  
    -   추가 기능은 주로 호스트 응용 프로그램에 사용되는 서비스를 수행하며 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 통해 호스트 응용 프로그램에 상태를 보고합니다.  
  
2.  **UI인 추가 기능**.  추가 기능은 계약으로 정의되는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]입니다.  이 시나리오는 다음과 같은 경우에 사용됩니다.  
  
    -   추가 기능이 광고와 같이 표시 중인 서비스 이외의 서비스를 제공하지 않는 경우  
  
    -   추가 기능으로 제공되는 서비스의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 계산기나 색 선택과 같은 추가 기능을 사용할 수 있는 모든 호스트 응용 프로그램에 공통으로 나타나는 경우  
  
 이러한 시나리오에서는 호스트 응용 프로그램과 추가 기능 응용 프로그램 도메인 간에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 개체를 전달할 수 있어야 합니다.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델은 원격 기능에 의존하여 응용 프로그램 도메인 간 통신을 수행하므로 그 사이에서 전달되는 개체를 원격화할 수 있어야 합니다.  
  
 원격화할 수 있는 개체는 다음과 같은 클래스의 인스턴스입니다.  
  
-   <xref:System.MarshalByRefObject> 클래스에서 파생됩니다.  
  
-   <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현합니다.  
  
-   <xref:System.SerializableAttribute> 특성이 적용되어 있습니다.  
  
> [!NOTE]
>  원격화할 수 있는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 개체의 생성과 관련된 자세한 내용은 [Making Objects Remotable](http://msdn.microsoft.com/ko-kr/01197253-3f13-43b7-894d-9683e431192a)를 참조하십시오.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 형식은 원격화할 수 없습니다.  이 문제를 해결하기 위해서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델을 확장하여 추가 기능으로 생성된 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 호스트 응용 프로그램에서 표시할 수 있게 만듭니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 두 가지 형식으로 이러한 지원을 제공합니다. 하나는 <xref:System.AddIn.Contract.INativeHandleContract> 인터페이스이고 다른 하나는 <xref:System.AddIn.Pipeline.FrameworkElementAdapters> 클래스로 구현된 두 정적 메서드인 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 및 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>입니다.  상위 수준에서는 이러한 형식과 메서드가 다음과 같은 방식으로 사용됩니다.  
  
1.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 추가 기능으로 제공되는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]가 모양, 컨트롤, 사용자 정의 컨트롤, 레이아웃 패널 및 페이지와 같은 <xref:System.Windows.FrameworkElement>에서 직접 또는 간접적으로 파생된 클래스여야 합니다.  
  
2.  계약에서 추가 기능과 호스트 응용 프로그램 간에 전달되는 UI를 선언할 때에는 항상 <xref:System.Windows.FrameworkElement>가 아닌 <xref:System.AddIn.Contract.INativeHandleContract>로 UI를 선언해야 합니다. <xref:System.AddIn.Contract.INativeHandleContract>는 격리 경계에 구애 받지 않고 전달할 수 있는 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 원격화 가능 형식으로 나타낸 것입니다.  
  
3.  <xref:System.Windows.FrameworkElement>는 추가 기능의 응용 프로그램 도메인에서 전달되기 전에 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>를 호출하여 <xref:System.AddIn.Contract.INativeHandleContract>로 패키지됩니다.  
  
4.  호스트 응용 프로그램의 응용 프로그램 도메인으로 전달된 후에는 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>를 호출하여 <xref:System.AddIn.Contract.INativeHandleContract>를 <xref:System.Windows.FrameworkElement>로 다시 패키지해야 합니다.  
  
 <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 및 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>를 사용하는 방법은 시나리오에 따라 달라집니다.  다음 단원에서는 각 프로그래밍 모델에 대해 자세하게 설명합니다.  
  
<a name="ReturnUIFromAddInContract"></a>   
## 사용자 인터페이스를 반환하는 추가 기능  
 추가 기능이 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 호스트 응용 프로그램에 반환하려면 다음이 필요합니다.  
  
1.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [추가 기능 및 확장성](../../../../ml/index.xml) 설명서에서 설명하는 것처럼 호스트 응용 프로그램, 추가 기능 및 파이프라인을 만들어야 합니다.  
  
2.  계약에서 <xref:System.AddIn.Contract.IContract>를 구현하고, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 반환하려면 계약에서 <xref:System.AddIn.Contract.INativeHandleContract> 형식의 반환 값으로 메서드를 선언해야 합니다.  
  
3.  추가 기능과 호스트 응용 프로그램 간에 전달되는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 <xref:System.Windows.FrameworkElement>에서 직접 또는 간접적으로 파생되어야 합니다.  
  
4.  추가 기능에서 반환되는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 격리 경계를 통과하기 전에 <xref:System.Windows.FrameworkElement>에서 <xref:System.AddIn.Contract.INativeHandleContract>로 변환되어야 합니다.  
  
5.  반환되는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 격리 경계를 통과한 후 <xref:System.AddIn.Contract.INativeHandleContract>에서 <xref:System.Windows.FrameworkElement>로 변환되어야 합니다.  
  
6.  호스트 응용 프로그램에서 반환된 <xref:System.Windows.FrameworkElement>가 표시됩니다.  
  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 반환하는 추가 기능을 구현하는 방법을 보여 주는 예제를 보려면 [UI를 반환하는 추가 기능 만들기](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)를 참조하십시오.  
  
<a name="AddInIsAUI"></a>   
## 사용자 인터페이스인 추가 기능  
 추가 기능이 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]인 경우 다음이 필요합니다.  
  
1.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [추가 기능 및 확장성](../../../../ml/index.xml) 설명서에서 설명하는 것처럼 호스트 응용 프로그램, 추가 기능 및 파이프라인을 만들어야 합니다.  
  
2.  추가 기능에 대한 계약 인터페이스가 <xref:System.AddIn.Contract.INativeHandleContract>를 구현해야 합니다.  
  
3.  호스트 응용 프로그램으로 전달되는 추가 기능이 <xref:System.Windows.FrameworkElement>에서 직접 또는 간접적으로 파생되어야 합니다.  
  
4.  격리 경계를 통과하기 전에 추가 기능이 <xref:System.Windows.FrameworkElement>에서 <xref:System.AddIn.Contract.INativeHandleContract>로 변환되어야 합니다.  
  
5.  격리 경계를 통과한 후에 추가 기능이 <xref:System.AddIn.Contract.INativeHandleContract>에서 <xref:System.Windows.FrameworkElement>로 변환되어야 합니다.  
  
6.  호스트 응용 프로그램에서 반환된 <xref:System.Windows.FrameworkElement>가 표시됩니다.  
  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]인 추가 기능을 구현하는 방법을 보여 주는 예제를 보려면 [UI인 추가 기능 만들기](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-is-a-ui.md)를 참조하십시오.  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## 추가 기능에서 여러 UI 반환  
 추가 기능은 호스트 응용 프로그램에서 표시할 여러 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 제공하는 경우가 많습니다.  예를 들어 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]인 추가 기능이 호스트 응용 프로그램에 상태 정보를 제공하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]인 경우도 있습니다.  이와 같은 추가 기능은 [사용자 인터페이스를 반환하는 추가 기능](#ReturnUIFromAddInContract)과 [사용자 인터페이스인 추가 기능](#AddInIsAUI) 모델의 기술을 조합하여 구현할 수 있습니다.  
  
<a name="AddInsAndXBAPs"></a>   
## 추가 기능 및 XAML 브라우저 응용 프로그램  
 지금까지의 예제에서는 호스트 응용 프로그램이 독립 실행형 응용 프로그램으로 설치되었습니다.  하지만 다음과 같은 추가 빌드 및 구현 요구 사항을 충족하면 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]도 추가 기능을 호스팅할 수 있습니다.  
  
-   클라이언트 컴퓨터의 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] 응용 프로그램 캐시에, 특히 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]와 동일한 폴더에 파이프라인\(폴더 및 어셈블리\)과 추가 기능 어셈블리가 다운로드되도록 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 응용 프로그램 매니페스트를 구성해야 합니다.  
  
-   추가 기능을 검색하고 로드하는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 코드가 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]의 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 응용 프로그램 캐시를 파이프라인 및 추가 기능 위치로 사용해야 합니다.  
  
-   추가 기능이 원본 사이트에 위치한 느슨한 파일을 참조하는 경우 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]는 추가 기능을 특수 보안 컨텍스트로 로드해야 합니다. [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]에서 호스팅될 경우 추가 기능은 호스트 응용 프로그램의 원본 사이트에 있는 느슨한 파일만 참조할 수 있습니다.  
  
 이러한 작업은 다음 하위 단원에서 자세하게 설명합니다.  
  
### ClickOnce 배포를 위한 파이프라인 및 추가 기능 구성  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]는 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 배포 캐시의 안전한 폴더에 다운로드되고 이 폴더에서 실행됩니다.  [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]가 추가 기능을 호스팅하려면 파이프라인 및 추가 기능 어셈블리 역시 안전한 폴더로 다운로드해야 합니다.  이 작업을 수행하려면 다운로드할 파이프라인 및 추가 기능 어셈블리를 모두 포함하는 응용 프로그램 매니페스트를 구성해야 합니다.  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]를 사용하면 이 작업을 쉽게 수행할 수 있지만 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]가 파이프라인 어셈블리를 검색하려면 파이프라인 및 추가 기능 어셈블리가 호스트 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 프로젝트의 루트 폴더에 있어야 합니다.  
  
 결과적으로 첫 번째 단계는 각 파이프라인 어셈블리 및 추가 기능 어셈블리 프로젝트의 빌드 출력을 설정하여 파이프라인 및 추가 기능 어셈블리를 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 프로젝트의 루트에 빌드하는 것입니다.  다음 표에서는 호스트 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 프로젝트와 동일한 솔루션 및 루트 폴더에 있는 파이프라인 어셈블리 프로젝트와 추가 기능 어셈블리 프로젝트의 빌드 출력 경로를 보여 줍니다.  
  
 표 1: XBAP로 호스팅되는 파이프라인 어셈블리의 빌드 출력 경로  
  
|파이프라인 어셈블리 프로젝트|빌드 출력 경로|  
|---------------------|--------------|  
|계약|`..  \HostXBAP\Contracts\`|  
|추가 기능 뷰|`..  \HostXBAP\AddInViews\`|  
|추가 기능측 어댑터|`..  \HostXBAP\AddInSideAdapters\`|  
|호스트측 어댑터|`..  \HostXBAP\HostSideAdapters\`|  
|추가 기능|`..  \HostXBAP\AddIns\WPFAddIn1`|  
  
 다음 단계에서는 다음 작업을 수행하여 파이프라인 및 추가 기능 어셈블리를 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]의 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 콘텐츠 파일로 지정합니다.  
  
1.  솔루션 탐색기에서 각 파이프라인 폴더를 마우스 오른쪽 단추로 클릭하고 **프로젝트에 포함**을 선택하여 프로젝트에 파이프라인 및 추가 기능 어셈블리를 포함시킵니다.  
  
2.  **속성** 창에서 각 파이프라인 어셈블리 및 추가 기능 어셈블리의 **빌드 작업**을 **콘텐츠**로 설정합니다.  
  
 마지막 단계는 다운로드할 파이프라인 어셈블리 파일과 추가 기능 어셈블리 파일을 포함하는 응용 프로그램 매니페스트를 구성하는 것입니다.  이러한 파일은 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 응용 프로그램이 차지하는 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 캐시의 폴더 루트에 있는 폴더에 있어야 합니다.  이러한 구성은 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]에서 다음을 수행하여 설정할 수 있습니다.  
  
1.  [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **속성**, **게시**, **응용 프로그램 파일** 단추를 차례로 클릭합니다.  
  
2.  **응용 프로그램 파일** 대화 상자에서 각 파이프라인 및 추가 기능 DLL의 **게시 상태**를 **포함\(자동\)**으로 설정하고 각 파이프라인 및 추가 기능 DLL의 **다운로드 그룹**을 **\(필수\)**로 설정합니다.  
  
### 응용 프로그램 기본 디렉터리에서 파이프라인 및 추가 기능 사용  
 파이프라인 및 추가 기능이 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 배포용으로 구성되어 있는 경우 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]와 동일한 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 캐시 폴더에 다운로드됩니다.  [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]에서 파이프라인 및 추가 기능을 사용하려면 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 코드가 응용 프로그램 기본 디렉터리에서 파이프라인 및 추가 기능을 가져와야 합니다.  파이프라인 및 추가 기능을 사용하는 다양한 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델 형식 및 멤버가 이러한 시나리오를 지원합니다.  먼저 <xref:System.AddIn.Hosting.PipelineStoreLocation> 열거형 값에 의해 경로가 식별됩니다.  다음을 포함하는 파이프라인을 사용하려면 관련 추가 기능 멤버의 오버로드와 함께 이 값을 사용합니다.  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
-   [AddInStore.FindAddIns\(Type, PipelineStoreLocation, String\<xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=fullName>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
### 호스트의 원본 사이트 액세스  
 추가 기능이 원본 사이트에서 파일을 참조할 수 있도록 호스트 응용 프로그램과 동일한 보안 격리로 추가 기능을 로드해야 합니다.  이 보안 수준은 추가 기능이 활성화될 때 <xref:System.AddIn.Hosting.AddInSecurityLevel?displayProperty=fullName> 열거형 값에 의해 식별되어 <xref:System.AddIn.Hosting.AddInToken.Activate%2A> 메서드로 전달됩니다.  
  
<a name="WPFAddInModelArchitecture"></a>   
## WPF 추가 기능 아키텍처  
 이미 확인한 것처럼 최상위 수준에서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 사용하면 <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 및 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>를 통해 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능으로 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]\(<xref:System.Windows.FrameworkElement>에서 직접 또는 간접적으로 파생됨\)를 구현할 수 있습니다.  그러면 호스트 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에서 표시되는 <xref:System.Windows.FrameworkElement>를 반환하는 호스트 응용 프로그램이 만들어집니다.  
  
 간단한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 추가 기능 시나리오의 경우 개발자가 알아야 하는 것은 이것이 전부입니다.  더 복잡한 시나리오의 경우, 특히 레이아웃, 리소스 및 데이터 바인딩과 같은 추가적인 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 서비스를 이용하는 시나리오의 경우에는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]가 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 지원하는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델을 확장하는 방법에 대해 보다 자세히 알아야 이 방법의 장점과 한계를 이해할 수 있습니다.  
  
 기본적으로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 추가 기능에서 호스트 응용 프로그램으로 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 전달하지 않습니다. 대신 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 상호 운용성을 사용하여 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 대한 Win32 창 핸들을 전달합니다.  따라서 추가 기능의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 호스트 응용 프로그램으로 전달될 때 다음 작업이 수행됩니다.  
  
-   추가 기능 쪽에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]가 호스트 응용 프로그램으로 표시될 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 창 핸들을 가져옵니다.  창 핸들은 <xref:System.Windows.Interop.HwndSource>에서 파생되고 <xref:System.AddIn.Contract.INativeHandleContract>를 구현하는 내부 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 클래스로 캡슐화됩니다.  이 클래스의 인스턴스는 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>에 의해 반환되고 추가 기능의 응용 프로그램 도메인에서 호스트 응용 프로그램의 응용 프로그램 도메인으로 마샬링됩니다.  
  
-   호스트 응용 프로그램 쪽에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]가 <xref:System.Windows.Interop.HwndHost>에서 파생되고 <xref:System.AddIn.Contract.INativeHandleContract>를 사용하는 내부 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 클래스로 <xref:System.Windows.Interop.HwndSource>를 다시 패키지합니다.  이 클래스의 인스턴스는 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>에 의해 호스트 응용 프로그램으로 반환됩니다.  
  
 <xref:System.Windows.Interop.HwndHost>는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]에서 창 핸들로 식별되는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 표시하기 위해 존재합니다.  자세한 내용은 [WPF 및 Win32 상호 운용성](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)를 참조하십시오.  
  
 요약하면 <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 및 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>는 추가 기능에서 호스트 응용 프로그램으로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 대한 창 핸들을 전달하기 위해 존재하며, <xref:System.Windows.Interop.HwndHost>로 캡슐화되고 호스트 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]로 표시됩니다.  
  
> [!NOTE]
>  호스트 응용 프로그램은 <xref:System.Windows.Interop.HwndHost>를 가져오기 때문에 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>를 통해 반환되는 개체를 추가 기능으로 구현된 형식\(예: <xref:System.Windows.Controls.UserControl>\)으로 변환할 수 없습니다.  
  
 원래 <xref:System.Windows.Interop.HwndHost>에는 호스트 응용 프로그램이 이를 사용하는 방식에 영향을 미치는 특정 제한이 있습니다.  하지만 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 추가 기능 시나리오를 위한 몇 가지 기능으로 <xref:System.Windows.Interop.HwndHost>를 확장합니다.  이러한 장점과 제한은 아래에서 설명합니다.  
  
<a name="WPFAddInModelBenefits"></a>   
## WPF 추가 기능의 이점  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 추가 기능의 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]는 <xref:System.Windows.Interop.HwndHost>에서 파생된 내부 클래스를 사용하여 호스트 응용 프로그램에서 표시되기 때문에 레이아웃, 렌더링, 데이터 바인딩, 스타일, 템플릿 및 리소스와 같은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 서비스와 비교할 때 이러한 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]는 <xref:System.Windows.Interop.HwndHost>의 기능에 의해 제한됩니다.  하지만 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 다음을 포함한 추가 기능을 사용하여 내부 <xref:System.Windows.Interop.HwndHost> 서브클래스를 보완합니다.  
  
-   호스트 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 간의 탭 기능.  "[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]인 추가 기능" 프로그래밍 모델에서는 추가 기능을 완전히 신뢰할 수 있는지 부분적으로 신뢰할 수 있는지에 따라 추가 기능측 어댑터가 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>를 재정의하여 탭 기능을 활성화해야 합니다.  
  
-   호스트 응용 프로그램 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]에서 표시되는 추가 기능 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]에 대해 내게 필요한 옵션 요구 사항 준수  
  
-   여러 응용 프로그램 도메인 시나리오에서 안전하게 실행되도록 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 활성화  
  
-   추가 기능이 보안 격리 상태\(즉, 부분적으로 신뢰되는 보안 샌드박스\)에서 실행될 경우 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 창 핸들에 대한 무단 액세스 방지.  이 보안을 위해 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>를 호출합니다.  
  
    -   "[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 반환하는 추가 기능" 프로그래밍 모델의 경우 격리 경계를 통해 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 대한 창 핸들을 전달하는 유일한 방법은 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>를 호출하는 것입니다.  
  
    -   "[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]인 추가 기능" 프로그래밍 모델의 경우 호스트측 어댑터에서 추가 기능측 `QueryContract` 구현을 호출하는 것처럼 추가 기능측 어댑터에서 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>를 재정의하고 이전 예제와 같이 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>를 호출해야 합니다.  
  
-   여러 응용 프로그램 도메인 실행 보호 제공.  응용 프로그램 도메인과 관련된 제한 때문에 격리 경계가 존재하는 경우에도 추가 기능 응용 프로그램 도메인에서 throw되는 처리되지 않은 예외가 전체 응용 프로그램을 중단시킵니다.  하지만 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 및 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 추가 기능 모델은 이 문제를 해결하고 응용 프로그램 안정성을 향상시키는 간단한 방법을 제공합니다.  호스트 응용 프로그램이 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램인 경우 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 표시하는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 추가 기능은 응용 프로그램 도메인이 실행되는 스레드에 대한 <xref:System.Windows.Threading.Dispatcher>를 만듭니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 추가 기능 <xref:System.Windows.Threading.Dispatcher>의 <xref:System.Windows.Threading.Dispatcher.UnhandledException> 이벤트를 처리하면 응용 프로그램 도메인에서 발생하는 처리되지 않은 예외를 모두 감지할 수 있습니다.  <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> 속성에서 <xref:System.Windows.Threading.Dispatcher>를 가져올 수 있습니다.  
  
<a name="WPFAddInModelLimitations"></a>   
## WPF 추가 기능 제한  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> 및 창 핸들에 의해 제공되는 기본 동작에서 추가적인 혜택을 얻을 수 있지만 호스트 응용 프로그램에서 표시되는 추가 기능 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]의 경우 제한도 있습니다.  
  
-   호스트 응용 프로그램에서 표시되는 추가 기능 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]는 호스트 응용 프로그램의 클리핑 동작을 반영하지 않습니다.  
  
-   상호 운용성 시나리오에서 *에어스페이스* 개념은 추가 기능에도 적용됩니다\([기술 영역 개요](../../../../docs/framework/wpf/advanced/technology-regions-overview.md) 참조\).  
  
-   리소스 상속, 데이터 바인딩 및 명령 등과 같은 호스트 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 서비스를 추가 기능 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]에서 자동으로 사용할 수 있는 것은 아닙니다.  추가 기능에 이러한 서비스를 제공하려면 파이프라인을 업데이트해야 합니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 회전하거나 배율을 조정하거나 기울일 수 없으며 변환을 통해 달리 변경할 수 없습니다\([Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md) 참조\).  
  
-   <xref:System.Drawing> 네임스페이스의 그리기 작업으로 렌더링되는 추가 기능 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 내부의 콘텐츠가 알파 혼합을 포함할 수 있습니다.  하지만 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와 그것을 포함하는 호스트 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 모두 100% 불투명한 상태를 유지해야 합니다. 즉, 둘 모두 `Opacity` 속성이 1로 설정되어 있어야 합니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 포함하는 호스트 응용 프로그램에서 창의 <xref:System.Windows.Window.AllowsTransparency%2A> 속성이 `true`로 설정되어 있으면 추가 기능이 표시되지 않습니다.  이것은 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 100% 불투명한 경우 즉, `Opacity` 속성 값이 1인 경우에도 마찬가지입니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 동일한 최상위 창에 있는 다른 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 요소의 위에 나타납니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 어떤 부분도 <xref:System.Windows.Media.VisualBrush>를 사용하여 렌더링할 수 없습니다.  대신 추가 기능에서 생성된 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 스냅숏을 가져와 계약으로 정의된 메서드를 통해 호스트 응용 프로그램으로 전달할 수 있는 비트맵을 만들 수 있습니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 있는 <xref:System.Windows.Controls.MediaElement>에서 미디어 파일을 재생할 수 없습니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]용으로 생성되는 마우스 이벤트를 호스트 응용 프로그램에서 수신하거나 발생시킬 수 없으며 호스트 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 `IsMouseOver` 속성이 `false` 값을 가집니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에서 컨트롤 간에 포커스가 이동할 때 호스트 응용 프로그램에서 `GotFocus` 및 `LostFocus` 이벤트를 수신하거나 발생시킬 수 없습니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 들어 있는 호스트 응용 프로그램을 인쇄하면 일부가 흰색으로 표시됩니다.  
  
-   호스트 응용 프로그램이 계속 실행되는 경우 소유자 추가 기능을 언로드하기 전에 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]로 생성된 모든 디스패처\(<xref:System.Windows.Threading.Dispatcher> 참조\)를 수동으로 종료해야 합니다.  계약은 호스트 응용 프로그램에서 추가 기능을 언로드하기 전에 추가 기능으로 해당 사실을 알리는 메서드를 구현할 수 있으므로 추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 해당 디스패처를 종료할 수 있습니다.  
  
-   추가 기능 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 <xref:System.Windows.Controls.InkCanvas>이거나 <xref:System.Windows.Controls.InkCanvas>를 포함하는 경우 추가 기능을 언로드할 수 없습니다.  
  
<a name="PerformanceOptimization"></a>   
## 성능 최적화  
 기본적으로 여러 응용 프로그램 도메인을 사용할 경우 각 응용 프로그램에 필요한 다양한 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 어셈블리가 해당 응용 프로그램의 도메인으로 모두 로드됩니다.  따라서 새 응용 프로그램 도메인을 만들고 해당 도메인에서 응용 프로그램을 시작하는 데 필요한 시간이 성능에 영향을 미칠 수 있습니다.  하지만 어셈블리가 이미 로드된 경우 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 응용 프로그램 도메인 간에 어셈블리를 공유하게 하여 시작 시간을 줄이는 방법을 제공합니다.  진입점 메서드\(`Main`\)에 적용되어야 하는 <xref:System.LoaderOptimizationAttribute> 특성을 사용하여 이 작업을 수행합니다.  이 경우 응용 프로그램 정의를 구현하는 코드만 사용해야 합니다\([응용 프로그램 관리 개요](../../../../docs/framework/wpf/app-development/application-management-overview.md) 참조\).  
  
## 참고 항목  
 <xref:System.LoaderOptimizationAttribute>   
 [추가 기능 및 확장성](../../../../ml/index.xml)   
 [응용 프로그램 도메인](../../../../docs/framework/app-domains/application-domains.md)   
 [.NET Framework Remoting Overview](http://msdn.microsoft.com/ko-kr/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)   
 [Making Objects Remotable](http://msdn.microsoft.com/ko-kr/01197253-3f13-43b7-894d-9683e431192a)   
 [방법 항목](../../../../docs/framework/wpf/app-development/how-to-topics.md)