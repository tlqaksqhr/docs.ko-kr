---
title: ICorDebugBreakpoint::Activate 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82dad6af545464baade2b82d65e7ad4dba19fe3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402342"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="b2ce1-102">ICorDebugBreakpoint::Activate 메서드</span><span class="sxs-lookup"><span data-stu-id="b2ce1-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="b2ce1-103">이 활성 상태를 설정 `ICorDebugBreakpoint`합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ce1-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2ce1-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2ce1-104">Syntax</span></span>  
  
```  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2ce1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2ce1-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="b2ce1-106">[in] 이 값을 설정 `true` 으로 활성화 상태를 지정 하려면 그렇지 않은 경우이 값을 설정 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ce1-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2ce1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2ce1-107">Requirements</span></span>  
 <span data-ttu-id="b2ce1-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ce1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2ce1-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2ce1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2ce1-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2ce1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2ce1-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2ce1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
