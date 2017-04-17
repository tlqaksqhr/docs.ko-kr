---
title: ".NET 응용 프로그램 배포를 지원하기 위한 Firefox 추가 기능 | Microsoft Docs"
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
  - ".NET 응용 프로그램 배포, Firefox 추가 기능 배포"
  - "Firefox용 .NET Framework Assistant"
  - ".NET 응용 프로그램 배포를 위한 Firefox 추가 기능"
  - "Firefox용 WPF 플러그 인"
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# .NET 응용 프로그램 배포를 지원하기 위한 Firefox 추가 기능
Firefox용 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 플러그 인과 Firefox용 .NET Framework Assistant를 사용하면 [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 ClickOnce 응용 프로그램이 Mozilla Firefox 브라우저에서 작동하도록 할 수 있습니다.  
  
## Firefox용 WPF 플러그 인  
 Firefox용 WPF 플러그 인을 사용하면 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 및 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 Firefox 브라우저의 HTML IFRAME이나 최상위 수준에서 탐색하고 실행할 수 있습니다.  [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]는 웹 서버에 게시하고 지원되는 브라우저 내에서 시작할 수 있는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램입니다.  느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]은 XML 파일과 마찬가지로 지원되는 브라우저에서 탐색 및 표시할 수 있는 XAML 전용 파일입니다.  
  
 Firefox용 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 플러그 인은 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]와 함께 설치됩니다.  Window 7에는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]가 포함되어 있지만 Firefox용 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 플러그 인은 포함되어 있지 않습니다. Windows 7.에는 Firefox용 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 플러그 인을 설치할 수 없습니다.  
  
 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]에는 Firefox용 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 플러그 인이 포함되어 있지 않습니다. 그러나 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]와 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]를 모두 설치하면 Firefox용 WPF 플러그 인이 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]와 함께 설치됩니다.  따라서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 응용 프로그램도 실행됩니다. WPF 호스트에서는 올바른 버전의 프레임워크를 로드하기 때문입니다.  자세한 내용은 [WPF 호스트\(PresentationHost.exe\)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)를 참조하십시오.  
  
## Firefox용 .NET Framework Assistant  
 Firefox용 .NET Framework Assistant를 사용하면 독립 실행형 ClickOnce 응용 프로그램을 Firefox 브라우저에서 실행할 수 있습니다.  Firefox용 .NET Framework Assistant는 Firefox 브라우저보다 먼저 설치되었든 나중에 설치되었든 관계없이 동일하게 작동합니다.  Firefox 브라우저를 시작할 때 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]이 설치되어 있으면 Firefox에서는 Firefox용 .NET Framework Assistant를 찾아 설치합니다.  사용자는 Firefox용 .NET Framework Assistant에서 다음을 수행하도록 구성할 수 있습니다.  
  
-   ClickOnce 응용 프로그램을 실행하기 전에 메시지 표시  
  
-   설치된 모든 .NET Framework 버전 보고 또는 최신 버전만 보고  
  
 Firefox용 .NET Framework Assistant는 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]에 포함되어 있습니다.  Firefox용 .NET Framework Assistant를 제거하는 방법에 대한 자세한 내용은 [Firefox용 .NET Framework Assistant를 제거하는 방법](http://go.microsoft.com/fwlink/?LinkId=177944)을 참조하십시오.  
  
## 참고 항목  
 [WPF 응용 프로그램 배포](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)   
 [WPF XAML 브라우저 응용 프로그램 개요](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)   
 [Firefox용 WPF 플러그 인 설치 여부 확인](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)