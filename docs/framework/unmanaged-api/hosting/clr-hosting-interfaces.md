---
title: "CLR 호스팅 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3efdf649d0039f2eb6b39d5cb17c839b90e97508
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="3647f-102">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="3647f-103">이 섹션에서는 관리 되지 않은 인터페이스 설명 호스트 응용 프로그램에 공용 언어 런타임 (CLR)를 통합 하 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="3647f-104">정보는.NET Framework 버전 2.0 이상 버전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="3647f-105">이러한 인터페이스는 런타임 버전 1.0 및 1.1에에서 비해 더 많은 요소를 제어 하려면 호스트를 활성화 하 고 CLR 및 호스트의 실행 모델 많은 밀접 하 게 통합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="3647f-106">.NET Framework 버전 1.0 및 1.1에서는 호스팅 모델에서 특정 설정을 구성 하 고 이벤트 알림을 받을 수는 프로세스에 CLR을 로드 하는 관리 되지 않는 호스트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="3647f-107">그러나 일반적으로 호스트와 CLR에서에서 실행 되었습니다 독립적으로 해당 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="3647f-108">.NET Framework 버전 2.0 및 이후 버전에서는 새로운 추상화 계층을 다양 한 Win32 어셈블리의 형식에서 현재 제공 되는 리소스를 제공 하 고 호스트를 구성할 수 있는 기능 집합이 확장 호스트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3647f-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="3647f-109">In This Section</span></span>  
 [<span data-ttu-id="3647f-110">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="3647f-111">등록 된 이벤트에 대 한 콜백을 수행 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="3647f-112">IApartmentCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="3647f-113">콜백을 아파트 내에서 수행 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="3647f-114">IAppDomainBinding 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="3647f-115">런타임에 구성 설정에 대 한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="3647f-116">ICatalogServices 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="3647f-117">카탈로그 서비스를 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="3647f-118">(이 인터페이스는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="3647f-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="3647f-119">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="3647f-120">호스트와 어셈블리에 대 한 CLR 간의 통신을 지 원하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="3647f-121">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="3647f-122">호스트가 아닌 CLR에서 로드 하는 어셈블리 목록을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="3647f-123">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="3647f-124">액세스 하 고 CLR의 다양 한 측면을 구성 하기 위해 호스트에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="3647f-125">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="3647f-126">호스트 식별자 및 이름을 사용 하 여 작업 집합을 연결 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="3647f-127">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="3647f-128">오류 보고에 대 한 사용자 지정 힙 덤프를 구성 하기 위해 호스트에 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="3647f-129">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="3647f-130">호스트 CLR의 가비지 수집 시스템과 상호 작용 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="3647f-131">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="3647f-132">호스트를 평가 하 여 어셈블리에 대 한 정책 정보 변경 내용을 적용 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="3647f-133">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="3647f-134">호스트를에서 특정 관리 되는 클래스, 메서드, 속성 및 부분적으로 신뢰할 수 있는 코드에서 실행 되는 필드를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="3647f-135">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="3647f-136">호스트가 CLR에 지정 된 I/O 요청의 상태를 알릴 수 있도록 하는 콜백 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="3647f-137">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="3647f-138">호스트가 win32과 유사한 방법을 사용 하 여 메모리 부족 상태를 보고할 수 있도록 `CreateMemoryResourceNotification` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="3647f-139">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="3647f-140">등록 및 CLR 이벤트에 대 한 콜백을 등록 취소 하기 위해 호스트에 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="3647f-141">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="3647f-142">정책 오류 및 시간 초과가 발생할 경우 수행할 작업을 지정 하려면 호스트를 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="3647f-143">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="3647f-144">호스트가 만들거나 해당 id를 이해할 필요 없이 내부에서 clr 어셈블리의 id 정보를 사용 하 여 어셈블리 검색 id를 가져오는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="3647f-145">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="3647f-146">파일 또는 스트림에서 만들거나 있는 필요 없이 내부에서 clr 어셈블리 id 데이터를 사용 하 여 참조 되는 어셈블리 집합을 조작 하는 호스트를 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="3647f-147">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="3647f-148">유사한 기능을 제공 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), 호스트 컨트롤 인터페이스를 설정 하는 추가 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="3647f-149">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="3647f-150">요청 된 작업에 대 한 정보를 동기화 구현에서 교착 상태를 검색 하는 호스트에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="3647f-151">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="3647f-152">호스트는 CLR의 요청을 만드는 하거나 관련된 작업에 대 한 CLR에 알림을 제공 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="3647f-153">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="3647f-154">호스트가 있는지 CLR 새 작업 만들기, 현재 실행 중인 작업을 가져오고 설정 언어와 문화권을 작업에 대 한 명시적으로 요청 하 고 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="3647f-155">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="3647f-156">이식 가능한 실행 (PE) 이미지 유효성 검사 및 유효성 검사 오류를 보고에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="3647f-157">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="3647f-158">CLR을 구성 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="3647f-159">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="3647f-160">스레드 풀에 액세스 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="3647f-161">IDebuggerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="3647f-162">디버깅 서비스의 상태에 대 한 정보를 얻기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="3647f-163">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="3647f-164">차단 하는 방법에 대 한 호스트에 알리기 및 디버깅 서비스에 의해 스레드 차단 해제에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="3647f-165">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="3647f-166">가비지 수집의 일부 측면을 제어 하기 위한 가비지 수집 시스템에 대 한 정보를 얻기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="3647f-167">IGCHost2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="3647f-168">제공 된 [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) 가비지 수집 세그먼트의 크기와를 설정 하려면 0 세대 가비지 수집 시스템의 최대 크기 값 보다 큰 수 있게 해 메서드 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="3647f-169">IGCHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="3647f-170">가비지 수집기가 호스트의 가상 메모리 제한을 변경 하려면 요청할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="3647f-171">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="3647f-172">가비지 수집에 대 한 차단 될 수 있는 스레드 일정에 참여 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="3647f-173">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="3647f-174">호스트는 clr 또는 호스트에 의해 로드 하는 어셈블리 집합을 지정 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="3647f-175">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="3647f-176">호스트 별도로 CLR 어셈블리와 모듈을 로드 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="3647f-177">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="3647f-178">호스트에서 구현 하는 자동 재설정 이벤트의 표현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="3647f-179">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="3647f-180">어셈블리 로드를 구성 하 고 호스팅 인터페이스를 호스트에서 지원할 결정 하기 위한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="3647f-181">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="3647f-182">스레딩에 대 한 임계 영역 호스트의 표시로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="3647f-183">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="3647f-184">호스트의 이벤트는 CLR에서 구현 하는 가비지 수집 메커니즘에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="3647f-185">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="3647f-186">호스트에서 제공 하는 I/O 완료 포트와 상호 작용 하는 CLR를 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="3647f-187">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="3647f-188">CLR 힙으로부터 호스트를 통해 세분화 된 할당을 요청을 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="3647f-189">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="3647f-190">수동 다시 설정 이벤트의 표현 호스트의 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="3647f-191">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="3647f-192">표준 Win32 가상 메모리 함수를 사용 하는 대신 호스트를 통해 가상 메모리를 요청 하는 CLR에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="3647f-193">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="3647f-194">CLR의 경우 수행 하는 동작의 호스트 중단, 제한 시간, 또는 실패를 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="3647f-195">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="3647f-196">CLR을 호스트에서 구현 하는 보안 컨텍스트 정보를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="3647f-197">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="3647f-198">현재 실행 중인 스레드의 보안 컨텍스트 제어 하 고에 액세스할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="3647f-199">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="3647f-200">호스트에서 구현 되는 세마포 표현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="3647f-201">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="3647f-202">Win32 동기화 함수를 사용 하는 대신 호스트를 호출 하 여 동기화 기본 형식을 만들 수는 CLR에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="3647f-203">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="3647f-204">작업을 관리 하기 위해 호스트와 통신 하는 CLR를 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="3647f-205">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="3647f-206">표준 운영 체제 스레드 또는 파이버 함수를 사용 하는 대신 호스트를 통해 작업을 CLR를 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="3647f-207">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="3647f-208">CLR 스레드 풀을 구성 하 고 스레드 풀에 작업 항목 큐에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="3647f-209">IManagedObject 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="3647f-210">관리 되는 개체를 제어 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="3647f-211">"IObjectHandle"</span><span class="sxs-lookup"><span data-stu-id="3647f-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="3647f-212">간접 참조에서 래핑 해제 값 방식 마샬링 개체에 대 한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="3647f-213">ITypeName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="3647f-214">형식 이름 정보를 얻기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="3647f-215">(이 인터페이스는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="3647f-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="3647f-216">ITypeNameBuilder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="3647f-217">형식 이름을 만들기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-217">Provides methods for building a type name.</span></span> <span data-ttu-id="3647f-218">(이 인터페이스는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="3647f-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="3647f-219">ITypeNameFactory 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="3647f-220">형식 이름을 제거 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="3647f-221">(이 인터페이스는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="3647f-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="3647f-222">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="3647f-222">"IValidator"</span></span>  
 <span data-ttu-id="3647f-223">이식 가능한 실행 (PE) 이미지 유효성 검사 및 유효성 검사 오류를 보고에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3647f-224">관련 단원</span><span class="sxs-lookup"><span data-stu-id="3647f-224">Related Sections</span></span>  
 [<span data-ttu-id="3647f-225">사용 되지 않는 CLR 호스팅 인터페이스 및 Coclass</span><span class="sxs-lookup"><span data-stu-id="3647f-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="3647f-226">.NET Framework 버전 1.0 및 1.1에서에서 제공 하는 호스팅 인터페이스를 설명 하는 항목이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="3647f-227">4 및 4.5.NET Framework에 추가 된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3647f-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="3647f-228">제공 하는 호스팅 인터페이스를 설명 하는 항목이 포함 되어는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3647f-228">Contains topics that describe the hosting interfaces provided in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>
