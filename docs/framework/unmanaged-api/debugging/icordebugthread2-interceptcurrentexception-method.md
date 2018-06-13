---
title: ICorDebugThread2::InterceptCurrentException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f417fcd001d9e442ae518dbcd9df26eecb6efae9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421976"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="9326f-102">ICorDebugThread2::InterceptCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="9326f-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="9326f-103">디버거에서를이 스레드에서 현재 예외를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9326f-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9326f-104">구문</span><span class="sxs-lookup"><span data-stu-id="9326f-104">Syntax</span></span>  
  
```  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9326f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9326f-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="9326f-106">[in] 활성 스택 프레임을 나타내는 ICorDebugFrame에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9326f-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9326f-107">설명</span><span class="sxs-lookup"><span data-stu-id="9326f-107">Remarks</span></span>  
 <span data-ttu-id="9326f-108">`InterceptCurrentException` 예외 콜백 간에 메서드를 호출할 수 있습니다 ([icordebugmanagedcallback:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) 또는 [icordebugmanagedcallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md))와 연관 된 호출을 [Icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9326f-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9326f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9326f-109">Requirements</span></span>  
 <span data-ttu-id="9326f-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9326f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9326f-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9326f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9326f-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9326f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9326f-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9326f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
