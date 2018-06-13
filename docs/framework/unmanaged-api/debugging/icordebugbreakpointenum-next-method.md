---
title: ICorDebugBreakpointEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11c08e59813014bf9a474e92d06c6bd2576dd7d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404874"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="901d8-102">ICorDebugBreakpointEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="901d8-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="901d8-103">현재 위치부터 시작 하는 열거형에서 지정 된 ICorDebugBreakpoint 인스턴스 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="901d8-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="901d8-104">구문</span><span class="sxs-lookup"><span data-stu-id="901d8-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="901d8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="901d8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="901d8-106">[in] 수가 `ICorDebugBreakpoint` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901d8-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="901d8-107">[out] 각각 가리키는 포인터의 배열은 `ICorDebugBreakpoint` 중단점을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="901d8-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="901d8-108">[out] 수에 대 한 포인터 `ICorDebugBreakpoint` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="901d8-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="901d8-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="901d8-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="901d8-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="901d8-110">Requirements</span></span>  
 <span data-ttu-id="901d8-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="901d8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="901d8-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="901d8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="901d8-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="901d8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="901d8-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="901d8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
