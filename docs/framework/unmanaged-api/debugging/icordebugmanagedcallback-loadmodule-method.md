---
title: "ICorDebugManagedCallback::LoadModule 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LoadModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d17001db68043f5d46a90738a8ad3e0635de762
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="99679-102">ICorDebugManagedCallback::LoadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="99679-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="99679-103">공용 언어 런타임 (CLR) 모듈 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="99679-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99679-104">구문</span><span class="sxs-lookup"><span data-stu-id="99679-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99679-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99679-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="99679-106">[in] 모듈 로드 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99679-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="99679-107">[in] CLR 모듈을 나타내는 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99679-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99679-108">설명</span><span class="sxs-lookup"><span data-stu-id="99679-108">Remarks</span></span>  
 <span data-ttu-id="99679-109">`LoadModule` 콜백 모듈에 대 한 메타 데이터를 검사 또는, 적시에 (JIT) 컴파일러 플래그를 설정 하거나 사용 모듈에 대 한 콜백을 로드 하는 클래스를 사용 하지 않도록 설정 하려면 적절 한 시간을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99679-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99679-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99679-110">Requirements</span></span>  
 <span data-ttu-id="99679-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="99679-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99679-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99679-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99679-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99679-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99679-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99679-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99679-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99679-115">See Also</span></span>  
 [<span data-ttu-id="99679-116">UnloadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="99679-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)  
 [<span data-ttu-id="99679-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99679-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
