---
title: "ICorDebugCode3 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode3
helpviewer_keywords: ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ee60d052c65df64b1a753166b301ba0012cdc8e4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="e0e3d-102">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0e3d-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="e0e3d-103">확장 "ICorDebugCode" 및 "ICorDebugCode2" 관리 되는 반환 값에 대 한 정보를 제공 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e3d-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0e3d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e0e3d-104">Methods</span></span>  
  
|<span data-ttu-id="e0e3d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e0e3d-105">Method</span></span>|<span data-ttu-id="e0e3d-106">설명</span><span class="sxs-lookup"><span data-stu-id="e0e3d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0e3d-107">GetReturnValueLiveOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="e0e3d-107">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="e0e3d-108">지정된 된 IL 오프셋에 대 한 디버거 함수에서 반환 값을 가져올 수 있도록 중단점을 배치할 위치 네이티브 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0e3d-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0e3d-109">설명</span><span class="sxs-lookup"><span data-stu-id="e0e3d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0e3d-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e3d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0e3d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0e3d-111">Requirements</span></span>  
 <span data-ttu-id="e0e3d-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e3d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0e3d-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0e3d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0e3d-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0e3d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0e3d-115">**.NET framework 버전:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0e3d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e3d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0e3d-116">See Also</span></span>  
    
    
    
 [<span data-ttu-id="e0e3d-117">ICorDebugILFrame3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0e3d-117">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 [<span data-ttu-id="e0e3d-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0e3d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
