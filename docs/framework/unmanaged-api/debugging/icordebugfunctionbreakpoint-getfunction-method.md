---
title: "ICorDebugFunctionBreakpoint::GetFunction 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunctionBreakpoint.GetFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunctionBreakpoint::GetFunction
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetFunction method [.NET Framework debugging]
- GetFunction method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 2a62dae5-dd8a-4696-b817-0e1e586c24a0
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b9e59c26053d2eec534ca1cd56cf0ed277f87fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="e5b48-102">ICorDebugFunctionBreakpoint::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="e5b48-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="e5b48-103">중단점이 설정 함수를 참조 하는 ICorDebugFunction에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e5b48-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5b48-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5b48-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5b48-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5b48-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="e5b48-106">[out] 중단점이 설정 된 함수의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b48-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5b48-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5b48-107">Requirements</span></span>  
 <span data-ttu-id="e5b48-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b48-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5b48-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5b48-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5b48-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5b48-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5b48-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5b48-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
