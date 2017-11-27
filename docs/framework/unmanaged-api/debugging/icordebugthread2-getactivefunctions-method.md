---
title: "ICorDebugThread2::GetActiveFunctions 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetActiveFunctions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1f7f416a5441b788394e93a98d274d02fa2ec2f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="203e7-102">ICorDebugThread2::GetActiveFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="203e7-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="203e7-103">각이 스레드 프레임에서 현재 함수에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="203e7-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="203e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="203e7-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="203e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="203e7-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="203e7-106">[in] `pFunctions` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="203e7-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="203e7-107">[out] 반환 되는 개체의 수에 대 한 포인터는 `pFunctions` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="203e7-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="203e7-108">반환 된 개체 수는 관리 되는 스택 프레임의 수와 같지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="203e7-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="203e7-109">[out에서] 이 스레드 프레임에서 현재 함수에 대 한 정보를 포함 하며 각 COR_ACTIVE_FUNCTION 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="203e7-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="203e7-110">리프 프레임 및 스택 루트까지 이어집니다에 대 한 첫 번째 요소를 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="203e7-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="203e7-111">설명</span><span class="sxs-lookup"><span data-stu-id="203e7-111">Remarks</span></span>  
 <span data-ttu-id="203e7-112">경우 `pFunctions` 입력 시 null `GetActiveFunctions` 스택에 있는 함수의 수만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="203e7-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="203e7-113">즉, 경우 `pFunctions` 입력 시 null `GetActiveFunctions` 값을 반환에 `pcFunctions`합니다.</span><span class="sxs-lookup"><span data-stu-id="203e7-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="203e7-114">`GetActiveFunctions` 메서드는 스택 추적에는 프레임에서 동일한 정보를 가져오는 최적화로 위한 것 이며 프레임 했지만 이제 ICorDebugILFrame 개체에는 전체 스택 추적을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="203e7-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="203e7-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="203e7-115">Requirements</span></span>  
 <span data-ttu-id="203e7-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="203e7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="203e7-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="203e7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="203e7-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="203e7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="203e7-119">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="203e7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
