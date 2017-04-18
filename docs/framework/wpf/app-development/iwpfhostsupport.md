---
title: "IWpfHostSupport | Microsoft Docs"
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
  - "IWpfHostSupport 인터페이스"
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# IWpfHostSupport
PresentationHost.exe를 통해 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 콘텐츠를 호스팅하는 응용 프로그램에서는 이 인터페이스를 구현하여 호스트와 PresentationHost.exe 사이의 통합 지점을 제공합니다.  
  
## 설명  
 웹 브라우저와 같은 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 응용 프로그램은 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 및 느슨한 XAML을 포함하여 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] 콘텐츠를 호스팅할 수 있습니다.  [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 응용 프로그램에서는 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] 콘텐츠를 호스팅하기 위해 [WebBrowser control](http://go.microsoft.com/fwlink/?LinkId=97911)의 인스턴스를 만들고,  [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]에서는 호스팅되기 위해 PresentationHost.exe의 인스턴스를 만듭니다. 이 인스턴스는 [WebBrowser control](http://go.microsoft.com/fwlink/?LinkId=97911)에 표시되도록 호스팅 대상 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] 콘텐츠를 호스트에 제공합니다.  
  
 PresentationHost.exe는 `IWpfHostSupport`가 제공하는 통합 기능을 통해 다음과 같은 작업을 수행할 수 있습니다.  
  
-   호스트 응용 프로그램이 원하는 원시 입력 장치\(휴먼 인터페이스 장치\)를 검색하고 등록합니다.  
  
-   등록된 원시 입력 장치로부터 입력 메시지를 받고 호스트 응용 프로그램에 적절한 메시지를 전달합니다.  
  
-   호스트 응용 프로그램에서 사용자 지정 진행률 및 오류 사용자 인터페이스를 쿼리합니다.  
  
> [!NOTE]
>  이 API는 로컬 클라이언트 컴퓨터에서만 사용되고 지원됩니다.  
  
## Members  
  
|멤버|설명|  
|--------|--------|  
|[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|PresentationHost.exe를 사용하여 호스트 응용 프로그램이 원하는 원시 입력 장치\(휴먼 인터페이스 장치\)를 검색할 수 있습니다.|  
|[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|E\_NOTIMPL이 반환되지 않는 경우 메시지를 받을 때마다 PresentationHost.exe가 호출됩니다.|  
|[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)|기본적으로 PresentationHost.exe는 WPF 콘텐츠를 배포할 때 표시되는 고유한 배포 진행률 및 배포 오류 사용자 인터페이스를 제공합니다.|