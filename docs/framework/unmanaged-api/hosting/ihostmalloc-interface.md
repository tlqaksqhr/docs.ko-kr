---
title: IHostMalloc 인터페이스
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbf889aaa6a78e67d0f08758adc0bf31cd932e88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441350"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="6935c-102">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6935c-102">IHostMalloc Interface</span></span>
<span data-ttu-id="6935c-103">공용 언어 런타임 (CLR)에서 호스트를 통해 힙의 세분화 된 할당을 요청을 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6935c-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6935c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="6935c-104">Methods</span></span>  
  
|<span data-ttu-id="6935c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6935c-105">Method</span></span>|<span data-ttu-id="6935c-106">설명</span><span class="sxs-lookup"><span data-stu-id="6935c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6935c-107">Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="6935c-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="6935c-108">호스트 힙에서 요청된 된 양의 메모리를 할당 하는 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6935c-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="6935c-109">DebugAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="6935c-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="6935c-110">호스트는 힙의 요청 된 양의 메모리를 할당 하 고 추가로 메모리 할당 된 추적 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="6935c-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="6935c-111">Free 메서드</span><span class="sxs-lookup"><span data-stu-id="6935c-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="6935c-112">사용 하 여 할당 된 메모리를 해제는 `Alloc` 메서드.</span><span class="sxs-lookup"><span data-stu-id="6935c-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6935c-113">설명</span><span class="sxs-lookup"><span data-stu-id="6935c-113">Remarks</span></span>  
 <span data-ttu-id="6935c-114">CLR에 대 한 인터페이스 포인터를 가져옵니다는 `IHostMalloc` 호출 하 여 인스턴스는 [ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6935c-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6935c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6935c-115">Requirements</span></span>  
 <span data-ttu-id="6935c-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6935c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6935c-117">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6935c-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6935c-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6935c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6935c-119">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6935c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6935c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6935c-120">See Also</span></span>  
 [<span data-ttu-id="6935c-121">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6935c-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="6935c-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6935c-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
