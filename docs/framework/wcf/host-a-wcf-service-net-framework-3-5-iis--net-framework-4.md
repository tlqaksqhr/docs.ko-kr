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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e2c9dbf92ddaf1c23cb09184f046cb536717015
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-host-a-wcf-service-written-with-net-framework-35-in-iis-running-under-net-framework-4"></a><span data-ttu-id="3a0d2-102">방법: .NET Framework 4에서 실행되는 IIS에서 .NET Framework 3.5를 사용하여 작성한 WCF 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="3a0d2-102">How to: Host a WCF Service Written with .NET Framework 3.5 in IIS Running Under .NET Framework 4</span></span>
<span data-ttu-id="3a0d2-103">[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]를 실행하는 컴퓨터에서 [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)]로 작성된 [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] 서비스를 호스팅하면 다음 텍스트와 함께 <xref:System.ServiceModel.ProtocolException>이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-103">When hosting a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service written with [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] on a machine running [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], you may get a <xref:System.ServiceModel.ProtocolException> with the following text.</span></span>  
  
```Output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8). If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly. The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 <span data-ttu-id="3a0d2-104">또는 서비스의 .svc 파일을 찾으려고 하면 다음 텍스트가 포함된 오류 페이지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-104">Or if you try to browse to the service's .svc file you may see an error page with the following text.</span></span>  
  
```Output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 <span data-ttu-id="3a0d2-105">이러한 오류는 IIS가 실행되는 응용 프로그램 도메인에서 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]를 실행하고 있지만 WCF 서비스를 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]에서 실행해야 하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-105">These errors occur because the application domain IIS is running within is running [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] and the WCF service is expecting to run under [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> <span data-ttu-id="3a0d2-106">이 항목에서는 서비스가 실행되도록 하는 데 필요한 수정 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-106">This topic explains the modifications required to get the service to run.</span></span>  
  
 <span data-ttu-id="3a0d2-107">다음 찾기는 <`compilers`> 요소와 값이 4.0 CompilerVersion 공급자 옵션을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-107">Next find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="3a0d2-108">기본적으로는 두 개의 <`compiler`> 아래의 요소는 <`compilers`> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-108">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="3a0d2-109">다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-109">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
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
  
### <a name="add-the-required-targetframework-attribute"></a><span data-ttu-id="3a0d2-110">필수 targetFramework 특성 추가</span><span class="sxs-lookup"><span data-stu-id="3a0d2-110">Add the required targetFramework attribute</span></span>  
  
1.  <span data-ttu-id="3a0d2-111">서비스의 Web.config 파일을 열고를 찾습니다는 <`compilation`> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-111">Open the service's Web.config file and look for the <`compilation`> element.</span></span>  
  
2.  <span data-ttu-id="3a0d2-112">추가 `targetFramework` 특성을 <`compilation`> 요소는 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-112">Add the `targetFramework` attribute to the <`compilation`> element as shown in the following example.</span></span>  
  
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
  
3.  <span data-ttu-id="3a0d2-113">찾을 <`compilers`> 요소와 값이 4.0 CompilerVersion 공급자 옵션을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-113">Find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="3a0d2-114">기본적으로는 두 개의 <`compiler`> 아래의 요소는 <`compilers`> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-114">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="3a0d2-115">다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a0d2-115">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
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
