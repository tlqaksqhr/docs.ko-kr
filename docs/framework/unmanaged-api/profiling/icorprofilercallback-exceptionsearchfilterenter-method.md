---
title: "ICorProfilerCallback::ExceptionSearchFilterEnter 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionSearchFilterEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 129bc39fc9edd8f3101e7d03272bcab35c746d73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="d34be-102">ICorProfilerCallback::ExceptionSearchFilterEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="d34be-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="d34be-103">예외 처리의 검색 단계는 사용자 정의 예외 필터를 실행을 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d34be-104">구문</span><span class="sxs-lookup"><span data-stu-id="d34be-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d34be-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d34be-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d34be-106">[in] 필터를 포함 하는 함수의의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d34be-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d34be-107">Requirements</span></span>  
 <span data-ttu-id="d34be-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d34be-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d34be-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d34be-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d34be-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d34be-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d34be-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d34be-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d34be-112">See Also</span></span>  
 [<span data-ttu-id="d34be-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d34be-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="d34be-114">ExceptionSearchFilterLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="d34be-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
