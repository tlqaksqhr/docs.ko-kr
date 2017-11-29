---
title: "ICLRGCManager2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2
helpviewer_keywords: ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b025ec31e3797fec3ac184929f1274cb5f68501b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="6bd41-102">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bd41-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="6bd41-103">공용 언어 런타임의 가비지 수집 시스템과 상호 작용 하는 데 사용 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd41-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6bd41-104">메서드</span><span class="sxs-lookup"><span data-stu-id="6bd41-104">Methods</span></span>  
  
|<span data-ttu-id="6bd41-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6bd41-105">Method</span></span>|<span data-ttu-id="6bd41-106">설명</span><span class="sxs-lookup"><span data-stu-id="6bd41-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6bd41-107">SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="6bd41-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="6bd41-108">가비지 수집 세그먼트의 크기와 0 세대 가비지 수집 시스템의 최대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd41-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="6bd41-109">0 세대 및 세그먼트 크기 보다 큰 수 있도록 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd41-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bd41-110">설명</span><span class="sxs-lookup"><span data-stu-id="6bd41-110">Remarks</span></span>  
 <span data-ttu-id="6bd41-111">이 인터페이스에서 상속 된 [ICLRGCManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd41-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="6bd41-112">관리 되는 가비지 수집 메커니즘을 구현 하는 공용 언어 런타임 (CLR) <xref:System.GC> 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd41-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="6bd41-113">가비지 수집 시스템에 대 한 자세한 내용은 참조 [가비지 수집](../../../../docs/standard/garbage-collection/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd41-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bd41-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6bd41-114">Requirements</span></span>  
 <span data-ttu-id="6bd41-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd41-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bd41-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6bd41-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6bd41-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6bd41-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bd41-118">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bd41-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd41-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bd41-119">See Also</span></span>  
 [<span data-ttu-id="6bd41-120">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="6bd41-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="6bd41-121">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="6bd41-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="6bd41-122">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bd41-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="6bd41-123">4 및 4.5.NET Framework에 추가 된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bd41-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="6bd41-124">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bd41-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="6bd41-125">호스팅</span><span class="sxs-lookup"><span data-stu-id="6bd41-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
