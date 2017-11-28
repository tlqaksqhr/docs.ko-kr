---
title: "ICorDebugManagedCallback2::CreateConnection 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.CreateConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 716321508c18a415dc8e5c1c3e7e350deaf00a4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="01c3c-102">ICorDebugManagedCallback2::CreateConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="01c3c-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="01c3c-103">새 연결 만들어졌는지 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="01c3c-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c3c-104">구문</span><span class="sxs-lookup"><span data-stu-id="01c3c-104">Syntax</span></span>  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01c3c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01c3c-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="01c3c-106">[in] 연결을 만든 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터</span><span class="sxs-lookup"><span data-stu-id="01c3c-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="01c3c-107">[in] 새 연결의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="01c3c-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="01c3c-108">[in] 새 연결의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="01c3c-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01c3c-109">설명</span><span class="sxs-lookup"><span data-stu-id="01c3c-109">Remarks</span></span>  
 <span data-ttu-id="01c3c-110">A `CreateConnection` 콜백 중 한 가지는 다음과 같은 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="01c3c-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="01c3c-111">때 연결을 포함 하는 프로세스에 디버거 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="01c3c-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="01c3c-112">이 경우 런타임에 생성 되며 발송 한 `CreateConnection` 이벤트 및 [icordebugmanagedcallback2:: Changeconnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) 프로세스에서 각 연결에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="01c3c-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
-   <span data-ttu-id="01c3c-113">호스트를 호출 하는 경우 [iclrdebugmanager:: Beginconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) 에 [호스팅 API](../../../../docs/framework/unmanaged-api/hosting/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01c3c-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01c3c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01c3c-114">Requirements</span></span>  
 <span data-ttu-id="01c3c-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01c3c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01c3c-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01c3c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01c3c-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01c3c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01c3c-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01c3c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c3c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01c3c-119">See Also</span></span>  
 [<span data-ttu-id="01c3c-120">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01c3c-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="01c3c-121">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01c3c-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
