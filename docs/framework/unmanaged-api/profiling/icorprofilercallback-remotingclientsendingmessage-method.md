---
title: "ICorProfilerCallback::RemotingClientSendingMessage 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientSendingMessage
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d22843c3489aae24003df1e91b0cae4481f4599c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="712ab-102">ICorProfilerCallback::RemotingClientSendingMessage 메서드</span><span class="sxs-lookup"><span data-stu-id="712ab-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="712ab-103">클라이언트가 서버에 요청을 보내기는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="712ab-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="712ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="712ab-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="712ab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="712ab-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="712ab-106">[in] 에 제공 된 값에 해당 하는 값 [icorprofilercallback:: Remotingserverreceivingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) 이러한 조건:</span><span class="sxs-lookup"><span data-stu-id="712ab-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="712ab-107">원격 GUID 쿠키가 활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="712ab-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="712ab-108">채널에서 메시지를 전송 하는 데 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="712ab-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="712ab-109">GUID 쿠키는 서버 쪽 프로세스에서 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="712ab-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="712ab-110">이렇게 하면 원격 호출 및 논리 호출 스택의 만드는 쉽게 쌍 있습니다.</span><span class="sxs-lookup"><span data-stu-id="712ab-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="712ab-111">[in] 값을 `true` 는 호출이 고, 그렇지 않으면 비동기 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="712ab-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="712ab-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="712ab-112">Requirements</span></span>  
 <span data-ttu-id="712ab-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="712ab-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="712ab-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="712ab-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="712ab-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="712ab-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="712ab-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="712ab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="712ab-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="712ab-117">See Also</span></span>  
 [<span data-ttu-id="712ab-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="712ab-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
