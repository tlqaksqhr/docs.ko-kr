---
title: "ICorProfilerCallback::RemotingServerInvocationStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerInvocationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerInvocationStarted
helpviewer_keywords:
- RemotingServerInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerInvocationStarted method [.NET Framework profiling]
ms.assetid: 86051a11-ad8e-4ace-9a11-ff0f982a5e11
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e0e2e2136b084f8dc1ea17001f4f6fff89adc575
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="cf28e-102">ICorProfilerCallback::RemotingServerInvocationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="cf28e-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>
<span data-ttu-id="cf28e-103">프로세스가 원격 메서드 호출 요청에 대 한 응답에서 메서드를 호출 하는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cf28e-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf28e-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf28e-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="cf28e-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf28e-105">Requirements</span></span>  
 <span data-ttu-id="cf28e-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf28e-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf28e-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf28e-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf28e-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf28e-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf28e-109">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf28e-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf28e-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf28e-110">See Also</span></span>  
 [<span data-ttu-id="cf28e-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf28e-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
