---
title: "응용 프로그램 관리 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
caps.latest.revision: "56"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 09129f2dc2bac2bb17ebacd6d6db020288b6f616
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="application-management-overview"></a>응용 프로그램 관리 개요
모든 응용 프로그램은 응용 프로그램 구현 및 관리에 적용하는 일반적인 기능 집합을 공유하는 경향이 있습니다. 이 항목에서는에서 기능의 개요는 <xref:System.Windows.Application> 만들고 응용 프로그램을 관리 하기 위한 클래스입니다.  
   
  
## <a name="the-application-class"></a>Application 클래스  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 일반적인 응용 프로그램 범위의 기능에 캡슐화 되어는 <xref:System.Windows.Application> 클래스입니다. <xref:System.Windows.Application> 클래스에는 다음과 같은 기능이 포함 됩니다.  
  
-   응용 프로그램 수명 추적 및 상호 작용  
  
-   명령줄 매개 변수 검색 및 처리  
  
-   처리되지 않은 예외의 검색 및 응답  
  
-   응용 프로그램 범위 속성 및 리소스 공유  
  
-   독립 실행형 응용 프로그램에서 창 관리  
  
-   탐색 추적 및 관리  
  
<a name="The_Application_Class"></a>   
## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Application 클래스를 사용하여 일반적인 작업을 수행하는 방법  
 모든의 세부 정보에 관심이 없는 경우는 <xref:System.Windows.Application> 클래스, 다음 표에서 몇 가지 일반적인 작업에 대 한 <xref:System.Windows.Application> 방법과 이러한 작업을 수행 합니다. 관련 API 및 항목을 확인하여 추가 정보 및 샘플 코드를 찾을 수 있습니다.  
  
|작업|방식|  
|----------|--------------|  
|현재 응용 프로그램을 나타내는 개체 가져오기|<xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> 속성을 사용합니다.|  
|응용 프로그램에 시작 화면 추가|참조 [WPF 응용 프로그램 시작 화면 추가](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)합니다.|  
|응용 프로그램 시작|<xref:System.Windows.Application.Run%2A?displayProperty=nameWithType> 메서드를 사용하세요.|  
|응용 프로그램 중지|사용 하 여는 <xref:System.Windows.Application.Shutdown%2A> 의 메서드는 <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> 개체입니다.|  
|명령줄에서 인수 가져오기|처리는 <xref:System.Windows.Application.Startup?displayProperty=nameWithType> 이벤트 및 사용 된 <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> 속성입니다. 예를 들어 참조는 <xref:System.Windows.Application.Startup?displayProperty=nameWithType> 이벤트입니다.|  
|응용 프로그램 종료 코드 가져오기 및 설정|설정의 <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> 속성에는 <xref:System.Windows.Application.Exit?displayProperty=nameWithType> 호출 또는 이벤트 처리기는 <xref:System.Windows.Application.Shutdown%2A> 메서드와 정수를 전달 합니다.|  
|처리되지 않은 예외의 검색 및 응답|처리는 <xref:System.Windows.Application.DispatcherUnhandledException> 이벤트입니다.|  
|응용 프로그램 범위 리소스 가져오기 및 설정|<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 속성을 사용합니다.|  
|응용 프로그램 범위 리소스 사전 사용|참조 [응용 프로그램 범위 리소스 사전을 사용 하 여](../../../../docs/framework/wpf/app-development/how-to-use-an-application-scope-resource-dictionary.md)합니다.|  
|응용 프로그램 범위 속성 가져오기 및 설정|<xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType> 속성을 사용합니다.|  
|응용 프로그램 상태 가져오기 및 저장|참조 [속성 유지 및 복원 응용 프로그램 범위 응용 프로그램 세션 간에](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md)합니다.|  
|리소스 파일, 콘텐츠 파일 및 원본 사이트 파일을 포함하여 비코드 데이터 파일 관리|참조 [WPF 응용 프로그램 리소스, 내용 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)합니다.|  
|독립 실행형 응용 프로그램의 창 관리|참조 [WPF Windows 개요](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)합니다.|  
|탐색 추적 및 관리|참조 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)합니다.|  
  
<a name="The_Application_Definition"></a>   
## <a name="the-application-definition"></a>응용 프로그램 정의  
 기능을 활용 하는 <xref:System.Windows.Application> 클래스, 응용 프로그램 정의 구현 해야 합니다. A [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 정의에서 파생 되는 클래스는 <xref:System.Windows.Application> 고가 특별 한 구성 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] 설정 합니다.  
  
### <a name="implementing-an-application-definition"></a>응용 프로그램 정의 구현  
 일반적인 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 정의 태그와 코드 숨김을 사용 하 여 구현 됩니다. 따라서 코드 숨김에서 응용 프로그램별 동작을 구현하고 이벤트를 처리하는 동시에 태그를 사용하여 응용 프로그램 속성과 리소스를 선언적으로 설정하고 이벤트를 등록할 수 있습니다.  
  
 다음 예제에서는 태그 및 코드 숨김을 모두 사용하여 응용 프로그램 정의를 구현하는 방법을 보여 줍니다.  
  
 [!code-xaml[ApplicationSnippets#ApplicationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 태그 파일과 코드 숨김 파일이 함께 작동하도록 하려면 다음이 필요합니다.  
  
-   태그에서는 `Application` 요소 포함 되어야 합니다는 `x:Class` 특성입니다. 응용 프로그램을 빌드할 때 `x:Class` 파일 사용 하면 태그에서 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 만들려는 `partial` 에서 파생 된 클래스 <xref:System.Windows.Application> 변수로 지정 된 이름을 가진는 `x:Class` 특성입니다. 이 위해서는 추가 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 에 대 한 네임 스페이스 선언을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 스키마 ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).  
  
-   코드 숨김 클래스 여야 합니다는 `partial` 변수로 지정 된 동일한 이름의 클래스는 `x:Class` 태그에서 특성을 마우스에서 파생 되어야 <xref:System.Windows.Application>합니다. 이렇게 하면 연결 된 코드 숨김 파일이 `partial` 응용 프로그램이 빌드될 때 마크업 파일에 대해 생성 되는 클래스 (참조 [WPF 응용 프로그램 빌드](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
> [!NOTE]
>  새 WPF 응용 프로그램 프로젝트 또는 사용 하 여 WPF 브라우저 응용 프로그램 프로젝트를 만들 때 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], 응용 프로그램 정의 기본적으로 포함 되 고 태그와 코드 숨김을 사용 하 여 정의 됩니다.  
  
 이 코드는 응용 프로그램 정의를 구현하는 데 필요한 최소한의 코드이지만, 그러나 추가 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 구성으로 빌드하고 응용 프로그램을 실행 하기 전에 응용 프로그램 정의에 설정 해야 합니다.  
  
### <a name="configuring-the-application-definition-for-msbuild"></a>MSBuild용 응용 프로그램 정의 구성  
 독립 실행형 응용 프로그램 및 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 을 실행 하기 전에 특정 수준의 인프라의 구현이 필요 합니다. 이 인프라의 가장 중요한 부분은 진입점입니다. 사용자가 응용 프로그램을 시작하면 운영 체제에서는 잘 알려진 응용 프로그램 시작 함수인 진입점을 호출합니다.  
  
 일반적으로는 기술에 따라 개발자가 직접 이 코드 일부나 전체를 작성해야 합니다. 그러나 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 마크업 파일의 응용 프로그램 정의로 구성 될 때이 코드를 생성 한 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition` 항목을 다음에 표시 된 대로 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 프로젝트 파일:  
  
```xml  
<Project   
  DefaultTargets="Build"  
                        xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  ...  
  <ApplicationDefinition Include="App.xaml" />  
  <Compile Include="App.xaml.cs" />  
  ...  
</Project>  
```  
  
 로 표시 된 코드를 포함 하는 코드 숨김 파일은 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` 항목을 일반적인 합니다.  
  
 이러한 응용 프로그램 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 응용 프로그램 정의 태그 및 코드 숨김 파일에 구성을 사용 하면 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 다음과 같은 코드를 생성 합니다.  
  
 [!code-csharp[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode1)]
 [!code-vb[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode1)]  
[!code-csharp[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode2)]
[!code-vb[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode2)]  
  
 결과 코드 진입점 메서드를 포함 하는 추가 인프라 코드를 응용 프로그램 정의 확대 `Main`합니다. <xref:System.STAThreadAttribute> 특성이 적용 되는 `Main` 함을 나타내려면 메서드 주 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 에 대 한 스레드는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에 필요한는 STA 스레드가 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램입니다. 를 호출할 때는 `Main` 의 새 인스턴스를 만듭니다 `App` 호출 하기 전에 `InitializeComponent` 태그에서 이벤트를 등록 하 고 속성을 설정 하는 메서드 구현 됩니다. 때문에 `InitializeComponent` 생성을 명시적으로 호출할 필요가 없습니다 `InitializeComponent` 응용 프로그램 정의 대 한 것 처럼에서 <xref:System.Windows.Controls.Page> 및 <xref:System.Windows.Window> 구현 합니다. 마지막으로 <xref:System.Windows.Application.Run%2A> 메서드는 응용 프로그램을 시작 합니다.  
  
<a name="Getting_the_Current_Application"></a>   
## <a name="getting-the-current-application"></a>현재 응용 프로그램 가져오기  
 때문에 기능을는 <xref:System.Windows.Application> 클래스는 응용 프로그램에서 공유의 인스턴스가 하나만 있을 수 있습니다는 <xref:System.Windows.Application> 당 클래스 <xref:System.AppDomain>합니다. 이 적용 하는 <xref:System.Windows.Application> 클래스가 단일 클래스로 구현 되는 (참조 [C#에서 Singleton 구현](http://go.microsoft.com/fwlink/?LinkId=100567))를 자체의 단일 인스턴스를 만들고 제공는 공유 액세스를 사용 하 여는 `static` <xref:System.Windows.Application.Current%2A> 속성입니다.  
  
 다음 코드에 대 한 참조를 확보 하는 방법을 보여 줍니다는 <xref:System.Windows.Application> 현재에 대 한 개체 <xref:System.AppDomain>합니다.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A>인스턴스에 대 한 참조 반환은 <xref:System.Windows.Application> 클래스입니다. 에 대 한 참조를 원하는 경우 프로그램 <xref:System.Windows.Application> 파생 클래스의 값을 캐스팅 해야는 <xref:System.Windows.Application.Current%2A> 속성을 다음 예제와 같이 합니다.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 값을 검사할 수 <xref:System.Windows.Application.Current%2A> 수명 중에 언제 든 지 프로그램 <xref:System.Windows.Application> 개체입니다. 하지만 이러한 검사를 수행할 때는 주의해야 합니다. 후의 <xref:System.Windows.Application> 클래스가 인스턴스화되면는 기간이의 상태는 <xref:System.Windows.Application> 개체가 일치 하지 않습니다. 이 기간 동안 <xref:System.Windows.Application> 응용 프로그램 인프라를 설정, 속성을 설정 하 고, 이벤트 등록을 포함 하 여를 실행 하려면 코드에 필요한 다양 한 초기화 작업을 수행 됩니다. 사용 하려는 경우는 <xref:System.Windows.Application> 개체에이 기간 동안 코드 수 예기치 않은 결과 다양 한 의존 하는 경우에 특히 <xref:System.Windows.Application> 속성이 설정 되 고 합니다.  
  
 때 <xref:System.Windows.Application> 초기화 작업을 완료 실제 수명이 시작 합니다.  
  
<a name="Application_Lifetime"></a>   
## <a name="application-lifetime"></a>응용 프로그램 수명  
 수명을 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에 의해 발생 하는 몇 가지 이벤트로 표시 되어 <xref:System.Windows.Application> 를 응용 프로그램 시작 된 시기를 알려 주는 활성화 및 비활성화 종료 되었습니다.  
  
  
<a name="Splash_Screen"></a>   
### <a name="splash-screen"></a>시작 화면  
 부터는 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], 시작 창에서 사용할 이미지를 지정할 수 있습니다 또는 *시작 화면*합니다. <xref:System.Windows.SplashScreen> 클래스를 사용 하면 쉽게 응용 프로그램을 로드 하는 동안 시작 창을 표시할 수 있습니다. <xref:System.Windows.SplashScreen> 창이 생성 되어 위에 나와 있는 것 <xref:System.Windows.Application.Run%2A> 호출 됩니다. 자세한 내용은 참조 [응용 프로그램 시작 시](../../../../docs/framework/wpf/advanced/application-startup-time.md) 및 [WPF 응용 프로그램 시작 화면 추가](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)합니다.  
  
<a name="Starting_an_Application"></a>   
### <a name="starting-an-application"></a>응용 프로그램 시작  
 후 <xref:System.Windows.Application.Run%2A> 라고 하 고 응용 프로그램 초기화, 응용 프로그램을 실행할 준비가 되었습니다. 이 현재 때 표시 되는 <xref:System.Windows.Application.Startup> 이벤트가 발생 합니다.  
  
 [!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind1)]
 [!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind1)]  
[!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind2)]
[!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind2)]  
  
 이 시점에서 응용 프로그램의 수명에서 가장 일반적인 작업을 수행 해야 하는 방법을 설명는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다.  
  
<a name="Showing_a_User_Interface"></a>   
### <a name="showing-a-user-interface"></a>사용자 인터페이스 표시  
 대부분의 독립 실행형 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 응용 프로그램을 열어는 <xref:System.Windows.Window> 시작할 때 실행 됩니다. <xref:System.Windows.Application.Startup> 다음 코드 에서처럼 이벤트 처리기는이 수행할 수 있는 한 위치입니다.  
  
 [!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  첫 번째 <xref:System.Windows.Window> 응용 프로그램이 기본적으로 주 응용 프로그램 창 되는 독립 실행형에서 인스턴스화할 수 있습니다. 이 <xref:System.Windows.Window> 개체를 참조 하는 <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> 속성입니다. 값은 <xref:System.Windows.Application.MainWindow%2A> 속성 경우 첫 번째 보다 다양 한 창 프로그래밍 방식으로 변경할 수 있습니다 인스턴스화할 <xref:System.Windows.Window> 주 창 이어야 합니다.  
  
 경우는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 처음 시작 될 가능성이 가장 검색을 시작 합니다는 <xref:System.Windows.Controls.Page>합니다. 다음 코드에서 이를 확인할 수 있습니다.  
  
 [!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 처리 하는 경우 <xref:System.Windows.Application.Startup> 만 <xref:System.Windows.Window> 하거나으로 이동 하는 <xref:System.Windows.Controls.Page>를 설정할 수 있습니다는 `StartupUri` 태그에서 특성을 대신 합니다.  
  
 사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Application.StartupUri%2A> 열려는 독립 실행형 응용 프로그램에서 한 <xref:System.Windows.Window>합니다.  
  
 [!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 다음 예제에서는 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Application.StartupUri%2A> 에서 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 으로 이동 하는 <xref:System.Windows.Controls.Page>합니다.  
  
 [!code-xaml[PageSnippets#XBAPStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 이 태그는 창을 여는 이전 코드와 같은 효과를 갖습니다.  
  
> [!NOTE]
>  탐색 모음에 대 한 자세한 내용은 참조 하십시오. [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)합니다.  
  
 처리는 <xref:System.Windows.Application.Startup> 이벤트를 열려면는 <xref:System.Windows.Window> 기본이 아닌 생성자를 사용 하 여 인스턴스화할 또는 해당 속성을 설정 하거나, 표시 하기 전에 해당 이벤트를 구독할 필요 하거나 모든 명령줄 인수를 처리 해야 하는 경우는 응용 프로그램을 시작할 때 제공 된 합니다.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### <a name="processing-command-line-arguments"></a>명령줄 인수 처리  
 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)], 명령 프롬프트 또는 바탕 화면에서 독립 실행형 응용 프로그램을 시작할 수 있습니다. 두 경우 모두 명령줄 인수를 응용 프로그램으로 전달할 수 있습니다. 다음 예제에서는 단일 명령줄 인수 "/StartMinimized"를 사용하여 시작되는 응용 프로그램을 보여 줍니다.  
  
 `wpfapplication.exe /StartMinimized`  
  
 응용 프로그램을 초기화 하는 동안 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 운영 체제에서 명령줄 인수를 검색 하 고 파이프라인 연산자는 <xref:System.Windows.Application.Startup> 를 통해 이벤트 처리기는 <xref:System.Windows.StartupEventArgs.Args%2A> 의 속성은 <xref:System.Windows.StartupEventArgs> 매개 변수입니다. 다음과 같은 코드를 사용하여 명령줄 인수를 검색하고 저장할 수 있습니다.  
  
 [!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 코드 핸들 <xref:System.Windows.Application.Startup> 확인 하려면 여부는 **/StartMinimized** 명령줄 인수가 제공; 열었을 있는 주 창 그렇다면는 <xref:System.Windows.WindowState> 의 <xref:System.Windows.WindowState.Minimized>합니다. 되므로 <xref:System.Windows.Window.WindowState%2A> 속성을 설정 해야 프로그래밍 방식으로 주 <xref:System.Windows.Window> 코드에서 명시적으로 열어야 합니다.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]검색 및 사용 하 여 시작 되기 때문에 명령줄 인수를 처리할 수 없는 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] 배포 (참조 [WPF 응용 프로그램 배포](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)). 그러나 XBAP를 시작하는 데 사용되는 URL에서 쿼리 문자열 매개 변수를 검색하고 처리할 수 있습니다.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### <a name="application-activation-and-deactivation"></a>응용 프로그램 활성화 및 비활성화  
 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)]를 사용하면 응용 프로그램 간을 전환할 수가 있습니다. 가장 일반적인 방법은 ALT+TAB 키 조합을 사용하는 것입니다. 응용 프로그램만 전환할 수 있는 표시 되어 있는 경우 <xref:System.Windows.Window> 사용자가 선택할 수 있는 합니다. 현재 선택 된 <xref:System.Windows.Window> 는 *활성 창* (라고도 *전경 창이*) 이며는 <xref:System.Windows.Window> 사용자 입력을 받는 합니다. 활성 창이 있는 응용 프로그램은는 *활성 응용 프로그램* (또는 *포그라운드 응용 프로그램이*). 다음과 같은 경우에 응용 프로그램이 활성 응용 프로그램이 됩니다.  
  
-   시작 하 고 표시는 <xref:System.Windows.Window>합니다.  
  
-   사용자가을 선택 하 여 다른 응용 프로그램에서 전환는 <xref:System.Windows.Window> 응용 프로그램에 있습니다.  
  
 처리 하 여 응용 프로그램이 활성화 될 때를 감지할 수 있습니다는 <xref:System.Windows.Application.Activated?displayProperty=nameWithType> 이벤트입니다.  
  
 마찬가지로 다음과 같은 경우에는 응용 프로그램이 비활성화됩니다.  
  
-   사용자가 현재 응용 프로그램에서 다른 응용 프로그램으로 전환하는 경우  
  
-   응용 프로그램이 종료되는 경우  
  
 처리 하 여 응용 프로그램이 비활성화 될 때를 감지할 수 있습니다는 <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> 이벤트입니다.  
  
 다음 코드에서는 처리 하는 방법을 보여 줍니다.는 <xref:System.Windows.Application.Activated> 및 <xref:System.Windows.Application.Deactivated> 응용 프로그램이 활성 상태 인지 확인 하는 이벤트입니다.  
  
 [!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 A <xref:System.Windows.Window> 수도 활성화 및 비활성화 합니다. 자세한 내용은 <xref:System.Windows.Window.Activated?displayProperty=nameWithType> 및 <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>를 참조하세요.  
  
> [!NOTE]
>  모두 <xref:System.Windows.Application.Activated?displayProperty=nameWithType> 나 <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> 에 대해 발생 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]합니다.  
  
<a name="Application_Shutdown"></a>   
### <a name="application-shutdown"></a>응용 프로그램 종료  
 다음과 같은 이유로 응용 프로그램이 종료되면 응용 프로그램 수명이 끝납니다.  
  
-   사용자가 모든 <xref:System.Windows.Window>합니다.  
  
-   사용자가 주 <xref:System.Windows.Window>합니다.  
  
-   사용자는 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 세션 로그 오프 하거나 종료 합니다.  
  
-   응용 프로그램별 조건이 충족된 경우  
  
 응용 프로그램 종료를 관리할 수 있도록 <xref:System.Windows.Application> 제공는 <xref:System.Windows.Application.Shutdown%2A> 메서드를는 <xref:System.Windows.Application.ShutdownMode%2A> 속성 및 <xref:System.Windows.Application.SessionEnding> 및 <xref:System.Windows.Application.Exit> 이벤트입니다.  
  
> [!NOTE]
>  <xref:System.Windows.Application.Shutdown%2A>이 있는 응용 프로그램에서 호출할 수만 <xref:System.Security.Permissions.UIPermission>합니다. 독립 실행형 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에는 항상이 권한을 가집니다. 그러나 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 인터넷 영역 부분 신뢰 보안 샌드박스에서 실행 되는 그렇지 않습니다.  
  
#### <a name="shutdown-mode"></a>종료 모드  
 대부분의 응용 프로그램은 모든 창을 닫거나 주 창을 닫으면 종료됩니다. 하지만 다른 응용 프로그램과 관련된 조건이 특정 응용 프로그램의 종료 시점을 결정하는 경우가 있습니다. 응용 프로그램을 설정 하 여 종료 됩니다 조건을 지정할 수 있습니다 <xref:System.Windows.Application.ShutdownMode%2A> 다음 중 하나가 지정 된 <xref:System.Windows.ShutdownMode> 열거형 값:  
  
-   <xref:System.Windows.ShutdownMode.OnLastWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnMainWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnExplicitShutdown>  
  
 기본값 <xref:System.Windows.Application.ShutdownMode%2A> 은 <xref:System.Windows.ShutdownMode.OnLastWindowClose>, 응용 프로그램를 사용자가 응용 프로그램에서 마지막 창의 닫을 때 자동으로 종료 되었음을 의미 합니다. 그러나 응용 프로그램을 종료 해야 하는 경우 주 창을 닫을 때, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 를 자동으로 수행 하는 설정 하면 <xref:System.Windows.Application.ShutdownMode%2A> 를 <xref:System.Windows.ShutdownMode.OnMainWindowClose>합니다. 다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 응용 프로그램별 종료 조건이 있는 경우 설정 <xref:System.Windows.Application.ShutdownMode%2A> 를 <xref:System.Windows.ShutdownMode.OnExplicitShutdown>합니다. 명시적으로 호출 하 여 응용 프로그램을 종료 하려면 작업은이 경우에 <xref:System.Windows.Application.Shutdown%2A> 메서드도 있습니다; 그렇지 않으면 응용 프로그램이 실행 모든 창을 닫은 경우에 계속 됩니다. <xref:System.Windows.Application.Shutdown%2A> 때 암시적으로 호출 됩니다는 <xref:System.Windows.Application.ShutdownMode%2A> 있거나 <xref:System.Windows.ShutdownMode.OnLastWindowClose> 또는 <xref:System.Windows.ShutdownMode.OnMainWindowClose>합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Application.ShutdownMode%2A>설정할 수 있습니다는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], 되지만 무시 됩니다; [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 가 항상 종료를 탐색에서 브라우저 또는 브라우저를 호스팅하는 경우는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 닫힙니다. 자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하세요.  
  
#### <a name="session-ending"></a>세션 종료  
 설명 하는 종료 조건을 <xref:System.Windows.Application.ShutdownMode%2A> 속성 응용 프로그램에 따라 다릅니다. 하지만 외부 조건에 따라 응용 프로그램이 종료되는 경우도 있습니다. 가장 일반적인 외부 상태 종료 하는 경우에 발생는 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 다음 작업에 의해 세션:  
  
-   로그오프  
  
-   종료  
  
-   다시 시작  
  
-   최대 절전 모드  
  
 시기를 알 수는 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 세션이 종료를 처리할 수 있습니다는 <xref:System.Windows.Application.SessionEnding> 이벤트, 다음 예제의 그림과 같이 합니다.  
  
 [!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 이 예제에서는 코드 검사는 <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> 속성 확인 하는 방법을 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 세션이 종료 되는 합니다. 또한 이 값을 사용하여 사용자에게 확인 메시지를 표시합니다. 이 코드를 설정 하는 사용자가을 종료 하려면 세션을 원하지 않을 경우 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 를 `true` 방지 하기 위해는 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 세션이 종료 됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Application.SessionEnding>에 대 한 끝나면 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]합니다.  
  
#### <a name="exit"></a>종료  
 응용 프로그램이 종료될 때 응용 프로그램 상태 유지와 같은 몇 가지 최종 처리를 수행해야 할 경우가 있습니다. 이러한 상황을 처리할 수 있습니다는 <xref:System.Windows.Application.Exit> 이벤트입니다.  
  
 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml1)]  
[!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml2)]  
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind1)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind1)]  
[!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind2)]
[!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind2)]  
  
 전체 예제를 참조 하십시오. [지속 및 응용 프로그램 세션 간에 응용 프로그램 범위의 속성 복원](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md)합니다.  
  
 <xref:System.Windows.Application.Exit>두 독립 실행형 응용 프로그램에 의해 처리 될 수 있습니다 및 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]합니다. 에 대 한 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], <xref:System.Windows.Application.Exit> 는 다음과 같은 경우에 있을 때 발생 합니다.  
  
-   [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 에서 멀리 이동 하 게 됩니다.  
  
-   [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)]때 호스팅하는 탭의 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 닫힙니다.  
  
-   브라우저가 닫힌 경우  
  
#### <a name="exit-code"></a>종료 코드  
 대부분의 경우 응용 프로그램은 운영 체제에서 사용자 요청에 대한 응답으로 시작하게 됩니다. 하지만 다른 응용 프로그램에서 일부 특정 작업을 수행하기 위해 응용 프로그램을 시작할 수도 있습니다. 시작된 응용 프로그램이 종료될 경우 시작하는 응용 프로그램에서 시작된 응용 프로그램이 종료되는 조건을 알고 싶을 수 있습니다. 이러한 상황에서는 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 응용 프로그램이 응용 프로그램 종료 코드를 반환할 수 있습니다. 기본적으로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램은 종료 코드 값 0을 반환 합니다.  
  
> [!NOTE]
>  디버깅할 경우 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], 응용 프로그램 종료 코드에 표시 됩니다는 **출력** 다음과 같은 메시지에 응용 프로그램이 종료 될 때 창:  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  열은 **출력** 클릭 하 여 창을 **출력** 에 **보기** 메뉴.  
  
 종료 코드를 변경 하려면 호출할 수 있습니다는 <xref:System.Windows.Application.Shutdown%28System.Int32%29> 오버 로드, 종료 코드는 정수 인수를 수락 합니다.  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 종료 코드의 값을 감지 하 고, 처리 하 여 변경할 수 있습니다는 <xref:System.Windows.Application.Exit> 이벤트입니다. <xref:System.Windows.Application.Exit> 이벤트 처리기가 전달는 <xref:System.Windows.ExitEventArgs> 사용 하 여 종료 코드에 대 한 액세스를 제공 하는 <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> 속성입니다. 자세한 내용은 <xref:System.Windows.Application.Exit>을 참조하십시오.  
  
> [!NOTE]
>  두 독립 실행형 응용 프로그램에서 종료 코드를 설정할 수 있습니다 및 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]합니다. 에 대 한 종료 코드 값을 무시 하는 반면 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]합니다.  
  
<a name="Unhandled_Exceptions"></a>   
### <a name="unhandled-exceptions"></a>처리되지 않은 예외  
 원하지 않는 예외를 throw하는 경우와 같이 응용 프로그램이 비정상적인 상황에서 종료되는 경우가 있습니다. 이런 경우에는 응용 프로그램에 예외를 검색하고 처리할 코드가 없을 수 있습니다. 이런 형식의 예외가 처리되지 않은 예외이며, 응용 프로그램이 닫히기 전에 다음 그림에 표시된 것과 비슷한 알림으로 표시됩니다.  
  
 ![처리되지 않은 예외 알림](../../../../docs/framework/wpf/app-development/media/applicationmanagementoverviewfigure2.png "ApplicationManagementOverviewFigure2")  
  
 사용자 환경의 관점에서는 응용 프로그램에서 다음과 같은 작업의 일부 또는 전부를 수행하여 이러한 기본 동작을 방지하는 것이 바람직합니다.  
  
-   사용자에게 친숙한 정보 표시  
  
-   응용 프로그램을 실행 상태로 유지  
  
-   , 개발자 기반의 예외 정보를 기록 하는 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 이벤트 로그입니다.  
  
 이 지원을 구현에 따라 달라 집니다 처리 되지 않은 예외를 탐지 하 되 어떤는 <xref:System.Windows.Application.DispatcherUnhandledException> 처리 됩니다.  
  
 [!code-xaml[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
 [!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind1)]
 [!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind1)]  
[!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind2)]
[!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind2)]  
  
 <xref:System.Windows.Application.DispatcherUnhandledException> 이벤트 처리기에 전달 되는 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> 예외 자체를 포함 하 여 처리 되지 않은 예외에 대 한 컨텍스트 정보를 포함 하는 매개 변수 (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>). 이 정보를 사용하여 예외를 처리하는 방법을 결정할 수 있습니다.  
  
 처리할 때 <xref:System.Windows.Application.DispatcherUnhandledException>를 설정 해야는 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> 속성을 `true`, 그렇지 않으면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 여전히 예외가 처리 되지 것으로 간주 하 고 앞에서 설명한 기본 동작으로 돌아갑니다. 처리 되지 않은 예외가 발생 하는 경우와 <xref:System.Windows.Application.DispatcherUnhandledException> 처리 되지 않은 이벤트 또는 이벤트를 처리 하 고 <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> 로 설정 된 `false`, 응용 프로그램이 즉시 종료 합니다. 또한 다른 <xref:System.Windows.Application> 이벤트가 발생 합니다. 따라서 처리할 필요가 <xref:System.Windows.Application.DispatcherUnhandledException> 응용 프로그램에 응용 프로그램이 종료 되기 전에 실행 해야 하는 코드가 있을 경우.  
  
 처리되지 않은 예외의 결과로 응용 프로그램이 종료될 수는 있지만 응용 프로그램은 대개 다음 섹션에서 설명하는 것처럼 사용자 요청에 대한 응답으로 종료됩니다.  
  
<a name="Application_Lifetime_Events"></a>   
### <a name="application-lifetime-events"></a>응용 프로그램 수명 이벤트  
 독립 실행형 응용 프로그램 및 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 수명이 동일 필요는 없습니다. 다음 그림에서는 독립 실행형 응용 프로그램 수명에서의 주요 이벤트와 이러한 이벤트가 발생하는 순서를 보여 줍니다.  
  
 ![독립 실행형 응용 프로그램 &#45; 응용 프로그램 개체 이벤트](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")  
  
 마찬가지로, 다음 그림에 이러한 키 이벤트의 수명 중에 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], 발생 하는 순서를 보여 줍니다.  
  
 ![XBAP &#45; 응용 프로그램 개체 이벤트](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Application>  
 [WPF 창 개요](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)  
 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)  
 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)  
 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)  
 [응용 프로그램 모델: 방법 도움말 항목](http://msdn.microsoft.com/en-us/76771b09-3688-4d1c-8818-9b3f4cf39a30)  
 [응용 프로그램 개발](../../../../docs/framework/wpf/app-development/index.md)
