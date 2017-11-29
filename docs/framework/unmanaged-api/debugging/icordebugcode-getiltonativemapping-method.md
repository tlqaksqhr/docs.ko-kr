---
title: "ICorDebugCode::GetILToNativeMapping 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetILToNativeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 54937e8d5d7a2e345ebcbccadbc592b12e3ee9b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="3e4a8-102">ICorDebugCode::GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="3e4a8-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="3e4a8-103">Microsoft MSIL (intermediate language) 오프셋과 네이티브 오프셋 간의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3e4a8-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e4a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e4a8-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e4a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e4a8-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="3e4a8-106">[in] `map` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3e4a8-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="3e4a8-107">[out] 반환 되는 요소의 실제 수에 대 한 포인터는 `map` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3e4a8-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="3e4a8-108">[out] 배열 `COR_DEBUG_IL_TO_NATIVE_MAP` MSIL 오프셋에서 네이티브 오프셋으로의 매핑을 나타내는 각각의 구조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e4a8-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="3e4a8-109">반환 되는 요소 배열에 순서가 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e4a8-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e4a8-110">설명</span><span class="sxs-lookup"><span data-stu-id="3e4a8-110">Remarks</span></span>  
 <span data-ttu-id="3e4a8-111">`GetILToNativeMapping` 메서드가이 "ICorDebugCode" 인스턴스가 된 just-in-time (JIT) MSIL 코드에서 컴파일된 네이티브 코드를 나타내는 경우에 의미 있는 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e4a8-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e4a8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e4a8-112">Requirements</span></span>  
 <span data-ttu-id="3e4a8-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e4a8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e4a8-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e4a8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e4a8-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e4a8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e4a8-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e4a8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e4a8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e4a8-117">See Also</span></span>  
 [<span data-ttu-id="3e4a8-118">ICorDebugCode Interface1</span><span class="sxs-lookup"><span data-stu-id="3e4a8-118">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
