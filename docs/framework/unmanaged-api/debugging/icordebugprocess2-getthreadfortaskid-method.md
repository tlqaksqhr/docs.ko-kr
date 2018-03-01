---
title: "ICorDebugProcess2::GetThreadForTaskID 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess2.GetThreadForTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: af63e6cf0d7e4b51f9365c1ccc4ac78158c091bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="d6676-102">ICorDebugProcess2::GetThreadForTaskID 메서드</span><span class="sxs-lookup"><span data-stu-id="d6676-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="d6676-103">지정한 식별자를 가진 작업 실행 중인 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d6676-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6676-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6676-104">Syntax</span></span>  
  
```  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6676-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d6676-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="d6676-106">[in] 작업의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d6676-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="d6676-107">[out] 스레드를 검색할 수를 나타내는 ICorDebugThread2 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d6676-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6676-108">설명</span><span class="sxs-lookup"><span data-stu-id="d6676-108">Remarks</span></span>  
 <span data-ttu-id="d6676-109">호스트를 사용 하 여 작업 식별자를 설정할 수는 [iclrtask:: Settaskidentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d6676-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6676-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6676-110">Requirements</span></span>  
 <span data-ttu-id="d6676-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6676-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6676-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6676-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6676-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6676-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6676-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6676-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
