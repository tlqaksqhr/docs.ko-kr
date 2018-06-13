---
title: ICorDebugAppDomain::EnumerateBreakpoints 메서드
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfd7ee890a7f2c3ea8cd3de9fbe830575c0ca10c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402776"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="83dd6-102">ICorDebugAppDomain::EnumerateBreakpoints 메서드</span><span class="sxs-lookup"><span data-stu-id="83dd6-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="83dd6-103">응용 프로그램 도메인에서 활성화 된 모든 중단점에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="83dd6-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83dd6-104">구문</span><span class="sxs-lookup"><span data-stu-id="83dd6-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83dd6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83dd6-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="83dd6-106">[out] 응용 프로그램 도메인에서 활성화 된 모든 중단점에 대 한 열거자를 ICorDebugBreakpointEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="83dd6-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83dd6-107">설명</span><span class="sxs-lookup"><span data-stu-id="83dd6-107">Remarks</span></span>  
 <span data-ttu-id="83dd6-108">열거자에는 모든 유형의 중단점, 중단점 함수 및 데이터 중단점을 포함 하 여 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="83dd6-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83dd6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83dd6-109">Requirements</span></span>  
 <span data-ttu-id="83dd6-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83dd6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83dd6-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83dd6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83dd6-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83dd6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83dd6-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83dd6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
