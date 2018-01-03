---
title: "ICorDebugThread::GetID 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cab889761c204204e7eda46fde0df42f31b89fbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="0f018-102">ICorDebugThread::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="0f018-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="0f018-103">이 ICorDebugThread의 활성 부분의 현재 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f018-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f018-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f018-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f018-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f018-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="0f018-106">[out] 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="0f018-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f018-107">설명</span><span class="sxs-lookup"><span data-stu-id="0f018-107">Remarks</span></span>  
 <span data-ttu-id="0f018-108">운영 체제 식별자는 프로세스를 실행 하는 동안 변경 될 수 있습니다 및 스레드의 다른 부분에 다른 값이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f018-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f018-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f018-109">Requirements</span></span>  
 <span data-ttu-id="0f018-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f018-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f018-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f018-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f018-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f018-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f018-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f018-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
