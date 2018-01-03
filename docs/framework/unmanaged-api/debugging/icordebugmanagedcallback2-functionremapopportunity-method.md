---
title: "ICorDebugManagedCallback2::FunctionRemapOpportunity 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 208803acea65b24429938dc646e7abe70949b237
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="15b85-102">ICorDebugManagedCallback2::FunctionRemapOpportunity 메서드</span><span class="sxs-lookup"><span data-stu-id="15b85-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="15b85-103">코드 실행 이전 버전의 편집된 된 함수에서 시퀀스 위치에 도달 했습니다 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="15b85-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15b85-104">구문</span><span class="sxs-lookup"><span data-stu-id="15b85-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15b85-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15b85-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="15b85-106">[in] 편집 된 함수를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="15b85-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="15b85-107">[in] 다시 매핑 중단점 만났습니다 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="15b85-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="15b85-108">[in] 현재 스레드에서 실행 중인 함수의 버전을 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="15b85-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="15b85-109">[in] 최신 버전의 함수를 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="15b85-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="15b85-110">[in] 이전 버전의 함수에 명령 포인터의 Microsoft MSIL (intermediate language) 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="15b85-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15b85-111">설명</span><span class="sxs-lookup"><span data-stu-id="15b85-111">Remarks</span></span>  
 <span data-ttu-id="15b85-112">이 콜백은 있도록 디버거를 호출 하 여 지정 된 함수의 새 버전에 적절 한 위치에 대 한 명령 포인터를 다시 매핑할 수는 [icordebugilframe2:: Remapfunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="15b85-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="15b85-113">디버거를 호출 하지 않는 경우 `RemapFunction` 호출 하기 전에 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 메서드를 런타임에서 계속 이전 코드를 실행 하 고 다른 트리거는 발생 `FunctionRemapOpportunity` 다음 시퀀스 위치에서 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="15b85-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="15b85-114">이 콜백은 디버거 하면 S_OK가 반환 될 때까지 이전 버전의 지정된 된 함수를 실행 하는 모든 프레임에 대 한 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15b85-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15b85-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15b85-115">Requirements</span></span>  
 <span data-ttu-id="15b85-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15b85-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15b85-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15b85-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15b85-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15b85-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15b85-119">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15b85-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15b85-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15b85-120">See Also</span></span>  
 [<span data-ttu-id="15b85-121">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15b85-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="15b85-122">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15b85-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
