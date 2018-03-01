---
title: "IHostMemoryManager::AcquiredVirtualAddressSpace 메서드"
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
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: af80a43b86b1a16c5afe2741cb3d2bd7f0d874ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="513ed-102">IHostMemoryManager::AcquiredVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="513ed-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="513ed-103">공용 언어 런타임 (CLR)가 운영 체제에서 지정된 된 메모리를 확보 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="513ed-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="513ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="513ed-104">Syntax</span></span>  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="513ed-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="513ed-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="513ed-106">[in] 시작 주소는 메모리입니다.</span><span class="sxs-lookup"><span data-stu-id="513ed-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="513ed-107">[in] 메모리의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="513ed-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="513ed-108">설명</span><span class="sxs-lookup"><span data-stu-id="513ed-108">Remarks</span></span>  
 <span data-ttu-id="513ed-109">`AcquiredVirtualAddressSpace` 메서드는 콜백 메서드 및 호스팅 응용 프로그램의 작성자가 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="513ed-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="513ed-110">CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="513ed-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="513ed-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="513ed-111">Requirements</span></span>  
 <span data-ttu-id="513ed-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="513ed-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="513ed-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="513ed-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="513ed-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="513ed-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="513ed-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="513ed-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="513ed-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="513ed-116">See Also</span></span>  
 [<span data-ttu-id="513ed-117">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="513ed-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
