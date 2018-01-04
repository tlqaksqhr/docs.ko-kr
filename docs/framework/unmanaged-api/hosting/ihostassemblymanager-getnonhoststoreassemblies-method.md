---
title: "IHostAssemblyManager::GetNonHostStoreAssemblies 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyManager.GetNonHostStoreAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6af013a833ae694aca991f9a71769869cc79b76b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="d3ece-102">IHostAssemblyManager::GetNonHostStoreAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="d3ece-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="d3ece-103">한 인터페이스 포인터를 가져옵니다는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 호스트에서는 공용 언어 런타임 (CLR)를 로드 하는 어셈블리의 목록을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ece-104">구문</span><span class="sxs-lookup"><span data-stu-id="d3ece-104">Syntax</span></span>  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3ece-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3ece-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="d3ece-106">[out] 주소에 대 한 포인터는 `ICLRAssemblyReferenceList` 호스트에서는 로드 하기 위해 CLR 어셈블리에 대 한 참조의 목록이 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3ece-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="d3ece-107">Return Value</span></span>  
  
|<span data-ttu-id="d3ece-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3ece-108">HRESULT</span></span>|<span data-ttu-id="d3ece-109">설명</span><span class="sxs-lookup"><span data-stu-id="d3ece-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3ece-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3ece-110">S_OK</span></span>|<span data-ttu-id="d3ece-111">`GetNonHostStoreAssemblies`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="d3ece-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d3ece-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d3ece-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d3ece-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d3ece-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d3ece-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-115">The call timed out.</span></span>|  
|<span data-ttu-id="d3ece-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d3ece-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d3ece-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d3ece-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d3ece-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d3ece-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d3ece-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d3ece-120">E_FAIL</span></span>|<span data-ttu-id="d3ece-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d3ece-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d3ece-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d3ece-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d3ece-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d3ece-125">요청 된 작업에 대 한 참조 목록을 만드는 데 사용할 수 있는 메모리가 부족 했습니다 `ICLRAssemblyReferenceList`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3ece-126">설명</span><span class="sxs-lookup"><span data-stu-id="d3ece-126">Remarks</span></span>  
 <span data-ttu-id="d3ece-127">CLR 참조는 다음과 같은 지침 집합을 사용 하 여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
-   <span data-ttu-id="d3ece-128">반환 하는 어셈블리 참조의 목록을 확인 먼저 `GetNonHostStoreAssemblies`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
-   <span data-ttu-id="d3ece-129">어셈블리의 목록에 표시 하는 경우 CLR에 정상적으로 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
-   <span data-ttu-id="d3ece-130">어셈블리 목록에 나타나지 않으며 호스트의 구현에서 제공 하는 경우 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR에서는 [ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 호스트가 제공할 수 있도록 하는 바인딩할 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
-   <span data-ttu-id="d3ece-131">그렇지 않으면 CLR 어셈블리에 바인딩하는 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="d3ece-132">호스트 설정 하는 경우 `ppReferenceList` null이 고, CLR 첫 번째 프로브를 전역 어셈블리 캐시 호출 `ProvideAssembly`, 다음 어셈블리 참조를 확인 하려면 응용 프로그램 기준 위치를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3ece-133">CLR은 호출 초기화 될 `GetNonHostStoreAssemblies` 한 번만 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="d3ece-134">메서드가 다시 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3ece-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3ece-135">Requirements</span></span>  
 <span data-ttu-id="d3ece-136">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ece-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3ece-137">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d3ece-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3ece-138">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d3ece-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3ece-139">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3ece-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ece-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3ece-140">See Also</span></span>  
 [<span data-ttu-id="d3ece-141">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3ece-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="d3ece-142">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3ece-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="d3ece-143">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3ece-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
