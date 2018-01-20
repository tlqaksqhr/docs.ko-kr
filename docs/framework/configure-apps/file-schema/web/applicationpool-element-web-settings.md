---
title: "&lt;applicationPool&gt; 요소 (웹 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d75e9eedf42523301b3c1745c05d90bcdafbdbf5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ltapplicationpoolgt-element-web-settings"></a><span data-ttu-id="7c4fc-102">&lt;applicationPool&gt; 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="7c4fc-102">&lt;applicationPool&gt; Element (Web Settings)</span></span>
<span data-ttu-id="7c4fc-103">ASP.NET 응용 프로그램 통합된 모드에서 실행 중인 경우 프로세스 전체 동작을 관리 하려면 ASP.NET에서 사용 되는 구성 설정을 지정 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 이후 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7c4fc-104">ASP.NET 응용 프로그램에서 호스팅되는 경우 유일한 작업 지원이 요소 및 기능 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 이후 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-104">This element and the feature it supports only work if your ASP.NET application is hosted on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="7c4fc-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7c4fc-105">\<configuration></span></span>  
<span data-ttu-id="7c4fc-106">\<system.web > 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="7c4fc-106">\<system.web> Element (Web Settings)</span></span>  
<span data-ttu-id="7c4fc-107">\<applicationPool > 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="7c4fc-107">\<applicationPool> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c4fc-108">구문</span><span class="sxs-lookup"><span data-stu-id="7c4fc-108">Syntax</span></span>  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c4fc-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7c4fc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7c4fc-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c4fc-111">특성</span><span class="sxs-lookup"><span data-stu-id="7c4fc-111">Attributes</span></span>  
  
|<span data-ttu-id="7c4fc-112">특성</span><span class="sxs-lookup"><span data-stu-id="7c4fc-112">Attribute</span></span>|<span data-ttu-id="7c4fc-113">설명</span><span class="sxs-lookup"><span data-stu-id="7c4fc-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="7c4fc-114">ASP.NET을 사용 하면 CPU 당 동시 요청 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="7c4fc-115">각 CPU에 대 한 응용 프로그램 풀에 대 한 동시 스레드를 실행할 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="7c4fc-116">이 CPU 당는 요청을 처리 하는 데 사용할 수 있는 관리 되는 스레드 수를 제한할 수 있기 때문에 ASP.NET 동시성 제어 하는 대체 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="7c4fc-117">기본적으로이 설정은 0 이며 ASP.NET CLR 스레드 풀도 만들 수 있는 스레드 수를 제한 하지만 CPU 당 만들 수 있는 스레드 수가 제한 되지 않습니다입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="7c4fc-118">단일 프로세스에서 ASP.NET에 대해 대기할 수 있는 요청의 최대 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="7c4fc-119">둘 이상의 ASP.NET 응용 프로그램을 단일 응용 프로그램 풀에서 실행 누적 집합 응용 프로그램 풀에서 응용 프로그램에 전송 되는 요청을이 설정을 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c4fc-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7c4fc-120">Child Elements</span></span>  
 <span data-ttu-id="7c4fc-121">없음</span><span class="sxs-lookup"><span data-stu-id="7c4fc-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c4fc-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7c4fc-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7c4fc-123">요소</span><span class="sxs-lookup"><span data-stu-id="7c4fc-123">Element</span></span>|<span data-ttu-id="7c4fc-124">설명</span><span class="sxs-lookup"><span data-stu-id="7c4fc-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c4fc-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="7c4fc-125">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="7c4fc-126">ASP.NET 응용 프로그램을 호스트와 상호 작용 하는 방법에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c4fc-127">설명</span><span class="sxs-lookup"><span data-stu-id="7c4fc-127">Remarks</span></span>  
 <span data-ttu-id="7c4fc-128">실행 하는 경우 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 통합된 모드에서 최신 버전을이 요소 조합을 사용 하 여 응용 프로그램은 IIS 응용 프로그램 풀에서 호스팅되는 경우 ASP.NET 스레드 및 큐 요청을 관리 하는 방법을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-128">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="7c4fc-129">IIS 6을 실행 하거나 실행 하면 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 클래식 모드에서 또는 ISAPI 모드에서 이러한 설정이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-129">If you run IIS 6 or you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
 <span data-ttu-id="7c4fc-130">`applicationPool` 설정은 특정 버전의.NET Framework에서 실행 되는 모든 응용 프로그램 풀에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="7c4fc-131">Aspnet.config 파일에는 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="7c4fc-132">버전 2.0 및.NET framework 4.0이 파일 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="7c4fc-133">(버전 3.0 및 3.5는.NET Framework의 공유할 aspnet.config 파일 버전 2.0.)</span><span class="sxs-lookup"><span data-stu-id="7c4fc-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7c4fc-134">실행 하는 경우 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 에 [!INCLUDE[win7](../../../../../includes/win7-md.md)], 모든 응용 프로그램 풀에 대 한 별도 aspnet.config 파일을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-134">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] on [!INCLUDE[win7](../../../../../includes/win7-md.md)], you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="7c4fc-135">이렇게 하면 각 응용 프로그램 풀에 대 한 스레드의 성능을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
 <span data-ttu-id="7c4fc-136">에 대 한는 `maxConcurrentRequestsPerCPU` , "5000"의 기본 설정에서 설정 된 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 하는 경우가 아니면 CPU 당 5000 개 이상의 요청이 ASP.NET에서 제어 효과적으로 000입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="7c4fc-137">기본 설정은 자동으로 동시성을 관리할 수는 CPU 당 CLR 스레드 풀에 따라 대신 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="7c4fc-138">비동기 요청 처리를 많이 사용 하는 하거나 네트워크 I/O에서 차단 된 많은 장기 실행 요청 응용 프로그램에서 향상 된 기본 제한에서 이익을 얻을 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="7c4fc-139">설정 `maxConcurrentRequestsPerCPU` 을 ASP.NET 요청을 처리 하기 위해 0으로 관리 되는 스레드 사용을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="7c4fc-140">응용 프로그램 IIS 응용 프로그램 풀에서 실행 되 면 요청 IIS I/O 스레드에서 대기 하며 IIS 스레드 설정 하 여 동시성 스로틀 되는지는 따라서 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
 <span data-ttu-id="7c4fc-141">`requestQueueLimit` 동일한 방식으로 작동 하는 설정을 `requestQueueLimit` 특성에는 [processModel](http://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) ASP.NET 응용 프로그램에 대 한 Web.config 파일에 설정 된 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](http://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="7c4fc-142">그러나는 `requestQueueLimit` aspnet.config 파일의 설정 재정의 `requestQueueLimit` Web.config 파일에서 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="7c4fc-143">즉, 두 특성이 모두 설정 된 경우 (기본적으로 true 이면)는 `requestQueueLimit` aspnet.config 파일에서 설정이 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c4fc-144">예</span><span class="sxs-lookup"><span data-stu-id="7c4fc-144">Example</span></span>  
 <span data-ttu-id="7c4fc-145">다음 예제에는 다음과 같은 경우 aspnet.config 파일에서 ASP.NET 프로세스 수준 동작을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
-   <span data-ttu-id="7c4fc-146">응용 프로그램에서 호스트 되는 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 응용 프로그램 풀.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-146">The application is hosted in an [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] application pool.</span></span>  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)]<span data-ttu-id="7c4fc-147">통합된 모드에서 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-147"> is running in Integrated mode.</span></span>  
  
-   <span data-ttu-id="7c4fc-148">응용 프로그램을 사용 하 여는 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] 또는 이후 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-148">The application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span>  
  
 <span data-ttu-id="7c4fc-149">예제에서 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-149">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="7c4fc-150">요소 정보</span><span class="sxs-lookup"><span data-stu-id="7c4fc-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7c4fc-151">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="7c4fc-151">Namespace</span></span>||  
|<span data-ttu-id="7c4fc-152">스키마 이름</span><span class="sxs-lookup"><span data-stu-id="7c4fc-152">Schema Name</span></span>||  
|<span data-ttu-id="7c4fc-153">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="7c4fc-153">Validation File</span></span>||  
|<span data-ttu-id="7c4fc-154">비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="7c4fc-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c4fc-155">See Also</span></span>  
 [<span data-ttu-id="7c4fc-156">\<system.web> 요소(웹 설정)</span><span class="sxs-lookup"><span data-stu-id="7c4fc-156">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
