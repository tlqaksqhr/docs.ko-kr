---
title: "방법: .NET Framework 4에서 실행되는 IIS에서 .NET Framework 3.5를 사용하여 작성한 WCF 서비스 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 88d9b6b8b4aa1d551e292057e0fecf746b17cecd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-host-a-wcf-service-written-with-net-framework-35-in-iis-running-under-net-framework-4"></a>방법: .NET Framework 4에서 실행되는 IIS에서 .NET Framework 3.5를 사용하여 작성한 WCF 서비스 호스팅
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]를 실행하는 컴퓨터에서 [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)]로 작성된 [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] 서비스를 호스팅하면 다음 텍스트와 함께 <xref:System.ServiceModel.ProtocolException>이 발생할 수 있습니다.  
  
```Output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8). If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly. The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 또는 서비스의 .svc 파일을 찾으려고 하면 다음 텍스트가 포함된 오류 페이지가 표시될 수 있습니다.  
  
```Output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 이러한 오류는 IIS가 실행되는 응용 프로그램 도메인에서 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]를 실행하고 있지만 WCF 서비스를 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]에서 실행해야 하는 경우 발생합니다. 이 항목에서는 서비스가 실행되도록 하는 데 필요한 수정 작업에 대해 설명합니다.  
  
 다음 찾기는 <`compilers`> 요소와 값이 4.0 CompilerVersion 공급자 옵션을 변경 합니다. 기본적으로는 두 개의 <`compiler`> 아래의 요소는 <`compilers`> 요소입니다. 다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.  
  
```xml  
<system.codedom>  
      <compilers>  
        <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                  type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
        <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                  type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="OptionInfer" value="true"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
      </compilers>  
    </system.codedom>  
```  
  
### <a name="add-the-required-targetframework-attribute"></a>필수 targetFramework 특성 추가  
  
1.  서비스의 Web.config 파일을 열고를 찾습니다는 <`compilation`> 요소입니다.  
  
2.  추가 `targetFramework` 특성을 <`compilation`> 요소는 다음 예제와 같이 합니다.  
  
    ```xml  
    <compilation debug="false"  
            targetFramework="4.0">  
  
            <assemblies>  
              <add assembly="System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Xml.Linq, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35"/>  
              <add assembly="System.Data.DataSetExtensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
            </assemblies>  
  
          </compilation>  
    ```  
  
3.  찾을 <`compilers`> 요소와 값이 4.0 CompilerVersion 공급자 옵션을 변경 합니다. 기본적으로는 두 개의 <`compiler`> 아래의 요소는 <`compilers`> 요소입니다. 다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.  
  
    ```xml  
    <system.codedom>  
          <compilers>  
            <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                      type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
            <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                      type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="OptionInfer" value="true"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
          </compilers>  
        </system.codedom>  
    ```
