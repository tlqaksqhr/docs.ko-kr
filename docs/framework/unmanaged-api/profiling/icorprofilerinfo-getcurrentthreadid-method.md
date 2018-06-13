---
title: ICorProfilerInfo::GetCurrentThreadID 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89f7ff2c213dc510268f9e6c802813a48e870d99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453858"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="acc9a-102">ICorProfilerInfo::GetCurrentThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="acc9a-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="acc9a-103">관리 되는 스레드 이면 현재 스레드의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="acc9a-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acc9a-104">구문</span><span class="sxs-lookup"><span data-stu-id="acc9a-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="acc9a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="acc9a-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="acc9a-106">[out] 관리 되는 스레드의 반환된 된 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="acc9a-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acc9a-107">설명</span><span class="sxs-lookup"><span data-stu-id="acc9a-107">Remarks</span></span>  
 <span data-ttu-id="acc9a-108">내부 런타임 스레드에서 또는 다른 관리 되지 않는 스레드가 현재 스레드가 경우 `GetCurrentThreadID` CORPROF_E_NOT_MANAGED_THREAD HRESULT, 및의 반환된 된 값으로 반환 된 `pThreadId` 매개 변수는 null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acc9a-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acc9a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="acc9a-109">Requirements</span></span>  
 <span data-ttu-id="acc9a-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="acc9a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acc9a-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="acc9a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="acc9a-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acc9a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acc9a-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acc9a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acc9a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acc9a-114">See Also</span></span>  
 [<span data-ttu-id="acc9a-115">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acc9a-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
