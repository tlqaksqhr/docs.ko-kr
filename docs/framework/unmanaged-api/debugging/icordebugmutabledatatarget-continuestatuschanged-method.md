---
title: ICorDebugMutableDataTarget::ContinueStatusChanged 메서드
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d2560aa484c6965047b2fdaf2c539b8ab675bc8
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207705"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="a0f68-102">ICorDebugMutableDataTarget::ContinueStatusChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="a0f68-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>
<span data-ttu-id="a0f68-103">지정된 스레드에서 해결되지 않은 디버그 이벤트의 연속 상태를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f68-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0f68-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0f68-104">Syntax</span></span>  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0f68-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a0f68-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="a0f68-106">운영 체제에서 정의된 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a0f68-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="a0f68-107">요청된 새 연속 상태를 나타내는 [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a0f68-107">A [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0f68-108">설명</span><span class="sxs-lookup"><span data-stu-id="a0f68-108">Remarks</span></span>  
 <span data-ttu-id="a0f68-109">디버거는 정상적일 경우 처리되는 방식과 다른 방식으로 현재 디버그 이벤트가 처리되도록 요구하는 ICorDebug 메서드를 호출할 때 `ContinueStatusChanged` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f68-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="a0f68-110">예를 들어 해결되지 않은 예외가 있고 디버거가 예외를 취소하는 작업(예: [ICorDebugILFrame::SetIP`FuncEval` 또는 ](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md))을 요청하는 경우 이 API는 예외가 취소되도록 요청하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0f68-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0f68-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0f68-111">Requirements</span></span>  
 <span data-ttu-id="a0f68-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0f68-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0f68-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0f68-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0f68-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0f68-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0f68-115">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0f68-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f68-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0f68-116">See Also</span></span>  
 [<span data-ttu-id="a0f68-117">ICorDebugMutableDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0f68-117">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="a0f68-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0f68-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
