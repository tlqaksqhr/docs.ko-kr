---
title: IGCHost::GetStats 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3e0d6f68ffa5280d4616d4fa4ac60b4cb86f6a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437767"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="1fbe6-102">IGCHost::GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="1fbe6-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="1fbe6-103">가비지 수집 시스템의 현재 상태에 대 한 통계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1fbe6-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fbe6-104">구문</span><span class="sxs-lookup"><span data-stu-id="1fbe6-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1fbe6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1fbe6-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="1fbe6-106">[out에서] 에 대 한 포인터는 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) 가비지 수집 시스템의 현재 상태에 대 한 통계를 포함 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="1fbe6-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fbe6-107">설명</span><span class="sxs-lookup"><span data-stu-id="1fbe6-107">Remarks</span></span>  
 <span data-ttu-id="1fbe6-108">통계는 가비지 수집 시스템의 작업을 위해 스마트 할당 시스템에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbe6-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="1fbe6-109">예를 들어 더 많은 메모리를 추가 하거나 컬렉션을 강제 적용 하는 데 필요한 통계를 검토 한 후 할당 시스템 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fbe6-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fbe6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1fbe6-110">Requirements</span></span>  
 <span data-ttu-id="1fbe6-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1fbe6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fbe6-112">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="1fbe6-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="1fbe6-113">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1fbe6-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1fbe6-114">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fbe6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fbe6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1fbe6-115">See Also</span></span>  
 [<span data-ttu-id="1fbe6-116">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fbe6-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
