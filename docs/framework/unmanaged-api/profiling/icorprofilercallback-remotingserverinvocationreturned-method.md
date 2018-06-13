---
title: ICorProfilerCallback::RemotingServerInvocationReturned 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationReturned
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned method [.NET Framework profiling]
- RemotingServerInvocationReturned method [.NET Framework profiling]
ms.assetid: a4de6805-e159-4280-99e5-3390c86166d0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3f32b9ab9b4e29dd101729dc43cde03985f5994
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451226"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="51877-102">ICorProfilerCallback::RemotingServerInvocationReturned 메서드</span><span class="sxs-lookup"><span data-stu-id="51877-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="51877-103">프로세스가 원격 메서드 호출 요청에 대 한 응답에서 메서드를 호출할 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="51877-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51877-104">구문</span><span class="sxs-lookup"><span data-stu-id="51877-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="51877-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51877-105">Requirements</span></span>  
 <span data-ttu-id="51877-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="51877-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51877-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51877-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51877-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51877-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51877-109">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51877-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51877-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51877-110">See Also</span></span>  
 [<span data-ttu-id="51877-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51877-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
