---
title: "보안 고려 사항 및 추적에 대한 유용한 정보"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88bc2880-ecb9-47cd-9816-39016a07076f
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 07ac814253a563a0cbdad1014970af3d18c6fdde
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="security-concerns-and-useful-tips-for-tracing"></a><span data-ttu-id="c1136-102">보안 고려 사항 및 추적에 대한 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="c1136-102">Security Concerns and Useful Tips for Tracing</span></span>
<span data-ttu-id="c1136-103">이 항목에서는 WebHost를 사용할 때의 유용한 팁뿐만 아니라 중요한 정보가 노출되지 않도록 보호할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-103">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
## <a name="using-a-custom-trace-listener-with-webhost"></a><span data-ttu-id="c1136-104">WebHost에 사용자 지정 추적 수신기 사용</span><span class="sxs-lookup"><span data-stu-id="c1136-104">Using a Custom Trace Listener with WebHost</span></span>  
 <span data-ttu-id="c1136-105">고유한 추적 수신기를 작성하는 경우 웹 호스팅 서비스에서는 추적이 손실될 가능성이 있다는 것을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-105">If you are writing your own trace listener, you should be aware of the possibility that traces might be lost in the case of a Web-hosted service.</span></span> <span data-ttu-id="c1136-106">WebHost가 재활용되면 복제가 수행되는 동안 활성 프로세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-106">When WebHost recycles, it shuts down the live process while a duplicate takes over.</span></span> <span data-ttu-id="c1136-107">그러나 두 프로세스에는 같은 리소스에 액세스할 권한이 있어야 하며, 이는 수신기 형식에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-107">However, the two processes must still have access to the same resource for some time, which is dependent on the listener type.</span></span> <span data-ttu-id="c1136-108">이 경우 `XmlWriterTraceListener`는 두 번째 프로세스에 대한 새 추적 파일을 만들지만, Windows 이벤트 추적은 동일한 세션 내의 여러 프로세스를 관리하고 동일한 파일에 대한 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-108">In this case, , `XmlWriterTraceListener` creates a new trace file for the second process; while Windows event tracing manages multiple processes within the same session and gives access to the same file.</span></span> <span data-ttu-id="c1136-109">수신기에서 비슷한 기능을 제공하지 않으면 두 프로세스에서 파일을 잠근 경우 추적이 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-109">If your own listener does not provide similar functionalities, traces can be lost when the file is locked up by the two processes.</span></span>  
  
 <span data-ttu-id="c1136-110">사용자 지정 추적 수신기에서 원격 데이터베이스와 같은 연결을 통해 추적 및 메시지를 보낼 수 있는지도 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-110">You should also be aware that a custom trace listener can send traces and messages on the wire, for example, to a remote database.</span></span> <span data-ttu-id="c1136-111">응용 프로그램 개발자는 적절한 액세스 권한으로 사용자 지정 수신기를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-111">As an application deployer, you should configure custom listeners with appropriate access control.</span></span> <span data-ttu-id="c1136-112">원격 위치에서 노출될 수 있는 개인 정보에 보안 컨트롤을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-112">You should also apply security control on any personal information that can be exposed at the remote location.</span></span>  
  
## <a name="logging-sensitive-information"></a><span data-ttu-id="c1136-113">중요한 정보 로깅</span><span class="sxs-lookup"><span data-stu-id="c1136-113">Logging Sensitive Information</span></span>  
 <span data-ttu-id="c1136-114">메시지가 범위 내에 있으면 추적에 메시지 헤더가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-114">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="c1136-115">추적을 사용하도록 설정하면 쿼리 문자열 등의 응용 프로그램별 헤더와 신용 카드 번호 등의 본문 정보에 있는 개인 정보가 로그에서 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-115">When tracing is enabled, personal information in application-specific headers, such as, a query string; and body information, such as, a credit card number, can become visible in the logs.</span></span> <span data-ttu-id="c1136-116">응용 프로그램 배포자는 구성 및 추적 파일에 액세스 제어를 적용하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-116">The application deployer is responsible for enforcing access control on the configuration and trace files.</span></span> <span data-ttu-id="c1136-117">이런 종류의 정보가 표시되지 않도록 하려면 추적을 사용하지 않도록 설정하거나 추적 로그를 공유하려는 데이터의 일부를 필터링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-117">If you do not want this kind of information to be visible, you should disable tracing, or filter out part of the data if you want to share the trace logs.</span></span>  
  
 <span data-ttu-id="c1136-118">다음 팁은 추적 파일의 내용이 실수로 노출되지 않도록 보호하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-118">The following tips can help you to prevent the content of a trace file from being exposed unintentionally:</span></span>  
  
-   <span data-ttu-id="c1136-119">로그 파일이 WebHost 및 자체 호스트 시나리오 둘 다에서 ACL(액세스 제어 목록)을 통해 보호되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-119">Ensure that the log files are protected by Access Control Lists (ACL) both in WebHost and self-host scenarios.</span></span>  
  
-   <span data-ttu-id="c1136-120">웹 요청을 사용하여 쉽게 제공될 수 없는 파일 확장명을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-120">Choose a file extension that cannot be easily served using a Web request.</span></span> <span data-ttu-id="c1136-121">예를 들어 .xml 파일 확장명을 사용하는 것은 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-121">For example, the .xml file extension is not a safe choice.</span></span> <span data-ttu-id="c1136-122">제공될 수 있는 확장명 목록을 보기 위해 IIS 관리 설명서를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-122">You can check the IIS administration guide to see a list of extensions that can be served.</span></span>  
  
-   <span data-ttu-id="c1136-123">로그 파일 위치의 절대 경로를 지정합니다. 절대 경로는 웹 브라우저를 사용하여 외부 사용자가 해당 파일에 액세스하지 못하도록 WebHost vroot 공용 디렉터리의 외부에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-123">Specify an absolute path for the log file location, which should be outside of the WebHost vroot public directory to prevent it from being accessed by an external party using a Web browser.</span></span>  
  
 <span data-ttu-id="c1136-124">기본적으로 사용자 이름 및 암호와 같은 PII(개인적으로 식별할 수 있는 정보)와 키는 추적 및 기록된 메시지에 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-124">By default, keys and personally identifiable information (PII) such as username and password are not logged in traces and logged messages.</span></span> <span data-ttu-id="c1136-125">그러나 컴퓨터 관리자는 다음과 같이 Machine.config 파일의 `enableLoggingKnownPII` 요소에 있는 `machineSettings` 특성을 사용하여 컴퓨터에서 실행되는 응용 프로그램이 알려진 PII(개인적으로 식별할 수 있는 정보)를 기록하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-125">A machine administrator, however, can use the `enableLoggingKnownPII` attribute in the `machineSettings` element of the Machine.config file to permit applications running on the machine to log known personally identifiable information (PII) as follows:</span></span>  
  
```xml  
<configuration>  
   <system.ServiceModel>  
      <machineSettings enableLoggingKnownPii="Boolean"/>  
   </system.ServiceModel>  
</configuration>   
```  
  
 <span data-ttu-id="c1136-126">그런 다음 응용 프로그램 배포자는 App.config 또는 Web.config 파일 중 하나에 있는 `logKnownPii` 특성을 사용하여 다음과 같이 PII 로깅을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-126">An application deployer can then use the `logKnownPii` attribute in either the App.config or Web.config file to enable PII logging as follows:</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="true">  
        <listeners>  
                 <add name="messages"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="c1136-127">두 개의 설정 모두 `true`인 경우에만 PII 로깅을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-127">Only when both settings are `true` is PII logging enabled.</span></span> <span data-ttu-id="c1136-128">두 스위치를 조합하면 각 응용 프로그램에 대해 알려진 PII를 유연하게 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-128">The combination of two switches allows the flexibility to log known PII for each application.</span></span>  
  
 <span data-ttu-id="c1136-129">하나의 구성 파일에서 두 개 이상의 사용자 지정 소스를 지정할 경우 첫 번째 소스의 특성만 읽는다는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-129">You should be aware that if you specify two or more custom sources in a configuration file, only the attributes of the first source are read.</span></span> <span data-ttu-id="c1136-130">다른 소스는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-130">The others are ignored.</span></span> <span data-ttu-id="c1136-131">이는 다음 App.config 파일의 경우, 두 번째 소스에 PII 로깅을 사용하도록 명시적으로 설정되어 있더라도 두 개의 소스 모두에 대해 PII가 기록되지는 않는다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-131">This means that, for the following App.config, file, PII is not logged for both sources even though PII logging is explicitly enabled for the second source.</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="false">  
        <listeners>  
           <add name="messages"  
                type="System.Diagnostics.XmlWriterTraceListener"  
                initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
      <source name="System.ServiceModel"   
         logKnownPii="true">  
         <listeners>  
            <add name="xml" />  
         </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="c1136-132">`<machineSettings enableLoggingKnownPii="Boolean"/>` 요소가 Machine.config 파일의 외부에 존재할 경우 시스템은 <xref:System.Configuration.ConfigurationErrorsException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-132">If the `<machineSettings enableLoggingKnownPii="Boolean"/>` element exists outside the Machine.config file, the system throws a <xref:System.Configuration.ConfigurationErrorsException>.</span></span>  
  
 <span data-ttu-id="c1136-133">변경 내용은 응용 프로그램이 시작되거나 다시 시작되어야만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-133">The changes are effective only when the application starts or restarts.</span></span> <span data-ttu-id="c1136-134">두 개의 특성이 모두 `true`로 설정된 경우에 시작 시 이벤트가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-134">An event is logged at startup when both attributes are set to `true`.</span></span> <span data-ttu-id="c1136-135">`logKnownPii`가 `true`로 설정되어 있지만 `enableLoggingKnownPii`는 `false`인 경우에도 이벤트가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-135">An event is also logged if `logKnownPii` is set to `true` but `enableLoggingKnownPii` is `false`.</span></span>  
  
 <span data-ttu-id="c1136-136">PII 로깅에 대 한 자세한 내용은 참조 하십시오. [PII 보안 잠금](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="c1136-136">For more information on PII logging, see [PII Security Lockdown](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md) sample.</span></span>  
  
 <span data-ttu-id="c1136-137">컴퓨터 관리자와 응용 프로그램 배포자는 이러한 두 개의 스위치를 사용할 때 특별히 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-137">The machine administrator and application deployer should exercise extreme caution when using these two switches.</span></span> <span data-ttu-id="c1136-138">PII 로깅을 사용하도록 설정하면 보안 키와 PII가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-138">If PII logging is enabled, security keys and PII are logged.</span></span> <span data-ttu-id="c1136-139">PII 로깅을 사용하지 않도록 설정해도 중요한 데이터와 응용 프로그램별 데이터는 메시지 헤더 및 본문에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-139">If it is disabled, sensitive and application-specific data is still logged in message headers and bodies.</span></span> <span data-ttu-id="c1136-140">개인 정보 및 PII 노출 되지 않도록 보호 하기에 보다 철저 한 논의 알려면 [사용자 개인 정보 보호](http://go.microsoft.com/fwlink/?LinkID=94647)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-140">For a more thorough discussion on privacy and protecting PII from being exposed, see [User Privacy](http://go.microsoft.com/fwlink/?LinkID=94647).</span></span>  
  
 <span data-ttu-id="c1136-141">또한, 연결 지향 전송에 대한 연결마다 한 번, 그리고 그렇지 않게 전송된 메시지마다 한 번 메시지 발신자의 IP 주소가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-141">In addition, the IP address of the message sender is logged once per connection for connection-oriented transports, and once per message sent otherwise.</span></span> <span data-ttu-id="c1136-142">이 작업은 발신자의 동의 없이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-142">This is done without the consent of the sender.</span></span> <span data-ttu-id="c1136-143">그러나 이 로깅은 Information 또는 Verbose 추적 수준에서만 발생하며 이러한 수준은 라이브 디버깅을 제외하고 프로덕션에서 기본 추적 수준 또는 권장 추적 수준이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c1136-143">However, this logging only occurs at the Information or Verbose tracing levels, which are not the default or recommended tracing levels in production, except for live debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1136-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1136-144">See Also</span></span>  
 [<span data-ttu-id="c1136-145">추적</span><span class="sxs-lookup"><span data-stu-id="c1136-145">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
