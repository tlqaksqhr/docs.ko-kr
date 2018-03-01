---
title: "ICorProfilerCallback::RuntimeResumeStarted 메서드"
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
- ICorProfilerCallback.RuntimeResumeStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7949d742044eeffca2a35ffec790a7f91c418076
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="699b9-102">ICorProfilerCallback::RuntimeResumeStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="699b9-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="699b9-103">런타임은 모든 런타임 스레드가 다시 시작 하는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="699b9-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="699b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="699b9-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="699b9-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="699b9-105">Requirements</span></span>  
 <span data-ttu-id="699b9-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="699b9-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="699b9-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="699b9-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="699b9-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="699b9-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="699b9-109">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="699b9-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699b9-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="699b9-110">See Also</span></span>  
 [<span data-ttu-id="699b9-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="699b9-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="699b9-112">RuntimeResumeFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="699b9-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
