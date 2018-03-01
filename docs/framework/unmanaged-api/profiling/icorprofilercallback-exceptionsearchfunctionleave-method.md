---
title: "ICorProfilerCallback::ExceptionSearchFunctionLeave 메서드"
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
- ICorProfilerCallback.ExceptionSearchFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionLeave
helpviewer_keywords:
- ExceptionSearchFunctionLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionLeave method [.NET Framework profiling]
ms.assetid: 01de7ac6-0aad-42ef-bf93-50737667b0a4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e63309ea1d92018b41c8ee32fcd66f865af5d891
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="a4baf-102">ICorProfilerCallback::ExceptionSearchFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="a4baf-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>
<span data-ttu-id="a4baf-103">예외 처리의 검색 단계 함수 검색 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a4baf-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4baf-104">구문</span><span class="sxs-lookup"><span data-stu-id="a4baf-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="a4baf-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4baf-105">Requirements</span></span>  
 <span data-ttu-id="a4baf-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4baf-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4baf-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a4baf-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a4baf-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4baf-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4baf-109">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4baf-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4baf-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4baf-110">See Also</span></span>  
 [<span data-ttu-id="a4baf-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4baf-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a4baf-112">ExceptionSearchFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="a4baf-112">ExceptionSearchFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)
