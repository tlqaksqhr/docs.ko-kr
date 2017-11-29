---
title: "ICorProfilerInfo2::GetNotifiedExceptionClauseInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3e5ad1742d6f714b53b109bb99fc288bccd4a3bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="011b2-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="011b2-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>
<span data-ttu-id="011b2-103">예외 절에 대 한 기본 주소 및 프레임 정보를 가져옵니다 (`catch`/`finally`/`filter`) 방금 실행 되거나 실행 하 려 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="011b2-103">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="011b2-104">구문</span><span class="sxs-lookup"><span data-stu-id="011b2-104">Syntax</span></span>  
  
```  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="011b2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="011b2-105">Parameters</span></span>  
 `pinfo`  
 <span data-ttu-id="011b2-106">[out] 에 대 한 포인터는 [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) 현재 예외 절 인스턴스 및 관련된 프레임에 설명 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="011b2-106">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="011b2-107">설명</span><span class="sxs-lookup"><span data-stu-id="011b2-107">Remarks</span></span>  
 <span data-ttu-id="011b2-108">예외 알림이 수신 되 면 `GetNotifiedExceptionClauseInfo` 예외 절에 대 한 기본 주소 및 프레임 정보를 가져오는 데 사용할 수 있습니다 (`catch`/`finally`/`filter`) (실행하려입니다[ Icorprofilercallback:: Exceptioncatcherenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [icorprofilercallback:: Exceptionunwindfinallyenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), 또는 [icorprofilercallback:: Exceptionsearchfilterenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)프로파일러 콜백 수신) 중이거나 방금 실행 ([icorprofilercallback:: Exceptioncatcherleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [icorprofilercallback:: Exceptionunwindfinallyleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), 또는 [ Icorprofilercallback:: Exceptionsearchfilterleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) 프로파일러 콜백 수신) 합니다.</span><span class="sxs-lookup"><span data-stu-id="011b2-108">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="011b2-109">일치 하는 Leave 콜백 수신 하거나 이런 경우의 해당 절에 대 한 Leave 알림이 없는 현재 절에 중첩 된 예외가 발생 될 때까지이 호출을 위의 Enter 콜백의 하나 후 언제 든 지 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="011b2-109">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="011b2-110">값이 되도록 이스케이프 throw 된 예외에 대 한 수 있다는 것에 유의 `filter` 이므로 항상 Leave 알림이 경우 예외 절입니다.</span><span class="sxs-lookup"><span data-stu-id="011b2-110">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="011b2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="011b2-111">Requirements</span></span>  
 <span data-ttu-id="011b2-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="011b2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="011b2-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="011b2-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="011b2-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="011b2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="011b2-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="011b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="011b2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="011b2-116">See Also</span></span>  
 [<span data-ttu-id="011b2-117">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="011b2-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="011b2-118">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="011b2-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
