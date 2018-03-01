---
title: "ICorDebugExceptionObjectCallStackEnum::Next 메서드"
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
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: be050ad1c7b6e10f286a45844f5741689f264923
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="9e8db-102">ICorDebugExceptionObjectCallStackEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="9e8db-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="9e8db-103">지정된 된 수의 가져옵니다 [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) 예외 개체의 호출 스택 정보가 포함 된 인스턴스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e8db-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e8db-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e8db-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e8db-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e8db-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9e8db-106">[in] 수가 [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e8db-106">[in] The number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="9e8db-107">[out] 각각 가리키는 포인터의 배열은 [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8db-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9e8db-108">[out] 수에 대 한 포인터 [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9e8db-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e8db-109">설명</span><span class="sxs-lookup"><span data-stu-id="9e8db-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e8db-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e8db-110">Requirements</span></span>  
 <span data-ttu-id="9e8db-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8db-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e8db-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e8db-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e8db-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e8db-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e8db-114">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e8db-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e8db-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e8db-115">See Also</span></span>  
 [<span data-ttu-id="9e8db-116">ICorDebugExceptionObjectCallStackEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e8db-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 [<span data-ttu-id="9e8db-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e8db-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
