---
title: "ICorDebugManagedCallback::UnloadModule 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UnloadModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 509206045164a35d9740c7369f8d7c90f1b2b0e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="9229a-102">ICorDebugManagedCallback::UnloadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="9229a-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="9229a-103">공용 언어 런타임 모듈 (DLL) 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9229a-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9229a-104">구문</span><span class="sxs-lookup"><span data-stu-id="9229a-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9229a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9229a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9229a-106">[in] 모듈을 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9229a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="9229a-107">[in] 모듈을 나타내는 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9229a-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9229a-108">설명</span><span class="sxs-lookup"><span data-stu-id="9229a-108">Remarks</span></span>  
 <span data-ttu-id="9229a-109">모듈이이 호출 후에 쓰일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9229a-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9229a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9229a-110">Requirements</span></span>  
 <span data-ttu-id="9229a-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9229a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9229a-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9229a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9229a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9229a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9229a-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9229a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9229a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9229a-115">See Also</span></span>  
 [<span data-ttu-id="9229a-116">LoadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="9229a-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)  
 [<span data-ttu-id="9229a-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9229a-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
