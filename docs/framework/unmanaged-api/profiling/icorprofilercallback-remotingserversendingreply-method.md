---
title: "ICorProfilerCallback::RemotingServerSendingReply 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerSendingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f8fa5a81231c8181e0d0257a1bbfdb4a1f0a7a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="60b58-102">ICorProfilerCallback::RemotingServerSendingReply 메서드</span><span class="sxs-lookup"><span data-stu-id="60b58-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="60b58-103">프로세스에서 원격 메서드 호출 요청 처리를 완료 하 고 채널을 통해 회신을 전송 하려고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="60b58-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60b58-104">구문</span><span class="sxs-lookup"><span data-stu-id="60b58-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60b58-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60b58-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="60b58-106">[in] 에 제공 된 값과 일치 하는 GUID에 대 한 포인터 [icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 이러한 조건:</span><span class="sxs-lookup"><span data-stu-id="60b58-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="60b58-107">원격 GUID 쿠키가 활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b58-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="60b58-108">채널에서 메시지를 전송 하는 데 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b58-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="60b58-109">GUID 쿠키는 클라이언트 프로세스에서 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="60b58-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="60b58-110">이렇게 하면 원격 호출 및 논리 호출 스택의 만드는 쉽게 쌍 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b58-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="60b58-111">[in] 값을 `true` 는 호출이 고, 그렇지 않으면 비동기 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="60b58-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60b58-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60b58-112">Requirements</span></span>  
 <span data-ttu-id="60b58-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="60b58-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60b58-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60b58-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="60b58-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60b58-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60b58-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60b58-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b58-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60b58-117">See Also</span></span>  
 [<span data-ttu-id="60b58-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60b58-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
