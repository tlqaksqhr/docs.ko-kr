---
title: "COR_PRF_FUNCTION 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION
helpviewer_keywords: COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4b8ca316814b6f4df8792d068bea36d499b77374
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corprffunction-structure"></a><span data-ttu-id="d7e94-102">COR_PRF_FUNCTION 구조체</span><span class="sxs-lookup"><span data-stu-id="d7e94-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="d7e94-103">함수의 ID와 다시 컴파일된 함수 버전의 ID를 결합하여 함수의 고유한 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e94-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e94-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7e94-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="d7e94-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d7e94-105">Members</span></span>  
  
|<span data-ttu-id="d7e94-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d7e94-106">Member</span></span>|<span data-ttu-id="d7e94-107">설명</span><span class="sxs-lookup"><span data-stu-id="d7e94-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="d7e94-108">함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e94-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="d7e94-109">다시 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e94-109">The ID of the recompiled function.</span></span> <span data-ttu-id="d7e94-110">값이 0 (영) 함수의 원래 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d7e94-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7e94-111">설명</span><span class="sxs-lookup"><span data-stu-id="d7e94-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7e94-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7e94-112">Requirements</span></span>  
 <span data-ttu-id="d7e94-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e94-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7e94-114">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="d7e94-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d7e94-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7e94-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7e94-116">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7e94-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e94-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7e94-117">See Also</span></span>  
 [<span data-ttu-id="d7e94-118">프로 파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="d7e94-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
