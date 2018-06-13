---
title: ICorDebugMutableDataTarget::ContinueStatusChanged 메서드
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb07c519743c41a7a31994e42d2fdc5220e5e2ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418213"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="3860a-102">ICorDebugMutableDataTarget::ContinueStatusChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="3860a-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>
<span data-ttu-id="3860a-103">지정된 스레드에서 해결되지 않은 디버그 이벤트의 연속 상태를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3860a-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3860a-104">구문</span><span class="sxs-lookup"><span data-stu-id="3860a-104">Syntax</span></span>  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3860a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3860a-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="3860a-106">운영 체제에서 정의된 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="3860a-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="3860a-107">A[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)요청한 연속 상태를 나타내는 새 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3860a-107">A[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3860a-108">설명</span><span class="sxs-lookup"><span data-stu-id="3860a-108">Remarks</span></span>  
 <span data-ttu-id="3860a-109">디버거는 정상적일 경우 처리되는 방식과 다른 방식으로 현재 디버그 이벤트가 처리되도록 요구하는 ICorDebug 메서드를 호출할 때 `ContinueStatusChanged` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3860a-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="3860a-110">예를 들어, 해결 되지 않은 예외가 있고 디버거가 예외를 취소 하는 작업을 요청 하는 경우 (같은 [icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) 또는 `FuncEval`),이 API를 사용 하는 예외 되도록 요청 취소 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3860a-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3860a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3860a-111">Requirements</span></span>  
 <span data-ttu-id="3860a-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3860a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3860a-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3860a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3860a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3860a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3860a-115">**.NET framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3860a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3860a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3860a-116">See Also</span></span>  
 [<span data-ttu-id="3860a-117">ICorDebugMutableDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3860a-117">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="3860a-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3860a-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
