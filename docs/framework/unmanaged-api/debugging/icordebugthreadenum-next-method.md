---
title: "ICorDebugThreadEnum::Next 메서드"
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
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ac9ff468f85248631ffd7f3a39a8827b1aef45b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="7f04f-102">ICorDebugThreadEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="7f04f-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="7f04f-103">현재 위치부터 시작 하는 열거형에서 지정 된 ICorDebugThread 인스턴스 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7f04f-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f04f-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f04f-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f04f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f04f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7f04f-106">[in] 수가 `ICorDebugThread` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f04f-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="7f04f-107">[out] 각각 가리키는 포인터의 배열은 `ICorDebugThread` 스레드를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7f04f-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7f04f-108">[out] 수에 대 한 포인터 `ICorDebugThread` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="7f04f-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="7f04f-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7f04f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f04f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f04f-110">Requirements</span></span>  
 <span data-ttu-id="7f04f-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7f04f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f04f-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f04f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f04f-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f04f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f04f-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f04f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
