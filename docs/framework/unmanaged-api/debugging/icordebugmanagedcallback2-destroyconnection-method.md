---
title: "ICorDebugManagedCallback2::DestroyConnection 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.DestroyConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c35c39e5ce2b6478d6945d765403c6e4b63eef89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="9a77c-102">ICorDebugManagedCallback2::DestroyConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="9a77c-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="9a77c-103">지정한 연결이 종료 되었습니다 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9a77c-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a77c-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a77c-104">Syntax</span></span>  
  
```  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a77c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9a77c-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="9a77c-106">[in] 소멸 된 연결을 포함 하는 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9a77c-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="9a77c-107">[in] 소멸 하는 연결의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9a77c-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a77c-108">설명</span><span class="sxs-lookup"><span data-stu-id="9a77c-108">Remarks</span></span>  
 <span data-ttu-id="9a77c-109">A `DestroyConnection` 호스트 호출 때 콜백 발생 [iclrdebugmanager:: Endconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) 에 [호스팅 API](../../../../docs/framework/unmanaged-api/hosting/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a77c-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a77c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a77c-110">Requirements</span></span>  
 <span data-ttu-id="9a77c-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a77c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a77c-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a77c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a77c-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a77c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a77c-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a77c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a77c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a77c-115">See Also</span></span>  
 [<span data-ttu-id="9a77c-116">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a77c-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="9a77c-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a77c-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
