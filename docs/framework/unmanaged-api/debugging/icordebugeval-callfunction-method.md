---
title: ICorDebugEval::CallFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86d48461c601b53d4461331a11a0e0ac7ddc6e7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412554"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="3dbee-102">ICorDebugEval::CallFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="3dbee-102">ICorDebugEval::CallFunction Method</span></span>
<span data-ttu-id="3dbee-103">지정된 된 함수에 대 한 호출을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbee-103">Sets up a call to the specified function.</span></span>  
  
 <span data-ttu-id="3dbee-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbee-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="3dbee-105">사용 하 여 [icordebugeval2:: Callparameterizedfunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbee-105">Use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dbee-106">구문</span><span class="sxs-lookup"><span data-stu-id="3dbee-106">Syntax</span></span>  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3dbee-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3dbee-107">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="3dbee-108">[in] 함수 호출 수를 지정 하는 ICorDebugFunction 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbee-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="3dbee-109">[in] 함수에 대 한 인수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbee-109">[in] The number of arguments for the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="3dbee-110">[in] 함수에 전달 될 인수를 지정 하는 ICorDebugValue 개체를 가리키는 각각 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbee-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dbee-111">설명</span><span class="sxs-lookup"><span data-stu-id="3dbee-111">Remarks</span></span>  
 <span data-ttu-id="3dbee-112">함수는 virtual 이거나 경우 `CallFunction` 가상 디스패치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbee-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="3dbee-113">함수는 다른 응용 프로그램 도메인에 있으면 모든 인수에에서도 포함 되어 해당 응용 프로그램 도메인으로 전환이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbee-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dbee-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3dbee-114">Requirements</span></span>  
 <span data-ttu-id="3dbee-115">**플랫폼:** WindowSee [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbee-115">**Platforms:** WindowSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dbee-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dbee-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dbee-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dbee-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dbee-118">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="3dbee-118">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dbee-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3dbee-119">See Also</span></span>  
 [<span data-ttu-id="3dbee-120">CallParameterizedFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="3dbee-120">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
