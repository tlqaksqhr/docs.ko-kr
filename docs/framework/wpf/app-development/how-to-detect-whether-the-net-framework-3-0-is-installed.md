---
title: "방법: .NET Framework 3.0 설치 여부 확인 | Microsoft Docs"
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
  - "WPF 존재 여부 감지"
  - "WPT의 존재 여부, 검색"
  - "WinFX 런타임 사용자 에이전트 문자열"
ms.assetid: 7f71d652-1749-4379-945a-aa2e3994cb43
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: .NET Framework 3.0 설치 여부 확인
시스템에 [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] 응용 프로그램을 배포하려면 관리자는 먼저 [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] 런타임이 있는지 확인해야 합니다.  이 항목에서는 관리자가 시스템에 [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)]이 있는지 확인하기 위해 사용할 수 있는 HTML\/JavaScript 스크립트를 제공합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]의 설치, 배포 및 확인에 대한 자세한 내용은 [Deploying Microsoft .NET Framework Version 3.0](http://go.microsoft.com/fwlink/?LinkId=96739)을 참조하십시오.  
  
<a name="content_expiration"></a>   
## ".NET CLR" UserAgent 문자열 확인  
 [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)]을 설치할 때 MSI는 ".NET CLR" 및 버전 번호를 UserAgent 문자열에 추가합니다.  다음 예제에서는 간단한 HTML 페이지에 포함된 스크립트를 보여 줍니다.  스크립트는 UserAgent 문자열을 검색하여 [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)]이 설치되었는지 확인하고 검색 결과에 상태 메시지를 표시합니다.  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.0</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.0.04425.00";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.0: "   
          + dotNETRuntimeVersion  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.0."  
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
  
 `This machine has the correct version of the .NET Framework 3.0: 3.0.04425.00`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727; .NET CLR 3.0.04425.00).`  
  
 그렇지 않으면 다음과 같은 상태 메시지가 나타납니다.  
  
 `This machine does not have correct version of the .NET Framework 3.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727).`