---
title: "ICorDebugEval::GetThread 메서드"
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
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a2ed99c2a939d2b39f6b236165b79634f2fc2c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="cc37d-102">ICorDebugEval::GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="cc37d-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="cc37d-103">이 평가 실행 되거나 실행 됩니다 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc37d-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc37d-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc37d-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc37d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc37d-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="cc37d-106">[out] 스레드를 나타내는 ICorDebugThread 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cc37d-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc37d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc37d-107">Requirements</span></span>  
 <span data-ttu-id="cc37d-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cc37d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc37d-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc37d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc37d-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc37d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc37d-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc37d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
