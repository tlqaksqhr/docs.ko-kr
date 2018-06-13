---
title: COR_PRF_GC_GENERATION 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8283139566050b1858a003316dc46581822a9bbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450156"
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="11a99-102">COR_PRF_GC_GENERATION 열거형</span><span class="sxs-lookup"><span data-stu-id="11a99-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="11a99-103">가비지 수집 생성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a99-104">구문</span><span class="sxs-lookup"><span data-stu-id="11a99-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="11a99-105">멤버</span><span class="sxs-lookup"><span data-stu-id="11a99-105">Members</span></span>  
  
|<span data-ttu-id="11a99-106">멤버</span><span class="sxs-lookup"><span data-stu-id="11a99-106">Member</span></span>|<span data-ttu-id="11a99-107">설명</span><span class="sxs-lookup"><span data-stu-id="11a99-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="11a99-108">개체는 세대 0으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="11a99-109">개체는 세대 1로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="11a99-110">개체는 2 세대도 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="11a99-111">개체는 큰 개체 힙에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11a99-112">설명</span><span class="sxs-lookup"><span data-stu-id="11a99-112">Remarks</span></span>  
 <span data-ttu-id="11a99-113">가비지 수집기 나가에 따른 세대로 나눈 개체에서 메모리 관리 성능을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="11a99-114">가비지 수집기는 현재 0, 1, 2, 및 큰 개체에 사용 되는 특별 한 힙에 세그먼트 번호가 지정 된 세 가지 세대를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="11a99-115">특정 값 보다 큰 개체는 큰 개체 힙에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="11a99-116">0 세대에 속하는 다른 할당 된 개체를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="11a99-117">0 세대의 가비지 수집이 수행 된 후 존재 하는 모든 개체는 세대 1로 승격 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="11a99-118">1 세대에서 가비지 수집이 수행 된 후에 있는 개체는 2 세대를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="11a99-119">사용 되는 세대의 가비지 수집기는 한 번에 할당 된 개체의 하위 집합만 사용 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="11a99-120">`COR_PRF_GC_GENERATION` 열거형에서 사용 되는 [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a99-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11a99-121">Requirements</span></span>  
 <span data-ttu-id="11a99-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11a99-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a99-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="11a99-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="11a99-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11a99-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11a99-125">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a99-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a99-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11a99-126">See Also</span></span>  
 [<span data-ttu-id="11a99-127">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="11a99-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
