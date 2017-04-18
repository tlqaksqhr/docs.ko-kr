---
title: "WPF XAML 브라우저 응용 프로그램 개요 | Microsoft Docs"
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
  - "브라우저에서 호스팅되는 응용 프로그램[WPF]"
  - "WPF XAML 브라우저 응용 프로그램(XBAP)"
  - "XBAP(XAML 브라우저 응용 프로그램)"
  - "XBAP, XAML 브라우저 응용 프로그램"
ms.assetid: 3a7a86a8-75d5-4898-96b9-73da151e5e16
caps.latest.revision: 47
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 47
---
# WPF XAML 브라우저 응용 프로그램 개요
<a name="introduction"></a> [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]에는 웹 응용 프로그램과 리치 클라이언트 응용 프로그램의 장점이 결합되어 있습니다.  웹 응용 프로그램과 마찬가지로 XBAP를 웹 서버에 배포하고 Internet Explorer 또는 Firefox에서 시작할 수 있습니다.  리치 클라이언트 응용 프로그램과 마찬가지로 XBAP에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 기능을 이용할 수 있습니다.  XBAP 개발은 리치 클라이언트 개발과 유사합니다.  이 항목에서는 개론적인 수준에서 간단히 XBAP 개발에 대해 소개하고 XBAP 개발과 표준 리치 클라이언트 개발의 다른 점에 대해 설명합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [새 XBAP\(XAML 브라우저 응용 프로그램\) 만들기](#creating_a_new_xaml_browser_application_xbap)  
  
-   [XBAP 배포](#deploying_a_xbap)  
  
-   [호스트 웹 페이지와 통신](#communicating_with_the_host_web_page)  
  
-   [XBAP 보안 고려 사항](#xbap_security_considerations)  
  
-   [XBAP 시작 시간 성능 고려 사항](#xbap_start_time_performance_considerations)  
  
<a name="creating_a_new_xaml_browser_application_xbap"></a>   
## 새 XBAP\(XAML 브라우저 응용 프로그램\) 만들기  
 새 XBAP 프로젝트를 만드는 가장 간단한 방법은 [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)]을 사용하는 것입니다.  새 프로젝트를 만들 경우 템플릿 목록에서 **WPF 브라우저 응용 프로그램**을 선택합니다.  자세한 내용은 [방법: 새 WPF 브라우저 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/ko-kr/72ef4d90-e163-42a1-8df0-ea7ccfd1901f)를 참조하십시오.  
  
 XBAP 프로젝트를 실행하면 독립 실행형 창이 아니라 브라우저 창에서 열립니다.  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]에서 XBAP를 디버깅하면 응용 프로그램이 인터넷 영역 권한으로 실행되므로 권한이 부족하면 보안 예외가 throw됩니다.  자세한 내용은 [보안](../../../../docs/framework/wpf/security-wpf.md) 및 [WPF 부분 신뢰 보안](../../../../docs/framework/wpf/wpf-partial-trust-security.md)을 참조하십시오.  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]를 사용하여 개발하지 않거나 프로젝트 파일에 대한 자세한 내용을 보려면 [WPF 응용 프로그램 만들기](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)를 참조하십시오.  
  
<a name="deploying_a_xbap"></a>   
## XBAP 배포  
 XBAP를 빌드하면 출력에 다음 세 파일이 포함됩니다.  
  
|파일|설명|  
|--------|--------|  
|실행 파일\(.exe\)|컴파일된 코드가 들어 있으며 확장명이 .exe입니다.|  
|응용 프로그램 매니페스트\(.manifest\)|이 파일에는 응용 프로그램과 관련된 메타데이터가 들어 있으며 확장명이 .manifest입니다.|  
|배포 매니페스트\(.xbap\)|이 파일에는 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]가 응용 프로그램을 배포하기 위해 사용하는 정보가 들어 있으며 확장명이 .xbap입니다.|  
  
 XBAP를 웹 서버\(예: [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 이후 버전\)에 배포합니다.  웹 서버에 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]을 설치할 필요는 없지만 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] 형식 및 파일 확장명을 등록해야 합니다.  자세한 내용은 [IIS 5.0 및 IIS 6.0을 구성하여 WPF 응용 프로그램 배포](../../../../docs/framework/wpf/app-development/how-to-configure-iis-5-0-and-iis-6-0-to-deploy-wpf-applications.md)을 참조하십시오.  
  
 XBAP 배포를 준비하려면 .exe 파일과 관련 매니페스트를 웹 서버로 복사합니다.  확장명이 .xbap인 배포 매니페스트를 여는 하이퍼링크가 포함된 HTML 페이지를 만듭니다.  사용자가 .xbap 파일에 대한 링크를 클릭하면 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]에서 자동으로 응용 프로그램을 다운로드하고 시작하는 과정을 처리합니다.  다음 예제 코드에서는 XBAP를 가리키는 하이퍼링크가 포함된 HTML 페이지를 보여 줍니다.  
  
```  
<html>   
  <head></head>  
  <body>   
    <a href="XbapEx.xbap">Click this link to launch the application</a>  
  </body>   
</html>  
  
```  
  
 웹 페이지의 프레임에서 XBAP를 호스팅할 수도 있습니다.  하나 이상의 프레임이 있는 웹 페이지를 만듭니다.  프레임의 소스 속성을 배포 매니페스트 파일로 설정합니다.  기본 제공 메커니즘을 사용하여 호스팅 웹 페이지와 XBAP 간에 통신하려면 프레임에서 응용 프로그램을 호스팅해야 합니다.  다음 예제 코드에서는 두 개의 프레임이 있고 두 번째 프레임의 소스가 XBAP로 설정된 HTML 페이지를 보여 줍니다.  
  
```  
<html>   
  <head>A page with frames.</head>  
    <frameset cols="50%,50%">   
      <frame src="introduction.htm" >   
      <frame src="XbapEx.xbap" >   
  </frameset>   
</html>  
```  
  
### 캐시된 XBAP 지우기  
 XBAP를 다시 빌드하고 시작하면 이전 버전의 XBAP가 열리는 경우가 있습니다.  예를 들어 XBAP 어셈블리 버전 번호가 정적이고 명령줄에서 XBAP를 시작하면 이 동작이 발생할 수 있습니다.  이 경우에는 캐시된 버전\(이전에 시작한 버전\)과 새 버전의 버전 번호가 동일하기 때문에 새 버전의 XBAP가 다운로드되지 않습니다.  대신 캐시된 버전이 로드됩니다.  
  
 이러한 상황에서는 명령 프롬프트에서 **Mage** 명령\(Visual Studio 또는 [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)]와 함께 설치됨\)을 사용하여 캐시된 버전을 제거할 수 있습니다.  다음 명령은 응용 프로그램 캐시를 지웁니다.  
  
 `Mage.exe -cc`  
  
 이 명령을 실행하면 최신 버전의 XBAP가 시작됩니다.  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]에서 응용 프로그램을 디버깅하는 경우 최신 버전의 XBAP가 시작됩니다. 일반적으로 각 빌드에서 배포 버전 번호를 업데이트해야 합니다.  Mage에 대한 자세한 내용은 [Mage.exe\(매니페스트 생성 및 편집 도구\)](../../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)를 참조하십시오.  
  
<a name="communicating_with_the_host_web_page"></a>   
## 호스트 웹 페이지와 통신  
 응용 프로그램이 HTML 프레임에 호스팅되는 경우 XBAP를 포함하는 웹 페이지와 통신할 수 있습니다.  <xref:System.Windows.Interop.BrowserInteropHelper>의 <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> 속성을 검색하여 이 작업을 수행합니다.  이 속성은 HTML 창을 나타내는 스크립트 개체를 반환합니다.  그런 다음 일반 점 구문을 사용하여 [창 개체](http://go.microsoft.com/fwlink/?LinkId=160274)에서 속성, 메서드 및 이벤트에 액세스할 수 있습니다.  또한 스크립트 메서드 및 전역 변수에 액세스할 수 있습니다.  다음 예제에서는 스크립트 개체를 검색하고 브라우저를 닫는 방법을 보여 줍니다.  
  
 [!code-csharp[XbapBrowserInterop#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/xbapbrowserinterop/cs/page1.xaml.cs#10)]
 [!code-vb[XbapBrowserInterop#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/xbapbrowserinterop/vb/page1.xaml.vb#10)]  
  
### HostScript를 사용하는 XBAP 디버깅  
 XBAP에서 <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> 개체를 사용하여 HTML 창과 통신하는 경우 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]에서 응용 프로그램을 실행하고 디버깅하려면 두 가지 설정을 지정해야 합니다.  응용 프로그램이 원본 사이트에 대한 액세스 권한이 있고 XBAP를 포함하는 HTML 페이지에서 응용 프로그램을 시작해야 합니다.  다음 단계에서는 이 두 가지 설정을 확인하는 방법을 설명합니다.  
  
1.  Visual Studio에서 프로젝트 속성을 엽니다.  
  
2.  **보안** 탭에서 **고급**을 클릭합니다.  
  
     고급 보안 설정 대화 상자가 나타납니다.  
  
3.  **원본 사이트에 응용 프로그램 액세스 허용** 확인란이 선택되어 있는지 확인하고 **확인**을 클릭합니다.  
  
4.  **디버그** 탭에서 **다음 URL로 브라우저 시작** 옵션을 선택하고 XBAP가 들어 있는 HTML 페이지에 대한 URL을 지정합니다.  
  
5.  Internet Explorer에서 **도구** 단추를 클릭하고 **인터넷 옵션**을 선택합니다.  
  
     인터넷 옵션 대화 상자가 나타납니다.  
  
6.  **고급** 탭을 클릭합니다.  
  
7.  **보안** 아래의 **설정** 목록에서 **\[내 컴퓨터\]에 있는 파일에서 액티브 콘텐츠가 실행되는 것을 허용** 확인란을 선택합니다.  
  
8.  **확인**을 클릭합니다.  
  
     Internet Explorer를 다시 시작하면 변경 내용이 적용됩니다.  
  
> [!CAUTION]
>  Internet Explorer에서 액티브 콘텐츠를 사용하도록 설정하면 컴퓨터가 위험에 노출될 수 있습니다.  자세한 내용은 [Security and privacy features in Internet Explorer](http://go.microsoft.com/fwlink/?LinkId=179286)을 참조하십시오.  Internet Explorer 보안 설정을 변경하지 않으려면 서버에서 HTML 페이지를 시작하고 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 디버거를 프로세스에 연결하십시오.  
  
<a name="xbap_security_considerations"></a>   
## XBAP 보안 고려 사항  
 XBAP는 일반적으로 인터넷 영역 권한 집합으로 제한되는 부분 신뢰 보안 샌드박스 내에서 실행됩니다.  따라서 인터넷 영역에서 지원되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소의 하위 집합을 지원하도록 구현하거나 응용 프로그램의 권한을 높여야 합니다.  자세한 내용은 [보안](../../../../docs/framework/wpf/security-wpf.md)을 참조하십시오.  
  
 응용 프로그램에서 <xref:System.Windows.Controls.WebBrowser> 컨트롤을 사용하는 경우 WPF는 네이티브 WebBrowser ActiveX 컨트롤을 내부적으로 인스턴스화합니다.  응용 프로그램이 Internet Explorer에서 실행 중인 부분 신뢰 XBAP이면 ActiveX 컨트롤은 Internet Explorer 프로세스의 전용 스레드에서 실행됩니다.  따라서 다음과 같은 제한 사항이 적용됩니다.  
  
-   <xref:System.Windows.Controls.WebBrowser> 컨트롤은 보안 제한 사항을 포함하여 호스트 브라우저와 비슷한 동작을 제공해야 합니다.  Internet Explorer 보안 설정을 통해 일부 보안 제한 사항을 제어할 수 있습니다.  자세한 내용은 [보안](../../../../docs/framework/wpf/security-wpf.md)을 참조하십시오.  
  
-   XBAP가 HTML 페이지에서 도메인 경계를 넘어서 로드되면 예외가 throw됩니다.  
  
-   입력이 WPF <xref:System.Windows.Controls.WebBrowser>와 별도의 스레드에 있으므로 키보드 입력을 가로챌 수 없고 IME 상태가 공유되지 않습니다.  
  
-   다른 스레드에서 실행 중인 ActiveX 컨트롤로 인해 탐색 타이밍 또는 순서가 달라질 수 있습니다.  예를 들어 다른 탐색 요청을 시작해도 페이지 탐색이 취소되지 않습니다.  
  
-   WPF 응용 프로그램이 별도의 스레드에서 실행되고 있기 때문에 사용자 지정 ActiveX 컨트롤에서 통신 문제가 발생할 수 있습니다.  
  
-   <xref:System.Windows.Interop.HwndHost>에서 다른 스레드 또는 프로세스에서 실행 중인 창을 하위 분류할 수 없으므로 <xref:System.Windows.Interop.HwndHost.MessageHook>가 발생되지 않습니다.  
  
### 완전 신뢰 XBAP 만들기  
 XBAP에서 완전 신뢰가 필요한 경우 이 권한을 사용하도록 프로젝트를 변경할 수 있습니다.  다음 단계에서는 완전 신뢰를 사용하도록 설정하는 방법을 설명합니다.  
  
1.  Visual Studio에서 프로젝트 속성을 엽니다.  
  
2.  **보안** 탭에서 **완전 신뢰 응용 프로그램** 옵션을 선택합니다.  
  
 이 설정은 다음과 같이 변경됩니다.  
  
-   프로젝트 파일에서 `<TargetZone>` 요소 값이 `Custom`으로 변경됩니다.  
  
-   응용 프로그램 매니페스트\(app.manifest\)에서 `Unrestricted="true"` 특성이 `PermissionSet` 요소에 추가됩니다.  
  
    ```  
    <PermissionSet class="System.Security.PermissionSet"   
        version="1"   
        ID="Custom"   
        SameSite="site"   
        Unrestricted="true"   
    />  
    ```  
  
### 완전 신뢰 XBAP 배포  
 ClickOnce 배포 모델을 따르지 않는 완전 신뢰 XBAP를 배포하는 경우 사용자가 응용 프로그램을 실행할 때의 동작은 보안 영역에 따라 다릅니다.  설치하려고 시도할 때 경고가 발생하는 경우도 있습니다.  사용자는 설치를 계속하거나 취소하도록 선택할 수 있습니다.  다음 표에서는 각 보안 영역에 대한 응용 프로그램 동작과 응용 프로그램에서 완전 신뢰를 받기 위해 수행해야 하는 작업에 대해 설명합니다.  
  
|보안 영역|동작|완전 신뢰 얻기|  
|-----------|--------|--------------|  
|로컬 컴퓨터|자동 완전 신뢰|아무런 작업도 수행할 필요가 없습니다.|  
|인트라넷 및 신뢰할 수 있는 사이트|완전 신뢰 확인|사용자가 프롬프트에서 소스를 볼 수 있도록 인증서로 XBAP에 서명합니다.|  
|Internet|"신뢰할 수 없음"이라는 메시지가 표시되고 실패함|인증서로 XBAP에 서명합니다.|  
  
> [!NOTE]
>  위의 표에서 설명한 동작은 ClickOnce 배포 모델을 따르지 않는 완전 신뢰 XBAP에 대한 동작입니다.  
  
 완전 신뢰 XBAP를 배포하려면 ClickOnce 배포 모델을 사용하는 것이 좋습니다.  이 모델을 사용하면 보안 영역에 상관없이 XBAP에 완전 신뢰가 자동으로 부여되므로 확인 메시지가 표시되지 않습니다.  이 모델의 일부로 신뢰할 수 있는 게시자의 인증서로 응용 프로그램에 서명해야 합니다.  자세한 내용은 [신뢰할 수 있는 응용 프로그램 배포 개요](../Topic/Trusted%20Application%20Deployment%20Overview.md) 및 [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=166327](http://go.microsoft.com/fwlink/?LinkId=166327)를 참조하십시오.  
  
<a name="xbap_start_time_performance_considerations"></a>   
## XBAP 시작 시간 성능 고려 사항  
 시작 시간은 XBAP 성능에 있어 중요한 부분입니다.  로드되는 첫 번째 WPF 응용 프로그램이 XBAP이면 *콜드 시작* 시간이 10초 이상 걸릴 수 있습니다.  그 이유는 WPF에서 진행률 페이지가 렌더링되고 응용 프로그램을 표시하기 위해 CLR과 WPF 모두 콜드 시작되어야 하기 때문입니다.  
  
 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]부터는 배포 초기 단계에 비관리 진행률 페이지를 표시하므로 XBAP 콜드 시작 시간이 단축됩니다. 비관리 진행률 페이지는 네이티브 호스팅 코드를 통해 표시되어 HTML에 렌더링되기 때문에 응용 프로그램의 시작과 거의 동시에 표시됩니다.  
  
 또한 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 다운로드 시퀀스의 동시성이 향상되어 시작 시간이 10%까지 향상되었습니다.  [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]가 매니페스트를 다운로드하고 유효성을 검사하면 응용 프로그램 다운로드가 시작되고 진행률 표시줄 업데이트가 시작됩니다.  
  
## 참고 항목  
 [Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 응용 프로그램 디버깅](../../../../docs/framework/wpf/app-development/configure-vs-to-debug-a-xaml-browser-to-call-a-web-service.md)   
 [WPF 응용 프로그램 배포](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)