---
title: "ICorDebugFrameEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrameEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2139661621d7ebe2bf20e96b400096393964b89
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="35742-102">ICorDebugFrameEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="35742-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="35742-103">ICorDebugFrame 인스턴스, 현재 위치부터 지정한 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35742-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35742-104">구문</span><span class="sxs-lookup"><span data-stu-id="35742-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35742-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35742-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="35742-106">[in] 수가 `ICorDebugFrame` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35742-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="35742-107">[out] 각각 가리키는 포인터의 배열은 `ICorDebugFrame` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="35742-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="35742-108">[out] 수에 대 한 포인터 `ICorDebugFrame` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="35742-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="35742-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="35742-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35742-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35742-110">Requirements</span></span>  
 <span data-ttu-id="35742-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="35742-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35742-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35742-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35742-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35742-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35742-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35742-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
