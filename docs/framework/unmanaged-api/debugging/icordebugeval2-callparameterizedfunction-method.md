---
title: "ICorDebugEval2::CallParameterizedFunction 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.CallParameterizedFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 055ded7f3309ff1011d1ca390daf353cba870376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="acc8d-102">ICorDebugEval2::CallParameterizedFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="acc8d-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="acc8d-103">클래스의 생성자 사용에 중첩 될 수 있는 지정 된 ICorDebugFunction에 대 한 호출을 설정 <xref:System.Type> 매개 변수 또는 자체 있습니다 사용할 <xref:System.Type> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acc8d-104">구문</span><span class="sxs-lookup"><span data-stu-id="acc8d-104">Syntax</span></span>  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="acc8d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="acc8d-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="acc8d-106">[in] 에 대 한 포인터는 `ICorDebugFunction` 함수를 호출할 수를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="acc8d-107">[in] 함수에서 사용 하는 인수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="acc8d-108">[in] 함수 인수를 나타내는 ICorDebugType 개체를 가리키는 각각 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="acc8d-109">[in] 값의 수는 함수에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="acc8d-110">[in] 함수 인수에 전달 된 값을 나타내는 ICorDebugValue 개체를 가리키는 각각 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acc8d-111">설명</span><span class="sxs-lookup"><span data-stu-id="acc8d-111">Remarks</span></span>  
 <span data-ttu-id="acc8d-112">`CallParameterizedFunction`비슷합니다 [icordebugeval:: Callfunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) 점을 제외 하 고 함수는 형식 매개 변수를 사용 하 여 클래스 내에 있을 수 있습니다, 걸릴 수 있음을 자체 형식 매개 변수 또는 둘 다 합니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="acc8d-113">클래스를 선택한 다음 함수에 대 한 형식 인수를 먼저 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="acc8d-114">함수가 다른 응용 프로그램 도메인에 포함 된 경우 전환을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="acc8d-115">그러나 형식 및 값에 대 한 모든 인수는 대상 응용 프로그램 도메인에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="acc8d-116">함수 실행은 제한 된 경우에만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="acc8d-117">경우 `CallParameterizedFunction` 또는 `ICorDebugEval::CallFunction` 실패 하면 반환된 된 HRESULT는 오류에 대 한 가능한 가장 일반적인 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acc8d-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="acc8d-118">Requirements</span></span>  
 <span data-ttu-id="acc8d-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="acc8d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acc8d-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acc8d-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acc8d-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acc8d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acc8d-122">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acc8d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
