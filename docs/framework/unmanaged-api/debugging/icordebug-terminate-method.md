---
title: "ICorDebug::Terminate 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.Terminate
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e416f8ea20bde49a1c1cdb5d61bc4a6bfbce7913
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="5d68e-102">ICorDebug::Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="5d68e-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="5d68e-103">종료는 `ICorDebug` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5d68e-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d68e-104">`Terminate`호출 될 때까지 해서는 안는 [icordebugmanagedcallback:: Exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) 디버깅 중인 모든 프로세스에 대 한 콜백 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="5d68e-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d68e-105">구문</span><span class="sxs-lookup"><span data-stu-id="5d68e-105">Syntax</span></span>  
  
```  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5d68e-106">설명</span><span class="sxs-lookup"><span data-stu-id="5d68e-106">Remarks</span></span>  
 <span data-ttu-id="5d68e-107">`Terminate`호출 해야 합니다는 `ICorDebug` 개체가 더 이상 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d68e-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d68e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d68e-108">Requirements</span></span>  
 <span data-ttu-id="5d68e-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d68e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d68e-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d68e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d68e-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d68e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d68e-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d68e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d68e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d68e-113">See Also</span></span>  
 [<span data-ttu-id="5d68e-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d68e-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
