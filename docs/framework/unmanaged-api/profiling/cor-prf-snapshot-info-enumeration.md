---
title: "COR_PRF_SNAPSHOT_INFO 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_SNAPSHOT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_SNAPSHOT_INFO
helpviewer_keywords: COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9c854360881426f2fc7fc9e401da1dc93b9bd84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="58538-102">COR_PRF_SNAPSHOT_INFO 열거형</span><span class="sxs-lookup"><span data-stu-id="58538-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="58538-103">프로파일러를 호출할 때마다 스택 스냅숏과 함께 다시 전달할 데이터 양을 지정 [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="58538-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58538-104">구문</span><span class="sxs-lookup"><span data-stu-id="58538-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="58538-105">멤버</span><span class="sxs-lookup"><span data-stu-id="58538-105">Members</span></span>  
  
|<span data-ttu-id="58538-106">멤버</span><span class="sxs-lookup"><span data-stu-id="58538-106">Members</span></span>|<span data-ttu-id="58538-107">설명</span><span class="sxs-lookup"><span data-stu-id="58538-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="58538-108">모든 값을 전달 해야 나타냅니다 `StackSnapshotCallback` 매개 변수를 제외 하 고는 `context` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="58538-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="58538-109">모든 값을 전달 해야 나타냅니다 `StackSnapshotCallback` 매개 변수를 포함 하는 `context` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="58538-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="58538-110">스택 워크 간단 하 고 대체 알고리즘 사용될지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="58538-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58538-111">설명</span><span class="sxs-lookup"><span data-stu-id="58538-111">Remarks</span></span>  
 <span data-ttu-id="58538-112">제공 되는 값은 `COR_PRF_SNAPSHOT_INFO` 열거형에 매개 변수로 전달 되는 [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="58538-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58538-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58538-113">Requirements</span></span>  
 <span data-ttu-id="58538-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58538-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58538-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58538-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58538-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58538-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58538-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58538-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58538-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58538-118">See Also</span></span>  
 [<span data-ttu-id="58538-119">DoStackSnapshot 메서드</span><span class="sxs-lookup"><span data-stu-id="58538-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [<span data-ttu-id="58538-120">프로 파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="58538-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
