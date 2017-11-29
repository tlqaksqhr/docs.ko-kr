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
ms.openlocfilehash: 31ae48d62221d45a8457c304a1929886738190c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="7626c-102">ICorDebugThread::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="7626c-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="7626c-103">이 ICorDebugThread의 활성 부분의 현재 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7626c-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7626c-104">구문</span><span class="sxs-lookup"><span data-stu-id="7626c-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7626c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7626c-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="7626c-106">[out] 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7626c-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7626c-107">설명</span><span class="sxs-lookup"><span data-stu-id="7626c-107">Remarks</span></span>  
 <span data-ttu-id="7626c-108">운영 체제 식별자는 프로세스를 실행 하는 동안 변경 될 수 있습니다 및 스레드의 다른 부분에 다른 값이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7626c-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7626c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7626c-109">Requirements</span></span>  
 <span data-ttu-id="7626c-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7626c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7626c-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7626c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7626c-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7626c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7626c-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7626c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
