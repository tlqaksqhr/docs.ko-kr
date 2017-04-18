---
title: "방법: Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 응용 프로그램 디버깅 | Microsoft Docs"
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
  - "Visual Studio를 구성하여 XAML 브라우저 응용 프로그램 디버깅[WPF]"
  - "Visual Studio를 구성하여 XBAP 디버깅[WPF]"
  - "XBAP에 대한 보안 예외 디버깅[WPF]"
  - "웹 서비스를 호출하는 XBAP 디버깅[WPF]"
  - "XBAP에 대한 보안 예외[WPF], 디버깅"
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 응용 프로그램 디버깅
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]는 인터넷 영역 권한 집합으로 제한되는 부분 신뢰 보안 샌드박스에서 실행됩니다.  이 권한 집합은 웹 서비스 호출을 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 응용 프로그램의 원래 위치에 있는 웹 서비스로만 제한합니다.  하지만 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]에서 디버깅하는 경우 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]는 자신이 참조하는 웹 서비스와 동일한 원래 위치에 있는 것으로 간주되지 않습니다.  이 때문에 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]가 웹 서비스를 호출하려고 하면 보안 예외가 발생합니다.  하지만 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 프로젝트의 경우 디버깅하는 동안 프로젝트 위치가 프로젝트가 호출하는 웹 서비스의 원래 위치와 동일하게 되도록 구성할 수 있습니다.  이렇게 하면 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]가 보안 예외를 발생시키지 않고 안전하게 웹 서비스를 호출할 수 있습니다.  
  
## Visual Studio 구성  
 웹 서비스를 호출하는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]를 디버깅하도록 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]를 구성하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **프로젝트 디자이너**에서 **디버그** 탭을 클릭합니다.  
  
3.  **시작 작업** 섹션에서 **시작 외부 프로그램**을 선택하고 다음을 입력합니다.  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  **시작 옵션** 섹션에서 **명령줄 인수** 텍스트 상자에 다음을 입력합니다.  
  
     `-debug`  *filename*  
  
     **\-debug** 매개 변수에 대한 *filename* 값은 .xbap 파일 이름입니다. 예를 들면 다음과 같습니다.  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  이는 [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 프로젝트 템플릿을 사용하여 만든 솔루션에 대한 기본 구성입니다.  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **프로젝트 디자이너**에서 **디버그** 탭을 클릭합니다.  
  
3.  **시작 옵션** 섹션에서 **명령줄 인수** 텍스트 상자에 다음 명령줄 매개 변수를 추가합니다.  
  
     `-debugSecurityZoneURL`  *URL*  
  
     **\-debugSecurityZoneURL** 매개 변수의 *URL* 값은 응용 프로그램의 원래 위치로 시뮬레이션할 위치에 대한 [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)]입니다.  
  
 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]의 웹 서비스를 사용하는 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]를 예로 들 수 있습니다.  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 이 웹 서비스의 원래 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 위치는 다음과 같습니다.  
  
 `http://services.msdn.microsoft.com`  
  
 따라서 전체 **\-debugSecurityZoneURL** 명령줄 매개 변수와 값은 다음과 같습니다.  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## 참고 항목  
 [WPF 호스트\(PresentationHost.exe\)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)