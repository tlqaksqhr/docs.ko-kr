---
title: ICorDebugFunctionBreakpoint::GetOffset 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetOffset
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: e619eae4-3ac3-4c37-bba4-55e59989b9cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aca1d77ace512ca84cda3b6844d214e4c8d6cad7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412067"
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a><span data-ttu-id="10dc7-102">ICorDebugFunctionBreakpoint::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="10dc7-102">ICorDebugFunctionBreakpoint::GetOffset Method</span></span>
<span data-ttu-id="10dc7-103">함수 내에서 중단점의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10dc7-103">Gets the offset of the breakpoint within the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10dc7-104">구문</span><span class="sxs-lookup"><span data-stu-id="10dc7-104">Syntax</span></span>  
  
```  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10dc7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10dc7-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="10dc7-106">[out] 중단점의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="10dc7-106">[out] A pointer to the offset of the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10dc7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10dc7-107">Requirements</span></span>  
 <span data-ttu-id="10dc7-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10dc7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10dc7-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10dc7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10dc7-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10dc7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10dc7-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10dc7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
