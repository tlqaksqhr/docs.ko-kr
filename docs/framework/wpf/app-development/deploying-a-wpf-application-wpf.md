---
title: "WPF 응용 프로그램 배포(WPF) | Microsoft Docs"
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
  - "배포[WPF], 응용 프로그램"
  - "WPF 응용 프로그램, 배포"
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# WPF 응용 프로그램 배포(WPF)
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램을 빌드한 후 배포해야 합니다.  [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 및 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]에는 여러 배포 기술이 포함되어 있습니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램을 배포하는 데 사용되는 배포 기술은 응용 프로그램의 종류에 따라 다릅니다.  이 항목에서는 각 배포 기술에 대해 간략하게 살펴보고 각 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 종류의 배포 요구 사항에 이러한 기술을 결합하는 방법에 대해 설명합니다.  
  
   
  
<a name="Deployment_Technologies"></a>   
## 배포 기술  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 및 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]에는 다음과 같은 여러 배포 기술이 포함되어 있습니다.  
  
-   XCopy 배포  
  
-   [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 배포  
  
-   [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] 배포  
  
<a name="XCopy_Deployment"></a>   
### XCopy 배포  
 XCopy 배포는 XCopy 명령줄 프로그램을 사용하여 한 위치에서 다른 위치로 파일을 복사하는 것을 말합니다.  XCopy 배포는 다음과 같은 경우에 적합합니다.  
  
-   응용 프로그램이 독립적인 경우.  클라이언트를 실행하기 위해 업데이트할 필요는 없습니다.  
  
-   응용 프로그램 파일을 한 위치에서 다른 위치로 이동해야 하는 경우\(예: 파일을 빌드 위치\(로컬 디스크, [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] 파일 공유 등\)에서 게시 위치\(웹 사이트, [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] 파일 공유 등\)로 이동해야 하는 경우\)  
  
-   응용 프로그램에 셸 통합이 필요하지 않은 경우\(시작 메뉴 바로 가기, 바탕 화면 아이콘 등\)  
  
 XCopy는 단순한 배포 시나리오에 적합하며 기능이 제한되므로 보다 복잡한 배포 기능이 필요한 경우에는 적합하지 않습니다.  특히, XCopy를 자주 사용할 경우 배포를 강력한 방식으로 관리하기 위해 스크립트를 만들고, 실행하고, 유지 관리하는 데 따르는 오버헤드가 발생합니다.  또한 XCopy는 버전 관리, 제거 또는 롤백을 지원하지 않습니다.  
  
<a name="Windows_Installer"></a>   
### Windows Installer  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]를 사용하면 클라이언트에 배포하고 실행하기가 간편한 독립 실행 파일로 응용 프로그램을 패키징할 수 있습니다.  또한 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]가 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]와 함께 설치되므로 바탕 화면, 시작 메뉴 및 프로그램 제어판과 통합할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]를 사용하면 응용 프로그램의 설치와 제거가 간편하지만 버전 관리 측면에서 볼 때 설치된 응용 프로그램을 최신 상태로 유지하는 기능을 제공하지 않는 단점이 있습니다.  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]에 대한 자세한 내용은 [Windows Installer Deployment](http://msdn.microsoft.com/ko-kr/121be21b-b916-43e2-8f10-8b080516d2a0)를 참조하십시오.  
  
<a name="ClickOnce_Deployment"></a>   
### ClickOnce 배포  
 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]를 사용하면 웹 응용 프로그램이 아닌 응용 프로그램을 웹 스타일로 배포할 수 있습니다. 응용 프로그램은 웹 또는 파일 서버에 게시되어 해당 서버에서 배포됩니다.  [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]는 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]에서 설치된 응용 프로그램이 제공하는 기능을 모두 지원하지는 않으며 다음과 같은 일부 기능 집합을 지원합니다.  
  
-   시작 메뉴 및 프로그램 제어판과의 통합  
  
-   버전 관리, 롤백, 제거  
  
-   응용 프로그램을 항상 배포 위치에서 시작하는 온라인 설치 모드  
  
-   새 버전 릴리스 시 자동 업데이트  
  
-   파일 확장명 등록  
  
 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]에 대한 자세한 내용은 [ClickOnce 보안 및 배포](../Topic/ClickOnce%20Security%20and%20Deployment.md)를 참조하십시오.  
  
<a name="Deploying_WPF_Applications"></a>   
## WPF 응용 프로그램 배포  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에 사용되는 배포 옵션은 응용 프로그램의 종류에 따라 다릅니다.  배포 관점에서 볼 때 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에는 세 가지 중요한 응용 프로그램 유형이 있습니다.  
  
-   독립 실행형 응용 프로그램  
  
-   태그 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
<a name="Deploying_Standalone_Applications"></a>   
### 독립 실행형 응용 프로그램 배포  
 독립 실행형 응용 프로그램은 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] 또는 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]를 사용하여 배포합니다.  어떤 방법을 사용하든 응용 프로그램을 실행하려면 응용 프로그램에 완전 신뢰를 부여해야 합니다.  [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]를 사용하여 배포한 독립 실행형 응용 프로그램에는 자동으로 완전 신뢰가 부여되지만  [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]를 사용하여 배포한 독립 실행형 응용 프로그램에는 자동으로 완전 신뢰가 부여되지 않습니다.  대신 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]는 독립 실행형 응용 프로그램을 설치하기에 앞서 사용자의 동의를 필요로 하는 보안 경고 대화 상자를 표시합니다.  동의하면 독립 실행형 응용 프로그램이 설치되고 완전 신뢰가 부여됩니다.  동의하지 않으면 독립 실행형 응용 프로그램이 설치되지 않습니다.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### 태그 전용 XAML 응용 프로그램 배포  
 태그 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지는 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 페이지와 같이 일반적으로 웹 서버에 게시되고 [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)]를 사용하여 볼 수 있습니다.  태그 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지는 인터넷 영역 권한 집합에 정의된 제한 하에 부분 신뢰 보안 샌드박스 내에서 실행됩니다.  이는 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 기반 웹 응용 프로그램에도 동일한 보안 샌드박스를 제공합니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램의 보안에 대한 자세한 내용은 [보안](../../../../docs/framework/wpf/security-wpf.md)을 참조하십시오.  
  
 태그 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지는 XCopy 또는 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]를 사용하여 로컬 파일 시스템에 설치할 수 있으며  [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] 또는 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 탐색기를 사용하여 볼 수 있습니다.  
  
 XAML에 대한 자세한 내용은 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)를 참조하십시오.  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### XAML 브라우저 응용 프로그램 배포  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]는 다음 세 가지 파일을 배포해야만 실행할 수 있는 컴파일된 응용 프로그램입니다.  
  
-   *ApplicationName*.exe. 실행 가능한 어셈블리 응용 프로그램 파일입니다.  
  
-   *ApplicationName*.xbap. 배포 매니페스트입니다.  
  
-   *ApplicationName*.exe.manifest. 응용 프로그램 매니페스트입니다.  
  
> [!NOTE]
>  배포 및 응용 프로그램 매니페스트에 대한 자세한 내용은 [WPF 응용 프로그램 만들기](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)를 참조하십시오.  
  
 이러한 파일은 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]를 빌드할 때 생성됩니다.  자세한 내용은 [방법: 새 WPF 브라우저 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/ko-kr/72ef4d90-e163-42a1-8df0-ea7ccfd1901f)를 참조하십시오.  태그 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지와 마찬가지로 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]도 일반적으로 웹 서버에 게시되고 [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)]를 사용하여 볼 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]는 배포 방법을 임의로 사용하여  클라이언트에 배포할 수 있습니다.  그러나 다음과 같은 기능을 제공하는 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]를 사용하는 것이 좋습니다.  
  
1.  새 버전이 게시될 때 자동으로 업데이트  
  
2.  완전 신뢰 수준에서 실행되는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]를 위한 권한 상승  
  
 기본적으로 ClickOnce에서는 .deploy 확장명으로 응용 프로그램 파일을 게시합니다.  이로 인해 문제가 발생할 수 있지만 이 기본 설정은 비활성화할 수 있습니다.  자세한 내용은 [ClickOnce 배포 시 서버 및 클라이언트 구성 문제](../Topic/Server%20and%20Client%20Configuration%20Issues%20in%20ClickOnce%20Deployments.md)를 참조하십시오.  
  
 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 배포에 대한 자세한 내용은 [WPF XAML 브라우저 응용 프로그램 개요](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)를 참조하십시오.  
  
<a name="Installing__NET_Framework_3_0"></a>   
## .NET Framework 설치  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램을 실행하려면 클라이언트에 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]가 설치되어 있어야 합니다.  [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]은 브라우저에서 호스팅되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램을 확인할 때 클라이언트에 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]이 설치되어 있는지 자동으로 검색합니다.  [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]가 설치되어 있지 않으면 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]에서 설치 여부를 확인하는 메시지를 표시합니다.  
  
 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]에는 확장명이 .xaml, .xps, .xbap 및 .application인 콘텐츠 파일에 대한 대체\(fallback\) [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] 처리기로 등록된 부트스트래퍼 응용 프로그램이 있어 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]이 설치되었는지 검색할 수 있습니다.  이러한 파일 형식을 탐색하려는데 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]이 클라이언트에 설치되어 있지 않으면 이 부트스트래퍼 응용 프로그램이 .NET Framework 3.0 설치 권한을 요청합니다.  권한을 제공하지 않으면 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]과 응용 프로그램이 모두 설치되지 않습니다.  
  
 권한을 부여하면 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]에서 [!INCLUDE[TLA#tla_bits](../../../../includes/tlasharptla-bits-md.md)]를 사용하여 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]를 다운로드하고 설치합니다.  [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]이 설치되고 나면 원래 요청되었던 파일이 새 브라우저 창에서 열립니다.  
  
 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 자동 검색 기능은 [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] 이상이 설치된 [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)], [!INCLUDE[TLA#tla_winxpsp2](../../../../includes/tlasharptla-winxpsp2-md.md)] 및 [!INCLUDE[TLA#tla_winnetsvrfamsp1](../../../../includes/tlasharptla-winnetsvrfamsp1-md.md)] 클라이언트에서 사용할 수 있습니다.  
  
 자세한 내용은 [.NET Framework 및 응용 프로그램 배포](../../../../docs/framework/deployment/net-framework-and-applications.md)를 참조하십시오.  
  
## 참고 항목  
 [WPF 응용 프로그램 만들기](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [보안](../../../../docs/framework/wpf/security-wpf.md)