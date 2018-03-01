---
title: "ICorDebugAppDomain::EnumerateBreakpoints 메서드"
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
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2363b3159bef4453eb3eeb910d3d304806c56e6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="26b7c-102">ICorDebugAppDomain::EnumerateBreakpoints 메서드</span><span class="sxs-lookup"><span data-stu-id="26b7c-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="26b7c-103">응용 프로그램 도메인에서 활성화 된 모든 중단점에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="26b7c-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26b7c-104">구문</span><span class="sxs-lookup"><span data-stu-id="26b7c-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26b7c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="26b7c-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="26b7c-106">[out] 응용 프로그램 도메인에서 활성화 된 모든 중단점에 대 한 열거자를 ICorDebugBreakpointEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="26b7c-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26b7c-107">설명</span><span class="sxs-lookup"><span data-stu-id="26b7c-107">Remarks</span></span>  
 <span data-ttu-id="26b7c-108">열거자에는 모든 유형의 중단점, 중단점 함수 및 데이터 중단점을 포함 하 여 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="26b7c-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26b7c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26b7c-109">Requirements</span></span>  
 <span data-ttu-id="26b7c-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26b7c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26b7c-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26b7c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26b7c-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26b7c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26b7c-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26b7c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
