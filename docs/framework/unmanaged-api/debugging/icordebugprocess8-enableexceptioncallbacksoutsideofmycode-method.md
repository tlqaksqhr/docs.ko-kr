---
title: "ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e7de3622498e8417a961e0d4708c53527a833ef2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="ae9ce-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드</span><span class="sxs-lookup"><span data-stu-id="ae9ce-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="ae9ce-103">[[!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="ae9ce-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="ae9ce-104">특정 유형의 사용할지 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9ce-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae9ce-105">구문</span><span class="sxs-lookup"><span data-stu-id="ae9ce-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae9ce-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae9ce-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="ae9ce-107">[in]</span><span class="sxs-lookup"><span data-stu-id="ae9ce-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae9ce-108">설명</span><span class="sxs-lookup"><span data-stu-id="ae9ce-108">Remarks</span></span>  
 <span data-ttu-id="ae9ce-109">`enableExceptionsOutsideOfJMC`의 값이 `false`인 경우:</span><span class="sxs-lookup"><span data-stu-id="ae9ce-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
-   <span data-ttu-id="ae9ce-110">DEBUG_EXCEPTION_FIRST_CHANCE 예외 디버거 콜백이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae9ce-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
-   <span data-ttu-id="ae9ce-111">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 예외가 발생 하지 것입니다 콜백에서 디버거는 예외가 사용자 코드로 이스케이프 되지 않는 경우 (즉, 예외 출처에서에서 예외 처리기로의 경로 JustMyCode 또는 JMC로 표시 된 메서드가 없음).</span><span class="sxs-lookup"><span data-stu-id="ae9ce-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="ae9ce-112">`enableExceptionsOutsideOfJMC`의 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9ce-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae9ce-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae9ce-113">Requirements</span></span>  
 <span data-ttu-id="ae9ce-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9ce-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae9ce-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae9ce-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae9ce-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae9ce-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae9ce-117">**.NET framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae9ce-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9ce-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae9ce-118">See Also</span></span>  
 [<span data-ttu-id="ae9ce-119">ICorDebugProcess8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae9ce-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 [<span data-ttu-id="ae9ce-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae9ce-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
