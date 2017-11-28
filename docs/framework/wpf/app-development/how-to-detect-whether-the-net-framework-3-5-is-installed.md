---
title: "방법:.NET Framework 3.5 설치 여부 검색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- verifying whether.NET Framework 3.5 is installed [WPF]
- detecting .NET Framework 3.5 installation [WPF]
- detecting whether.NET Framework 3.5 is installed [WPF]
- determining whether.NET Framework 3.5 is installed [WPF]
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b603bbd86bb5eb12782ff8aff7797b73444b8518
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-detect-whether-the-net-framework-35-is-installed"></a><span data-ttu-id="9feef-102">방법:.NET Framework 3.5 설치 여부 검색</span><span class="sxs-lookup"><span data-stu-id="9feef-102">How to: Detect Whether the .NET Framework 3.5 Is Installed</span></span>
<span data-ttu-id="9feef-103">배포 하려면 관리자 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램을 대상으로 하는 시스템에서는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], 했는지 먼저 확인 해야 하는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] 런타임이 있는지 합니다.</span><span class="sxs-lookup"><span data-stu-id="9feef-103">Before administrators can deploy [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] applications on a system that targets the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], they must first confirm that the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] runtime is present.</span></span> <span data-ttu-id="9feef-104">이 항목에서는 작성 된 스크립트 관리자가 결정 하는 데 사용할 수 있는 HTML/javascript 여부는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] 는 시스템에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9feef-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is present on a system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9feef-105">자세한 내용은 설치, 배포 및 검색에 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], 참조 [개발자를 위한.NET Framework 설치](../../../../docs/framework/install/guide-for-developers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9feef-105">For more detailed information on installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9feef-106">예제</span><span class="sxs-lookup"><span data-stu-id="9feef-106">Example</span></span>  
 <span data-ttu-id="9feef-107">경우는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] 가 설치 된 MSI ".NET CLR" 및 버전 번호를 추가 UserAgent 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9feef-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="9feef-108">다음 예제에서는 간단한 HTML 페이지에 포함 된 스크립트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9feef-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="9feef-109">스크립트를 확인할 UserAgent 문자열을 검색 여부는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] 설치 되 고 검색 결과에 상태 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9feef-109">The script searches the UserAgent string to determine whether the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, and displays a status message on the results of the search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9feef-110">이 스크립트는 Internet Explorer에 대해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9feef-110">This script is designed for Internet Explorer.</span></span> <span data-ttu-id="9feef-111">다른 브라우저 UserAgent 문자열에.NET CLR 정보를 포함 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9feef-111">Other browsers may not include .NET CLR information in the UserAgent string.</span></span>  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.5</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.5.0.0";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.5."  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.5." +  
          " The required version is v" + dotNETRuntimeVersion + ".";  
      }  
      result.innerText += "\n\nThis machine's userAgent string is: " +   
        navigator.userAgent + ".";  
    }  
  
    //  
    // Retrieve the version from the user agent string and   
    // compare with the specified version.  
    //  
    function HasRuntimeVersion(versionToCheck)  
    {  
      var userAgentString =   
        navigator.userAgent.match(/.NET CLR [0-9.]+/g);  
  
      if (userAgentString != null)  
      {  
        var i;  
  
        for (i = 0; i < userAgentString.length; ++i)  
        {  
          if (CompareVersions(GetVersion(versionToCheck),   
            GetVersion(userAgentString[i])) <= 0)  
            return true;  
        }  
      }  
  
      return false;  
    }  
  
    //  
    // Extract the numeric part of the version string.  
    //  
    function GetVersion(versionString)  
    {  
      var numericString =   
        versionString.match(/([0-9]+)\.([0-9]+)\.([0-9]+)/i);  
      return numericString.slice(1);  
    }  
  
    //  
    // Compare the 2 version strings by converting them to numeric format.  
    //  
    function CompareVersions(version1, version2)  
    {  
      for (i = 0; i < version1.length; ++i)  
      {  
        var number1 = new Number(version1[i]);  
        var number2 = new Number(version2[i]);  
  
        if (number1 < number2)  
          return -1;  
  
        if (number1 > number2)  
          return 1;  
      }  
  
      return 0;  
    }  
  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY>  
    <div id="result" />  
  </BODY>  
</HTML>  
```  
  
 <span data-ttu-id="9feef-112">".NET CLR" 버전에 대 한 검색 되 면 다음과 같은 유형의 상태 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9feef-112">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 <span data-ttu-id="9feef-113">그렇지 않으면 다음과 같은 유형의 상태 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9feef-113">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have the correct version of the .NET Framework 3.5. The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## <a name="see-also"></a><span data-ttu-id="9feef-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9feef-114">See Also</span></span>  
 [<span data-ttu-id="9feef-115">.NET Framework 3.0 설치 여부 확인</span><span class="sxs-lookup"><span data-stu-id="9feef-115">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)
