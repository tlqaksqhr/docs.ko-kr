---
title: "ICorDebugManagedCallback::UnloadAssembly 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UnloadAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29400e5bda2a17c731cb33e67c0123cffc89c48b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="fb547-102">ICorDebugManagedCallback::UnloadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="fb547-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="fb547-103">공용 언어 런타임 어셈블리 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fb547-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb547-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb547-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb547-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb547-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fb547-106">[in] 어셈블리를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb547-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="fb547-107">[in] 어셈블리를 나타내는 ICorDebugAssembly 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb547-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb547-108">설명</span><span class="sxs-lookup"><span data-stu-id="fb547-108">Remarks</span></span>  
 <span data-ttu-id="fb547-109">이 콜백은 후 어셈블리를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb547-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb547-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb547-110">Requirements</span></span>  
 <span data-ttu-id="fb547-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb547-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb547-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb547-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb547-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb547-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb547-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb547-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb547-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb547-115">See Also</span></span>  
 [<span data-ttu-id="fb547-116">LoadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="fb547-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)  
 [<span data-ttu-id="fb547-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb547-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
