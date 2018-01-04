---
title: ".NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
caps.latest.revision: "26"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61231715a24978e7fe57b2c9e87e7968dc0fdbc5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="d33b8-102">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d33b8-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="d33b8-103">이 섹션에서는 관리 되지 않는 인터페이스를 설명 호스트에 공용 언어 런타임 (CLR)를 통합 하 사용할 수는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], 응용 프로그램에 이상 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], and later versions into their applications.</span></span> <span data-ttu-id="d33b8-104">이러한 인터페이스는 런타임 프로세스에 로드 하기 위해 호스트에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="d33b8-105">부터는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], 모든 호스팅 인터페이스는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-105">Starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], all hosting interfaces have the following characteristics:</span></span>  
  
-   <span data-ttu-id="d33b8-106">수명 관리를 사용 (`AddRef` 및 `Release`), 캡슐화 (암시적 컨텍스트) 및 `QueryInterface` com</span><span class="sxs-lookup"><span data-stu-id="d33b8-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
-   <span data-ttu-id="d33b8-107">사용 하지 않습니다 COM 형식이 같은 `BSTR`, `SAFEARRAY`, 또는 `VARIANT`합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-107">There do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
-   <span data-ttu-id="d33b8-108">아파트 모델, 집계 또는 없는지 레지스트리 활성화를 사용 하 여 [CoCreateInstance 함수](http://go.microsoft.com/fwlink/?LinkId=142894)합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](http://go.microsoft.com/fwlink/?LinkId=142894).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d33b8-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d33b8-109">In This Section</span></span>  
 [<span data-ttu-id="d33b8-110">ICLRAppDomainResourceMonitor 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d33b8-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="d33b8-111">응용 프로그램 도메인의 메모리 및 CPU 사용량을 검사 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="d33b8-112">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d33b8-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="d33b8-113">호스트를에서 기본 응용 프로그램 도메인을 초기화 하 고 초기화 속성을 지정 하는 데 사용 될 응용 프로그램 도메인 관리자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="d33b8-114">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d33b8-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="d33b8-115">제공 된 [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) 메서드를 가비지 수집 세그먼트의 크기와를 설정 하려면 0 세대 가비지 수집 시스템의 최대 크기 값 보다 큰 호스트를 사용 하면 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="d33b8-116">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d33b8-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="d33b8-117">CLR의 특정 버전을 반환, 모든 설치 된 Clr 목록, 모든 프로세스에서 런타임을 나열, 정품 인증 인터페이스를 반환 되며 어셈블리로 컴파일하는 데 사용 되는 CLR 버전을 검색 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="d33b8-118">ICLRMetaHostPolicy 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d33b8-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="d33b8-119">제공 된 [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) 정책 기준을, 관리 되는 어셈블리, 버전 및 구성 파일을 기반으로 CLR 인터페이스를 제공 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="d33b8-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="d33b8-120">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d33b8-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="d33b8-121">버전, 디렉터리 및 부하 상태를 포함 하는 특정 런타임에 대 한 정보를 반환 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="d33b8-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d33b8-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="d33b8-123">강력한 이름의 어셈블리를 서명 하는 것에 대 한 기본 전역 정적 함수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="d33b8-124">모든는 [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) 메서드 표준 COM Hresult를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="d33b8-125">ICLRStrongName2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d33b8-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="d33b8-126">(Sha-256, sha-384 및 s h A-512) 보안 해시 알고리즘의 sha-2 그룹을 사용 하 여 강력한 이름을 만들 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="d33b8-127">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d33b8-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="d33b8-128">모든 기능을 제공 된 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)의 스레드는 현재 스레드에서 지연 될 중단을 허용 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d33b8-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d33b8-129">Related Sections</span></span>  
 [<span data-ttu-id="d33b8-130">사용되지 않는 CLR 호스팅 인터페이스 및 Coclass</span><span class="sxs-lookup"><span data-stu-id="d33b8-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="d33b8-131">.NET Framework 버전 1.0 및 1.1와 함께 제공 되는 호스팅 인터페이스에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="d33b8-132">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d33b8-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="d33b8-133">.NET Framework 버전 2.0, 3.0 및 3.5와 함께 제공 되는 호스팅 인터페이스에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="d33b8-134">호스팅</span><span class="sxs-lookup"><span data-stu-id="d33b8-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="d33b8-135">.NET Framework에서의 호스팅 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="d33b8-135">Introduces hosting in the .NET Framework.</span></span>
