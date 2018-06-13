---
title: COR_PRF_FUNCTION_ARGUMENT_INFO 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fbc41ca1366b412c37d6af09e90e3f1b042ba21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449987"
---
# <a name="corprffunctionargumentinfo-structure"></a><span data-ttu-id="41438-102">COR_PRF_FUNCTION_ARGUMENT_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="41438-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="41438-103">왼쪽에서 오른쪽 순서의 함수 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="41438-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41438-104">구문</span><span class="sxs-lookup"><span data-stu-id="41438-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="41438-105">멤버</span><span class="sxs-lookup"><span data-stu-id="41438-105">Members</span></span>  
  
|<span data-ttu-id="41438-106">멤버</span><span class="sxs-lookup"><span data-stu-id="41438-106">Member</span></span>|<span data-ttu-id="41438-107">설명</span><span class="sxs-lookup"><span data-stu-id="41438-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="41438-108">인수는 블록의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="41438-108">The number of blocks of arguments.</span></span> <span data-ttu-id="41438-109">즉,이 값은 수가 [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) 구조체에 `ranges` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="41438-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="41438-110">모든 인수의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="41438-110">The total size of all arguments.</span></span> <span data-ttu-id="41438-111">즉,이 값은 인수 길이 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="41438-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="41438-112">배열 `COR_PRF_FUNCTION_ARGUMENT_RANGE` 구조를 각각 한 함수 인수 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="41438-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41438-113">설명</span><span class="sxs-lookup"><span data-stu-id="41438-113">Remarks</span></span>  
 <span data-ttu-id="41438-114">함수는 많은 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41438-114">A function may have many arguments.</span></span> <span data-ttu-id="41438-115">메모리에 연속적으로 이러한 인수를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41438-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="41438-116">블록을 한 곳에 세 개의 인수, 다른 위치에서 두 개의 인수 블록 및 다른 위치에 한 인수의 마지막 블록을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41438-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="41438-117">이 인수는 모두 동일한 함수;에 대 한 방금 서로 다른 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="41438-118">`COR_PRF_FUNCTION_ARGUMENT_INFO` 구조 단일 함수의 모든 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="41438-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="41438-119">함수 인수 블록을 모두 참조 하는 배열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="41438-120">따라서 단일 있는 단일 함수에 대 한 `COR_PRF_FUNCTION_ARGUMENT_INFO` 여러 참조 하는 구조 `COR_PRF_FUNCTION_ARGUMENT_RANGE` 구조에는 각각 하나 이상의 함수 인수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="41438-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="41438-121">레지스터에 저장 된 인수는 구조체를 메모리로 넘어가 합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41438-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41438-122">Requirements</span></span>  
 <span data-ttu-id="41438-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41438-124">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="41438-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="41438-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41438-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41438-126">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41438-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41438-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41438-127">See Also</span></span>  
 [<span data-ttu-id="41438-128">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="41438-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
