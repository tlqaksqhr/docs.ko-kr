---
title: ICorDebugComObjectValue::GetCachedInterfacePointers 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef6fb76ca25a1255393b66c52d82cb94df2b48b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411904"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="59c6a-102">ICorDebugComObjectValue::GetCachedInterfacePointers 메서드</span><span class="sxs-lookup"><span data-stu-id="59c6a-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="59c6a-103">현재 런타임 호출 가능 래퍼 (RCW)에 캐시 된 원시 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59c6a-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59c6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="59c6a-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59c6a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59c6a-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="59c6a-106">[in] 메서드는만 반환 하는지 여부를 나타내는 값 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 인터페이스 (`IInspectable` 인터페이스) 또는 런타임 호출 가능 래퍼 (RCW)에 의해 캐시 되는 모든 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="59c6a-106">[in] A value that indicates whether the method will return only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="59c6a-107">[in] 해당 주소를 검색할 수는 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="59c6a-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="59c6a-108">[out] 수에 대 한 포인터 `CORDB_ADDRESS` 에 실제로 반환 된 값 `ptrs`합니다.</span><span class="sxs-lookup"><span data-stu-id="59c6a-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="59c6a-109">배열의 시작 주소에 대 한 포인터 `CORDB_ADDRESS` 캐시 된 인터페이스 개체의 주소를 포함 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="59c6a-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59c6a-110">설명</span><span class="sxs-lookup"><span data-stu-id="59c6a-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59c6a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59c6a-111">Requirements</span></span>  
 <span data-ttu-id="59c6a-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59c6a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59c6a-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59c6a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59c6a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59c6a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59c6a-115">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59c6a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59c6a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59c6a-116">See Also</span></span>  
 [<span data-ttu-id="59c6a-117">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59c6a-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [<span data-ttu-id="59c6a-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59c6a-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
