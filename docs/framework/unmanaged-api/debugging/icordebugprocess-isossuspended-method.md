---
title: "ICorDebugProcess::IsOSSuspended 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.IsOSSuspended
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97c394e3084007227cf157c62a12df3f5cfac8e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="90cf9-102">ICorDebugProcess::IsOSSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="90cf9-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="90cf9-103">이 프로세스를 중지 하는 디버거 결과로 지정 된 스레드가 일시 중단 된 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="90cf9-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90cf9-104">구문</span><span class="sxs-lookup"><span data-stu-id="90cf9-104">Syntax</span></span>  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90cf9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90cf9-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="90cf9-106">[in] 해당 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="90cf9-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="90cf9-107">[out] 부울 값이에 대 한 포인터 `true` 고, 그렇지 않으면 일시 중단 된 지정된 된 스레드가 되었으면 *`pbSuspended` 은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="90cf9-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise *`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90cf9-108">설명</span><span class="sxs-lookup"><span data-stu-id="90cf9-108">Remarks</span></span>  
 <span data-ttu-id="90cf9-109">지정 된 스레드의 Win32 지정된 된 스레드가으로 일시 중단 된 결과로 디버거가이 프로세스를 중지 하는 경우 일시 중단 횟수가 1 씩 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="90cf9-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="90cf9-110">디버거 사용자 인터페이스 (UI) 열 수는 운영 체제를 표시 하는 경우 계정에이 정보를 사용자에 게 스레드의 개수를 일시 중단 (OS).</span><span class="sxs-lookup"><span data-stu-id="90cf9-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="90cf9-111">`IsOSSuspended` 메서드가 관리 되지 않는 디버깅의 경우에만 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="90cf9-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="90cf9-112">관리 되는 디버깅 하는 동안 스레드는 협조적으로 일시 중단 된 것이 아니라 OS 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90cf9-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90cf9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90cf9-113">Requirements</span></span>  
 <span data-ttu-id="90cf9-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90cf9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90cf9-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90cf9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90cf9-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90cf9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90cf9-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90cf9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
