---
title: "COR_PRF_FINALIZER_FLAGS 열거형"
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
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae0941e962b2fc1b08f0defb692038bd5fcf885a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="93d77-102">COR_PRF_FINALIZER_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="93d77-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="93d77-103">개체에 대한 종료자를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93d77-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93d77-104">구문</span><span class="sxs-lookup"><span data-stu-id="93d77-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="93d77-105">멤버</span><span class="sxs-lookup"><span data-stu-id="93d77-105">Members</span></span>  
  
|<span data-ttu-id="93d77-106">멤버</span><span class="sxs-lookup"><span data-stu-id="93d77-106">Member</span></span>|<span data-ttu-id="93d77-107">설명</span><span class="sxs-lookup"><span data-stu-id="93d77-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="93d77-108">종료자는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="93d77-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93d77-109">설명</span><span class="sxs-lookup"><span data-stu-id="93d77-109">Remarks</span></span>  
 <span data-ttu-id="93d77-110">`COR_PRF_FINALIZER_FLAGS` 열거형에서 사용 되는 [icorprofilercallback2:: Finalizeableobjectqueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) 개체에 대 한 종료자를 설명 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="93d77-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93d77-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93d77-111">Requirements</span></span>  
 <span data-ttu-id="93d77-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="93d77-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93d77-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="93d77-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="93d77-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93d77-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93d77-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93d77-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d77-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93d77-116">See Also</span></span>  
 [<span data-ttu-id="93d77-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="93d77-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
