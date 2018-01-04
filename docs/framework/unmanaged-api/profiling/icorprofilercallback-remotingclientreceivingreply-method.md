---
title: "ICorProfilerCallback::RemotingClientReceivingReply 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientReceivingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 831ce047f38f7f4a5c7a8b84efea423c482a418d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="f0b02-102">ICorProfilerCallback::RemotingClientReceivingReply 메서드</span><span class="sxs-lookup"><span data-stu-id="f0b02-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="f0b02-103">서버 쪽 부분의 원격 호출을 완료 하 고 클라이언트는 수신 하는 프로파일러에 알립니다 회신을 처리 하려고 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b02-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0b02-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0b02-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0b02-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0b02-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="f0b02-106">[in] 에 제공 된 값과 일치 하는 값 [icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) 이러한 조건:</span><span class="sxs-lookup"><span data-stu-id="f0b02-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="f0b02-107">원격 GUID 쿠키가 활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b02-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="f0b02-108">채널에서 메시지를 전송 하는 데 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b02-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="f0b02-109">GUID 쿠키는 서버 쪽 프로세스에서 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f0b02-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="f0b02-110">이렇게 하면 쌍 원격 호출을 손쉽게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b02-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="f0b02-111">[in] 값을 `true` 는 호출이 고, 그렇지 않으면 비동기 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b02-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0b02-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0b02-112">Requirements</span></span>  
 <span data-ttu-id="f0b02-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b02-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0b02-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0b02-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0b02-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0b02-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0b02-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0b02-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b02-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0b02-117">See Also</span></span>  
 [<span data-ttu-id="f0b02-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0b02-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
