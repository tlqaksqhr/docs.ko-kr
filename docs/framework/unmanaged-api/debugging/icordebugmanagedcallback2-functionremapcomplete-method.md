---
title: "ICorDebugManagedCallback2::FunctionRemapComplete 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.FunctionRemapComplete
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cee712c2ff8acf56049ca9e288fad21e4608da3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="ac930-102">ICorDebugManagedCallback2::FunctionRemapComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="ac930-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="ac930-103">편집 된 함수의 새 버전으로 코드 실행이 전환 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ac930-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac930-104">구문</span><span class="sxs-lookup"><span data-stu-id="ac930-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac930-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac930-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ac930-106">[in] 편집 된 함수를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac930-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ac930-107">[in] 다시 매핑 중단점 만났습니다 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac930-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="ac930-108">[in] 현재 스레드에서 실행 하는 함수의 버전을 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac930-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac930-109">설명</span><span class="sxs-lookup"><span data-stu-id="ac930-109">Remarks</span></span>  
 <span data-ttu-id="ac930-110">이 콜백은 스텝 이미 존재 하는 다시 만들 수 있는 디버거를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac930-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac930-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac930-111">Requirements</span></span>  
 <span data-ttu-id="ac930-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac930-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac930-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac930-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac930-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac930-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac930-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac930-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac930-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac930-116">See Also</span></span>  
 [<span data-ttu-id="ac930-117">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac930-117">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="ac930-118">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac930-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
