---
title: "ICorProfilerCallback::ExceptionSearchFilterEnter 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ExceptionSearchFilterEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8196b9393a96619c17fa2771e3481cd47aafd4b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="b3710-102">ICorProfilerCallback::ExceptionSearchFilterEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="b3710-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="b3710-103">예외 처리의 검색 단계는 사용자 정의 예외 필터를 실행을 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b3710-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3710-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3710-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3710-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3710-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="b3710-106">[in] 필터를 포함 하는 함수의의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3710-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3710-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3710-107">Requirements</span></span>  
 <span data-ttu-id="b3710-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3710-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3710-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3710-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3710-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3710-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3710-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3710-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3710-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3710-112">See Also</span></span>  
 [<span data-ttu-id="b3710-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3710-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="b3710-114">ExceptionSearchFilterLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="b3710-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
