---
title: "방법: .NET Framework 4에서 실행되는 IIS에서 .NET Framework 3.5를 사용하여 작성한 WCF 서비스 호스팅 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 방법: .NET Framework 4에서 실행되는 IIS에서 .NET Framework 3.5를 사용하여 작성한 WCF 서비스 호스팅
[!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]를 실행하는 컴퓨터에서 [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)]로 작성된 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스를 호스팅하면 다음 텍스트와 함께 <xref:System.ServiceModel.ProtocolException>이 발생할 수 있습니다.  
  
```Output  
처리되지 않은 예외: System.ServiceModel.ProtocolException: 응답 메시지의 콘텐츠 형식 text/html; charset=utf-8이(가) 바인딩의 콘텐츠 형식(application/soap+xml; charset=utf-8)과 일치하지 않습니다.사용자 지정 인코더를 사용 중인 경우 IsContentTypeSupported 메서드가 올바르게 구현되는지 확인하십시오.응답의 처음 1024바이트가 <html>    <head>        <title>입니다.' 응용 프로그램 도메인이나 응용 프로그램 풀이 현재 .NET Framework 버전 4 이상을 실행하고 있습니다.이 웹 응용 프로그램에 대한 IIS 설정이 4.0 이상으로 설정되었거나 ASP.NET Web Development Server 버전 4.0 이상을 사용하고 있는 경우 이 예외가 발생할 수 있습니다.이 웹 응용 프로그램의 Web.config 파일에 있는 <compilation> 요소에는 이 버전의 .NET Framework에 대한 필수 'targetFrameworkMoniker' 특성이 포함되어 있지 않습니다(예: '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">').이 특성을 사용하여 Web.config 파일을 업데이트하거나 다른 버전의 .NET Framework를 사용하도록 웹 응용 프로그램을 구성하십시오.</title>...  
```  
  
 또는 서비스의 .svc 파일을 찾으려고 하면 다음 텍스트가 포함된 오류 페이지가 표시될 수 있습니다.  
  
```Output  
현재 응용 프로그램 도메인 또는 응용 프로그램 풀에서 .NET Framework 버전 4.0 이상을 실행하고 있습니다.이 웹 응용 프로그램에 대한 IIS 설정이 4.0 이상으로 설정되었거나 ASP.NET Web Development Server 버전 4.0 이상을 사용하고 있는 경우 이 예외가 발생할 수 있습니다.이 웹 응용 프로그램의 Web.config 파일에 있는 <compilation> 요소에는 이 버전의 .NET Framework에 대한 required'targetFrameworkMoniker' 특성이 포함되어 있지 않습니다(예: '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">').이 특성을 사용하여 Web.config 파일을 업데이트하거나 다른 버전의 .NET Framework를 사용하도록 웹 응용 프로그램을 구성하십시오.  
```  
  
 이러한 오류는 IIS가 실행되는 응용 프로그램 도메인에서 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]를 실행하고 있지만 WCF 서비스를 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]에서 실행해야 하는 경우 발생합니다.이 항목에서는 서비스가 실행되도록 하는 데 필요한 수정 작업에 대해 설명합니다.  
  
 다음으로 \<`compilers`\> 요소를 찾고 CompilerVersion 공급자 옵션의 값을 4.0으로 변경합니다.기본적으로 \<`compilers`\> 요소 아래에는 두 개의 \<`compiler`\> 요소가 있습니다.다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.  
  
```  
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
  
### 필수 targetFramework 특성 추가  
  
1.  서비스의 Web.config 파일을 열고 \<`compilation`\> 요소를 찾습니다.  
  
2.  다음과 예제와 같이 \<`compilation`\> 요소에 `targetFramework` 특성을 추가합니다.  
  
    ```  
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
  
3.  \<`compilers`\> 요소를 찾고 CompilerVersion 공급자 옵션의 값을 4.0으로 변경합니다.기본적으로 \<`compilers`\> 요소 아래에는 두 개의 \<`compiler`\> 요소가 있습니다.다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.  
  
    ```  
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