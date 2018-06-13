---
title: ICLRErrorReportingManager::BeginCustomDump 메서드
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5d58a90901b7d7cb80ea7f25401b857b4d4875e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434514"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="97add-102">ICLRErrorReportingManager::BeginCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="97add-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="97add-103">오류 보고에 대 한 사용자 지정 힙 덤프 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97add-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97add-104">구문</span><span class="sxs-lookup"><span data-stu-id="97add-104">Syntax</span></span>  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97add-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97add-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="97add-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) 빌드 사용자 지정 힙 덤프를 힙 덤프의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="97add-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="97add-107">[in] 길이 `items` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="97add-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="97add-108">경우 `dwFlavor` DUMP_FLAVOR_Mini, 않습니다 `dwNumItems` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97add-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="97add-109">[in] 배열을 [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) 미니 덤프에 추가할 항목을 지정 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="97add-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="97add-110">경우 `dwFlavor` DUMP_FLAVOR_Mini, 않습니다 `items` null 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97add-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="97add-111">[in] 나중에 사용할 수는 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97add-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97add-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="97add-112">Return Value</span></span>  
  
|<span data-ttu-id="97add-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97add-113">HRESULT</span></span>|<span data-ttu-id="97add-114">설명</span><span class="sxs-lookup"><span data-stu-id="97add-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="97add-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="97add-115">S_OK</span></span>|<span data-ttu-id="97add-116">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="97add-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="97add-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="97add-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="97add-118">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97add-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="97add-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="97add-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="97add-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="97add-120">The call timed out.</span></span>|  
|<span data-ttu-id="97add-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="97add-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="97add-122">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97add-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="97add-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="97add-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="97add-124">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="97add-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="97add-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97add-125">E_FAIL</span></span>|<span data-ttu-id="97add-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="97add-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="97add-127">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97add-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="97add-128">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="97add-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97add-129">설명</span><span class="sxs-lookup"><span data-stu-id="97add-129">Remarks</span></span>  
 <span data-ttu-id="97add-130">`BeginCustomDump` 메서드는 사용자 지정 힙 덤프 구성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97add-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="97add-131">[EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) 메서드를 사용자 지정 힙 덤프 구성을 지워지고 연결 된 모든 상태를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="97add-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="97add-132">사용자 지정 힙 덤프 완료 된 후 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97add-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="97add-133">호출 하지 못하면 `EndCustomDump` 하면 메모리 누수를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="97add-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97add-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97add-134">Requirements</span></span>  
 <span data-ttu-id="97add-135">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="97add-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97add-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="97add-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97add-137">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="97add-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97add-138">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97add-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97add-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97add-139">See Also</span></span>  
 [<span data-ttu-id="97add-140">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="97add-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 [<span data-ttu-id="97add-141">ECustomDumpFlavor 열거형</span><span class="sxs-lookup"><span data-stu-id="97add-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 [<span data-ttu-id="97add-142">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97add-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
