---
title: "ICLRErrorReportingManager::BeginCustomDump 메서드"
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
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d09afd9fe0a2905c79ffb2d50b342041865b593b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="d05c8-102">ICLRErrorReportingManager::BeginCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="d05c8-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="d05c8-103">오류 보고에 대 한 사용자 지정 힙 덤프 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d05c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="d05c8-104">Syntax</span></span>  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d05c8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d05c8-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="d05c8-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) 빌드 사용자 지정 힙 덤프를 힙 덤프의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="d05c8-107">[in] 길이 `items` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="d05c8-108">경우 `dwFlavor` DUMP_FLAVOR_Mini, 않습니다 `dwNumItems` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="d05c8-109">[in] 배열을 [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) 미니 덤프에 추가할 항목을 지정 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="d05c8-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="d05c8-110">경우 `dwFlavor` DUMP_FLAVOR_Mini, 않습니다 `items` null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="d05c8-111">[in] 나중에 사용할 수는 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d05c8-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="d05c8-112">Return Value</span></span>  
  
|<span data-ttu-id="d05c8-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d05c8-113">HRESULT</span></span>|<span data-ttu-id="d05c8-114">설명</span><span class="sxs-lookup"><span data-stu-id="d05c8-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d05c8-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d05c8-115">S_OK</span></span>|<span data-ttu-id="d05c8-116">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="d05c8-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d05c8-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d05c8-118">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d05c8-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d05c8-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d05c8-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-120">The call timed out.</span></span>|  
|<span data-ttu-id="d05c8-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d05c8-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d05c8-122">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d05c8-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d05c8-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d05c8-124">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d05c8-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d05c8-125">E_FAIL</span></span>|<span data-ttu-id="d05c8-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d05c8-127">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d05c8-128">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d05c8-129">설명</span><span class="sxs-lookup"><span data-stu-id="d05c8-129">Remarks</span></span>  
 <span data-ttu-id="d05c8-130">`BeginCustomDump` 메서드는 사용자 지정 힙 덤프 구성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="d05c8-131">[EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) 메서드를 사용자 지정 힙 덤프 구성을 지워지고 연결 된 모든 상태를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="d05c8-132">사용자 지정 힙 덤프 완료 된 후 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d05c8-133">호출 하지 못하면 `EndCustomDump` 하면 메모리 누수를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d05c8-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d05c8-134">Requirements</span></span>  
 <span data-ttu-id="d05c8-135">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d05c8-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d05c8-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d05c8-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d05c8-137">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d05c8-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d05c8-138">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d05c8-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d05c8-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d05c8-139">See Also</span></span>  
 [<span data-ttu-id="d05c8-140">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="d05c8-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 [<span data-ttu-id="d05c8-141">ECustomDumpFlavor 열거형</span><span class="sxs-lookup"><span data-stu-id="d05c8-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 [<span data-ttu-id="d05c8-142">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d05c8-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
