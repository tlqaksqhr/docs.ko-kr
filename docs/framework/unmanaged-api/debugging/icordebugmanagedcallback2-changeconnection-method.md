---
title: "ICorDebugManagedCallback2::ChangeConnection 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.ChangeConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c62859cb6a3e61af9670834db169410cecb6787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="42881-102">ICorDebugManagedCallback2::ChangeConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="42881-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="42881-103">지정 된 연결과 관련 된 작업 집합이 변경 된 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="42881-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42881-104">구문</span><span class="sxs-lookup"><span data-stu-id="42881-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42881-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42881-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="42881-106">[in] 변경 된 연결을 포함 하는 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="42881-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="42881-107">[in] 변경 하는 연결의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="42881-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42881-108">설명</span><span class="sxs-lookup"><span data-stu-id="42881-108">Remarks</span></span>  
 <span data-ttu-id="42881-109">A `ChangeConnection` 콜백 중 한 가지는 다음과 같은 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="42881-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="42881-110">때 연결을 포함 하는 프로세스에 디버거 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="42881-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="42881-111">이 경우 런타임에 생성 되며 발송 한 [icordebugmanagedcallback2:: Createconnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) 이벤트 및 `ChangeConnection` 프로세스에서 각 연결에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="42881-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="42881-112">A `ChangeConnection` 만들어진 이후 해당 연결의 작업 집합이 변경 된 여부에 관계 없이 모든 기존 연결에 대해 이벤트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42881-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
-   <span data-ttu-id="42881-113">호스트를 호출 하는 경우 [iclrdebugmanager:: Setconnectiontasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) 에 [호스팅 API](../../../../docs/framework/unmanaged-api/hosting/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42881-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="42881-114">디버거에서 새 변경 내용을 적용할 프로세스의 모든 스레드를 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42881-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42881-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42881-115">Requirements</span></span>  
 <span data-ttu-id="42881-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42881-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42881-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42881-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42881-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42881-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42881-119">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42881-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42881-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42881-120">See Also</span></span>  
 [<span data-ttu-id="42881-121">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42881-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="42881-122">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42881-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
