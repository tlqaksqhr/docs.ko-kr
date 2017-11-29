---
title: "ICorDebugCode3::GetReturnValueLiveOffset 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugCode3.GetReturnValueLiveOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4516f2244b72bd4f254c5090b09d6d90579f1ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="0dd1d-102">ICorDebugCode3::GetReturnValueLiveOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="0dd1d-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="0dd1d-103">지정된 된 IL 오프셋에 대 한 디버거 함수에서 반환 값을 가져올 수 있도록 중단점을 배치할 위치 네이티브 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dd1d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0dd1d-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0dd1d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0dd1d-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="0dd1d-106">IL 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-106">The IL offset.</span></span> <span data-ttu-id="0dd1d-107">함수 호출 사이트 여야 합니다. 또는 함수 호출에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="0dd1d-108">저장할 수 있는 바이트 수가 `pOffsets`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="0dd1d-109">실제로 반환 된 오프셋의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="0dd1d-110">일반적으로 해당 값은 1이 있지만 단일 IL 명령 배수로 매핑할 수 `CALL` 어셈블리 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="0dd1d-111">배열 네이티브 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-111">An array of native offsets.</span></span> <span data-ttu-id="0dd1d-112">일반적으로 `pOffsets` 단일 IL 명령 배수로 여러 지도에 매핑할 수 있지만 단일 오프셋을 포함 `CALL` 어셈블리 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dd1d-113">설명</span><span class="sxs-lookup"><span data-stu-id="0dd1d-113">Remarks</span></span>  
 <span data-ttu-id="0dd1d-114">이 메서드는와 함께 사용 되는 [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) 참조 형식을 반환 하는 메서드의 반환 값을 가져오는 메서드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="0dd1d-115">이 메서드를 함수 호출 사이트에 대 한 오프셋 IL 전달 하나 이상의 네이티브 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="0dd1d-116">다음 디버거 함수에서 네이티브 이러한 오프셋에서 중단점을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="0dd1d-117">디버거는 중단점에 도달 하는 경우에 전달할 수 있습니다를이 메서드에 전달 된 IL 오프셋은 동일는 [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) 메서드 반환 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="0dd1d-118">디버거는 모든 중단점을 설정 하는 것을 선택을 취소 한 다음 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0dd1d-119">`ICorDebugCode3::GetReturnValueLiveOffset` 및 [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) 방법을 사용 하는 참조 형식만 대 한 반환 값 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="0dd1d-120">값 형식에서의 반환 값 정보 검색 (에서 파생 되는 모든 형식 즉, <xref:System.ValueType>) 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="0dd1d-121">함수 반환은 `HRESULT` 다음 표에 표시 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="0dd1d-122">`HRESULT` 값</span><span class="sxs-lookup"><span data-stu-id="0dd1d-122">`HRESULT` value</span></span>|<span data-ttu-id="0dd1d-123">설명</span><span class="sxs-lookup"><span data-stu-id="0dd1d-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="0dd1d-124">명령 실행 성공</span><span class="sxs-lookup"><span data-stu-id="0dd1d-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="0dd1d-125">지정된 된 IL 오프셋된 사이트 호출 명령을 이거나 함수 반환 `void`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="0dd1d-126">지정된 된 IL 오프셋은 적절 한 호출 하지만 반환 형식을 반환 값을 가져오기 위한 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="0dd1d-127">`ICorDebugCode3::GetReturnValueLiveOffset` 메서드는 x86 기반에 대해서만 사용할 수 및 AMD64 시스템.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dd1d-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0dd1d-128">Requirements</span></span>  
 <span data-ttu-id="0dd1d-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd1d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dd1d-130">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dd1d-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dd1d-131">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dd1d-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dd1d-132">**.NET framework 버전:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dd1d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd1d-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0dd1d-133">See Also</span></span>  
 [<span data-ttu-id="0dd1d-134">GetReturnValueForILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="0dd1d-134">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)  
 [<span data-ttu-id="0dd1d-135">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0dd1d-135">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
