---
title: "WPF 창 개요 | Microsoft Docs"
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
  - "응용 프로그램, 호스팅(hosting)"
  - "내용, 표시"
  - "내용, 프로시저 코드를 통해 표시"
  - "내용, XAML을 통해 표시"
  - "만들기, windows"
  - "대화 상자"
  - "콘텐츠 표시"
  - "프로시저 코드를 통해 콘텐츠 표시"
  - "XAML 페이지 표시"
  - "이벤트"
  - "호스팅(hosting), 응용 프로그램"
  - "창 관리"
  - "모달 대화 상자"
  - "모달 창"
  - "NavigationWindow 개체"
  - "Page 개체"
  - "프로시저 코드, 콘텐츠 표시"
  - "창 이벤트"
  - "창 관리"
  - "창 개체"
  - "windows"
  - "XAML 페이지, 표시"
  - "XAML, 콘텐츠 표시"
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
caps.latest.revision: 65
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 60
---
# WPF 창 개요
사용자는 창을 통해 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 독립 실행형 응용 프로그램과 상호 작용합니다.  창의 기본 용도는 데이터를 시각화하는 콘텐츠를 호스팅하고 사용자가 데이터와 상호 작용할 수 있도록 하는 것입니다. 독립 실행형 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서는 <xref:System.Windows.Window> 클래스를 사용하여 자체 창을 제공합니다.  이 항목에서는 독립 실행형 응용 프로그램에서 창을 만들고 관리하는 방법에 대한 기본적인 내용을 다루기 전에 <xref:System.Windows.Window>를 소개합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 및 느슨한 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지를 비롯한 브라우저에서 호스팅되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서는 자체 창을 제공하지 않습니다.  대신 [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]에서 제공하는 창에서 호스팅됩니다.  [WPF XAML 브라우저 응용 프로그램 개요](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)를 참조하십시오.  
  
   
  
<a name="TheWindowClass"></a>   
## Window 클래스  
 다음 그림에서는 창을 구성하는 부분을 보여 줍니다.  
  
 ![창 요소](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure1.PNG "WindowOverviewFigure1")  
  
 창은 비클라이언트 영역과 클라이언트 영역의 두 영역으로 나뉩니다.  
  
 창의 *비클라이언트 영역*은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에 의해 구현되며 다음을 비롯하여 대부분의 창에 공통적인 부분이 포함됩니다.  
  
-   테두리  
  
-   제목 표시줄  
  
-   아이콘  
  
-   최소화, 최대화 및 복원 단추  
  
-   닫기 단추  
  
-   사용자가 창을 최소화, 최대화, 복원, 이동, 크기 조정 및 닫을 수 있는 메뉴 항목이 들어 있는 시스템 메뉴  
  
 창의 *클라이언트 영역*은 창의 비클라이언트 영역 내에 포함된 영역이며, 개발자는 이 영역을 사용하여 메뉴 모음, 도구 모음 및 컨트롤 등의 응용 프로그램 특정 콘텐츠를 추가합니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 창은 다음을 수행하기 위해 사용하는 <xref:System.Windows.Window> 클래스에 의해 캡슐화됩니다.  
  
-   창을 표시합니다.  
  
-   창의 크기, 위치 및 모양을 구성합니다.  
  
-   응용 프로그램별 콘텐츠를 호스팅합니다.  
  
-   창의 수명을 관리합니다.  
  
<a name="DefiningAWindow"></a>   
## 창 구현  
 일반적인 창의 구현은 모양과 동작으로 구성됩니다. *모양*은 창이 사용자에게 표시되는 형태를 정의하고 *동작*은 사용자가 상호 작용할 때 창이 기능하는 방식을 정의합니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 코드나 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그를 사용하여 창의 모양과 동작을 구현할 수 있습니다.  
  
 하지만 다음 예제에서처럼 창의 모양은 대개 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그를 사용하여 구현하며 그 동작은 코드 숨김을 사용하여 구현합니다.  
  
 [!code-xml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 파일과 코드 숨김 파일이 함께 동작하려면 다음이 필요합니다.  
  
-   태그에서 `Window` 요소에 `x:Class` 특성이 포함되어야 합니다.  응용 프로그램을 빌드할 때 태그 파일에 `x:Class`가 있으면 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)]에서는 <xref:System.Windows.Window>에서 파생되며 `x:Class` 특성에 의해 이름이 지정되는 `partial` 클래스를 만듭니다.  이를 위해서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 스키마에 대한 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스 선언을 추가해야 합니다\(`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`\).  생성된 `partial` 클래스는 이벤트 등록을 위해 호출되고 태그에서 구현되는 속성을 설정하는 `InitializeComponent` 메서드를 구현합니다.  
  
-   코드 숨김에서 클래스는 태그의 `x:Class` 특성으로 지정된 이름과 같은 이름을 가진 `partial` 클래스여야 하며 <xref:System.Windows.Window>에서 파생되어야 합니다.  이를 통해 응용 프로그램 빌드 시 태그 파일에 대해 생성되는 `partial` 클래스와 코드 숨김 파일을 연결할 수 있습니다\([WPF 응용 프로그램 만들기](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md) 참조\).  
  
-   코드 숨김에서 <xref:System.Windows.Window> 클래스는 `InitializeComponent` 메서드를 호출하는 생성자를 구현해야 합니다.  `InitializeComponent`는 태그 파일에서 생성된 `partial` 클래스에 의해 구현되어 이벤트를 등록하고 태그에 정의된 속성을 설정합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]를 사용하여 프로젝트에 새 <xref:System.Windows.Window>를 추가하면 <xref:System.Windows.Window>가 태그와 코드 숨김을 모두 사용하여 구현되며, 여기서 설명한 것처럼 태그와 코드 숨김 파일 사이에 연결을 만들기 위해 필요한 구성을 포함합니다.  
  
 이 구성을 사용하면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그에서 창의 모양을 정의하고 코드 숨김에서 동작을 구현하는 작업에 집중할 수 있습니다.  다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그에서 구현된 단추와 코드 숨김에서 구현되는 단추의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대한 이벤트 처리기가 있는 창을 보여 줍니다.  
  
 [!code-xml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## MSBuild에 대해 창 정의 구성  
 창을 구현하는 방법에 따라 창을 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]에 대해 구성하는 방법이 달라집니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그와 코드 숨김을 모두 사용하여 정의되는 창의 경우에는 다음과 같습니다.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 파일은 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` 항목으로 구성됩니다.  
  
-   코드 숨김 파일은 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` 항목으로 구성됩니다.  
  
 다음 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 프로젝트 파일에서 이를 확인할 수 있습니다.  
  
```  
<Project ... xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 빌드에 대한 자세한 내용은 [WPF 응용 프로그램 만들기](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)를 참조하십시오.  
  
<a name="WindowLifetime"></a>   
## 창 수명  
 다른 클래스와 마찬가지로 창에는 창이 열린 후 처음 인스턴스화될 때 시작하여, 열린 후 활성화 및 비활성화되고 최종적으로 닫힐 때까지의 기간인 수명이 있습니다.  
  
   
  
<a name="Opening_a_Window"></a>   
### 창 열기  
 창을 열려면 먼저 다음 예제에서 설명하는 것처럼 창의 인스턴스를 만듭니다.  
  
 [!code-xml[WindowsOverviewStartupEventSnippets#AppMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 이 예제에서 `MarkupAndCodeBehindWindow`는 <xref:System.Windows.Application.Startup> 이벤트 발생 시 발생하는 응용 프로그램 시작 시점에 인스턴스화됩니다.  
  
 창이 인스턴스화될 때는 자동으로 해당 창에 대한 참조가 <xref:System.Windows.Application> 개체에서 관리하는 창 목록에 추가됩니다\(<xref:System.Windows.Application.Windows%2A?displayProperty=fullName> 참조\).  또한 인스턴스화될 첫 번째 창은 기본적으로 <xref:System.Windows.Application>에 의해 기본 응용 프로그램 창으로 설정됩니다\(<xref:System.Windows.Application.MainWindow%2A?displayProperty=fullName> 참조\).  
  
 마지막으로 <xref:System.Windows.Window.Show%2A> 메서드를 호출하여 창을 엽니다. 다음 그림에서 그 결과를 볼 수 있습니다.  
  
 ![Window.Show 호출로 열린 창](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure8.png "WindowOverviewFigure8")  
  
 <xref:System.Windows.Window.Show%2A>를 호출하여 여는 창은 모덜리스 창입니다. 즉, 응용 프로그램은 사용자가 같은 응용 프로그램의 다른 창을 활성화할 수 있는 모드에서 동작합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Window.ShowDialog%2A>를 호출하여 대화 상자와 같은 창을 모달 형식으로 엽니다.  자세한 내용은 [대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Window.Show%2A>를 호출하면 창은 초기화 작업을 수행한 후 표시되어 사용자 입력을 받을 수 있는 인프라를 설정합니다.  창이 초기화되면 <xref:System.Windows.Window.SourceInitialized> 이벤트가 발생하고 창이 표시됩니다.  
  
 또한 <xref:System.Windows.Application.StartupUri%2A>를 설정하여 응용 프로그램이 시작될 때 자동으로 열리는 첫 번째 창을 지정할 수 있습니다.  
  
 [!code-xml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 응용 프로그램이 시작되면 <xref:System.Windows.Application.StartupUri%2A>의 값으로 지정된 창이 모달리스 형식으로 열립니다. 내부적으로는 창의 <xref:System.Windows.Window.Show%2A> 메서드를 호출하여 창을 엽니다.  
  
<a name="Ownership"></a>   
#### 창 소유권  
 <xref:System.Windows.Window.Show%2A> 메서드를 사용하여 연 창에는 해당 창을 만든 창과의 암시적 관계가 없습니다. 즉, 사용자는 다른 창에 독립적으로 각 창과 상호 작용할 수 있으므로 각 창은 다음을 수행할 수 있습니다.  
  
-   다른 창을 가립니다\(<xref:System.Windows.Window.Topmost%2A> 속성이 `true`로 설정된 창이 있는 경우 제외\).  
  
-   다른 창에 영향을 주지 않고 최소화, 최대화 및 복원합니다.  
  
 일부 창은 해당 창을 여는 창과의 관계를 필요로 합니다.  예를 들어 [!INCLUDE[TLA#tla_ide](../../../../includes/tlasharptla-ide-md.md)] 응용 프로그램에서는 일반적으로 해당 창을 만드는 창을 가리는 동작을 하는 속성 창과 도구 창을 열 수 있습니다.  또한 이러한 창은 항상 해당 창을 만든 창과 함께 닫히고, 최소화되고, 최대화되고, 복원되어야 합니다.  이러한 관계는 하나의 창이 다른 창을 *소유*하도록 하는 방식으로 설정할 수 있습니다. *소유된 창*의 <xref:System.Windows.Window.Owner%2A> 속성을 *소유자 창*에 대한 참조로 설정하여 이런 관계를 만듭니다.  다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 소유권이 설정된 후:  
  
-   소유된 창은 <xref:System.Windows.Window.Owner%2A> 속성의 값을 검사하여 소유자 창을 참조할 수 있습니다.  
  
-   소유자 창은 <xref:System.Windows.Window.OwnedWindows%2A> 속성의 값을 검사하여 해당 창 소유의 모든 창을 검색할 수 있습니다.  
  
<a name="Preventing"></a>   
#### 창 활성화 방지  
 인터넷 메신저 스타일 응용 프로그램의 대화 창이나 전자 메일 응용 프로그램의 알림 창과 같이 창이 표시될 때 활성화하지 않아야 하는 경우가 있습니다.  
  
 응용 프로그램에 표시될 때 활성화하지 않아야 할 창이 있는 경우에는 <xref:System.Windows.Window.Show%2A> 메서드를 처음으로 호출하기 전에 해당 창의 <xref:System.Windows.Window.ShowActivated%2A> 속성을 `false`로 설정할 수 있습니다.  이렇게 하면 다음과 같은 결과가 나타납니다.  
  
-   창이 활성화되지 않습니다.  
  
-   창의 <xref:System.Windows.Window.Activated> 이벤트가 발생하지 않습니다.  
  
-   현재 활성 창이 활성 상태로 유지됩니다.  
  
 그러나 사용자가 클라이언트 영역이나 비클라이언트 영역을 클릭하여 창을 활성화하면 해당 창이 활성화됩니다.  이 경우 다음과 같은 결과가 나타납니다.  
  
-   창이 활성화됩니다.  
  
-   창의 <xref:System.Windows.Window.Activated> 이벤트가 발생합니다.  
  
-   이전에 활성 상태였던 창이 비활성화됩니다.  
  
-   사용자의 동작에 대한 응답으로 창의 <xref:System.Windows.Window.Deactivated> 및 <xref:System.Windows.Window.Activated> 이벤트가 발생합니다.  
  
<a name="Window_Activation"></a>   
### 창 활성화  
 <xref:System.Windows.Window.ShowActivated%2A>를 `false`로 설정하는 경우를 제외하고는 창을 처음으로 열면 해당 창이 활성 창이 됩니다.  *활성 창*은 키 입력 및 마우스 클릭과 같은 사용자 입력을 현재 캡처하고 있는 창입니다.  활성화된 창은 <xref:System.Windows.Window.Activated> 이벤트를 발생시킵니다.  
  
> [!NOTE]
>  창을 처음 열면 <xref:System.Windows.Window.Activated> 이벤트가 발생한 후 <xref:System.Windows.FrameworkElement.Loaded> 및 <xref:System.Windows.Window.ContentRendered> 이벤트가 발생합니다.  이를 염두에 두면 창은 <xref:System.Windows.Window.ContentRendered>가 발생할 때 열리는 것으로 간주할 수 있습니다.  
  
 창이 활성 창이 되면 사용자는 같은 응용 프로그램의 다른 창을 활성화하거나 다른 응용 프로그램을 활성화할 수 있습니다.  이 경우 현재의 활성 창은 비활성화되고 <xref:System.Windows.Window.Deactivated> 이벤트를 발생시킵니다.  마찬가지로 사용자가 현재 비활성화된 창을 선택하면 창이 다시 활성화되고 <xref:System.Windows.Window.Activated>가 발생합니다.  
  
 <xref:System.Windows.Window.Activated> 및 <xref:System.Windows.Window.Deactivated>를 처리하는 한 가지 일반적인 이유는 창이 활성 상태일 때만 실행될 수 있는 기능을 설정 또는 해제하기 위한 것입니다.  예를 들어 일부 창은 게임 및 비디오 플레이어를 포함하여 지속적인 사용자의 입력이나 주의가 필요한 대화식 콘텐츠를 표시합니다.  다음 예제에서는 이 동작을 구현하기 위해 <xref:System.Windows.Window.Activated> 및 <xref:System.Windows.Window.Deactivated>를 처리하는 방법을 보여 주는 단순화된 비디오 플레이어입니다.  
  
 [!code-xml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 다른 유형의 응용 프로그램은 창이 비활성화되었을 때 계속 백그라운드에서 코드를 실행할 수 있습니다.  예를 들어 메일 클라이언트는 사용자가 다른 응용 프로그램을 사용하고 있을 때 메일 서버를 계속 폴링할 수 있습니다.  이러한 응용 프로그램에는 기본 창이 비활성화되었을 때 다른 동작 또는 추가 동작을 제공하기도 합니다.  메일 프로그램의 경우에 이것은 새 메일 항목을 받은 편지함에 추가하고 시스템 트레이에 알림 아이콘을 추가하는 작업을 의미할 수 있습니다.  알림 아이콘은 메일 창이 활성 상태가 아닐 때만 표시하면 됩니다. 활성 상태인지 여부는 <xref:System.Windows.Window.IsActive%2A> 속성을 검사하여 확인할 수 있습니다.  
  
 백그라운드 작업이 완료되면 <xref:System.Windows.Window.Activate%2A> 메서드를 호출하여 사용자에게 더 신속하게 알릴 수 있습니다.  <xref:System.Windows.Window.Activate%2A>가 호출되었을 때 사용자가 활성화된 다른 응용 프로그램과 상호 작용하고 있으면 창의 작업 표시줄 단추가 깜박입니다.  사용자가 현재 응용 프로그램과 상호 작용하고 있을 때 <xref:System.Windows.Window.Activate%2A>를 호출하면 창이 포그라운드로 전환됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Application.Activated?displayProperty=fullName> 및 <xref:System.Windows.Application.Deactivated?displayProperty=fullName> 이벤트를 사용하여 응용 프로그램 범위 활성화를 처리할 수 있습니다.  
  
<a name="Closing_a_Window"></a>   
### 창 닫기  
 창의 수명은 사용자가 창을 닫을 때 끝나게 됩니다.  창은 다음을 포함하여 비클라이언트 영역의 요소를 사용하여 닫을 수 있습니다.  
  
-   **시스템** 메뉴의 **닫기** 항목  
  
-   Alt\+F4 누르기  
  
-   **닫기** 단추 누르기  
  
 클라이언트 영역에 창을 닫기 위한 추가적인 메커니즘을 제공할 수 있으며 이 메커니즘에는 일반적으로 다음이 포함됩니다.  
  
-   **파일** 메뉴의 **끝내기** 항목\(일반적으로 기본 응용 프로그램 창\)  
  
-   **파일** 메뉴의 **닫기** 항목\(일반적으로 보조 응용 프로그램 창\)  
  
-   **취소** 단추\(일반적으로 모달 대화 상자\)  
  
-   **닫기** 단추\(일반적으로 모덜리스 대화 상자\)  
  
 이러한 사용자 지정 메커니즘 중 하나에 응답하여 창을 닫으려면 <xref:System.Windows.Window.Close%2A> 메서드를 호출해야 합니다.  다음 예제에서는 **파일** 메뉴에서 **끝내기**를 선택하여 창을 닫는 기능을 구현합니다.  
  
 [!code-xml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 창이 닫히면 <xref:System.Windows.Window.Closing> 및 <xref:System.Windows.Window.Closed>의 두 이벤트가 발생합니다.  
  
 <xref:System.Windows.Window.Closing>은 창이 닫히기 전에 발생하며 창 닫기를 방지할 수 있는 메커니즘을 제공합니다.  대개 창이 닫히면 안 되는 한 가지 이유는 창 콘텐츠에 수정된 데이터가 있는 경우입니다.  이 상황에서는 <xref:System.Windows.Window.Closing> 이벤트를 처리하여 데이터가 변경되었는지 검사하고, 변경되었으면 사용자에게 데이터를 저장하지 않고 창을 닫을 것인지 아니면 창 닫기를 취소할 것인지 묻습니다.  다음 예제에서는 <xref:System.Windows.Window.Closing> 처리의 핵심적인 측면을 보여 줍니다.  
  
 [!code-csharp[WindowClosingSnippets#WindowClosingCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs#windowclosingcodebehind1)]
 [!code-vb[WindowClosingSnippets#WindowClosingCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb#windowclosingcodebehind1)]  
[!code-csharp[WindowClosingSnippets#WindowClosingCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs#windowclosingcodebehind2)]
[!code-vb[WindowClosingSnippets#WindowClosingCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb#windowclosingcodebehind2)]  
  
 창 닫기를 방지하기 위해 `true`로 설정한 `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 구현하는 <xref:System.ComponentModel.CancelEventArgs>를 <xref:System.Windows.Window.Closing> 이벤트 처리기가 전달합니다.  
  
 <xref:System.Windows.Window.Closing>이 처리되지 않거나, 처리는 되었지만 취소되지 않은 경우에는 창이 닫힙니다.  창이 실제로 닫히기 직전에 <xref:System.Windows.Window.Closed>가 발생합니다.  이 시점에서는 창 닫기를 방지할 수 없습니다.  
  
> [!NOTE]
>  기본 응용 프로그램 창\(<xref:System.Windows.Application.MainWindow%2A> 참조\) 또는 마지막 창이 닫힐 때 자동으로 종료되도록 응용 프로그램을 구성할 수 있습니다.  자세한 내용은 <xref:System.Windows.Application.ShutdownMode%2A>를 참조하십시오.  
  
 비클라이언트 및 클라이언트 영역에서 제공되는 메커니즘을 통해 창을 명시적으로 닫을 수 있지만, 창은 다음을 비롯하여 응용 프로그램 또는 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]의 다른 부분에서 발생한 동작에 의해 암시적으로 닫힐 수도 있습니다.  
  
-   사용자가 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)]를 로그오프하거나 종료하는 경우  
  
-   창의 소유자가 닫히는 경우\(<xref:System.Windows.Window.Owner%2A> 참조\)  
  
-   기본 응용 프로그램 창이 닫히고 <xref:System.Windows.Application.ShutdownMode%2A>가 <xref:System.Windows.ShutdownMode>인 경우  
  
-   <xref:System.Windows.Application.Shutdown%2A>이 호출됩니다.  
  
> [!NOTE]
>  창을 닫은 뒤에는 다시 열 수 없습니다.  
  
<a name="Window_Lifetime_Events"></a>   
### 창 수명 이벤트  
 다음 그림에서는 창의 수명에서 발생하는 주요 이벤트를 순서대로 보여 줍니다.  
  
 ![창 수명](../../../../docs/framework/wpf/app-development/media/windowlifetimeevents.png "WindowLifetimeEvents")  
  
 다음 그림에서는 활성화되지 않고 표시되는 창의 수명 동안 발생하는 주요 이벤트를 순서대로 보여 줍니다. 여기서는 창을 표시하기 전에 <xref:System.Windows.Window.ShowActivated%2A>가 `false`로 설정됩니다.  
  
 ![창 수명&#40;Window.ShowActivated &#61; False&#41;](../../../../docs/framework/wpf/app-development/media/windowlifetimenoact.png "WindowLifetimeNoAct")  
  
<a name="WindowLocation"></a>   
## 창 위치  
 창은 열릴 때 바탕 화면에 상대적인 x 및 y 크기의 위치를 가집니다.  이 위치는 각각 <xref:System.Windows.Window.Left%2A> 및 <xref:System.Windows.Window.Top%2A> 속성을 검사하여 확인할 수 있습니다.  이 속성을 설정하여 창의 위치를 변경할 수 있습니다.  
  
 또한 <xref:System.Windows.Window.WindowStartupLocation%2A> 속성을 다음 <xref:System.Windows.WindowStartupLocation> 열거형 값 중 하나로 설정하면 <xref:System.Windows.Window>가 처음 나타날 때의 초기 위치를 지정할 수 있습니다.  
  
-   <xref:System.Windows.WindowStartupLocation>\(기본값\)  
  
-   <xref:System.Windows.WindowStartupLocation>  
  
-   <xref:System.Windows.WindowStartupLocation>  
  
 시작 위치를 <xref:System.Windows.WindowStartupLocation>로 지정하고 <xref:System.Windows.Window.Left%2A> 및 <xref:System.Windows.Window.Top%2A> 속성을 설정하지 않으면 <xref:System.Windows.Window>가 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)]에게 표시될 위치를 묻습니다.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### 최상위 창 및 Z 순서  
 창에는 x 및 y 위치 이외에도 다른 창과 상대적인 수직 위치를 결정하는 z 차원의 위치도 있습니다.  이를 창의 z 순서라고 하며 여기에는 일반 z 순서와 최상위 z 순서의 두 가지 유형이 있습니다.  *일반 z 순서*에서 창의 위치는 현재 활성화되었는지 여부에 따라 결정됩니다.  기본적으로 창은 일반 z 순서로 배치됩니다.  *최상위 z 순서*에서 창의 위치도 현재 활성화되었는지 여부에 따라 결정됩니다.  최상위 z 수준의 창은 항상 일반 z 순서 창의 위에 위치합니다.  창의 <xref:System.Windows.Window.Topmost%2A> 속성을 `true`로 설정하면 창이 최상위 z 순서로 배치됩니다.  
  
 [!code-xml[WindowsOverviewSnippets#TopmostWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#TopmostWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup2)]  
  
 각 z 순서 안에서는 현재 활성화된 창이 같은 z 순서를 가진 다른 모든 창 위에 나타납니다.  
  
<a name="WindowSize"></a>   
## 창 크기  
 창은 바탕 화면 위치 이외에도 다양한 너비 및 높이 속성과 <xref:System.Windows.Window.SizeToContent%2A>를 비롯한 몇 가지 속성에 의해 결정되는 크기를 가집니다.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.MaxWidth%2A>는 창이 수명 동안 가질 수 있는 너비의 범위를 관리하는 데 사용하며 다음 예제와 같이 구성됩니다.  
  
 [!code-xml[WindowsOverviewSnippets#WidthWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WidthWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup2)]  
  
 창 높이는 <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.MaxHeight%2A>로 관리하며 다음 예제와 같이 구성됩니다.  
  
 [!code-xml[WindowsOverviewSnippets#HeightWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#HeightWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup2)]  
  
 다양한 너비 값과 높이 값이 각각 범위를 지정하고 있기 때문에, 크기 조정 가능한 창의 너비와 높이는 지정한 범위 내에서 임의의 크기로 설정될 수 있습니다.  현재 너비와 높이를 확인하려면 각각 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A>를 검사합니다.  
  
 창의 너비와 높이를 창 콘텐츠의 크기에 맞추려면 값이 다음과 같은 <xref:System.Windows.Window.SizeToContent%2A> 속성을 사용할 수 있습니다.  
  
-   <xref:System.Windows.SizeToContent>.  아무런 영향이 없습니다\(기본값\).  
  
-   <xref:System.Windows.SizeToContent>.  콘텐츠 너비에 맞춥니다. <xref:System.Windows.FrameworkElement.MinWidth%2A> 및 <xref:System.Windows.FrameworkElement.MaxWidth%2A>를 모두 콘텐츠의 너비로 설정하는 것과 같은 효과를 냅니다.  
  
-   <xref:System.Windows.SizeToContent>.  콘텐츠 높이에 맞춥니다. <xref:System.Windows.FrameworkElement.MinHeight%2A> 및 <xref:System.Windows.FrameworkElement.MaxHeight%2A>를 모두 콘텐츠의 높이로 설정하는 것과 같은 효과를 냅니다.  
  
-   <xref:System.Windows.SizeToContent>.  콘텐츠 너비와 높이에 맞춥니다. <xref:System.Windows.FrameworkElement.MinHeight%2A> 및 <xref:System.Windows.FrameworkElement.MaxHeight%2A>를 모두 콘텐츠 높이로 설정하고 <xref:System.Windows.FrameworkElement.MinWidth%2A> 및 <xref:System.Windows.FrameworkElement.MaxWidth%2A>를 모두 콘텐츠 너비로 설정하는 것과 같은 효과를 냅니다.  
  
 다음은 창이 처음 표시 될 때 내용, 수직 및 수평을 맞추기 위해 크기는 자동으로 표시 합니다.  
  
 [!code-xml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#SizeToContentWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup2)]  
  
 다음 예제를 설정 하는 방법을 보여 줍니다 있는 <xref:System.Windows.Window.SizeToContent%2A> 속성에는 창 크기를 조정 내용에 맞게 지정 하는 코드입니다.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## 크기 조정 속성에 대한 우선 순위 순서  
 기본적으로 창의 다양한 크기 속성이 결합되어 크기 조정 가능한 창의 너비와 높이의 범위가 정의됩니다.  유효한 범위를 유지하기 위해 <xref:System.Windows.Window>는 다음의 우선 순위 순서를 사용하여 크기 속성의 값을 평가합니다.  
  
 **높이 속성:**  
  
1.  <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=fullName> \>  
  
2.  <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=fullName> \>  
  
3.  <xref:System.Windows.SizeToContent?displayProperty=fullName>\/<xref:System.Windows.SizeToContent?displayProperty=fullName> \>  
  
4.  <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=fullName>  
  
 **너비 속성:**  
  
1.  <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=fullName> \>  
  
2.  <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=fullName> \>  
  
3.  <xref:System.Windows.SizeToContent?displayProperty=fullName>\/<xref:System.Windows.SizeToContent?displayProperty=fullName> \>  
  
4.  <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=fullName>  
  
 우선 순위에 따라 <xref:System.Windows.Window.WindowState%2A> 속성으로 관리되는 최대화되었을 때의 창 크기도 결정됩니다.  
  
<a name="WindowState"></a>   
## 창 상태  
 크기 조정 가능한 창의 수명은 표준, 최소화 및 최대화의 세 가지 상태를 가질 수 있습니다.  *표준* 상태는 창의 기본 상태입니다.  크기 조정 가능 창이 표준 상태인 경우 사용자는 크기 조정 그립이나 테두리를 사용하여 창을 이동하고 크기 조정할 수 있습니다.  
  
 *최소화* 상태의 창은 <xref:System.Windows.Window.ShowInTaskbar%2A>가 `true`로 설정된 경우 작업 표시줄 단추로 축소됩니다. 그렇지 않은 경우에는 가능한 가장 작은 크기로 축소되고 바탕 화면의 왼쪽 아래 모서리에 스스로 재배치됩니다.  이러한 최소화된 창 유형은 테두리나 크기 조정 그립을 사용하여 크기 조정할 수 없습니다. 하지만 작업 표시줄에 표시되지 않은 최소화된 창은 바탕 화면에서 끌 수 있습니다.  
  
 *최대화* 상태의 창은 가능한 가장 큰 크기로 확대되며 <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A> 및 <xref:System.Windows.Window.SizeToContent%2A> 속성에 지정된 크기까지 확대될 수 있습니다.  최소화된 창과 마찬가지로 최대화된 창은 크기 조정 그립을 사용하거나 테두리를 끌어서 크기 조정할 수 없습니다.  
  
> [!NOTE]
>  창의 <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성 값은 창이 현재 최대화되거나 최소화되어 있어도 항상 표준 상태에 해당하는 값을 나타냅니다.  
  
 창의 <xref:System.Windows.Window.WindowState%2A> 속성을 설정하여 창의 상태를 구성할 수 있으며 이 속성에는 다음 <xref:System.Windows.WindowState> 열거형 값 중 하나를 사용할 수 있습니다.  
  
-   <xref:System.Windows.WindowState>\(기본값\)  
  
-   <xref:System.Windows.WindowState>  
  
-   <xref:System.Windows.WindowState>  
  
 다음 예제에서는 열릴 때 최대화되어 표시되는 창을 만드는 방법을 보여 줍니다.  
  
 [!code-xml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WindowStateWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup2)]  
  
 일반적으로 창의 초기 상태를 구성하려면 <xref:System.Windows.Window.WindowState%2A>를 설정해야 합니다.  크기 조정 가능한 창이 표시되면 사용자는 창의 제목 표시줄에서 최소화, 최대화 및 복원 단추를 눌러 창 상태를 변경할 수 있습니다.  
  
<a name="WindowAppearance"></a>   
## 창 모양  
 단추, 레이블 및 텍스트 상자와 같은 창 특정 콘텐츠를 창에 추가하여 창의 클라이언트 영역의 모양을 변경할 수 있습니다.  비클라이언트 영역을 구성하기 위해 <xref:System.Windows.Window>는 창의 아이콘을 설정하는 <xref:System.Windows.Window.Icon%2A>과 제목을 설정하는 <xref:System.Windows.Window.Title%2A> 같은 몇 가지 속성을 제공합니다.  
  
 또한 창의 크기 조정 모드, 창 스타일 및 바탕 화면 작업 표시줄에 단추로 표시될 것인지 여부를 구성하여 비클라이언트 영역 테두리의 모양과 동작을 변경할 수도 있습니다.  
  
   
  
<a name="Resize_Mode"></a>   
### 크기 조정 모드  
 <xref:System.Windows.Window.WindowStyle%2A> 속성에 따라 사용자가 창의 크기를 조정하는 방법\(그리고 조정 가능 여부\)을 제어할 수 있습니다.  선택한 창 스타일에 따라 사용자가 마우스로 테두리를 끌어서 창 크기를 조정할 수 있는지 여부, **최소화**, **최대화** 및 **크기 조정** 단추가 비클라이언트 영역에 나타나는지 여부 및 나타나는 경우 해당 단추를 사용할 수 있는지 여부가 결정됩니다.  
  
 <xref:System.Windows.Window.ResizeMode%2A> 속성을 설정하여 창 크기를 조정하는 방법을 구성할 수 있습니다. 이 속성에는 다음 <xref:System.Windows.ResizeMode> 열거형 값 중 하나를 사용할 수 있습니다.  
  
-   <xref:System.Windows.ResizeMode>  
  
-   <xref:System.Windows.ResizeMode>  
  
-   <xref:System.Windows.ResizeMode>\(기본값\)  
  
-   <xref:System.Windows.ResizeMode>  
  
 <xref:System.Windows.Window.WindowStyle%2A>과 마찬가지로 창의 크기 조정 모드는 수명 내에서 변경될 가능성이 낮습니다. 따라서 대개의 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그에서 설정합니다.  
  
 [!code-xml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#ResizeModeWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup2)]  
  
 <xref:System.Windows.Window.WindowState%2A> 속성을 검사하여 창의 최대화, 최소화 또는 복원 여부를 확인할 수 있습니다.  
  
<a name="Window_Style"></a>   
### 창 스타일  
 창의 비클라이언트 영역에서 노출되는 테두리는 대부분의 응용 프로그램에 적합합니다.  하지만 창의 유형에 따라 다른 유형의 테두리가 필요하거나 테두리가 전혀 필요 없는 경우가 있습니다.  
  
 창의 테두리 유형을 제어하려면 <xref:System.Windows.Window.WindowStyle%2A> 속성을 다음과 같은 <xref:System.Windows.WindowStyle> 열거형 값 중 하나로 설정합니다.  
  
-   <xref:System.Windows.WindowStyle>  
  
-   <xref:System.Windows.WindowStyle>\(기본값\)  
  
-   <xref:System.Windows.WindowStyle>  
  
-   <xref:System.Windows.WindowStyle>  
  
 이러한 창 스타일의 효과는 다음 그림에서 볼 수 있습니다.  
  
 ![창 스타일](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure6.png "WindowOverviewFigure6")  
  
 <xref:System.Windows.Window.WindowStyle%2A>은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 또는 코드를 사용하여 설정할 수 있습니다. 창의 수명 내에서 이를 변경할 가능성이 많지 않으므로 대개의 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그를 사용하여 구성합니다.  
  
 [!code-xml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WindowStyleWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup2)]  
  
#### 사각형이 아닌 창 스타일  
 <xref:System.Windows.Window.WindowStyle%2A>로 사용할 수 있는 테두리 스타일로 부족한 경우가 있을 수 있습니다.  예를 들어 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)]에서처럼 사각형이 아닌 테두리가 사용된 응용 프로그램을 만들고자 할 수 있습니다.  
  
 예를 들어 다음 그림과 같은 말 상자 창을 고려해 보겠습니다.  
  
 ![사각형이 아닌 창](../../../../docs/framework/wpf/app-development/media/nonrectangularwindowfigure.PNG "NonRectangularWindowFigure")  
  
 이러한 유형의 창은 <xref:System.Windows.Window.WindowStyle%2A> 속성을 <xref:System.Windows.WindowStyle>으로 설정하고 투명도를 위해 <xref:System.Windows.Window>에서 제공하는 특별한 지원을 사용하여 만들 수 있습니다.  
  
 [!code-xml[WindowsOverviewSnippets#TransparentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#TransparentWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup2)]  
  
 값을 조합하여 사용하면 창이 완전히 투명하게 렌더링됩니다.  이 상태에서는 창의 비클라이언트 영역 표시\(닫기 메뉴, 최소화, 최대화 및 복원 단추 등\)를 사용할 수 없습니다.  따라서 직접 제공해야 합니다.  
  
<a name="Task_Bar_Presence"></a>   
### 작업 표시줄 표시  
 창의 기본 모양에는 다음 그림에서 볼 수 있는 것처럼 작업 표시줄 단추가 포함됩니다.  
  
 ![작업 표시줄 단추가 있는 창](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure7.png "WindowOverviewFigure7")  
  
 메시지 상자나 대화 상자와 같은 일부 유형의 창에는 작업 표시줄 단추가 없습니다\([대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md) 참조\).  <xref:System.Windows.Window.ShowInTaskbar%2A> 속성을 설정하여 창의 작업 표시줄 단추를 표시할지 여부를 제어할 수 있습니다\(기본값은 `true`\).  
  
 [!code-xml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup2)]  
  
<a name="SecurityConsiderations"></a>   
## 보안 고려 사항  
 <xref:System.Windows.Window>를 사용하려면 `UnmanagedCode` 보안 권한을 인스턴스화해야 합니다.  로컬 시스템에 설치되어 실행되는 응용 프로그램의 경우에는 응용 프로그램에 허용된 권한 집합에 속합니다.  
  
 하지만 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]를 사용하여 인터넷 또는 로컬 인트라넷 영역에서 실행되는 응용 프로그램에 부여되는 권한 집합에는 속하지 않습니다.  결과적으로 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 보안 경고가 나타나고 응용 프로그램에 대한 권한 집합을 완전 신뢰로 승격해야 합니다.  
  
 또한 기본적으로 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]에서는 창이나 대화 상자를 표시할 수 없습니다.  독립 실행형 응용 프로그램 보안 고려 사항에 대한 자세한 내용은 [WPF 보안 전략 \- 플랫폼 보안](../../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)을 참조하십시오.  
  
<a name="Other_Types_of_Windows"></a>   
## 기타 유형의 창  
 <xref:System.Windows.Navigation.NavigationWindow>는 탐색 가능한 콘텐츠를 호스팅하도록 디자인된 창입니다.  자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하십시오.  
  
 대화 상자는 기능 수행을 위해 사용자로부터 정보를 수집할 때 많이 사용됩니다.  예를 들어 사용자가 파일을 열려고 할 때에는 사용자로부터 파일 이름을 얻기 위해 응용 프로그램은 일반적으로 **파일 열기** 대화 상자를 엽니다.  자세한 내용은 [대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Window>   
 <xref:System.Windows.MessageBox>   
 <xref:System.Windows.Navigation.NavigationWindow>   
 <xref:System.Windows.Application>   
 [대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)   
 [WPF 응용 프로그램 만들기](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)