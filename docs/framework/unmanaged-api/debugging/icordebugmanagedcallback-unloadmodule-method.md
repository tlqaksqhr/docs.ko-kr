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
ms.workload: dotnet
ms.openlocfilehash: 7aeb3f12d5217c57d8d8f1f5665840a4515c0998
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="9cce9-102">ICorDebugManagedCallback::UnloadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="9cce9-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="9cce9-103">공용 언어 런타임 모듈 (DLL) 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9cce9-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cce9-104">구문</span><span class="sxs-lookup"><span data-stu-id="9cce9-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cce9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9cce9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9cce9-106">[in] 모듈을 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9cce9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="9cce9-107">[in] 모듈을 나타내는 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9cce9-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cce9-108">설명</span><span class="sxs-lookup"><span data-stu-id="9cce9-108">Remarks</span></span>  
 <span data-ttu-id="9cce9-109">모듈이이 호출 후에 쓰일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9cce9-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cce9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9cce9-110">Requirements</span></span>  
 <span data-ttu-id="9cce9-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9cce9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cce9-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cce9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cce9-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cce9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cce9-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cce9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cce9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cce9-115">See Also</span></span>  
 [<span data-ttu-id="9cce9-116">LoadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="9cce9-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)  
 [<span data-ttu-id="9cce9-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cce9-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
