---
title: "ICorDebugBreakpointEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpointEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0be36669678d33a73809c6be95563321f754697c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="8bdfc-102">ICorDebugBreakpointEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="8bdfc-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="8bdfc-103">현재 위치부터 시작 하는 열거형에서 지정 된 ICorDebugBreakpoint 인스턴스 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8bdfc-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bdfc-104">구문</span><span class="sxs-lookup"><span data-stu-id="8bdfc-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8bdfc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8bdfc-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8bdfc-106">[in] 수가 `ICorDebugBreakpoint` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bdfc-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="8bdfc-107">[out] 각각 가리키는 포인터의 배열은 `ICorDebugBreakpoint` 중단점을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8bdfc-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8bdfc-108">[out] 수에 대 한 포인터 `ICorDebugBreakpoint` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8bdfc-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="8bdfc-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8bdfc-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bdfc-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bdfc-110">Requirements</span></span>  
 <span data-ttu-id="8bdfc-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8bdfc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bdfc-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bdfc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bdfc-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bdfc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bdfc-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bdfc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
