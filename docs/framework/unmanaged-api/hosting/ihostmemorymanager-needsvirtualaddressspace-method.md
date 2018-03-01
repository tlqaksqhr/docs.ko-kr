---
title: "IHostMemoryManager::NeedsVirtualAddressSpace 메서드"
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
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9251cbadaf182cda8d52f3f5792452310561c376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="9b4be-102">IHostMemoryManager::NeedsVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="9b4be-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="9b4be-103">공용 언어 런타임 (CLR)이 지정 된 메모리 사용을 시도 하려는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9b4be-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b4be-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b4be-104">Syntax</span></span>  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b4be-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b4be-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="9b4be-106">[in] 시작 주소는 메모리입니다.</span><span class="sxs-lookup"><span data-stu-id="9b4be-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="9b4be-107">[in] 메모리의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9b4be-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b4be-108">설명</span><span class="sxs-lookup"><span data-stu-id="9b4be-108">Remarks</span></span>  
 <span data-ttu-id="9b4be-109">`NeedsVirtualAddressSpace` 메서드는 콜백 메서드 및 호스팅 응용 프로그램의 작성자가 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4be-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="9b4be-110">CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b4be-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="9b4be-111">호스트에서 지정된 된 메모리를 사용 하는 CLR을 원하지 않을 경우 E_OUTOFMEMORY HRESULT를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b4be-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b4be-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b4be-112">Requirements</span></span>  
 <span data-ttu-id="9b4be-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b4be-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b4be-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9b4be-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b4be-115">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9b4be-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b4be-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b4be-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b4be-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b4be-117">See Also</span></span>  
 [<span data-ttu-id="9b4be-118">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b4be-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
