---
title: ICorDebugProcess2::GetThreadForTaskID 메서드
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd04e6d8bed86039b6f43985a8fb712b4612f76d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418352"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="22f4d-102">ICorDebugProcess2::GetThreadForTaskID 메서드</span><span class="sxs-lookup"><span data-stu-id="22f4d-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="22f4d-103">지정한 식별자를 가진 작업 실행 중인 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="22f4d-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22f4d-104">구문</span><span class="sxs-lookup"><span data-stu-id="22f4d-104">Syntax</span></span>  
  
```  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22f4d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="22f4d-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="22f4d-106">[in] 작업의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="22f4d-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="22f4d-107">[out] 스레드를 검색할 수를 나타내는 ICorDebugThread2 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="22f4d-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22f4d-108">설명</span><span class="sxs-lookup"><span data-stu-id="22f4d-108">Remarks</span></span>  
 <span data-ttu-id="22f4d-109">호스트를 사용 하 여 작업 식별자를 설정할 수는 [iclrtask:: Settaskidentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="22f4d-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22f4d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22f4d-110">Requirements</span></span>  
 <span data-ttu-id="22f4d-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="22f4d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22f4d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22f4d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22f4d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22f4d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22f4d-114">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22f4d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
