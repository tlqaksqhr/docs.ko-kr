---
title: "ICorProfilerInfo::GetThreadContext 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetThreadContext
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 630236e6f20b61d4a73bcb26a61112151a8ed80c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="b03b6-102">ICorProfilerInfo::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="b03b6-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="b03b6-103">현재 스레드와 연결 된 지정 된 컨텍스트 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b03b6-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b03b6-104">구문</span><span class="sxs-lookup"><span data-stu-id="b03b6-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b03b6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b03b6-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b03b6-106">[in] 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b03b6-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="b03b6-107">[out] 현재 스레드와 연결 된 지정 된 컨텍스트 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b03b6-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="b03b6-108">스레드가 현재 연결 된 컨텍스트가,이 함수는 CORPROF_E_DATAINCOMPLETE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03b6-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b03b6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b03b6-109">Requirements</span></span>  
 <span data-ttu-id="b03b6-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b03b6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b03b6-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b03b6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b03b6-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b03b6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b03b6-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b03b6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03b6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b03b6-114">See Also</span></span>  
 [<span data-ttu-id="b03b6-115">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b03b6-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
