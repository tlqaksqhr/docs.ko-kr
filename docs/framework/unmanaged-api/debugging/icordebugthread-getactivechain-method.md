---
title: ICorDebugThread::GetActiveChain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9030319ca12aafcf452e3ecd816fc269f0abfc0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417517"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="e1075-102">ICorDebugThread::GetActiveChain 메서드</span><span class="sxs-lookup"><span data-stu-id="e1075-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="e1075-103">활성 (가장 최근) 스택 체인을이 ICorDebugThread 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1075-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1075-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1075-104">Syntax</span></span>  
  
```  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1075-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1075-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="e1075-106">[out] 스택 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1075-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1075-107">설명</span><span class="sxs-lookup"><span data-stu-id="e1075-107">Remarks</span></span>  
 <span data-ttu-id="e1075-108">`ppChain` 매개 변수는 현재 활성 스택 체인이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="e1075-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1075-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1075-109">Requirements</span></span>  
 <span data-ttu-id="e1075-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1075-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1075-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1075-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1075-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1075-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1075-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1075-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
