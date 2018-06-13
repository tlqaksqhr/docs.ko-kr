---
title: ICorProfilerCallback::RemotingClientInvocationFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec45b73b496efdbe6328985b5f77f731d8a78cc7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453407"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="8425d-102">ICorProfilerCallback::RemotingClientInvocationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="8425d-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="8425d-103">클라이언트에서 원격 호출이 완료 될 때까지 실행이 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8425d-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8425d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8425d-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8425d-105">설명</span><span class="sxs-lookup"><span data-stu-id="8425d-105">Remarks</span></span>  
 <span data-ttu-id="8425d-106">원격 호출을 동기 경우 서버에서 완료 될 때까지 실행할 수도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8425d-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="8425d-107">원격 호출을 비동기 경우 회신 필요할 수 있습니다는 호출이 처리 될 때입니다.</span><span class="sxs-lookup"><span data-stu-id="8425d-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="8425d-108">에 대 한 호출으로 이루어집니다 한 회신이 필요한 경우 [icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 및은 추가 호출을 `RemotingClientInvocationFinished` 에 필요한 보조 처리는 비동기 호출을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8425d-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="8425d-109">다음 콜백 쌍의 각 항목은 동일한 스레드에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8425d-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="8425d-110">`RemotingClientInvocationStarted` 및 [icorprofilercallback:: Remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="8425d-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="8425d-111">[Icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 및 [icorprofilercallback:: Remotingclientinvocationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="8425d-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="8425d-112">[Icorprofilercallback:: Remotingserverinvocationreturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) 및 [icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="8425d-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="8425d-113">원격 콜백와 관련 된 다음 문제를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8425d-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="8425d-114">원격 함수가 실행 하므로 클라이언트에서 호출 되 고 서버에서 실행 되는 함수에 대 한 알림을 올바르게 수신 되지 않습니다 프로파일러 API에서 반영 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8425d-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="8425d-115">프록시 개체;를 통해 발생 하는 실제로 호출 프로파일러를 특정 함수는 JIT 컴파일 되었지만 사용 되지는 않습니다 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8425d-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="8425d-116">프로파일러는 비동기 원격 이벤트에 대 한 정확한 알림을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8425d-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8425d-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8425d-117">Requirements</span></span>  
 <span data-ttu-id="8425d-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8425d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8425d-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8425d-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8425d-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8425d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8425d-121">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8425d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8425d-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8425d-122">See Also</span></span>  
 [<span data-ttu-id="8425d-123">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8425d-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
