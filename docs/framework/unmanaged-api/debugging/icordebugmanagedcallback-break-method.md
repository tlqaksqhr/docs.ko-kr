---
title: "ICorDebugManagedCallback::Break 메서드"
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
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1f9d3a39859d4e44bef2622d456ae0fbac233e7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="94ab2-102">ICorDebugManagedCallback::Break 메서드</span><span class="sxs-lookup"><span data-stu-id="94ab2-102">ICorDebugManagedCallback::Break Method</span></span>
<span data-ttu-id="94ab2-103">디버거에 알립니다 때는 <xref:System.Reflection.Emit.OpCodes.Break> 코드 스트림의 명령이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94ab2-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94ab2-104">구문</span><span class="sxs-lookup"><span data-stu-id="94ab2-104">Syntax</span></span>  
  
```  
HRESULT Break (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94ab2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94ab2-105">Parameters</span></span>  
 `pAppDOmain`  
 <span data-ttu-id="94ab2-106">[in] 중단 명령을 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="94ab2-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>  
  
 `thread`  
 <span data-ttu-id="94ab2-107">[in] Break 명령이 포함 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="94ab2-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94ab2-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94ab2-108">Requirements</span></span>  
 <span data-ttu-id="94ab2-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94ab2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94ab2-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94ab2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94ab2-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94ab2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94ab2-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94ab2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ab2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94ab2-113">See Also</span></span>  
 [<span data-ttu-id="94ab2-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94ab2-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
