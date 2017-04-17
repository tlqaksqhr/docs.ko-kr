---
title: "방법: .NET Framework 3.5 설치 여부 확인 | Microsoft Docs"
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
  - ".NET Framework 3.5 설치 감지[WPF]"
  - ".NET Framework 3.5 설치 여부 확인[WPF]"
  - ".NET Framework 3.5 설치 여부 확인[WPF]"
  - ".NET Framework 3.5 설치 여부 확인[WPF]"
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: .NET Framework 3.5 설치 여부 확인
시스템에 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]를 대상으로 하는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램을 배포하려면 관리자는 먼저 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] 런타임이 있는지 확인해야 합니다.  이 항목에서는 관리자가 시스템에 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]가 있는지 확인하기 위해 사용할 수 있는 HTML\/JavaScript 스크립트를 제공합니다.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 설치, 배포 및 확인에 대한 자세한 내용은 [.NET Framework 설치](../../../../docs/framework/install/guide-for-developers.md)을 참조하십시오.  
  
## 예제  
 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]를 설치할 때 MSI는 ".NET CLR" 및 버전 번호를 UserAgent 문자열에 추가합니다.  다음 예제에서는 간단한 HTML 페이지에 포함된 스크립트를 보여 줍니다.  스크립트는 UserAgent 문자열을 검색하여 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]가 설치되었는지 확인하고 검색 결과에 상태 메시지를 표시합니다.  
  
> [!NOTE]
>  이 스크립트는 Internet Explorer용입니다.  다른 브라우저에서는 UserAgent 문자열에 .NET CLR 정보가 포함되지 않을 수 있습니다.  
  
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
  
 ".NET CLR " 버전 검색에 성공하면 다음과 같은 메시지가 나타납니다.  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 그렇지 않으면 다음과 같은 상태 메시지가 나타납니다.  
  
 `This machine does not have the correct version of the .NET Framework 3.5.  The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## 참고 항목  
 [.NET Framework 3.0 설치 여부 확인](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)