---
title: '방법: Firefox용 WPF 플러그 인 설치 여부 확인'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2b58abda33aa48372e4642dca48599867f389045
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="fc91c-102">방법: Firefox용 WPF 플러그 인 설치 여부 확인</span><span class="sxs-lookup"><span data-stu-id="fc91c-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>
<span data-ttu-id="fc91c-103">WPF Windows Presentation Foundation () Firefox에 대 한 플러그 인을 사용 하면 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 및 느슨한 XAML 파일에서 Mozilla Firefox 브라우저에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc91c-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="fc91c-104">이 항목에서는 관리자 WPF Firefox에 대 한 플러그 인이 설치 되어 있는지 확인 하는 데 사용할 수 있는 JavaScript 및 HTML로 작성 된 스크립트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc91c-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc91c-105">설치, 배포 및 검색 하는 방법에 대 한 자세한 내용은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], 참조 [개발자를 위한.NET Framework 설치](../../../../docs/framework/install/guide-for-developers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc91c-105">For more information about installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc91c-106">예제</span><span class="sxs-lookup"><span data-stu-id="fc91c-106">Example</span></span>  
 <span data-ttu-id="fc91c-107">경우는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] 가 설치 된 클라이언트 컴퓨터가 사용 하는 WPF 플러그 인 Firefox에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc91c-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="fc91c-108">다음 예제 스크립트 Firefox에 대 한 WPF 플러그 인에 대 한 확인 하 고 적절 한 상태 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc91c-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>  
  
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
  
 <span data-ttu-id="fc91c-109">Firefox에 대 한 WPF 플러그 인에 대 한 확인 되 면 다음 상태 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc91c-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is installed.`  
  
 <span data-ttu-id="fc91c-110">그렇지 않으면 다음 상태 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc91c-110">Otherwise, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a><span data-ttu-id="fc91c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc91c-111">See Also</span></span>  
 [<span data-ttu-id="fc91c-112">.NET Framework 3.0 설치 여부 확인</span><span class="sxs-lookup"><span data-stu-id="fc91c-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [<span data-ttu-id="fc91c-113">.NET Framework 3.5 설치 여부 확인</span><span class="sxs-lookup"><span data-stu-id="fc91c-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [<span data-ttu-id="fc91c-114">WPF XAML 브라우저 응용 프로그램 개요</span><span class="sxs-lookup"><span data-stu-id="fc91c-114">WPF XAML Browser Applications Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
