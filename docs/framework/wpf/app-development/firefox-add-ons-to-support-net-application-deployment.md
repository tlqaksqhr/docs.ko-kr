---
title: .NET 응용 프로그램 배포를 지원하기 위한 Firefox 추가 기능
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: f05f5afa0c0a7ef858442bd98233865834b8b89b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547445"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>.NET 응용 프로그램 배포를 지원하기 위한 Firefox 추가 기능
WPF Windows Presentation Foundation () Firefox 및 Firefox에 대 한.NET Framework 길잡이 대 한 플러그 인을 사용 하도록 설정 [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)]느슨한, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Mozilla Firefox 브라우저에서 실행 되도록 ClickOnce 응용 프로그램 및입니다.  
  
## <a name="wpf-plug-in-for-firefox"></a>WPF Firefox에 대 한 플러그 인  
 Firefox에 대 한 플러그 인 WPF를 통해 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 및 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 탐색 하 고 최상위 수준에서 또는 Firefox 브라우저에서 HTML IFRAME에 실행 합니다. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 지원 되는 브라우저 응용 프로그램을 웹 서버에 게시할 수 있고 내에서 시작 됩니다. 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 탐색 및 XML 파일과 같은 훨씬 지원 되는 브라우저에 표시 될 수 있는 XAML 전용 파일입니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Firefox와 함께 설치에 대 한 플러그 인은 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]합니다. 7 창에는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], 되지만 포함 되지 않습니다는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Firefox에 대 한 플러그 인 합니다. 설치할 수 없습니다는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Firefox Windows 7에 대 한 플러그 인 합니다.  
  
 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 포함 되지 않습니다는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Firefox에 대 한 플러그 인 합니다. 그러나 두는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] 및 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 는 설치, Firefox에 대 한 플러그 인 WPF와 함께 설치 되는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]합니다. 따라서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] WPF 호스트 올바른 버전의 프레임 워크 로드 되므로 응용 프로그램은 계속 실행 됩니다. 자세한 내용은 참조 [WPF 호스트 (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)합니다.  
  
## <a name="net-framework-assistant-for-firefox"></a>Firefox용 .NET Framework Assistant  
 Firefox에 대 한.NET Framework 도우미 Firefox 브라우저에서 실행 되도록 독립 실행형 ClickOnce 응용 프로그램을 수 있습니다. .NET Framework 도우미 Firefox에 대 한 동일한 방식으로 작동 Firefox 브라우저 전후 설치 되어 있는 경우. Firefox 브라우저를 시작할 때 및 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] 은 설치, Firefox 찾아서 Firefox에 대 한.NET Framework 도우미를 설치 합니다. 사용자는 다음 작업을 수행할 Firefox에 대 한.NET Framework 도우미를 구성할 수 있습니다.  
  
-   ClickOnce 응용 프로그램을 실행 하기 전에 확인 합니다.  
  
-   설치 된 모든 버전의.NET Framework 또는 최신 버전에만 보고 합니다.  
  
 Firefox에 대 한.NET Framework 도우미는에 포함 된 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]합니다. Firefox에 대 한.NET Framework 도구를 제거 하는 방법에 대 한 정보를 참조 하십시오. [Firefox에 대 한.NET Framework 도구를 제거 하는 방법](http://go.microsoft.com/fwlink/?LinkId=177944)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WPF 응용 프로그램 배포](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)  
 [WPF XAML 브라우저 응용 프로그램 개요](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)  
 [Firefox용 WPF 플러그 인 설치 여부 확인](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
