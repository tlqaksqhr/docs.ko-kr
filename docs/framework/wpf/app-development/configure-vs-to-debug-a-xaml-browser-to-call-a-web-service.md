---
title: "방법: Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 응용 프로그램 디버깅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5db89cf6220f086d2d71b99f3e6440e584d6a5d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>방법: Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 응용 프로그램 디버깅
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]사용 권한 인터넷 영역 집합으로 제한 되는 부분 신뢰 보안 샌드박스에서 실행 합니다. 이 권한 집합에는 웹 서비스 호출에 나와 있는 웹 서비스로을 제한 된 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 응용 프로그램의 원본 사이트입니다. 경우는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 에서 디버깅 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]경우 동일한 원본 사이트의 웹 서비스 참조 하도록 간주 되지 않습니다. 이 원인 보안 예외가 발생할 때에 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 웹 서비스를 호출 하려고 합니다. 그러나 한 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 디버깅 하는 동안 호출 웹 서비스와 동일한 원본 사이트를 시뮬레이션할 하도록 프로젝트를 구성할 수 있습니다. 이 통해는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 를 안전 하 게 보안 예외가 발생 하지 않고 웹 서비스를 호출 합니다.  
  
## <a name="configuring-visual-studio"></a>Visual Studio 구성  
 구성 하려면 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] 디버깅 하는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 웹 서비스를 호출 하는:  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  에 **프로젝트 디자이너**, 클릭는 **디버그** 탭 합니다.  
  
3.  에 **시작 작업** 섹션에서 **시작 외부 프로그램** 여 다음을 입력 합니다.  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  에 **시작 옵션** 섹션에서 다음을 입력 하는 **명령줄 인수** 텍스트 상자:  
  
     `-debug`  *파일 이름*  
  
     *filename* 에 대 한 값의 **-디버그** 매개 변수는.xbap 파일 이름 예:  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  이 기본 구성이 사용 하 여 만든 솔루션에 대 한는 [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 서식 파일 프로젝트.  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  에 **프로젝트 디자이너**, 클릭는 **디버그** 탭 합니다.  
  
3.  에 **시작 옵션** 섹션을 추가 하려면 다음 명령줄 매개 변수는 **명령줄 인수** 텍스트 상자:  
  
     `-debugSecurityZoneURL`  *URL*  
  
     *URL* 에 대 한 값은 **-debugSecurityZoneURL** 매개 변수는는 [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] 시뮬레이션할 응용 프로그램의 원본 사이트를 원하는 위치에 대 한 합니다.  
  
 예를 들어 고려는 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] 다음 웹 서비스를 사용 하는 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 원본 사이트의 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 이 웹 서비스는:  
  
 `http://services.msdn.microsoft.com`  
  
 따라서 전체 **-debugSecurityZoneURL** 명령줄 매개 변수 및 값은:  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## <a name="see-also"></a>참고 항목  
 [WPF 호스트(PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
