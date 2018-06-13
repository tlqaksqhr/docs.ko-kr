---
title: ICorDebugILFrame2::RemapFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f03d8c993be1ac83ca84275bcb94f1bb3cdf884
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414985"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="d06b7-102">ICorDebugILFrame2::RemapFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="d06b7-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="d06b7-103">새 Microsoft MSIL (intermediate language) 오프셋을 지정 하 여 편집된 된 함수를 다시 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d06b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="d06b7-104">Syntax</span></span>  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d06b7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d06b7-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="d06b7-106">[in] 스택 프레임의 새로운 MSIL 오프셋 명령 포인터를 배치할입니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="d06b7-107">이 값은 시퀀스 위치 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="d06b7-108">호출자의이 값의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="d06b7-109">예를 들어 MSIL 오프셋 함수 범위 바깥쪽 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d06b7-110">설명</span><span class="sxs-lookup"><span data-stu-id="d06b7-110">Remarks</span></span>  
 <span data-ttu-id="d06b7-111">프레임의 함수가 편집 되어, 디버거를 호출할 수는 `RemapFunction` 메서드를 실행할 수 있도록 최신 버전의 프레임의 함수에서 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="d06b7-112">코드 실행은 지정된 된 MSIL 오프셋에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d06b7-113">호출 `RemapFunction`처럼 호출 [icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), 관련 된 스레드에 대 한 스택 추적을 생성 하는 모든 디버깅 인터페이스를 즉시 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="d06b7-114">이러한 인터페이스 [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, 및 ICorDebugNativeFrame 합니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="d06b7-115">`RemapFunction` 메서드는 현재 프레임의 컨텍스트에서 하 고 하나는 다음과 같은 경우에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
-   <span data-ttu-id="d06b7-116">받은 후는 [icordebugmanagedcallback2:: Functionremapopportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) 계속 하지 아직 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
-   <span data-ttu-id="d06b7-117">때문에 코드 실행을 중지 하는 동안는 [icordebugmanagedcallback:: Editandcontinueremap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) 이 프레임에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d06b7-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d06b7-118">Requirements</span></span>  
 <span data-ttu-id="d06b7-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d06b7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d06b7-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d06b7-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d06b7-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d06b7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d06b7-122">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d06b7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
