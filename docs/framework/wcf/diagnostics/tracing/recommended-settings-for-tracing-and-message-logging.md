---
title: "추적 및 메시지 로깅에 권장되는 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1894ee59b6120abfe4cb216baba086fcd1650f77
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a><span data-ttu-id="5d0c3-102">추적 및 메시지 로깅에 권장되는 설정</span><span class="sxs-lookup"><span data-stu-id="5d0c3-102">Recommended Settings for Tracing and Message Logging</span></span>
<span data-ttu-id="5d0c3-103">이 항목에서는 다른 운영 환경에 권장되는 추적 및 메시지 로깅 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-103">This topic describes recommended tracing and message logging settings for different operating environments.</span></span>  
  
## <a name="recommended-settings-for-a-production-environment"></a><span data-ttu-id="5d0c3-104">프로덕션 환경에 대한 권장 설정</span><span class="sxs-lookup"><span data-stu-id="5d0c3-104">Recommended Settings for a Production Environment</span></span>  
 <span data-ttu-id="5d0c3-105">WCF 추적 소스를 사용하는 경우 프로덕션 환경에 대해 `switchValue`를 Warning으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-105">For a production environment, if you are using WCF trace sources, set the `switchValue` to Warning.</span></span> <span data-ttu-id="5d0c3-106">WCF `System.ServiceModel` 추적 소스를 사용하는 경우 `switchValue` 특성을 `Warning`, `propagateActivity` 특성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-106">If you are using the WCF `System.ServiceModel` trace source, set the `switchValue` attribute to `Warning` and the `propagateActivity` attribute to `true`.</span></span> <span data-ttu-id="5d0c3-107">사용자 정의 추적 소스를 사용하는 경우 `switchValue` 특성을 `Warning, ActivityTracing`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-107">If you are using a user-defined trace source, set the `switchValue` attribute to `Warning, ActivityTracing`.</span></span> <span data-ttu-id="5d0c3-108">사용 하 여 수동으로 수행할 수 있습니다는 [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-108">This can be done manually using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span> <span data-ttu-id="5d0c3-109">성능 향상을 기대하지 않는 경우 앞에서 설명한 모든 경우에서 `switchValue` 특성을 `Information`으로 설정할 수 있습니다. 이렇게 하면 상당히 많은 추적 데이터가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-109">If you do not anticipate a hit in performance, you can set the `switchValue` attribute to `Information` in all the previously mentioned cases, which generates a fairly large amount of trace data.</span></span> <span data-ttu-id="5d0c3-110">다음 예제에서는 이러한 권장 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-110">The following example demonstrates these recommended settings.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a><span data-ttu-id="5d0c3-111">배포 또는 디버깅에 대한 권장 설정</span><span class="sxs-lookup"><span data-stu-id="5d0c3-111">Recommended Settings for Deployment or Debugging</span></span>  
 <span data-ttu-id="5d0c3-112">배포 또는 디버깅 환경의 경우 `Information` 또는 `Verbose`를 선택하고 사용자 정의 또는 `ActivityTracing` 추적 소스에 대해 `System.ServiceModel`을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-112">For deployment or debugging environment, choose `Information` or `Verbose`, along with `ActivityTracing` for either a user-defined or `System.ServiceModel` trace source.</span></span> <span data-ttu-id="5d0c3-113">디버깅을 향상시키려면 다른 추적 소스(`System.ServiceModel.MessageLogging`)를 구성에 추가하여 메시지 로깅을 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-113">To enhance debugging, you should also add an additional trace source (`System.ServiceModel.MessageLogging`) to the configuration to enable message logging.</span></span> <span data-ttu-id="5d0c3-114">`switchValue` 특성은 이 추적 소스에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-114">Notice that the `switchValue` attribute has no impact on this trace source.</span></span>  
  
 <span data-ttu-id="5d0c3-115">다음 예제에서는 `XmlWriterTraceListener`를 이용하는 공유 수신기를 사용한 권장 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-115">The following example demonstrates the recommended settings, using a shared listener that utilizes the `XmlWriterTraceListener`.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"   
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a><span data-ttu-id="5d0c3-116">WMI를 사용하여 설정 수정</span><span class="sxs-lookup"><span data-stu-id="5d0c3-116">Using WMI to Modify Settings</span></span>  
 <span data-ttu-id="5d0c3-117">앞의 구성 예제와 같이 구성에서 `wmiProviderEnabled` 특성을 활성화하면 WMI를 사용하여 런타임에 구성 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-117">You can use WMI to change configuration settings at runtime (by enabling the `wmiProviderEnabled` attribute in the configuration, as demonstrated in the previously configuration example).</span></span> <span data-ttu-id="5d0c3-118">예를 들어 CIM Studio 내에서 WMI를 사용하여 런타임에 추적 소스 수준을 Warning에서 Information으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-118">For example, you can use WMI within the CIM Studio to change the trace source levels from Warning to Information at runtime.</span></span> <span data-ttu-id="5d0c3-119">이런 방식으로 라이브 디버깅을 사용하면 성능에 큰 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-119">You should be aware that the performance cost of live debugging in this way can be very high.</span></span> <span data-ttu-id="5d0c3-120">WMI를 사용 하는 방법에 대 한 자세한 내용은 참조는 [진단에 대 한 Windows Management Instrumentation를 사용 하 여](../../../../../docs/framework/wcf/diagnostics/wmi/index.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-120">For more information about using WMI, see the [Using Windows Management Instrumentation for Diagnostics](../../../../../docs/framework/wcf/diagnostics/wmi/index.md) topic.</span></span>  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a><span data-ttu-id="5d0c3-121">ASP.NET 추적에서 상호 관련된 이벤트 사용</span><span class="sxs-lookup"><span data-stu-id="5d0c3-121">Enable Correlated Events in ASP.NET Tracing</span></span>  
 <span data-ttu-id="5d0c3-122">ASP.NET 이벤트 추적이 켜져 있지 않은 경우 ASP.NET 이벤트는 상관 관계 ID(ActivityID)를 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-122">ASP.NET events do not set the correlation ID (ActivityID) unless ASP.NET event tracing is turned on.</span></span> <span data-ttu-id="5d0c3-123">상호 관련 된 이벤트를 제대로 참조 하려면 ASP.NET 이벤트 설정 할 명령 콘솔에서 다음 명령을 사용 하 여 추적을 호출할 수 있는으로 이동 하 여 **시작**, **실행** 유형과 **cmd** ,</span><span class="sxs-lookup"><span data-stu-id="5d0c3-123">To see correlated events properly, you have to turn on ASP.NET events tracing using the following command in the command console, which can be invoked by going to **Start**, **Run** and type **cmd**,</span></span>  
  
```  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 <span data-ttu-id="5d0c3-124">ASP.NET 이벤트 추적을 끄려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d0c3-124">To turn off tracing of ASP.NET events, use the following command,</span></span>  
  
```  
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d0c3-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d0c3-125">See Also</span></span>  
 [<span data-ttu-id="5d0c3-126">Windows Management Instrumentation를 사용 하 여 진단에 대 한</span><span class="sxs-lookup"><span data-stu-id="5d0c3-126">Using Windows Management Instrumentation for Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)
