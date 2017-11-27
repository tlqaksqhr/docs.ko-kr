---
title: "ICLRReferenceAssemblyEnum::Get 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRReferenceAssemblyEnum.Get
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab64f7983b5825505421e7bfbcf6866004778a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="0f4cf-102">ICLRReferenceAssemblyEnum::Get 메서드</span><span class="sxs-lookup"><span data-stu-id="0f4cf-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="0f4cf-103">지정된 된 인덱스에 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f4cf-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f4cf-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f4cf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f4cf-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="0f4cf-106">[in] 반환할 어셈블리 id의 0부터 시작 하는 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="0f4cf-107">[out] 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="0f4cf-108">[out에서] 크기는 `pwzBuffer` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f4cf-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="0f4cf-109">Return Value</span></span>  
  
|<span data-ttu-id="0f4cf-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f4cf-110">HRESULT</span></span>|<span data-ttu-id="0f4cf-111">설명</span><span class="sxs-lookup"><span data-stu-id="0f4cf-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f4cf-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f4cf-112">S_OK</span></span>|<span data-ttu-id="0f4cf-113">`Get`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="0f4cf-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="0f4cf-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="0f4cf-115">`pwzBuffer`너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="0f4cf-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="0f4cf-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="0f4cf-117">열거할 항목이 더 이상 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="0f4cf-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f4cf-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f4cf-119">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f4cf-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f4cf-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f4cf-121">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-121">The call timed out.</span></span>|  
|<span data-ttu-id="0f4cf-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f4cf-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f4cf-123">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f4cf-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f4cf-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f4cf-125">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f4cf-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f4cf-126">E_FAIL</span></span>|<span data-ttu-id="0f4cf-127">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f4cf-128">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f4cf-129">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f4cf-130">설명</span><span class="sxs-lookup"><span data-stu-id="0f4cf-130">Remarks</span></span>  
 <span data-ttu-id="0f4cf-131">`Get`두 번 호출 일반적으로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-131">`Get` is typically called twice.</span></span> <span data-ttu-id="0f4cf-132">첫 번째 호출에 대 한 null 값이 제공 `pwzBuffer`, 설정 및 `pcchBufferSize` 에 적합 한 크기로 `pwzBuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="0f4cf-133">두 번째 호출 제공는 적절 한 크기의 `pwzBuffer`, 완료 되 면 정식 어셈블리 id 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f4cf-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f4cf-134">Requirements</span></span>  
 <span data-ttu-id="0f4cf-135">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f4cf-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f4cf-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0f4cf-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f4cf-137">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0f4cf-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f4cf-138">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f4cf-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f4cf-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f4cf-139">See Also</span></span>  
 [<span data-ttu-id="0f4cf-140">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f4cf-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="0f4cf-141">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f4cf-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
