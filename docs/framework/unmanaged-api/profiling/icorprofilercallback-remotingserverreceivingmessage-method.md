---
title: "ICorProfilerCallback::RemotingServerReceivingMessage 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerReceivingMessage
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5947541204edf7fd4359dfa3aca78ea62c8009c6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="b0979-102">ICorProfilerCallback::RemotingServerReceivingMessage 메서드</span><span class="sxs-lookup"><span data-stu-id="b0979-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="b0979-103">프로세스에서 원격 메서드 호출 또는 정품 인증 요청을 받았음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b0979-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0979-104">구문</span><span class="sxs-lookup"><span data-stu-id="b0979-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0979-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b0979-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="b0979-106">[in] 에 제공 된 값과 일치 하는 값 [icorprofilercallback:: Remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) 이러한 조건:</span><span class="sxs-lookup"><span data-stu-id="b0979-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="b0979-107">원격 GUID 쿠키가 활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0979-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="b0979-108">채널에서 메시지를 전송 하는 데 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0979-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="b0979-109">GUID 쿠키는 클라이언트 프로세스에서 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="b0979-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="b0979-110">이렇게 하면 원격 호출 및 논리 호출 스택의 만드는 쉽게 쌍 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0979-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="b0979-111">[in] 값을 `true` 는 호출이 고, 그렇지 않으면 비동기 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="b0979-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0979-112">설명</span><span class="sxs-lookup"><span data-stu-id="b0979-112">Remarks</span></span>  
 <span data-ttu-id="b0979-113">메시지 요청을 비동기 경우 임의의 스레드에서 요청을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0979-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0979-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0979-114">Requirements</span></span>  
 <span data-ttu-id="b0979-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0979-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0979-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b0979-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b0979-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0979-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0979-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0979-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0979-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0979-119">See Also</span></span>  
 [<span data-ttu-id="b0979-120">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0979-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
