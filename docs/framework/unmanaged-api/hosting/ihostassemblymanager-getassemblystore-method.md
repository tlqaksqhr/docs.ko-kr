---
title: "IHostAssemblyManager::GetAssemblyStore 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 347947622601475147663b8838bef5f36a1f7e32
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="00cd3-102">IHostAssemblyManager::GetAssemblyStore 메서드</span><span class="sxs-lookup"><span data-stu-id="00cd3-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="00cd3-103">한 인터페이스 포인터를 가져옵니다는 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) 호스트에 의해 로드 된 어셈블리 목록을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00cd3-104">구문</span><span class="sxs-lookup"><span data-stu-id="00cd3-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00cd3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="00cd3-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="00cd3-106">[out] 에 대 한 함수 포인터는 `IHostAssemblyStore` 인스턴스에 지정 하거나 호스트를 구현 하지 않는 경우 null `IHostAssemblyStore`합니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00cd3-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="00cd3-107">Return Value</span></span>  
  
|<span data-ttu-id="00cd3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00cd3-108">HRESULT</span></span>|<span data-ttu-id="00cd3-109">설명</span><span class="sxs-lookup"><span data-stu-id="00cd3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00cd3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="00cd3-110">S_OK</span></span>|<span data-ttu-id="00cd3-111">`GetAssemblyStore`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="00cd3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="00cd3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="00cd3-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="00cd3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="00cd3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="00cd3-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-115">The call timed out.</span></span>|  
|<span data-ttu-id="00cd3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="00cd3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="00cd3-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="00cd3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="00cd3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="00cd3-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="00cd3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="00cd3-120">E_FAIL</span></span>|<span data-ttu-id="00cd3-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="00cd3-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="00cd3-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="00cd3-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="00cd3-124">E_NOINTERFACE</span></span>|<span data-ttu-id="00cd3-125">호스트의 구현을 제공 하지 않는 `IHostAssemblyStore`합니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00cd3-126">설명</span><span class="sxs-lookup"><span data-stu-id="00cd3-126">Remarks</span></span>  
 <span data-ttu-id="00cd3-127">`IHostAssemblyStore`호스트 어셈블리와 모듈은 CLR과 별도로 바인딩하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="00cd3-128">일반적으로 호스트 파일 시스템 이외의 다른 형식을 로드할 수 있도록 하려면 어셈블리 저장소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00cd3-129">호스트를 구현 하지 않는 경우 `IHostAssemblyStore`, `GetAssemblyStore` 은 E_NOINTERFACE의 HRESULT 값을 반환 해야 하 고 설정할지 `ppAssemblyStore` null로 합니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00cd3-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00cd3-130">Requirements</span></span>  
 <span data-ttu-id="00cd3-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00cd3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00cd3-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="00cd3-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00cd3-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="00cd3-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00cd3-134">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00cd3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00cd3-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00cd3-135">See Also</span></span>  
 [<span data-ttu-id="00cd3-136">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00cd3-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="00cd3-137">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00cd3-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
