---
title: ICorDebugManagedCallback::EvalException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4414bab535b63f55a580e93cc6de9cb0dedc073c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415518"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="cd627-102">ICorDebugManagedCallback::EvalException 메서드</span><span class="sxs-lookup"><span data-stu-id="cd627-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="cd627-103">계산이 처리 되지 않은 예외와 함께 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cd627-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd627-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd627-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd627-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd627-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="cd627-106">[in] 평가를 종료 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd627-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="cd627-107">[in] 평가 종료 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd627-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="cd627-108">[in] 평가 수행 하는 코드를 나타내는 ICorDebugEval 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd627-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd627-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd627-109">Requirements</span></span>  
 <span data-ttu-id="cd627-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd627-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd627-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd627-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd627-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd627-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd627-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd627-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd627-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd627-114">See Also</span></span>  
 [<span data-ttu-id="cd627-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd627-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
