---
title: "IHostMemoryManager::ReleasedVirtualAddressSpace 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.ReleasedVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6db2868405aadb5879241e12128c6db40c0a5c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="1bfbf-102">IHostMemoryManager::ReleasedVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="1bfbf-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="1bfbf-103">지정된 된 메모리를 사용 하 여 공용 언어 런타임 (CLR)가 완료 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1bfbf-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bfbf-104">구문</span><span class="sxs-lookup"><span data-stu-id="1bfbf-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1bfbf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1bfbf-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="1bfbf-106">[in] 메모리 해제를 시작 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1bfbf-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bfbf-107">설명</span><span class="sxs-lookup"><span data-stu-id="1bfbf-107">Remarks</span></span>  
 <span data-ttu-id="1bfbf-108">`ReleasedVirtualAddressSpace` 메서드는 콜백 메서드 및 호스팅 응용 프로그램의 작성자가 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bfbf-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="1bfbf-109">CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bfbf-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bfbf-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1bfbf-110">Requirements</span></span>  
 <span data-ttu-id="1bfbf-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1bfbf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bfbf-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1bfbf-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1bfbf-113">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1bfbf-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bfbf-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bfbf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfbf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bfbf-115">See Also</span></span>  
 [<span data-ttu-id="1bfbf-116">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1bfbf-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
