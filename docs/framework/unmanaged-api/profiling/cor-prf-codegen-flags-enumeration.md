---
title: "COR_PRF_CODEGEN_FLAGS 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_CODEGEN_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_CODEGEN_FLAGS
helpviewer_keywords: COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6fc50330b31e8b0f8def24aaafbf3a4b7e365e98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="70f54-102">COR_PRF_CODEGEN_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="70f54-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="70f54-103">으로 설정할 수 있는 코드 생성 플래그를 정의 고 [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="70f54-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70f54-104">구문</span><span class="sxs-lookup"><span data-stu-id="70f54-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="70f54-105">멤버</span><span class="sxs-lookup"><span data-stu-id="70f54-105">Members</span></span>  
  
|<span data-ttu-id="70f54-106">멤버</span><span class="sxs-lookup"><span data-stu-id="70f54-106">Member</span></span>|<span data-ttu-id="70f54-107">설명</span><span class="sxs-lookup"><span data-stu-id="70f54-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="70f54-108">함수가 없는이 함수 본문으로 인라인 처리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70f54-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="70f54-109">그러나 함수 자체의 호출자에 인라인 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f54-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="70f54-110">이 함수 본문에 대 한 모든 최적화를 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f54-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="70f54-111">그러나 함수 자체 수 여전히 인라인 처리할 수의 호출자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70f54-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70f54-112">설명</span><span class="sxs-lookup"><span data-stu-id="70f54-112">Remarks</span></span>  
 <span data-ttu-id="70f54-113">`COR_PRF_CODEGEN_FLAGS` 열거형에서 사용 되는 [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) 메서드 프로파일러는 JIT 다시 컴파일된 함수에 대 한 코드 생성을 제어를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f54-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70f54-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70f54-114">Requirements</span></span>  
 <span data-ttu-id="70f54-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70f54-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70f54-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70f54-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70f54-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70f54-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70f54-118">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70f54-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f54-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70f54-119">See Also</span></span>  
 [<span data-ttu-id="70f54-120">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="70f54-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
