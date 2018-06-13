---
title: ICorProfilerCallback::ExceptionSearchCatcherFound 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: beb0e4d3e22ffc3619a6c5281ab5d72efeda921d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450605"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="0f1e7-102">ICorProfilerCallback::ExceptionSearchCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="0f1e7-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="0f1e7-103">예외 처리의 검색 단계에서 throw 된 예외에 대 한 처리기를 찾았으며 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0f1e7-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f1e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f1e7-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f1e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f1e7-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="0f1e7-106">[in] 예외 처리기가 포함 된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0f1e7-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f1e7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f1e7-107">Requirements</span></span>  
 <span data-ttu-id="0f1e7-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f1e7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f1e7-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f1e7-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f1e7-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f1e7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f1e7-111">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f1e7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f1e7-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f1e7-112">See Also</span></span>  
 [<span data-ttu-id="0f1e7-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f1e7-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
