---
title: "응용 프로그램 관리 개요 | Microsoft Docs"
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
  - "응용 프로그램 관리[WPF]"
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
caps.latest.revision: 56
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 52
---
# 응용 프로그램 관리 개요
모든 응용 프로그램이 공통 집합을 적용 하는 응용 프로그램 구현 및 관리 하는 기능을 공유 하는 경향이 있습니다.  이 항목의 기능에 간략하게 설명에 <xref:System.Windows.Application> 클래스를 만들고 응용 프로그램을 관리 합니다.  
  
   
  
## 응용 프로그램 클래스  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 공통 응용 프로그램 범위 기능에 캡슐화 되는 <xref:System.Windows.Application> 클래스입니다.  <xref:System.Windows.Application> 클래스에는 다음과 같은 기능이 포함 되어 있습니다.  
  
-   응용 프로그램 수명 추적 및 상호 작용  
  
-   명령줄 매개 변수 검색 및 처리  
  
-   처리되지 않은 예외 검색 및 응답  
  
-   응용 프로그램 범위에 속한 속성 및 리소스 공유  
  
-   독립 실행형 응용 프로그램에서 창 관리  
  
-   추적 하 고 탐색을 관리 합니다.  
  
<a name="The_Application_Class"></a>   
## 응용 프로그램 클래스를 사용 하 여 일반적인 작업을 수행 하는 방법  
 모든 정보에 관심이 없는 경우는 <xref:System.Windows.Application> 클래스, 다음 표에서 일반적인 작업에 대 한 <xref:System.Windows.Application> 이러한 작업을 수행 하는 방법입니다.  관련 API 및 항목을 확인 하 여 자세한 내용 및 코드 예제를 찾을 수 있습니다.  
  
|Task|방법|  
|----------|--------|  
|현재 응용 프로그램을 나타내는 개체를 표시 합니다.|<xref:System.Windows.Application.Current%2A?displayProperty=fullName> 속성을 사용합니다.|  
|응용 프로그램에 시작 화면 추가|자세한 내용은 [WPF 응용 프로그램에 시작 화면 추가](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)를 참조하십시오.|  
|응용 프로그램 시작|<xref:System.Windows.Application.Run%2A?displayProperty=fullName> 메서드를 사용하십시오.|  
|응용 프로그램을 중지 합니다.|<xref:System.Windows.Application.Current%2A> 개체의 <xref:System.Windows.Application.Shutdown%2A?displayProperty=fullName> 메서드를 사용합니다.|  
|인수는 명령줄에서 가져오기|처리는 <xref:System.Windows.Application.Startup?displayProperty=fullName> 이벤트 및 사용은 <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=fullName> 속성입니다.  예를 들어, 참조는 <xref:System.Windows.Application.Startup?displayProperty=fullName> 이벤트.|  
|가져오고 응용 프로그램 종료 코드를 설정 합니다.|설정의 <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=fullName> 속성에는 <xref:System.Windows.Application.Exit?displayProperty=fullName> 호출 또는 이벤트 처리기는 <xref:System.Windows.Application.Shutdown%2A> 메서드 및 정수를 전달.|  
|검색 및 처리 되지 않은 예외에 응답|<xref:System.Windows.Application.DispatcherUnhandledException> 이벤트를 처리합니다.|  
|가져오고 응용 프로그램 범위 리소스를 설정 합니다.|<xref:System.Windows.Application.Resources%2A?displayProperty=fullName> 속성을 사용합니다.|  
|응용 프로그램 범위 리소스 사전 사용|자세한 내용은 [응용 프로그램 범위 리소스 사전 사용](../../../../docs/framework/wpf/app-development/how-to-use-an-application-scope-resource-dictionary.md)를 참조하십시오.|  
|Get 및 응용 프로그램 범위 속성을 설정 합니다.|<xref:System.Windows.Application.Properties%2A?displayProperty=fullName> 속성을 사용합니다.|  
|Get 및 응용 프로그램의 상태를 저장 합니다.|자세한 내용은 [응용 프로그램 세션 간의 응용 프로그램 범위 속성 유지 및 복원](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md)를 참조하십시오.|  
|비 코드 데이터 파일, 리소스 파일, 콘텐츠 파일 및 원본 사이트 파일을 비롯 하 여 관리 합니다.|자세한 내용은 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)를 참조하십시오.|  
|독립 실행형 응용 프로그램에서 창 관리|자세한 내용은 [WPF 창 개요](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)를 참조하십시오.|  
|추적 하 고 탐색 관리|자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하십시오.|  
  
<a name="The_Application_Definition"></a>   
## 응용 프로그램 정의  
 기능을 이용 하 여 <xref:System.Windows.Application> 클래스를 응용 프로그램 정의 구현 해야 합니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 정의는 <xref:System.Windows.Application>에서 파생된 클래스이며 특수한 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] 설정으로 구성됩니다.  
  
### 응용 프로그램 정의 구현  
 일반적인 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 정의는 태그와 코스 숨김을 모두 사용하여 구현됩니다.  따라서 코드 숨김을 사용하여 응용 프로그램별 동작을 구현하고 이벤트를 처리하는 동시에 태그를 사용하여 응용 프로그램 속성과 리소스를 선언적으로 설정하고 이벤트를 등록할 수 있습니다.  
  
 다음 예제에서는 태그와 코드 숨김을 함께 사용하여 응용 프로그램 정의를 구현하는 방법을 보여 줍니다.  
  
 [!code-xml[ApplicationSnippets#ApplicationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 태그 파일과 코드 숨김 파일이 함께 작동하도록 하려면 다음이 필요합니다.  
  
-   태그에서 `Application` 요소에 `x:Class` 특성이 포함되어야 합니다.  응용 프로그램을 빌드할 때 태그 파일에 `x:Class`가 있으면 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]에서는 <xref:System.Windows.Application>에서 파생되며 `x:Class` 특성에 의해 이름이 지정되는 `partial` 클래스를 만듭니다.  이를 위해서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 스키마에 대한 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스 선언을 추가해야 합니다\(`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`\).  
  
-   코드 숨김에서 클래스는 태그의 `x:Class` 특성으로 지정된 이름과 이름이 같은 `partial` 클래스여야 하며 <xref:System.Windows.Application>에서 파생되어야 합니다.  이를 통해 응용 프로그램 빌드 시 태그 파일에 대해 생성되는 `partial` 클래스와 코드 숨김 파일을 연결할 수 있습니다\([WPF 응용 프로그램 만들기](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md) 참조\).  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]를 사용하여 새 WPF 응용 프로그램 프로젝트나 WPF 브라우저 응용 프로그램 프로젝트를 만들면 응용 프로그램 정의가 기본적으로 포함되고 태그와 코드 숨김을 모두 사용하여 정의됩니다.  
  
 이 코드는 응용 프로그램 정의를 구현하는 데 필요한 최소한의 코드이지만,  응용 프로그램을 빌드하고 실행하려면 먼저 응용 프로그램 정의에 대해 추가 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 구성이 이루어져야 합니다.  
  
### MSBuild용으로 응용 프로그램 정의 구성  
 독립 실행형 응용 프로그램과 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]를 사용하려면 이를 실행할 수 있는 특정 수준의 인프라를 구현해야 합니다.  이 인프라의 가장 중요한 부분은 진입점입니다.  사용자가 응용 프로그램을 시작하면 운영 체제에서는 잘 알려진 응용 프로그램 시작 함수인 진입점을 호출합니다.  
  
 일반적으로는 사용하는 기술에 따라 개발자가 직접 이 코드 일부나 전체를 작성해야 합니다.  하지만 다음 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 프로젝트 파일에서 볼 수 있는 것처럼 응용 프로그램 정의의 태그 파일을 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition` 항목으로 구성하면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 이 코드가 자동으로 생성됩니다.  
  
```  
<Project   
  DefaultTargets="Build"  
  xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  ...  
  <ApplicationDefinition Include="App.xaml" />  
  <Compile Include="App.xaml.cs" />  
  ...  
</Project>  
```  
  
 코드 숨김 파일에 코드가 들어 있으므로 이 코드는 일반적인 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` 항목으로 표시됩니다.  
  
 응용 프로그램 정의의 태그 및 코드 숨김 파일에 이러한 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 구성을 적용하면 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]에서 다음과 같은 코드가 생성됩니다.  
  
 [!code-csharp[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode1)]
 [!code-vb[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode1)]  
[!code-csharp[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode2)]
[!code-vb[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode2)]  
  
 결과 코드는 진입점 메서드인 `Main`을 포함하는 추가 인프라 코드로 응용 프로그램 정의를 보완합니다.  <xref:System.STAThreadAttribute> 특성은 `Main` 메서드에 적용되어 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에 대한 기본 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에 필요한 STA 스레드임을 나타냅니다. `Main`을 호출하면 이벤트를 등록하고 태그에서 구현되는 속성을 설정하는 `InitializeComponent` 메서드를 호출하기 전에 새 `App` 인스턴스가 생성됩니다.  `InitializeComponent`가 자동으로 생성되기 때문에 <xref:System.Windows.Controls.Page> 및 <xref:System.Windows.Window> 구현에서 수행하는 것처럼 응용 프로그램 정의에서 `InitializeComponent`를 명시적으로 호출할 필요가 없습니다.  마지막으로 <xref:System.Windows.Application.Run%2A> 메서드가 호출되어 응용 프로그램이 시작됩니다.  
  
<a name="Getting_the_Current_Application"></a>   
## 현재 응용 프로그램 가져오기  
 때문에의 기능을 <xref:System.Windows.Application> 클래스는 응용 프로그램 간에 공유 되 고 인스턴스는 하나만 있을 수 있습니다.의 <xref:System.Windows.Application> 당 클래스 <xref:System.AppDomain>.  이를 강제하기 위해 <xref:System.Windows.Application> 클래스는 singleton 클래스로 구현됩니다\([Implementing Singleton in C\#](http://go.microsoft.com/fwlink/?LinkId=100567) 참조\). 그러면 singleton 클래스는 자체적인 단일 인스턴스를 생성하고 `static` <xref:System.Windows.Application.Current%2A> 속성으로 해당 인스턴스에 대한 공유 액세스를 제공합니다.  
  
 다음 코드에서는 현재 <xref:System.AppDomain>의 <xref:System.Windows.Application> 개체에 대한 참조를 가져오는 방법을 보여 줍니다.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A>는 <xref:System.Windows.Application> 클래스의 인스턴스에 대한 참조를 반환합니다.  <xref:System.Windows.Application> 파생 클래스를 참조하려면 다음 예제와 같이 <xref:System.Windows.Application.Current%2A> 속성 값을 캐스팅해야 합니다.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 <xref:System.Windows.Application> 개체의 수명 중 언제라도 <xref:System.Windows.Application.Current%2A> 값을 검사할 수 있습니다.  하지만 이러한 검사를 수행할 때는 주의해야 합니다.  <xref:System.Windows.Application> 클래스가 인스턴스화된 후 <xref:System.Windows.Application> 개체의 상태가 일치하지 않는 기간이 존재하기 때문입니다.  이 기간 중에는 <xref:System.Windows.Application>이 응용 프로그램 인프라 설정, 속성 설정, 이벤트 등록을 비롯하여 코드를 실행하는 데 필요한 다양한 초기화 작업을 수행합니다.  이 기간 중에 <xref:System.Windows.Application> 개체를 사용하려고 하면 코드가 예기치 않은 결과를 반환할 수 있습니다. 특히 코드가 현재 설정 중인 다양한 <xref:System.Windows.Application> 속성에 의존하는 경우에 그렇습니다.  
  
 <xref:System.Windows.Application>이 초기화 작업을 완료하면 실제 수명이 시작됩니다.  
  
<a name="Application_Lifetime"></a>   
## 응용 프로그램 수명  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램의 수명은 <xref:System.Windows.Application>에 의해 발생되는 몇 가지 이벤트로 표시되므로 응용 프로그램의 시작, 활성화 및 비활성화 시점, 종료 시점을 알 수 있습니다.  
  
   
  
<a name="Splash_Screen"></a>   
### 시작 화면  
 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]부터는 시작 창 또는 *시작 화면*에 사용할 이미지를 지정할 수 있습니다.  <xref:System.Windows.SplashScreen> 클래스를 사용하면 응용 프로그램이 로드되는 동안 손쉽게 시작 창을 표시할 수 있습니다.  <xref:System.Windows.SplashScreen> 창은 <xref:System.Windows.Application.Run%2A>이 호출되기 전에 만들어져 표시됩니다.  자세한 내용은 [응용 프로그램 시작 시간](../../../../docs/framework/wpf/advanced/application-startup-time.md) 및 [WPF 응용 프로그램에 시작 화면 추가](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)을 참조하십시오.  
  
<a name="Starting_an_Application"></a>   
### 응용 프로그램 시작  
 <xref:System.Windows.Application.Run%2A>이 호출되고 응용 프로그램이 초기화된 후에는 응용 프로그램을 실행할 수 있습니다.  이 시점은 <xref:System.Windows.Application.Startup> 이벤트가 발생하는 시점입니다.  
  
 [!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind1)]
 [!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind1)]  
[!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind2)]
[!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind2)]  
  
 응용 프로그램 수명 중 이 시점에서 가장 일반적으로 수행되는 작업은 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 표시하는 것입니다.  
  
<a name="Showing_a_User_Interface"></a>   
### 사용자 인터페이스 표시  
 대부분의 독립 실행형 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 응용 프로그램은 실행이 시작되면 <xref:System.Windows.Window>를 엽니다.  다음 코드와 같이 <xref:System.Windows.Application.Startup> 이벤트 처리기가 이 작업을 수행할 수 있는 위치입니다.  
  
 [!code-xml[AppShowWindowHardSnippets#StartupEventMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  독립 실행형 응용 프로그램에서 처음 인스턴스화되는 <xref:System.Windows.Window>가 기본적으로 기본 응용 프로그램 창이 됩니다.  이 <xref:System.Windows.Window> 개체는 <xref:System.Windows.Application.MainWindow%2A?displayProperty=fullName> 속성이 참조합니다.  처음 인스턴스화된 <xref:System.Windows.Window> 대신 다른 창이 기본 창이 되어야 하는 경우 <xref:System.Windows.Application.MainWindow%2A> 속성 값을 프로그래밍 방식으로 변경할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]를 처음 시작하면 대부분 <xref:System.Windows.Controls.Page>로 이동합니다.  이는 다음 코드에서 볼 수 있습니다.  
  
 [!code-xml[XBAPAppStartupSnippets#StartupXBAPMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 <xref:System.Windows.Application.Startup>을 처리하여 <xref:System.Windows.Window>만 열거나 <xref:System.Windows.Controls.Page>로 이동하려는 경우에는 태그에서 `StartupUri` 특성을 대신 설정할 수 있습니다.  
  
 다음 예제에서는 독립 실행형 응용 프로그램에서 <xref:System.Windows.Application.StartupUri%2A>를 사용하여 <xref:System.Windows.Window>를 여는 방법을 보여 줍니다.  
  
 [!code-xml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 다음 예제에서는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]에서 <xref:System.Windows.Application.StartupUri%2A>를 사용하여 <xref:System.Windows.Controls.Page>로 이동하는 방법을 보여 줍니다.  
  
 [!code-xml[PageSnippets#XBAPStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 이 태그는 창을 여는 이전 코드와 같은 효과를 갖습니다.  
  
> [!NOTE]
>  탐색에 대한 자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Window>를 기본 생성자가 아닌 생성자를 사용하여 인스턴스화하거나, 해당 속성을 설정하거나, 표시하기 전에 해당 이벤트를 등록해야 하는 경우 <xref:System.Windows.Application.Startup> 이벤트를 처리하거나 응용 프로그램이 시작될 때 제공된 모든 명령줄 인수를 처리해야 합니다.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### 명령줄 인수 처리  
 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)]에서는 명령 프롬프트나 바탕 화면에서 독립 실행형 응용 프로그램을 시작할 수 있습니다.  두 경우 모두 명령줄 인수를 응용 프로그램으로 전달할 수 있습니다. 다음 예제에서는 단일 명령줄 인수 "\/StartMinimized"를 사용하여 시작되는 응용 프로그램을 보여 줍니다.  
  
 `wpfapplication.exe /StartMinimized`  
  
 응용 프로그램이 초기화되는 중에 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 <xref:System.Windows.StartupEventArgs> 매개 변수의 <xref:System.Windows.StartupEventArgs.Args%2A> 속성을 통해 운영 체제에서 명령줄 인수를 검색하고 <xref:System.Windows.Application.Startup> 이벤트 처리기로 전달합니다.  다음과 같은 코드를 사용하여 명령줄 인수를 검색하고 저장할 수 있습니다.  
  
 [!code-xml[ApplicationStartupSnippets#HandleStartupXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 코드에서는 <xref:System.Windows.Application.Startup>을 처리하여 **\/StartMinimized** 명령줄 인수가 제공되었는지 확인합니다. 인수가 제공된 경우 <xref:System.Windows.WindowState>가 <xref:System.Windows.WindowState>인 기본 창을 엽니다.  <xref:System.Windows.Window.WindowState%2A> 속성은 프로그래밍 방식으로 설정되어야 하므로 기본 <xref:System.Windows.Window>는 코드에서 명시적으로 열려야 합니다.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]는 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] 배포를 사용하여 시작되기 때문에 명령줄 인수를 검색하고 처리할 수 없습니다\([WPF 응용 프로그램 배포](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md) 참조\).  그러나 XBAP를 시작하는 데 사용되는 URL에서 쿼리 문자열 매개 변수를 검색하고 처리할 수 있습니다.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### 응용 프로그램 활성화 및 비활성화  
 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)]를 사용하면 다른 응용 프로그램으로 전환할 수가 있습니다. 가장 일반적인 방법은 Alt\+Tab 키 조합을 사용하는 것입니다.  응용 프로그램은 사용자가 선택할 수 있는 <xref:System.Windows.Window>가 표시되어 있는 경우에만 전환할 수 있습니다.  현재 선택된 <xref:System.Windows.Window>는 *활성 창*\(*전경 창*이라고도 함\)이며 사용자 입력을 받는 <xref:System.Windows.Window>입니다. 활성 창이 있는 응용 프로그램을 *활성 응용 프로그램*\(또는 *전경 응용 프로그램*\)이라고 하는데, 다음과 같은 경우에 응용 프로그램이 활성 응용 프로그램이 됩니다.  
  
-   응용 프로그램이 시작되어 <xref:System.Windows.Window>를 표시하는 경우  
  
-   응용 프로그램에서 <xref:System.Windows.Window>를 선택하여 다른 응용 프로그램으로 전환하는 경우  
  
 <xref:System.Windows.Application.Activated?displayProperty=fullName> 이벤트를 처리하면 응용 프로그램이 활성화되는 시점을 감지할 수 있습니다.  
  
 마찬가지로 다음과 같은 경우에는 응용 프로그램이 비활성화됩니다.  
  
-   현재 응용 프로그램에서 다른 응용 프로그램으로 전환하는 경우  
  
-   응용 프로그램이 종료되는 경우  
  
 <xref:System.Windows.Application.Deactivated?displayProperty=fullName> 이벤트를 처리하면 응용 프로그램이 비활성화되는 시점을 감지할 수 있습니다.  
  
 다음 코드에서는 <xref:System.Windows.Application.Activated> 및 <xref:System.Windows.Application.Deactivated> 이벤트를 처리하여 응용 프로그램이 활성화되었는지 확인하는 방법을 보여 줍니다.  
  
 [!code-xml[ApplicationActivationSnippets#DetectActivationStateXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 <xref:System.Windows.Window>도 활성화 및 비활성화할 수 있습니다.  자세한 내용은 <xref:System.Windows.Window.Activated?displayProperty=fullName> 및 <xref:System.Windows.Window.Deactivated?displayProperty=fullName>를 참조하십시오.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]의 경우에는 <xref:System.Windows.Application.Activated?displayProperty=fullName>도 <xref:System.Windows.Application.Deactivated?displayProperty=fullName>도 발생하지 않습니다.  
  
<a name="Application_Shutdown"></a>   
### 응용 프로그램 종료  
 응용 프로그램이 종료되면 응용 프로그램 수명이 끝납니다. 이러한 경우는 다음과 같은 이유 때문에 발생합니다.  
  
-   사용자가 모든 <xref:System.Windows.Window>를 닫은 경우  
  
-   사용자가 기본 <xref:System.Windows.Window>를 닫은 경우  
  
-   사용자가 로그오프나 종료를 통해 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)]를 끝낸 경우  
  
-   응용 프로그램별 조건이 충족된 경우  
  
 응용 프로그램 종료를 쉽게 관리할 수 있도록 <xref:System.Windows.Application>에서는 <xref:System.Windows.Application.Shutdown%2A> 메서드, <xref:System.Windows.Application.ShutdownMode%2A> 속성, 그리고 <xref:System.Windows.Application.SessionEnding> 및 <xref:System.Windows.Application.Exit> 이벤트를 제공합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Application.Shutdown%2A>은 <xref:System.Security.Permissions.UIPermission>이 있는 응용 프로그램에서만 호출할 수 있습니다.  독립 실행형 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에는 항상 이 권한이 있습니다.  하지만 인터넷 영역의 부분 신뢰 보안 샌드박스에서 실행되는 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]에는 이 권한이 없습니다.  
  
#### 종료 모드  
 대부분의 응용 프로그램은 모든 창을 닫거나 기본 창을 닫으면 종료됩니다.  하지만 다른 응용 프로그램과 관련된 조건이 특정 응용 프로그램의 종료 시기를 결정하는 경우가 있습니다.  다음 <xref:System.Windows.ShutdownMode> 열거형 값 중 하나로 <xref:System.Windows.Application.ShutdownMode%2A>를 설정하여 응용 프로그램이 종료되는 조건을 지정할 수 있습니다.  
  
-   <xref:System.Windows.ShutdownMode>  
  
-   <xref:System.Windows.ShutdownMode>  
  
-   <xref:System.Windows.ShutdownMode>  
  
 <xref:System.Windows.Application.ShutdownMode%2A>의 기본값은 <xref:System.Windows.ShutdownMode>로, 이는 사용자가 응용 프로그램의 마지막 창을 닫으면 응용 프로그램이 자동으로 종료된다는 것을 의미합니다.  하지만 기본 창이 닫힐 때 응용 프로그램을 종료해야 하는 경우 <xref:System.Windows.Application.ShutdownMode%2A>를 <xref:System.Windows.ShutdownMode>로 설정하면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 자동으로 기본 창이 닫힙니다.  다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-xml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 응용 프로그램별 종료 조건이 있는 경우 <xref:System.Windows.Application.ShutdownMode%2A>를 <xref:System.Windows.ShutdownMode>으로 설정합니다.  이 경우 <xref:System.Windows.Application.Shutdown%2A> 메서드를 호출하여 명시적으로 응용 프로그램을 종료하는 것은 사용자의 책임입니다. 그렇지 않으면 모든 창을 닫은 경우에도 응용 프로그램이 계속 실행됩니다.  <xref:System.Windows.Application.ShutdownMode%2A>가 <xref:System.Windows.ShutdownMode> 또는 <xref:System.Windows.ShutdownMode>인 경우에는 <xref:System.Windows.Application.Shutdown%2A>이 암시적으로 호출됩니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]에서 <xref:System.Windows.Application.ShutdownMode%2A>를 설정할 수 있지만 이 설정은 무시됩니다. 브라우저에서 다른 위치를 탐색하거나 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]를 호스팅하는 브라우저가 닫히면 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]가 항상 종료됩니다.  자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하십시오.  
  
#### 세션 종료  
 <xref:System.Windows.Application.ShutdownMode%2A> 속성으로 기술되는 종료 조건은 응용 프로그램에 한정됩니다.  하지만 외부 조건에 따라 응용 프로그램이 종료되는 경우도 있습니다.  가장 일반적인 외부 조건은 다음과 같은 작업으로 사용자가 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 세션을 끝내는 경우에 발생합니다.  
  
-   로그오프  
  
-   종료  
  
-   다시 시작  
  
-   최대 절전 모드  
  
 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 세션이 종료되는 시점을 감지하려면 다음 예제에서 보여 주는 것처럼 <xref:System.Windows.Application.SessionEnding> 이벤트를 처리하면 됩니다.  
  
 [!code-xml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 이 예제에서는 코드가 <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> 속성을 검사하여 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 세션이 종료되는 방식을 결정합니다.  또한 이 값을 사용하여 사용자에게 확인 메시지를 표시합니다.  사용자가 세션이 종료되길 원하지 않는 경우에는 코드에서 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>을 `true`로 설정하여 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 세션이 종료되지 않게 합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]의 경우에는 <xref:System.Windows.Application.SessionEnding>이 발생하지 않습니다.  
  
#### Exit  
 응용 프로그램이 종료될 때 응용 프로그램 상태 유지와 같은 몇 가지 최종 처리를 수행해야 할 경우가 있습니다.  이러한 경우에는 <xref:System.Windows.Application.Exit> 이벤트를 처리할 수 있습니다.  
  
 [!code-xml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml1)]  
[!code-xml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml2)]  
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind1)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind1)]  
[!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind2)]
[!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind2)]  
  
 전체 예제를 보려면 [응용 프로그램 세션 간의 응용 프로그램 범위 속성 유지 및 복원](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md)을 참조하십시오.  
  
 독립 실행형 응용 프로그램 및 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 모두에서 <xref:System.Windows.Application.Exit>를 처리할 수 있습니다.  [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]의 경우 다음과 같은 상황에서 <xref:System.Windows.Application.Exit>가 발생합니다.  
  
-   탐색 위치가 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]를 벗어나는 경우  
  
-   [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)]에서 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]를 호스팅하는 탭이 닫힌 경우  
  
-   브라우저가 닫힌 경우  
  
#### 종료 코드  
 대부분의 경우 응용 프로그램은 운영 체제에서 사용자 요청에 대한 응답으로 시작하게 됩니다.  하지만 다른 응용 프로그램에서 특정 작업을 수행하기 위해 응용 프로그램을 시작할 수도 있습니다.  이렇게 시작된 응용 프로그램이 종료될 경우 시작하는 응용 프로그램에서 시작된 응용 프로그램이 종료되는 조건을 알아야 할 수 있습니다.  이런 경우 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)]에서는 응용 프로그램이 종료될 때 응용 프로그램 종료 코드를 반환할 수 있습니다.  기본적으로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램은 종료 코드 값으로 0을 반환합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]에서 디버깅할 경우 응용 프로그램이 종료되면 **출력** 창에 응용 프로그램 종료 코드가 다음과 같은 메시지로 표시됩니다.  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  **보기** 메뉴에서 **출력**을 클릭하여 **출력** 창을 엽니다.  
  
 종료 코드를 변경하려면 정수 인수를 종료 코드로 받아들이는 <xref:System.Windows.Application.Shutdown%28System.Int32%29> 오버로드를 호출할 수 있습니다.  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 <xref:System.Windows.Application.Exit> 이벤트를 처리하면 종료 코드 값을 감지하고 변경할 수 있습니다.  <xref:System.Windows.Application.Exit> 이벤트 처리기는 <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> 속성이 있는 종료 코드에 대한 액세스를 제공하는 <xref:System.Windows.ExitEventArgs>를 전달합니다.  자세한 내용은 <xref:System.Windows.Application.Exit>를 참조하십시오.  
  
> [!NOTE]
>  독립 실행형 응용 프로그램 및 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 모두에서 종료 코드를 설정할 수 있습니다.  하지만 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]의 경우 종료 코드 값이 무시됩니다.  
  
<a name="Unhandled_Exceptions"></a>   
### 처리되지 않은 예외  
 원하지 않는 예외를 throw하는 경우와 같이 응용 프로그램이 비정상적인 상황에서 종료되는 경우가 있습니다.  이런 경우에는 응용 프로그램에 예외를 감지하고 처리할 코드가 없을 수 있습니다.  이런 형식의 예외가 처리되지 않은 예외이며, 응용 프로그램이 닫히기 전에 다음 그림에 표시된 것과 비슷한 알림으로 표시됩니다.  
  
 ![처리되지 않은 예외 알림](../../../../docs/framework/wpf/app-development/media/applicationmanagementoverviewfigure2.png "ApplicationManagementOverviewFigure2")  
  
 사용자 환경의 관점에서는 응용 프로그램에서 다음과 같은 작업의 일부 또는 전부를 수행하여 이러한 기본 동작을 방지하는 것이 바람직합니다.  
  
-   사용자에게 친숙한 정보 표시  
  
-   응용 프로그램을 실행 상태로 유지  
  
-   [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 이벤트 로그에 개발자에게 친숙한 세부적인 예외 정보 기록  
  
 이러한 지원을 구현하는 것은 처리되지 않은 예외, 다시 말해 <xref:System.Windows.Application.DispatcherUnhandledException> 이벤트가 발생하는 원인을 감지할 수 있는지에 따라 달라집니다.  
  
 [!code-xml[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
 [!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind1)]
 [!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind1)]  
[!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind2)]
[!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind2)]  
  
 <xref:System.Windows.Application.DispatcherUnhandledException> 이벤트 처리기는 예외 자체\(<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=fullName>\)를 포함하여 처리되지 않은 예외와 관련된 컨텍스트 정보를 포함하는 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> 매개 변수를 전달합니다.  이 정보를 사용하여 예외를 처리하는 방법을 결정할 수 있습니다.  
  
 <xref:System.Windows.Application.DispatcherUnhandledException>을 처리할 때는 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=fullName> 속성을 `true`로 설정해야 합니다. 그렇지 않으면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 계속해서 예외가 처리되지 않은 것으로 간주하고 이전에 설명한 기본 동작으로 돌아갑니다.  처리되지 않은 예외가 발생하고 <xref:System.Windows.Application.DispatcherUnhandledException> 이벤트가 처리되지 않거나 이벤트가 처리되지만 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A>가 `false`로 설정되는 경우 응용 프로그램이 즉시 종료됩니다.  또한 다른 <xref:System.Windows.Application> 이벤트가 발생되지 않습니다.  따라서 응용 프로그램에 응용 프로그램이 종료되기 전에 실행되어야 하는 코드가 있는 경우 <xref:System.Windows.Application.DispatcherUnhandledException>을 처리해야 합니다.  
  
 처리되지 않은 예외의 결과로 응용 프로그램이 종료될 수는 있지만 응용 프로그램은 대개 다음 단원에서 설명하는 것처럼 사용자 요청에 대한 응답으로 종료됩니다.  
  
<a name="Application_Lifetime_Events"></a>   
### 응용 프로그램 수명 이벤트  
 독립 실행형 응용 프로그램과 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]는 수명이 동일하지 않습니다. 다음 그림에서는 독립 실행형 응용 프로그램의 주요 수명 이벤트와 이러한 이벤트가 발생하는 순서를 보여 줍니다.  
  
 ![독립 실행형 응용 프로그램 &#45; 응용 프로그램 개체 이벤트](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview\_ApplicationObjectEvents")  
  
 마찬가지로 다음 그림에서는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]의 주요 수명 이벤트와 이러한 이벤트가 발생하는 순서를 보여 줍니다.  
  
 ![XBAP &#45; 응용 프로그램 개체 이벤트](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview\_ApplicationObjectEvents\_xbap")  
  
## 참고 항목  
 <xref:System.Windows.Application>   
 [WPF 창 개요](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)   
 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)   
 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)   
 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Application Model: How\-to Topics](http://msdn.microsoft.com/ko-kr/76771b09-3688-4d1c-8818-9b3f4cf39a30)   
 [응용 프로그램 개발](../../../../docs/framework/wpf/app-development/index.md)