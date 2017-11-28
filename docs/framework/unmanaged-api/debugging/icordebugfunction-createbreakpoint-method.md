---
title: "ICorDebugFunction::CreateBreakpoint 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.CreateBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 68501943e1ac32cd39a3cdc674935c1c5705f911
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="3b5e8-102">ICorDebugFunction::CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="3b5e8-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="3b5e8-103">이 함수의 시작 부분에 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b5e8-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b5e8-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b5e8-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b5e8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b5e8-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="3b5e8-106">[out] 함수에 대 한 새 중단점을 나타내는 ICorDebugFunctionBreakpoint 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3b5e8-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b5e8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b5e8-107">Requirements</span></span>  
 <span data-ttu-id="3b5e8-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b5e8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b5e8-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b5e8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b5e8-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b5e8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b5e8-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b5e8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
