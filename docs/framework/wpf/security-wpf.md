---
title: "보안(WPF) | Microsoft Docs"
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
  - "응용 프로그램 보안[WPF]"
  - "브라우저에서 호스팅되는 응용 프로그램 보안[WPF]"
  - "기능 컨트롤[WPF], 보안"
  - "Internet Explorer 보안 설정[WPF]"
  - "느슨한 XAML 파일[WPF], 샌드박스 동작"
  - "탐색 보안[WPF]"
  - "WebBrowser 컨트롤[WPF], 보안"
  - "WPF 보안"
  - "XAML 파일[WPF], 샌드박스 동작"
  - "XBAP 보안[WPF]"
ms.assetid: ee1baea0-3611-4e36-9ad6-fcd5205376fb
caps.latest.revision: 38
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# 보안(WPF)
<a name="introduction"></a> [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] 독립 실행형 응용 프로그램과 브라우저에서 호스팅되는 응용 프로그램을 개발하는 경우 보안 모델에 대해 고려해야 합니다. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램은 Windows Installer\(.msi\), XCopy, 또는 [!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]를 사용하여 배포되었는지 여부에 상관없이 무제한 권한\([!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] **FullTrust** 권한 집합\)으로 실행됩니다.  ClickOnce를 사용하여 부분적으로 신뢰되는 독립 실행형 WPF 응용 프로그램을 배포하는 것은 지원되지 않습니다.  그러나 완전 신뢰 호스트 응용 프로그램은 .NET Framework 추가 기능 모델을 사용하여 부분 신뢰 <xref:System.AppDomain>을 만들 수 있습니다.  자세한 내용은 [WPF 추가 기능 개요](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)를 참조하십시오.  
  
 브라우저에서 호스팅되는 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] 응응 프로그램은 [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)] 또는 Firefox에서 호스팅되며 [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)] 또는 느슨한 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 문서일 수 있습니다. 자세한 내용은 [WPF XAML 브라우저 응용 프로그램 개요](../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)를 참조하십시오.  
  
 기본적으로 브라우저에서 호스팅되는 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램은 기본 [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] **Internet** 영역 권한 집합으로 제한되는 부분 신뢰 보안 샌드박스 내에서 실행됩니다.  이 경우 일반 웹 응용 프로그램이 격리될 것으로 예상할 때와 동일한 방식으로 브라우저에서 호스팅되는 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램이 실제로 클라이언트 컴퓨터에서 격리됩니다.  XBAP는 배포 URL의 보안 영역 및 클라이언트의 보안 구성에 따라 권한을 전체 신뢰까지 상승시킬 수 있습니다.  자세한 내용은 [WPF 부분 신뢰 보안](../../../docs/framework/wpf/wpf-partial-trust-security.md)을 참조하십시오.  
  
 이 항목에서는 [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] 독립 실행형 응용 프로그램과 브라우저에서 호스팅되는 응용 프로그램의 보안 모델을 설명합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [안전한 탐색](#SafeTopLevelNavigation)  
  
-   [웹 브라우징 소프트웨어 보안 설정](#InternetExplorerSecuritySettings)  
  
-   [WebBrowser 컨트롤 및 기능 컨트롤](#webbrowser_control_and_feature_controls)  
  
-   [부분적으로 신뢰할 수 있는 클라이언트 응용 프로그램에 대해 APTCA 어셈블리 사용 안 함](#APTCA)  
  
-   [느슨한 XAML 파일에 대한 샌드박스 동작](#LooseContentSandboxing)  
  
-   [보안을 향상시키는 WPF 응용 프로그램 개발을 위한 리소스](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>   
## 안전한 탐색  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]의 경우 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]는 두 가지 탐색 유형, 즉 응용 프로그램과 브라우저를 구별합니다.  
  
 *응용 프로그램 탐색*은 브라우저에서 호스팅하는 응용 프로그램 내의 콘텐츠 항목 간을 탐색하는 것입니다.  *브라우저 탐색*은 브라우저 자체의 콘텐츠 및 위치 URL을 변경하는 탐색입니다.  다음 그림에서는 응용 프로그램 탐색\(일반적으로 XAML\) 및 브라우저 탐색\(일반적으로 HTML\) 간의 관계를 보여 줍니다.  
  
 ![탐색 다이어그램](../../../docs/framework/wpf/media/safetoplevelnavigationfigure.png "SafeTopLevelNavigationFigure")  
  
 [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)]에서 탐색하기에 안전하다고 간주되는 콘텐츠 형식은 주로 응용 프로그램 탐색이 사용되는지 아니면 브라우저 탐색이 사용되는지 여부에 의해 결정됩니다.  
  
<a name="Application_Navigation_Security"></a>   
### 응용 프로그램 탐색 보안  
 다음 네 가지 형식의 콘텐츠를 지원하는 팩 [!INCLUDE[TLA2#tla_uri](../../../includes/tla2sharptla-uri-md.md)]로 식별할 수 있는 경우 응용 프로그램 탐색은 안전한 것으로 간주됩니다.  
  
|콘텐츠 형식|설명|URI 예제|  
|------------|--------|------------|  
|리소스|빌드 형식이 **리소스**인 프로젝트에 추가되는 파일입니다.|`pack://application:,,,/MyResourceFile.xaml`|  
|Content|빌드 형식이 **콘텐츠**인 프로젝트에 추가되는 파일입니다.|`pack://application:,,,/MyContentFile.xaml`|  
|원본 사이트|빌드 형식이 **없음**인 프로젝트에 추가되는 파일입니다.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|응용 프로그램 코드|컴파일된 코드 숨김이 있는 XAML 리소스입니다.<br /><br /> 또는<br /><br /> 빌드 형식이 **페이지**인 프로젝트에 추가되는 XAML 파일입니다.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
>  응용 프로그램 데이터 파일 및 팩 [!INCLUDE[TLA2#tla_uri#plural](../../../includes/tla2sharptla-urisharpplural-md.md)]에 대한 자세한 내용은 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)을 참조하십시오.  
  
 이러한 콘텐츠 형식의 파일은 사용자가 직접 탐색하거나 프로그래밍 방식으로 탐색할 수 있습니다.  
  
-   **사용자 탐색**.  사용자가 <xref:System.Windows.Documents.Hyperlink> 요소를 클릭하여 탐색합니다.  
  
-   **프로그래밍 방식 탐색**.  <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=fullName> 속성을 설정하는 등의 방법으로 사용자 개입 없이 응용 프로그램에서 탐색합니다.  
  
<a name="Browser_Navigation_Security"></a>   
### 브라우저 탐색 보안  
 브라우저 탐색은 다음 조건 하에서만 안전한 것으로 간주됩니다.  
  
-   **사용자 탐색**.  중첩된 <xref:System.Windows.Controls.Frame>이 아니라 주 <xref:System.Windows.Navigation.NavigationWindow> 내에 있는 <xref:System.Windows.Documents.Hyperlink> 요소를 클릭하여 사용자가 탐색합니다.  
  
-   **영역**.  탐색하는 콘텐츠가 인터넷 또는 로컬 인트라넷에 있습니다.  
  
-   **프로토콜**.  사용되는 프로토콜은 **http**, **https**, **file** 또는 **mailto**입니다.  
  
 [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)]가 이러한 조건을 충족하지 않는 방식으로 콘텐츠를 탐색하려고 할 경우 <xref:System.Security.SecurityException>이 throw됩니다.  
  
<a name="InternetExplorerSecuritySettings"></a>   
## 웹 브라우징 소프트웨어 보안 설정  
 웹 브라우징 소프트웨어에 부여되는 액세스는 컴퓨터의 보안 설정에 의해 결정됩니다.  웹 브라우징 소프트웨어에는 [WinINet](http://go.microsoft.com/fwlink/?LinkId=179379) 또는 [UrlMon](http://go.microsoft.com/fwlink/?LinkId=179383) API를 사용하는 Internet Explorer 및 PresentationHost.exe 등의 모든 응용 프로그램 또는 구성 요소가 포함됩니다.  
  
 [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)]에서 제공되는 메커니즘을 사용하면 다음을 비롯하여 [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)]에서 실행이 허용되는 기능을 구성할 수 있습니다.  
  
-   [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] 기반 구성 요소  
  
-   ActiveX 문서 및 플러그 인  
  
-   다운로드  
  
-   스크립팅  
  
-   사용자 인증  
  
 이 방법으로 보안 설정할 수 있는 기능 컬렉션은 **인터넷**, **인트라넷**, **신뢰할 수 있는 사이트** 및 **제한된 사이트** 영역에서 영역 단위로 구성됩니다.  다음 단계에서는 보안 설정 구성 방법을 설명합니다.  
  
1.  **제어판**을 엽니다.  
  
2.  **네트워크 및 인터넷**을 클릭한 다음 **인터넷 옵션**을 클릭합니다.  
  
     인터넷 옵션 대화 상자가 나타납니다.  
  
3.  **보안** 탭에서 보안 설정을 구성할 영역을 선택합니다.  
  
4.  **사용자 지정 수준** 단추를 클릭합니다.  
  
     **보안 설정** 대화 상자가 나타납니다. 선택한 영역의 보안 설정을 여기서 구성할 수 있습니다.  
  
     ![보안 설정 대화 상자](../../../docs/framework/wpf/media/wpfsecurityfigure1.PNG "WPFSecurityFigure1")  
  
> [!NOTE]
>  또한 Internet Explorer의 인터넷 옵션 대화 상자에 액세스할 수도 있습니다.  **도구**를 클릭한 다음 **인터넷 옵션**을 클릭합니다.  
  
 [!INCLUDE[TLA#tla_ie7](../../../includes/tlasharptla-ie7-md.md)]부터는 특히 [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)]에 대한 다음 보안 설정이 포함되어 있습니다.  
  
-   **느슨한 XAML**.  [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)]에서 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 파일을 탐색하여 느슨하게 하는지 여부를 제어합니다.  사용, 사용 안 함 및 확인 옵션이 있습니다.  
  
-   **XAML 브라우저 응용 프로그램**.  [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)]에서 [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]를 탐색하여 실행하는지 여부를 제어합니다.  사용, 사용 안 함 및 확인 옵션이 있습니다.  
  
 기본적으로 이러한 설정은 **인터넷**, **로컬 인터넷** 및 **신뢰할 수 있는 사이트** 영역의 경우 사용하도록 설정되고 **제한된 사이트** 영역의 경우 사용하지 않도록 설정됩니다.  
  
<a name="Security_Settings_for_IE6_and_Below"></a>   
### 보안 관련 WPF 레지스트리 설정  
 인터넷 옵션을 통해 사용 가능한 보안 설정 외에 보안상 중요한 여러 가지 WPF 기능을 선택적으로 차단하는 데 사용할 수 있는 다음과 같은 레지스트리 값이 있습니다.  이러한 값은 다음 키 아래에 정의됩니다.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 다음 표에서는 설정할 수 있는 값 목록을 보여 줍니다.  
  
|값 이름|값 형식|값 데이터|  
|----------|----------|-----------|  
|XBAPDisallow|REG\_DWORD|허용하지 않으려면 1이고, 허용하려면 0입니다.|  
|LooseXamlDisallow|REG\_DWORD|허용하지 않으려면 1이고, 허용하려면 0입니다.|  
|WebBrowserDisallow|REG\_DWORD|허용하지 않으려면 1이고, 허용하려면 0입니다.|  
|MediaAudioDisallow|REG\_DWORD|허용하지 않으려면 1이고, 허용하려면 0입니다.|  
|MediaImageDisallow|REG\_DWORD|허용하지 않으려면 1이고, 허용하려면 0입니다.|  
|MediaVideoDisallow|REG\_DWORD|허용하지 않으려면 1이고, 허용하려면 0입니다.|  
|ScriptInteropDisallow|REG\_DWORD|허용하지 않으려면 1이고, 허용하려면 0입니다.|  
  
<a name="webbrowser_control_and_feature_controls"></a>   
## WebBrowser 컨트롤 및 기능 컨트롤  
 WPF <xref:System.Windows.Controls.WebBrowser> 컨트롤은 웹 콘텐츠를 호스팅하는 데 사용할 수 있습니다.  WPF <xref:System.Windows.Controls.WebBrowser> 컨트롤은 기본 WebBrowser ActiveX 컨트롤을 래핑합니다.  에서는 신뢰할 수 있는 웹 콘텐츠를 호스팅하기 위해 WPF <xref:System.Windows.Controls.WebBrowser> 컨트롤을 사용하는 경우에 응용 프로그램을 보안하는 데 필요한 일부 지원을 제공합니다.  그러나 일부 보안 기능은 <xref:System.Windows.Controls.WebBrowser> 컨트롤을 사용하여 응용 프로그램에서 직접 적용되어야 합니다.  WebBrowser ActiveX 컨트롤에 대한 자세한 내용은 [WebBrowser Control Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=179388)를 참조하십시오.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Frame> 컨트롤의 경우 <xref:System.Windows.Controls.WebBrowser>를 사용하여 HTML 콘텐츠를 탐색하므로 이 컨트롤에도 이 단원의 내용이 적용됩니다.  
  
 WPF <xref:System.Windows.Controls.WebBrowser> 컨트롤이 신뢰할 수 없는 웹 콘텐츠를 호스팅하는 데 사용되는 경우 응용 프로그램에서는 부분 신뢰 <xref:System.AppDomain>을 사용하여 응용 프로그램 코드를 악의적인 HTML 스크립트 코드로부터 보호해야 합니다.  특히 응용 프로그램이 <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> 메서드 및 <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A> 속성을 사용하여 호스팅되는 스크립트와 상호 작용할 경우에는 이와 같이 보호해야 합니다.  자세한 내용은 [WPF 추가 기능 개요](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)를 참조하십시오.  
  
 응용 프로그램에서 WPF <xref:System.Windows.Controls.WebBrowser> 컨트롤을 사용하는 경우 보안을 향상시키고 공격을 완화하기 위해 Internet Explorer 기능 컨트롤이 사용되도록 설정할 수도 있습니다.  기능 컨트롤은 관리자 및 개발자가 Internet Explorer 및 WebBrowser ActiveX 컨트롤을 호스팅하는 응용 프로그램의 기능을 구성할 수 있도록 Internet Explorer에 추가됩니다. 이 컨트롤은 WPF <xref:System.Windows.Controls.WebBrowser> 컨트롤에서 래핑합니다.  기능 컨트롤은 [CoInternetSetFeatureEnabled](http://go.microsoft.com/fwlink/?LinkId=179394) 함수를 사용하거나 레지스트리의 값을 변경하여 구성할 수 있습니다.  기능 컨트롤에 대한 자세한 내용은 [Introduction to Feature Controls](http://go.microsoft.com/fwlink/?LinkId=179390) and [Internet Feature Controls](http://go.microsoft.com/fwlink/?LinkId=179392)를 참조하십시오.  
  
 WPF <xref:System.Windows.Controls.WebBrowser> 컨트롤을 사용하는 독립 실행형 WPF 응용 프로그램을 개발할 경우 WPF에서는 응용 프로그램을 위해 다음 기능 컨트롤을 자동으로 활성화합니다.  
  
|기능 컨트롤|  
|------------|  
|FEATURE\_MIME\_HANDLING|  
|FEATURE\_MIME\_SNIFFING|  
|FEATURE\_OBJECT\_CACHING|  
|FEATURE\_SAFE\_BINDTOOBJECT|  
|FEATURE\_WINDOW\_RESTRICTIONS|  
|FEATURE\_ZONE\_ELEVATION|  
|FEATURE\_RESTRICT\_FILEDOWNLOAD|  
|FEATURE\_RESTRICT\_ACTIVEXINSTALL|  
|FEATURE\_ADDON\_MANAGEMENT|  
|FEATURE\_HTTP\_USERNAME\_PASSWORD\_DISABLE|  
|FEATURE\_SECURITYBAND|  
|FEATURE\_UNC\_SAVEDFILECHECK|  
|FEATURE\_VALIDATE\_NAVIGATE\_URL|  
|FEATURE\_DISABLE\_TELNET\_PROTOCOL|  
|FEATURE\_WEBOC\_POPUPMANAGEMENT|  
|FEATURE\_DISABLE\_LEGACY\_COMPRESSION|  
|FEATURE\_SSLUX|  
  
 이러한 기능 컨트롤은 조건 없이 활성화되므로 전체 신뢰 응용 프로그램에 손상을 입힐 수도 있습니다.  이 경우 특정 응용 프로그램 및 해당 응용 프로그램에서 호스팅하는 콘텐츠에 대한 보안상 위험이 없으면 해당하는 기능 컨트롤을 비활성화할 수 있습니다.  
  
 기능 컨트롤은 WebBrowser ActiveX 개체를 인스턴스화하는 프로세스에 의해 적용됩니다.  따라서 신뢰할 수 없는 콘텐츠를 탐색할 수 있는 독립 실행형 응용 프로그램을 만들 경우 추가적인 기능 컨트롤의 활성화에 대해 신중히 고려해야 합니다.  
  
> [!NOTE]
>  이와 관련된 권장 사항은 MSHTML 및 SHDOCVW 호스트 보안에 대한 일반적 권장 사항을 기반으로 합니다.  자세한 내용은 [The MSHTML Host Security FAQ: Part I of II](http://go.microsoft.com/fwlink/?LinkId=179396) 및 [The MSHTML Host Security FAQ: Part II of II](http://go.microsoft.com/fwlink/?LinkId=179415)를 참조하십시오.  
  
 실행 파일의 경우 레지스트리 값을 1로 설정하여 다음 기능 컨트롤을 활성화하는 것이 좋습니다.  
  
|기능 컨트롤|  
|------------|  
|FEATURE\_ACTIVEX\_REPURPOSEDETECTION|  
|FEATURE\_BLOCK\_LMZ\_IMG|  
|FEATURE\_BLOCK\_LMZ\_OBJECT|  
|FEATURE\_BLOCK\_LMZ\_SCRIPT|  
|FEATURE\_RESTRICT\_RES\_TO\_LMZ|  
|FEATURE\_RESTRICT\_ABOUT\_PROTOCOL\_IE7|  
|FEATURE\_SHOW\_APP\_PROTOCOL\_WARN\_DIALOG|  
|FEATURE\_LOCALMACHINE\_LOCKDOWN|  
|FEATURE\_FORCE\_ADDR\_AND\_STATUS|  
|FEATURE\_RESTRICTED\_ZONE\_WHEN\_FILE\_NOT\_FOUND|  
  
 실행 파일의 경우 레지스트리 값을 0으로 설정하여 다음 기능 컨트롤을 비활성화하는 것이 좋습니다.  
  
|기능 컨트롤|  
|------------|  
|FEATURE\_ENABLE\_SCRIPT\_PASTE\_URLACTION\_IF\_PROMPT|  
  
 [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)]에서 WPF <xref:System.Windows.Controls.WebBrowser> 컨트롤을 포함하는 부분 신뢰 [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)]를 실행하는 경우 WPF는 Internet Explorer 프로세스의 주소 공간에 WebBrowser ActiveX 컨트롤을 호스팅합니다.  WebBrowser ActiveX 컨트롤이 [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] 프로세스에서 호스팅되기 때문에 Internet Explorer의 모든 기능 컨트롤이 WebBrowser ActiveX 컨트롤에 대해 활성화됩니다.  
  
 또한 Internet Explorer에서 실행되는 XBAP는 일반적인 독립 실행형 응용 프로그램과 달리 추가적인 보안 수준을 갖게 됩니다.  이 추가적인 보안은 Internet Explorer 및 WebBrowser ActiveX 컨트롤이 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] 및 [!INCLUDE[win7](../../../includes/win7-md.md)]에서 기본적으로 보호 모드로 실행되기 때문에 제공됩니다.  보호 모드에 대한 자세한 내용은 [Understanding and Working in Protected Mode Internet Explorer](http://go.microsoft.com/fwlink/?LinkId=179393)를 참조하십시오.  
  
> [!NOTE]
>  WPF <xref:System.Windows.Controls.WebBrowser> 컨트롤을 포함하는 XBAP를 Firefox에서 실행할 경우 인터넷 영역에 있으면 <xref:System.Security.SecurityException>이 throw됩니다.  이는 WPF 보안 정책에 의한 것입니다.  
  
<a name="APTCA"></a>   
## 부분적으로 신뢰할 수 있는 클라이언트 응용 프로그램에 대해 APTCA 어셈블리 사용 안 함  
 관리되는 어셈블리가 [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)]에 설치되는 경우 사용자는 설치를 위해 명시적 권한을 제공해야 하기 때문에 이러한 어셈블리는 완전히 신뢰할 수 있게 됩니다.  이러한 어셈블리는 완전히 신뢰할 수 있으므로 완전히 신뢰할 수 있는 관리되는 클라이언트 응용 프로그램에서만 사용할 수 있습니다.  부분적으로 신뢰할 수 있는 응용 프로그램에서 이러한 어셈블리를 사용하게 하려면 <xref:System.Security.AllowPartiallyTrustedCallersAttribute>\(APTCA\)로 표시해야 합니다.  부분 신뢰에서 안전하게 실행할 수 있는 것으로 테스트된 어셈블리만 이 특성으로 표시해야 합니다.  
  
 그러나 APTCA 어셈블리는 [!INCLUDE[TLA2#tla_gac](../../../includes/tla2sharptla-gac-md.md)]에 설치된 후 보안 결함을 드러낼 수 있습니다.  보안 결함이 발견되고 나면 어셈블리 게시자는 기존 설치에서 문제를 수정하는 동시에 문제 발견 후 수행되는 설치를 보호하기 위한 보안 업데이트를 생성할 수 있습니다.  업데이트의 한 옵션은 어셈블리를 제거하는 것이지만 이 경우 완전히 신뢰할 수 있는 다른 클라이언트 응용 프로그램이 어셈블리를 사용하지 못하게 될 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]는 APTCA 어셈블리를 제거하지 않고 부분적으로 신뢰할 수 있는 [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]에 대해 APTCA 어셈블리를 사용하지 않도록 설정하는 메커니즘을 제공합니다.  
  
 APTCA 어셈블리를 사용하지 않도록 설정하려면 특수 레지스트리 키를 만들어야 합니다.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 다음은 이러한 예제입니다.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 이 키는 APTCA 어셈블리에 대한 항목을 설정합니다.  또한 해당 어셈블리를 사용하거나 사용하지 않도록 설정하는 값을 이 키에 만들어야 합니다.  이 값에 대한 자세한 설명은 다음에 나와 있습니다.  
  
-   값 이름: **APTCA\_FLAG**  
  
-   값 형식: **REG\_DWORD**  
  
-   값 데이터: **1**\(사용 안 함\), **0**\(사용\)  
  
 부분적으로 신뢰할 수 있는 클라이언트 응용 프로그램에 대해 어셈블리를 사용하지 않도록 설정해야 하는 경우 해당 레지스트리 키와 값을 만드는 업데이트를 작성할 수 있습니다.  
  
> [!NOTE]
>  핵심 [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] 어셈블리는 관리되는 응용 프로그램을 실행하는 데 필요하므로 이 방법으로 사용하지 않게 설정해도 영향을 받지 않습니다.  APTCA 어셈블리를 사용하지 않게 설정하는 기능은 주로 이 아니거나 타사 응용 프로그램인 경우를 대상으로 합니다.  
  
<a name="LooseContentSandboxing"></a>   
## 느슨한 XAML 파일에 대한 샌드박스 동작  
 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 파일은 코드 숨김, 이벤트 처리기 또는 응용 프로그램별 어셈블리에 의존하지 않는 태그 전용 XAML 파일입니다.  브라우저에서 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 파일로 직접 탐색할 경우 기본 인터넷 영역 권한 집합에 기반하여 보안 샌드박스로 로드됩니다.  
  
 그러나 독립 실행형 응용 프로그램의 <xref:System.Windows.Navigation.NavigationWindow> 또는 <xref:System.Windows.Controls.Frame>에서 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 파일로 탐색할 경우 보안 동작이 다릅니다.  
  
 두 경우 모두에 탐색한 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 파일은 호스트 응용 프로그램의 권한을 상속합니다.  그러나 특히 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 파일이 신뢰할 수 없거나 알려지지 않은 엔터티에 의해 생성된 경우 이 동작은 보안 관점에서 바람직하지 않습니다.  이 형식의 콘텐츠는 외부 콘텐츠로 알려져 있으며 탐색한 경우 해당 파일을 격리시키도록 <xref:System.Windows.Controls.Frame> 및 <xref:System.Windows.Navigation.NavigationWindow> 모두를 구성할 수 있습니다.  <xref:System.Windows.Controls.Frame> 및 <xref:System.Windows.Navigation.NavigationWindow>에 대한 다음 예제와 같이 **SandboxExternalContent** 속성을 true로 설정하여 격리를 수행할 수 있습니다.  
  
 [!code-xml[SecurityOverviewSnippets#FrameMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xml[SecurityOverviewSnippets#NavigationWindowMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 이 설정을 사용하면 응용 프로그램을 호스팅하는 중인 프로세스와 별개인 프로세스에 외부 콘텐츠가 로드됩니다.  이 프로세스는 기본 인터넷 영역 권한 집합으로 제한되므로 호스팅 응용 프로그램 및 클라이언트 컴퓨터에서 효율적으로 격리됩니다.  
  
> [!NOTE]
>  독립 실행형 응용 프로그램에서 <xref:System.Windows.Navigation.NavigationWindow> 또는 <xref:System.Windows.Controls.Frame>으로부터 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 파일로 탐색하는 기능은 WPF 브라우저 호스팅 인프라를 기반으로 구현되고 PresentationHost 프로세스와 관련되지만 보안 수준은 [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] 및 [!INCLUDE[win7](../../../includes/win7-md.md)]에서 콘텐츠가 Internet Explorer에 직접 로드되는 경우\(이 경우에도 PresentationHost를 통해 로드됨\)에 비해 약간 낮습니다. 이는 웹 브라우저를 사용하는 독립 실행형 WPF 응용 프로그램에서 Internet Explorer의 추가적인 보호 모드 보안 기능을 제공하지 않기 때문입니다.  
  
<a name="BestPractices"></a>   
## 보안을 향상시키는 WPF 응용 프로그램 개발을 위한 리소스  
 다음은 보안을 향상시키는 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램을 개발하는 데 도움이 되는 추가적인 리소스입니다.  
  
|영역|리소스|  
|--------|---------|  
|관리 코드|[Patterns and Practices Security Guidance for Applications](http://go.microsoft.com/fwlink/?LinkId=117426)|  
|[!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)]|[코드 액세스 보안](../../../docs/framework/misc/code-access-security.md)|  
|[!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]|[ClickOnce 보안 및 배포](../Topic/ClickOnce%20Security%20and%20Deployment.md)|  
|[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]|[WPF 부분 신뢰 보안](../../../docs/framework/wpf/wpf-partial-trust-security.md)|  
  
## 참고 항목  
 [WPF 부분 신뢰 보안](../../../docs/framework/wpf/wpf-partial-trust-security.md)   
 [WPF 보안 전략 \- 플랫폼 보안](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)   
 [WPF 보안 전략 \- 보안 엔지니어링](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)   
 [Patterns and Practices Security Guidance for Applications](http://go.microsoft.com/fwlink/?LinkId=117426)   
 [코드 액세스 보안](../../../docs/framework/misc/code-access-security.md)   
 [ClickOnce 보안 및 배포](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [XAML 개요\(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)