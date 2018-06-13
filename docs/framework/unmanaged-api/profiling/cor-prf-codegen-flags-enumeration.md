---
title: COR_PRF_CODEGEN_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab5612a2bb48b2cc93e0150f45107e474a4e6217
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452119"
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="76bff-102">COR_PRF_CODEGEN_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="76bff-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="76bff-103">으로 설정할 수 있는 코드 생성 플래그를 정의 고 [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="76bff-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76bff-104">구문</span><span class="sxs-lookup"><span data-stu-id="76bff-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="76bff-105">멤버</span><span class="sxs-lookup"><span data-stu-id="76bff-105">Members</span></span>  
  
|<span data-ttu-id="76bff-106">멤버</span><span class="sxs-lookup"><span data-stu-id="76bff-106">Member</span></span>|<span data-ttu-id="76bff-107">설명</span><span class="sxs-lookup"><span data-stu-id="76bff-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="76bff-108">함수가 없는이 함수 본문으로 인라인 처리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76bff-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="76bff-109">그러나 함수 자체의 호출자에 인라인 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76bff-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="76bff-110">이 함수 본문에 대 한 모든 최적화를 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76bff-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="76bff-111">그러나 함수 자체 수 여전히 인라인 처리할 수의 호출자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76bff-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76bff-112">설명</span><span class="sxs-lookup"><span data-stu-id="76bff-112">Remarks</span></span>  
 <span data-ttu-id="76bff-113">`COR_PRF_CODEGEN_FLAGS` 열거형에서 사용 되는 [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) 메서드 프로파일러는 JIT 다시 컴파일된 함수에 대 한 코드 생성을 제어를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="76bff-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76bff-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76bff-114">Requirements</span></span>  
 <span data-ttu-id="76bff-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="76bff-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76bff-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="76bff-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="76bff-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76bff-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76bff-118">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76bff-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76bff-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76bff-119">See Also</span></span>  
 [<span data-ttu-id="76bff-120">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="76bff-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
