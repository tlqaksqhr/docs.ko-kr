---
title: ICorDebugThread2::GetTaskID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5690856b526bf0f7bc4527d04ae8044cda1f6e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417868"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="84d05-102">ICorDebugThread2::GetTaskID 메서드</span><span class="sxs-lookup"><span data-stu-id="84d05-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="84d05-103">이 스레드에서 실행 중인 작업의 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="84d05-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84d05-104">구문</span><span class="sxs-lookup"><span data-stu-id="84d05-104">Syntax</span></span>  
  
```  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84d05-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84d05-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="84d05-106">[out] 이 ICorDebugThread2 개체로 표현 되는 스레드에서 실행 중인 작업의 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="84d05-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84d05-107">설명</span><span class="sxs-lookup"><span data-stu-id="84d05-107">Remarks</span></span>  
 <span data-ttu-id="84d05-108">스레드가 연결과 관련 된 경우에 작업 스레드에서 실행 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d05-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="84d05-109">`GetTaskID` 0을 반환 `pTaskId` 스레드가 연결과 연결 되어 있지 않으면입니다.</span><span class="sxs-lookup"><span data-stu-id="84d05-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84d05-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84d05-110">Requirements</span></span>  
 <span data-ttu-id="84d05-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="84d05-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84d05-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84d05-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84d05-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84d05-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84d05-114">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84d05-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
