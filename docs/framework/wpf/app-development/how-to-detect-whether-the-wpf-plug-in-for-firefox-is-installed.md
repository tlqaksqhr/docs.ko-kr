---
title: "방법: Firefox용 WPF 플러그 인 설치 여부 확인 | Microsoft Docs"
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
  - "Firefox 플러그 인 검사[WPF]"
  - "Firefox 설치 검색[WPF]"
  - "Firefox용 WPF 플러그 인 설치 여부 확인[WPF]"
  - "FireFox[WPF], 설치 검색"
  - "Firefox 플러그 인[WPF]"
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: Firefox용 WPF 플러그 인 설치 여부 확인
Firefox용 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 플러그 인을 사용하면 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 및 느슨한 XAML 파일이 Mozilla Firefox 브라우저에서 실행되도록 할 수 있습니다.  이 항목에서는 관리자가 Firefox용 WPF 플러그 인이 설치되어 있는지 확인하기 위해 사용할 수 있는 HTML 및 JavaScript 스크립트를 제공합니다.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 설치, 배포 및 검색에 대한 자세한 내용은 [.NET Framework 설치](../../../../docs/framework/install/guide-for-developers.md)을 참조하십시오.  
  
## 예제  
 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]가 설치되면 클라이언트 컴퓨터가 Firefox용 WPF 플러그 인을 사용하도록 구성됩니다.  다음 예제 스크립트에서는 Firefox용 WPF 플러그 인이 있는지 확인한 후 해당하는 상태 메시지를 표시합니다.  
  
```  
<HTML>  
  
  <HEAD>  
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT type="text/javascript">  
    <!--  
    function OnLoad()  
    {  
  
       // Check for the WPF plug-in for Firefox and report  
       var msg = "The WPF plug-in for Firefox is ";  
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];  
       if( wpfPlugin != null ) {  
          document.writeln(msg + " installed.");  
       }  
       else {  
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");  
       }  
    }  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY onload="OnLoad()" />  
  
</HTML>  
```  
  
 Firefox용 WPF 플러그 인이 확인되면 다음 상태 메시지가 표시됩니다.  
  
 `The WPF plug-in for Firefox is installed.`  
  
 그렇지 않으면 다음과 같은 상태 메시지가 나타납니다.  
  
 `The WPF plug-in for Firefox is not installed.  Please install or reinstall the .NET Framework 3.5.`  
  
## 참고 항목  
 [.NET Framework 3.0 설치 여부 확인](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)   
 [.NET Framework 3.5 설치 여부 확인](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)   
 [WPF XAML 브라우저 응용 프로그램 개요](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)