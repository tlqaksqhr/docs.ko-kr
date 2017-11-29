---
title: "WCF 성능 카운터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
caps.latest.revision: "37"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2136b4f9ab97f7ed0e4c31e6ffc26f788546419b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-performance-counters"></a><span data-ttu-id="88e09-102">WCF 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="88e09-102">WCF Performance Counters</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="88e09-103">에는 응용 프로그램의 성능을 측정하는 데 도움이 되는 다양한 성능 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-103"> includes a large set of performance counters to help you gauge your application's performance.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="88e09-104">성능 카운터 사용</span><span class="sxs-lookup"><span data-stu-id="88e09-104">Enabling Performance Counters</span></span>  
 <span data-ttu-id="88e09-105">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스의 app.config 구성 파일을 통해 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스에 대한 성능 카운터를 다음과 같이 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-105">You can enable performance counters for a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service through the app.config configuration file of the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service as follows:</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="88e09-106">특정 유형의 성능 카운터를 활성화하도록 `performanceCounters` 특성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-106">The `performanceCounters` attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="88e09-107">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-107">Valid values are</span></span>  
  
-   <span data-ttu-id="88e09-108">All: 모든 범주 카운터(ServiceModelService, ServiceModelEndpoint, ServiceModelOperation)가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-108">All: All category counters (ServiceModelService, ServiceModelEndpoint and ServiceModelOperation) are enabled.</span></span>  
  
-   <span data-ttu-id="88e09-109">ServiceOnly: ServiceModelService 범주 카운터만 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-109">ServiceOnly: Only ServiceModelService category counters are enabled.</span></span> <span data-ttu-id="88e09-110">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-110">This is the default value.</span></span>  
  
-   <span data-ttu-id="88e09-111">Off: ServiceModel* 성능 카운터가 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-111">Off: ServiceModel* performance counters are disabled.</span></span>  
  
 <span data-ttu-id="88e09-112">모든 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 응용 프로그램에 대해 성능 카운터를 활성화하려면 Machine.config 파일에 구성 설정을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-112">If you want to enable performance counters for all [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] applications, you can place the configuration settings in the Machine.config file.</span></span>  <span data-ttu-id="88e09-113">참조 하십시오는 **성능 카운터에 대 한 메모리 크기 늘리기** 컴퓨터에 성능 카운터에 대 한 충분 한 메모리를 구성 하는 방법에 대 한 자세한 내용은 아래 섹션.</span><span class="sxs-lookup"><span data-stu-id="88e09-113">Please see the **Increasing Memory Size for Performance Counters** section below for more information on configuring sufficient memory for performance counters on your machine.</span></span>  
  
 <span data-ttu-id="88e09-114">사용자 지정 작업 호출자와 같은 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 확장성 지점을 사용하는 경우에는 성능 카운터도 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-114">If you use [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] extensibility points such as custom operation invokers, you should also emit your own performance counters.</span></span> <span data-ttu-id="88e09-115">이는 확장성 지점을 구현하는 경우 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서 더 이상 기본 경로에서 표준 성능 카운터 데이터를 내보낼 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-115">This is because if you implement an extensibility point, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] may no longer emit the standard performance counter data in the default path.</span></span> <span data-ttu-id="88e09-116">수동 성능 카운터 지원을 구현하지 않으면 예상하는 성능 카운터 데이터가 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-116">If you do not implement manual performance counter support, you may not see the performance counter data you expect.</span></span>  
  
 <span data-ttu-id="88e09-117">코드를 사용하여 다음과 같이 성능 카운터를 활성화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-117">You can also enable performance counters in your code as follows,</span></span>  
  
```  
using System.Configuration;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Diagnostics;  
Configuration config = ConfigurationManager.OpenExeConfiguration(  
    ConfigurationUserLevel.None);  
ServiceModelSectionGroup sg = ServiceModelSectionGroup.GetSectionGroup(config);  
sg.Diagnostic.PerformanceCounters = PerformanceCounterScope.All;  
config.Save();  
```  
  
## <a name="viewing-performance-data"></a><span data-ttu-id="88e09-118">성능 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="88e09-118">Viewing Performance Data</span></span>  
 <span data-ttu-id="88e09-119">성능 카운터에서 캡처한 데이터를 보려면 Windows와 함께 제공된 성능 모니터(Perfmon.exe)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-119">To view data captured by the performance counters, you can use the Performance Monitor (Perfmon.exe) that comes with Windows.</span></span> <span data-ttu-id="88e09-120">로 이동 하 여이 도구를 시작할 수 **시작**를 클릭 하 고 **실행** 유형과 `perfmon.exe` 대화 상자에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-120">You can launch this tool by going to **Start**, and click **Run** and type `perfmon.exe` in the dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88e09-121">끝점 디스패처가 마지막 메시지를 처리하기 이전에 성능 카운터 인스턴스가 해제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-121">Performance counter instances may be released before the last messages have been processed by the endpoint dispatcher.</span></span> <span data-ttu-id="88e09-122">그러면 일부 메시지에 대한 성능 데이터가 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-122">This can result in performance data not being captured for a few messages.</span></span>  
  
## <a name="increasing-memory-size-for-performance-counters"></a><span data-ttu-id="88e09-123">성능 카운터에 대한 메모리 크기 늘리기</span><span class="sxs-lookup"><span data-stu-id="88e09-123">Increasing Memory Size for Performance Counters</span></span>  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="88e09-124">에서는 성능 카운터 범주에 대해 별도의 공유 메모리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-124"> uses separate shared memory for its performance counter categories.</span></span>  
  
 <span data-ttu-id="88e09-125">기본적으로 별도의 공유 메모리는 전역 성능 카운터 메모리 크기의 1/4로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-125">By default, separate shared memory is set to a quarter the size of global performance counter memory.</span></span> <span data-ttu-id="88e09-126">기본 전역 성능 카운터 메모리는 524,288바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-126">The default global performance counter memory is 524,288 bytes.</span></span> <span data-ttu-id="88e09-127">따라서 세 개의 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 성능 카운터 범주의 기본 크기는 각각 약 128KB입니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-127">Therefore, the three [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] performance counter categories have a default size of approximately 128KB each.</span></span> <span data-ttu-id="88e09-128">컴퓨터에 있는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 응용 프로그램의 런타임 특성에 따라 성능 카운터 메모리가 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-128">Depending upon the runtime characteristics of the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] applications on a machine, performance counter memory may be exhausted.</span></span> <span data-ttu-id="88e09-129">이 때 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]는 응용 프로그램 이벤트 로그에 오류를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-129">When this happens, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] writes an error to the application event log.</span></span> <span data-ttu-id="88e09-130">오류 내용에는 성능 카운터가 로드되지 않았다는 설명이 표시되며, "System.InvalidOperationException: 사용자 지정 카운터 파일 뷰 메모리가 부족합니다."라는 예외가 항목에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-130">The content of the error states that a performance counter was not loaded, and the entry contains the exception "System.InvalidOperationException: Custom counters file view is out of memory."</span></span> <span data-ttu-id="88e09-131">오류 수준에서 추적 기능을 사용하도록 설정하면 이 오류도 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-131">If tracing is enabled at the error level, this failure is also traced.</span></span> <span data-ttu-id="88e09-132">성능 카운터 메모리가 부족한 상태에서 성능 카운터를 활성화한 상태로 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 응용 프로그램을 계속 실행하면 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-132">If performance counter memory is exhausted, continuing to run your [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] applications with performance counters enabled could result in performance degradation.</span></span> <span data-ttu-id="88e09-133">컴퓨터 관리자는 언제든지 최대 성능 카운터 수를 지원하는 데 충분한 메모리를 할당하도록 컴퓨터를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-133">If you are an administrator of the machine, you should configure it to allocate enough memory to support the maximum number of performance counters that can exist at any time.</span></span>  
  
 <span data-ttu-id="88e09-134">레지스트리에서 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 범주에 대한 성능 카운터 메모리 양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-134">You can change the amount of performance counter memory for [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] categories in the registry.</span></span> <span data-ttu-id="88e09-135">그렇게 하려면 다음 세 위치에 `FileMappingSize`라는 새로운 DWORD 값을 추가하여 원하는 값(바이트)으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-135">To do so, you need to add a new DWORD value named `FileMappingSize` to the three following locations, and set it to the desired value in bytes.</span></span> <span data-ttu-id="88e09-136">컴퓨터를 다시 부팅하여 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-136">Reboot your machine so that these changes are taken into effect.</span></span>  
  
-   <span data-ttu-id="88e09-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="88e09-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="88e09-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="88e09-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="88e09-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="88e09-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span></span>  
  
 <span data-ttu-id="88e09-140">많은 수의 개체(예: ServiceHost)를 삭제할 때 가비지가 수집되기를 대기 중인 경우 `PrivateBytes` 성능 카운터는 매우 높은 수를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-140">When a large number of objects (for example, ServiceHost) are disposed of but waiting to be garbage-collected, the `PrivateBytes` performance counter will register an unusually high number.</span></span> <span data-ttu-id="88e09-141">이 문제를 해결하려면 응용 프로그램 관련 카운터를 추가하거나 `performanceCounters` 특성을 사용하여 서비스 수준 카운터만 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-141">To resolve this problem, you can either add your own application-specific counters, or use the `performanceCounters` attribute to enable only service-level counters.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="88e09-142">성능 카운터 형식</span><span class="sxs-lookup"><span data-stu-id="88e09-142">Types of Performance Counters</span></span>  
 <span data-ttu-id="88e09-143">성능 카운터의 범위는 서비스, 끝점 및 작업의 세 가지 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-143">Performance counters are scoped to three different levels: Service, Endpoint and Operation.</span></span>  
  
 <span data-ttu-id="88e09-144">WMI를 사용하여 성능 카운터 인스턴스의 이름을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-144">You can use WMI to retrieve the name of a performance counter instance.</span></span> <span data-ttu-id="88e09-145">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-145">For example,</span></span>  
  
-   <span data-ttu-id="88e09-146">WMI를 통해 서비스 카운터 인스턴스 이름을 가져올 수 [서비스](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) 인스턴스의 "CounterInstanceName" 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-146">Service counter instance name can be obtained through WMI [Service](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="88e09-147">WMI를 통해 끝점 카운터 인스턴스 이름을 가져올 수 [끝점](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) 인스턴스의 "CounterInstanceName" 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-147">Endpoint counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="88e09-148">WMI를 통해 작업 카운터 인스턴스 이름을 가져올 수 [끝점](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) 인스턴스의 "GetOperationCounterInstanceName" 메서드.</span><span class="sxs-lookup"><span data-stu-id="88e09-148">Operation counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "GetOperationCounterInstanceName" method.</span></span>  
  
 <span data-ttu-id="88e09-149">WMI에 대 한 자세한 내용은 참조 하십시오. [진단에 대 한 Windows Management Instrumentation를 사용 하 여](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-149">For more information on WMI, see [Using Windows Management Instrumentation for Diagnostics](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span></span>  
  
### <a name="service-performance-counters"></a><span data-ttu-id="88e09-150">서비스 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="88e09-150">Service performance counters</span></span>  
 <span data-ttu-id="88e09-151">서비스 성능 카운터는 서비스 동작을 전반적으로 측정하며 전체 서비스 성능을 진단하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-151">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="88e09-152">이러한 카운터는 성능 모니터에서 볼 때 `ServiceModelService 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-152">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="88e09-153">인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-153">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
 <span data-ttu-id="88e09-154">서비스 범위 내의 카운터가 끝점 컬렉션 내의 카운터로부터 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-154">A counter in a service scope is aggregated from counter in a collection of endpoints.</span></span>  
  
 <span data-ttu-id="88e09-155">새 InstanceContext가 만들어지면 서비스 인스턴스 만들기에 대한 성능 카운터가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-155">Performance counters for service instance creation are incremented when a new InstanceContext is created.</span></span> <span data-ttu-id="88e09-156">기존 서비스에서 활성화 상태가 아닌 메시지를 받거나, 한 세션에서 인스턴스에 연결하고 세션을 끝낸 다음 다른 세션에서 다시 연결하는 경우에도 새 InstanceContext가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-156">Note that a new InstanceContext is created even when you receive a non-activating message (with an existing service), or when you connect to an instance from one session, end the session, and then reconnect from another session.</span></span>  
  
### <a name="endpoint-performance-counters"></a><span data-ttu-id="88e09-157">끝점 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="88e09-157">Endpoint performance counters</span></span>  
 <span data-ttu-id="88e09-158">끝점 성능 카운터를 사용하면 끝점이 메시지를 수신하는 방식을 나타내는 데이터를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-158">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="88e09-159">이러한 카운터는 성능 모니터를 사용하여 볼 때 `ServiceModelEndpoint 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-159">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing using the Performance Monitor.</span></span> <span data-ttu-id="88e09-160">인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-160">The instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="88e09-161">데이터는 개별 작업을 위해 수집된 데이터와 비슷하지만 끝점에서만 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-161">The data is similar to what is collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
 <span data-ttu-id="88e09-162">끝점 범위 내의 카운터가 작업 컬렉션 내의 카운터로부터 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-162">A counter in an endpoint scope is aggregated from counters in a collection of operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88e09-163">두 끝점의 계약 이름과 주소가 동일한 경우 두 끝점은 동일한 카운터 인스턴스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-163">If two endpoints have identical contract names and addresses, they are mapped to the same counter instance.</span></span>  
  
### <a name="operation-performance-counters"></a><span data-ttu-id="88e09-164">작업 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="88e09-164">Operation performance counters</span></span>  
 <span data-ttu-id="88e09-165">작업 성능 카운터는 성능 모니터에서 볼 때 `ServiceModelOperation 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-165">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="88e09-166">각 작업에는 개별 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-166">Each operation has an individual instance.</span></span> <span data-ttu-id="88e09-167">즉, 지정된 계약에 10개의 작업이 있는 경우 10개의 작업 카운터 인스턴스가 해당 계약에 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-167">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="88e09-168">개체 인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-168">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="88e09-169">이 카운터를 사용하면 호출이 사용되는 방법과 작업 진행 상태를 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-169">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
 <span data-ttu-id="88e09-170">카운터가 여러 범위에 표시될 때 상위 범위에서 수집된 데이터가 하위 범위의 데이터와 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-170">When counters are visible at multiple scopes, data gathered from a higher scope are aggregated with data from lower scopes.</span></span> <span data-ttu-id="88e09-171">예를 들어, 끝점의 `Calls`는 끝점에 있는 모든 작업 호출의 합계를 나타내고 서비스의 `Calls`는 서비스에 있는 모든 끝점에 대한 모든 호출 합계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-171">For example, `Calls` at an endpoint represents the sum of all operation calls within the endpoint; `Calls` at a service represents the sum of all calls to all endpoints within the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88e09-172">계약에 중복 작업 이름이 있는 경우 두 작업에 대해 카운터 인스턴스를 하나만 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-172">If you have duplicate operation names on a contract, you only get one counter instances for both operations.</span></span>  
  
## <a name="programming-the-wcf-performance-counters"></a><span data-ttu-id="88e09-173">WCF 성능 카운터 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="88e09-173">Programming the WCF Performance Counters</span></span>  
 <span data-ttu-id="88e09-174">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 성능 카운터를 프로그래밍 방식으로 액세스할 수 있도록 SDK 설치 폴더에 여러 파일이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-174">Several files are installed in the SDK install folder so that you can access the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] performance counters programmatically.</span></span> <span data-ttu-id="88e09-175">설치되는 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-175">These files are listed as follows.</span></span>  
  
-   <span data-ttu-id="88e09-176">_ServiceModelEndpointPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="88e09-176">_ServiceModelEndpointPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="88e09-177">_ServiceModelOperationPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="88e09-177">_ServiceModelOperationPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="88e09-178">_ServiceModelServicePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="88e09-178">_ServiceModelServicePerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="88e09-179">_SMSvcHostPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="88e09-179">_SMSvcHostPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="88e09-180">_TransactionBridgePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="88e09-180">_TransactionBridgePerfCounters.vrg</span></span>  
  
 <span data-ttu-id="88e09-181">카운터를 프로그래밍 방식으로 액세스 하는 방법에 대 한 자세한 내용은 참조 하십시오. [성능 카운터 프로그래밍 아키텍처](http://go.microsoft.com/fwlink/?LinkId=95179)합니다.</span><span class="sxs-lookup"><span data-stu-id="88e09-181">For more information on how to access the counters programmatically, see [Performance Counter Programming Architecture](http://go.microsoft.com/fwlink/?LinkId=95179).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88e09-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88e09-182">See Also</span></span>  
 [<span data-ttu-id="88e09-183">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="88e09-183">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
