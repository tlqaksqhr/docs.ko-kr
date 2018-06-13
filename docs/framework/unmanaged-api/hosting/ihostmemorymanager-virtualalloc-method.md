---
title: IHostMemoryManager::VirtualAlloc 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe54aed47d240be37ab9dbc5381235c4e962f1f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440316"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="f7242-102">IHostMemoryManager::VirtualAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="f7242-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="f7242-103">해당 Win32 함수에 대 한 논리적 래퍼입니다로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="f7242-104">Win32 구현은 `VirtualAlloc` 예약 하거나 호출 프로세스의 가상 주소 공간에 있는 페이지의 영역을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7242-105">구문</span><span class="sxs-lookup"><span data-stu-id="f7242-105">Syntax</span></span>  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7242-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7242-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="f7242-107">[in] 할당할 지역의 시작 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="f7242-108">[in] 영역의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="f7242-109">[in] 메모리 할당의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="f7242-110">[in] 지역에 대 한 보호를 메모리의 페이지를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="f7242-111">[in] [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) 할당 오류의 영향을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="f7242-112">[out] 요청을 충족할 수 있는 경우에 null 또는 할당 된 메모리의 시작 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7242-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="f7242-113">Return Value</span></span>  
  
|<span data-ttu-id="f7242-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f7242-114">HRESULT</span></span>|<span data-ttu-id="f7242-115">설명</span><span class="sxs-lookup"><span data-stu-id="f7242-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f7242-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7242-116">S_OK</span></span>|<span data-ttu-id="f7242-117">`VirtualAlloc` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="f7242-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f7242-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f7242-119">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f7242-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f7242-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f7242-121">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-121">The call timed out.</span></span>|  
|<span data-ttu-id="f7242-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f7242-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f7242-123">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f7242-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f7242-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f7242-125">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f7242-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f7242-126">E_FAIL</span></span>|<span data-ttu-id="f7242-127">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f7242-128">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f7242-129">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f7242-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f7242-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f7242-131">메모리가 부족 할당 요청을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7242-132">설명</span><span class="sxs-lookup"><span data-stu-id="f7242-132">Remarks</span></span>  
 <span data-ttu-id="f7242-133">호출 하 여 프로세스의 주소 공간에서 영역을 예약 `VirtualAlloc`합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="f7242-134">`pAddress` 매개 변수에 사용할 메모리 블록의 시작 주소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="f7242-135">이 매개 변수는 일반적으로 설정 하는 null로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-135">This parameter is typically set to null.</span></span> <span data-ttu-id="f7242-136">운영 체제 프로세스에 사용할 수 있는 사용 가능한 주소 범위에 대 한 기록을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="f7242-137">A `pAddress` null 값을 판단 되는 영역을 예약 하 고 시스템에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="f7242-138">또는 메모리 블록에 대 한 특정 시작 주소를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="f7242-139">두 경우 모두 출력 매개 변수 `ppMem` 할당된 된 메모리에 대 한 포인터로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="f7242-140">함수 자체 HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="f7242-141">Win32 `VirtualAlloc` 함수에는 한 `ppMem` 매개 변수를 대신에 할당된 된 메모리에 포인터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="f7242-142">자세한 내용은 Windows 플랫폼 설명서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7242-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7242-143">Requirements</span></span>  
 <span data-ttu-id="f7242-144">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7242-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7242-145">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f7242-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7242-146">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f7242-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7242-147">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7242-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7242-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7242-148">See Also</span></span>  
 [<span data-ttu-id="f7242-149">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7242-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
