---
title: '방법: Firefox용 WPF 플러그 인 설치 여부 확인'
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: ba411d662a8e5b0c4727e23c8d507e8924b6e9e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>방법: Firefox용 WPF 플러그 인 설치 여부 확인
WPF Windows Presentation Foundation () Firefox에 대 한 플러그 인을 사용 하면 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 및 느슨한 XAML 파일에서 Mozilla Firefox 브라우저에서 실행할 수 있습니다. 이 항목에서는 관리자 WPF Firefox에 대 한 플러그 인이 설치 되어 있는지 확인 하는 데 사용할 수 있는 JavaScript 및 HTML로 작성 된 스크립트를 제공 합니다.  
  
> [!NOTE]
>  설치, 배포 및 검색 하는 방법에 대 한 자세한 내용은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], 참조 [개발자를 위한.NET Framework 설치](../../../../docs/framework/install/guide-for-developers.md)합니다.  
  
## <a name="example"></a>예제  
 경우는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] 가 설치 된 클라이언트 컴퓨터가 사용 하는 WPF 플러그 인 Firefox에 대 한 합니다. 다음 예제 스크립트 Firefox에 대 한 WPF 플러그 인에 대 한 확인 하 고 적절 한 상태 메시지를 표시 합니다.  
  
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
  
 Firefox에 대 한 WPF 플러그 인에 대 한 확인 되 면 다음 상태 메시지가 표시 됩니다.  
  
 `The WPF plug-in for Firefox is installed.`  
  
 그렇지 않으면 다음 상태 메시지가 표시 됩니다.  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework 3.0 설치 여부 확인](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [.NET Framework 3.5 설치 여부 확인](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [WPF XAML 브라우저 응용 프로그램 개요](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
