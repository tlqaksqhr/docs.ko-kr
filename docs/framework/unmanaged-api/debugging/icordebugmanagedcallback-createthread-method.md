---
title: "ICorDebugManagedCallback::CreateThread 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.CreateThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8acb12d216949fc4e0636b5a2c28657ef5c79bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="e3a6a-102">ICorDebugManagedCallback::CreateThread 메서드</span><span class="sxs-lookup"><span data-stu-id="e3a6a-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="e3a6a-103">관리 코드를 실행 스레드가 시작 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e3a6a-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3a6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3a6a-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3a6a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3a6a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e3a6a-106">[in] 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e3a6a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="e3a6a-107">[in] 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e3a6a-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3a6a-108">설명</span><span class="sxs-lookup"><span data-stu-id="e3a6a-108">Remarks</span></span>  
 <span data-ttu-id="e3a6a-109">스레드는 실행할 첫 번째 관리 되는 코드 명령에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3a6a-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3a6a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3a6a-110">Requirements</span></span>  
 <span data-ttu-id="e3a6a-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a6a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3a6a-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3a6a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3a6a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3a6a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3a6a-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3a6a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a6a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3a6a-115">See Also</span></span>  
 [<span data-ttu-id="e3a6a-116">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3a6a-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
