---
title: "ICorProfilerCallback::ExceptionSearchFilterLeave 메서드"
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
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e0bbde11a2b9c346cbda73ee29da20140524b51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="6c108-102">ICorProfilerCallback::ExceptionSearchFilterLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="6c108-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="6c108-103">사용자 필터 실행을 완료 방금 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6c108-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c108-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c108-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="6c108-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c108-105">Requirements</span></span>  
 <span data-ttu-id="6c108-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c108-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c108-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c108-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c108-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c108-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c108-109">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c108-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c108-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c108-110">See Also</span></span>  
 [<span data-ttu-id="6c108-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c108-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="6c108-112">ExceptionSearchFilterEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="6c108-112">ExceptionSearchFilterEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)
