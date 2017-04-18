---
title: "WPF 호스트(PresentationHost.exe) | Microsoft Docs"
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
  - "PresentationHost.exe"
  - "WPF 호스트 응용 프로그램"
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# WPF 호스트(PresentationHost.exe)
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 호스트\(PresentationHost.exe\)는 [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] 이상을 비롯한 호환 브라우저에서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]응용 프로그램을 호스팅할 수 있도록 하는 응용 프로그램입니다.  기본적으로 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 호스트는 브라우저에서 호스팅되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 콘텐츠의 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 처리기 및 셸로 등록됩니다. 이러한 콘텐츠에는 다음이 포함됩니다.  
  
-   느슨하게 압축되지 않은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일\(.xaml\)  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]\(.xbap\)  
  
 이러한 형식의 파일에 대해 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 호스트는 다음을 수행합니다.  
  
-   [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 콘텐츠를 호스팅하기 위해 등록된 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 처리기를 시작합니다.  
  
-   필수 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 및 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 어셈블리의 올바른 버전을 로드합니다.  
  
-   배포 영역에 대해 적절한 권한 수준이 설정되어 있는지 확인합니다.  
  
 이 항목에서는 PresentationHost.exe에서 사용할 수 있는 명령줄 매개 변수를 설명합니다.  
  
## 용도  
 `PresentationHost.exe [parameters] uri|filename`  
  
## 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|filename|활성화할 파일의 경로입니다.  [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]가 될 수도 있습니다.|  
|\-debug|응용 프로그램을 활성화할 때 저장소에서 커밋하거나 실행하지 않습니다.  이는 로컬 파일이 활성화된 경우에만 작동합니다.|  
|\-debugSecurityZoneURL \<url\>|지정된 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]에서 배포된 것처럼 응용 프로그램이 디버깅되어야 함을 PresentationHost.exe에 알리기 위해 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 값과 함께 사용됩니다.  이를 통해 배포 영역과 원본 사이트가 모두 결정됩니다.|  
|\-embedding|OLE에 필요합니다.  `-event` 또는 `-debug` 매개 변수가 지정된 경우 `-embedding` 매개 변수가 내부적으로 설정되기 때문에 해당 매개 변수를 지정할 필요가 없습니다.|  
|\-event \<eventname\>|이 이름으로 이벤트를 연 다음 PresentationHost.exe가 초기화되고 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 콘텐츠를 호스팅할 준비가 되면 이 이벤트에 신호를 보냅니다.  이벤트가 아직 만들어지지 않은 등의 이유로 인해 이벤트를 여는 데 오류가 발생하면 PresentationHost.exe가 종료됩니다.|  
|\-launchApplication \<url\>|지정된 URL에서 독립 실행형 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 응용 프로그램을 실행합니다.  .NET 응용 프로그램과 관련된 [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] 및 WinINet 보안 정책이 적용됩니다.|  
  
## 시나리오  
  
### 셸 처리기  
 `PresentationHost.exe example.xbap`  
  
### MIME 처리기  
 `PresentationHost.exe -embedding example.xbap`  
  
### Visual Studio 디버깅  
 `PresentationHost.exe -debug example.xbap`  
  
### 영역에서 Visual Studio 디버깅  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## 참고 항목  
 [보안](../../../../docs/framework/wpf/security-wpf.md)