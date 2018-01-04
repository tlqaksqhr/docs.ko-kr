---
title: "ICorDebugModuleBreakpoint::GetModule 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleBreakpoint.GetModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 91e014a16420ea6790b592efe1ac57df960d2237
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="f89b3-102">ICorDebugModuleBreakpoint::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="f89b3-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="f89b3-103">"ICorDebugModule"이이 중단점이 설정 된 모듈을 참조 하는 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f89b3-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f89b3-104">구문</span><span class="sxs-lookup"><span data-stu-id="f89b3-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f89b3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f89b3-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="f89b3-106">[out] 주소에 대 한 포인터는 `ICorDebugModule` 중단점이 설정 되어 있는 모듈을 참조 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f89b3-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f89b3-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f89b3-107">Requirements</span></span>  
 <span data-ttu-id="f89b3-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f89b3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f89b3-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f89b3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f89b3-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f89b3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f89b3-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f89b3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f89b3-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f89b3-112">See Also</span></span>  
 
