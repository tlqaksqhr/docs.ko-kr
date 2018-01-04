---
title: "IHostMemoryManager::VirtualProtect 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualProtect
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 77e8e163a16752934d0a1d826cc8463b3d3281bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="4cfc7-102">IHostMemoryManager::VirtualProtect 메서드</span><span class="sxs-lookup"><span data-stu-id="4cfc7-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="4cfc7-103">해당 Win32 함수에 대 한 논리적 래퍼입니다로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="4cfc7-104">Win32 구현은 `VirtualProtect` 호출 프로세스의 가상 주소 공간에서 커밋된 페이지의 영역에 대해 보호를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cfc7-105">구문</span><span class="sxs-lookup"><span data-stu-id="4cfc7-105">Syntax</span></span>  
  
```  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cfc7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4cfc7-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="4cfc7-107">[in] 특성을 가진 보호를 변경할 수는 가상 메모리의 기본 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="4cfc7-108">[in] 바이트의 메모리 페이지를 변경할지 영역의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="4cfc7-109">[in] 적용할 메모리 보호의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="4cfc7-110">[out] 이전 메모리 보호 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cfc7-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="4cfc7-111">Return Value</span></span>  
  
|<span data-ttu-id="4cfc7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cfc7-112">HRESULT</span></span>|<span data-ttu-id="4cfc7-113">설명</span><span class="sxs-lookup"><span data-stu-id="4cfc7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cfc7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cfc7-114">S_OK</span></span>|<span data-ttu-id="4cfc7-115">`VirtualProtect`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="4cfc7-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4cfc7-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4cfc7-117">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4cfc7-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4cfc7-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4cfc7-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-119">The call timed out.</span></span>|  
|<span data-ttu-id="4cfc7-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4cfc7-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4cfc7-121">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4cfc7-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4cfc7-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4cfc7-123">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4cfc7-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4cfc7-124">E_FAIL</span></span>|<span data-ttu-id="4cfc7-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4cfc7-126">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4cfc7-127">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cfc7-128">설명</span><span class="sxs-lookup"><span data-stu-id="4cfc7-128">Remarks</span></span>  
 <span data-ttu-id="4cfc7-129">이 구현 `VirtualProtect` Win32 구현은 성공을 나타내려면 0이 아닌 값을 반환 하는 동안에 HRESULT 값 및 실패를 나타내려면 0 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="4cfc7-130">자세한 내용은 Windows 플랫폼 설명서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cfc7-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4cfc7-131">Requirements</span></span>  
 <span data-ttu-id="4cfc7-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfc7-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cfc7-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4cfc7-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cfc7-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4cfc7-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cfc7-135">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cfc7-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cfc7-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cfc7-136">See Also</span></span>  
 [<span data-ttu-id="4cfc7-137">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cfc7-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
