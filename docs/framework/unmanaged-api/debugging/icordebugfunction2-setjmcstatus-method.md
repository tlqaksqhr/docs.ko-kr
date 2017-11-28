---
title: "ICorDebugFunction2::SetJMCStatus 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ecbcd5b8171a169fbfdd7175d3d9dfbbcb3855f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="6782d-102">ICorDebugFunction2::SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="6782d-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="6782d-103">내 코드만 5d;에 대 한이 ICorDebugFunction2 함수가 표시 단계별로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6782d-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6782d-104">구문</span><span class="sxs-lookup"><span data-stu-id="6782d-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6782d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6782d-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="6782d-106">[in] 로 설정 `true` 사용자 코드; 함수로 표시를 그렇지 설정 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="6782d-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="6782d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6782d-107">Return Values</span></span>  
  
|<span data-ttu-id="6782d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6782d-108">HRESULT</span></span>|<span data-ttu-id="6782d-109">설명</span><span class="sxs-lookup"><span data-stu-id="6782d-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6782d-110">함수를 표시 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6782d-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="6782d-111">디버깅할 수 없는 사용자가 코드로 함수를 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6782d-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6782d-112">설명</span><span class="sxs-lookup"><span data-stu-id="6782d-112">Remarks</span></span>  
 <span data-ttu-id="6782d-113">내 코드만 스텝 퍼에 사용자 코드가 아닌 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="6782d-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="6782d-114">사용자 코드를 디버깅할 수 있는 코드의 하위 집합 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6782d-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6782d-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6782d-115">Requirements</span></span>  
 <span data-ttu-id="6782d-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6782d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6782d-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6782d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6782d-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6782d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6782d-119">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6782d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
