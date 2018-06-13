---
title: ICorDebugILFrame3::GetReturnValueForILOffset 메서드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 315bd78f660e093ecbf65224bd09a9b4f44300b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420936"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="1d367-102">ICorDebugILFrame3::GetReturnValueForILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="1d367-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="1d367-103">함수의 반환 값을 캡슐화 하는 "ICorDebugValue" 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d367-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d367-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d367-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d367-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="1d367-106">IL 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-106">The IL offset.</span></span> <span data-ttu-id="1d367-107">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d367-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="1d367-108">함수 호출의 반환 값에 대 한 정보를 제공 하는 "ICorDebugValue" 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d367-109">설명</span><span class="sxs-lookup"><span data-stu-id="1d367-109">Remarks</span></span>  
 <span data-ttu-id="1d367-110">이 메서드는와 함께 사용 되는 [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) 메서드의 반환 값을 가져오는 메서드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="1d367-111">다음 두 코드 예제와 같이 반환 값은 무시 되는 메서드의 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="1d367-112">첫 번째 호출에서 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 메서드, 하지만 메서드의 반환 값을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="1d367-113">두 번째 예에서는 디버깅에 훨씬 더 일반적인 문제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="1d367-114">메서드를 메서드 호출에서 인수로 사용 때문에 디버거는 호출된 된 메서드가 단계별로 실행할 때에 해당 반환 값은 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="1d367-115">대부분의 경우에서 특히 호출된 된 메서드에 외부 라이브러리에 정의 된 경우는 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="1d367-116">전달 하는 경우는 [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) 메서드 IL 오프셋 함수 호출 사이트에는 하나 이상의 네이티브 오프셋 간의 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="1d367-117">다음 디버거 함수에서 네이티브 이러한 오프셋에서 중단점을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="1d367-118">디버거는 중단점에 도달 하는 경우 반환 값을이 메서드에 전달 된 동일한 IL 오프셋에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="1d367-119">디버거는 모든 중단점을 설정 하는 것을 선택을 취소 한 다음 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="1d367-120">[icordebugcode3:: Getreturnvalueliveoffset 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) 및 `ICorDebugILFrame3::GetReturnValueForILOffset` 방법을 사용 하는 참조 형식만 대 한 반환 값 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="1d367-121">값 형식에서의 반환 값 정보 검색 (에서 파생 되는 모든 형식 즉, <xref:System.ValueType>) 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="1d367-122">지정 된 IL 오프셋은 `ILOffset` 매개 변수는 함수 호출 사이트에 있어야 하 고 디버기를 중지 하 여 반환한 네이티브 오프셋에 중단점을 설정한에서 해야는 [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) 메서드 에 대 한 동일한 IL 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="1d367-123">지정된 된 IL 오프셋에 대 한 올바른 위치에 중지 되지 않으면 디버기 API 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="1d367-124">함수 호출 값을 반환 하지 않는 경우 API가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="1d367-125">`ICorDebugILFrame3::GetReturnValueForILOffset` 메서드는 x86 기반에 대해서만 사용할 수 및 AMD64 시스템.</span><span class="sxs-lookup"><span data-stu-id="1d367-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d367-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d367-126">Requirements</span></span>  
 <span data-ttu-id="1d367-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d367-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d367-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d367-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d367-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d367-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d367-130">**.NET framework 버전:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d367-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d367-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d367-131">See Also</span></span>  
 [<span data-ttu-id="1d367-132">GetReturnValueLiveOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="1d367-132">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)  
 [<span data-ttu-id="1d367-133">ICorDebugILFrame3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d367-133">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
