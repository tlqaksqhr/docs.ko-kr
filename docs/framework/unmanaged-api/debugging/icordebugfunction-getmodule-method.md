---
title: "ICorDebugFunction::GetModule 메서드"
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
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 59808b2a1de969f7d530a1be4cb500fc32cec33f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="8f23c-102">ICorDebugFunction::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="8f23c-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="8f23c-103">이 함수가 정의 된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f23c-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f23c-104">구문</span><span class="sxs-lookup"><span data-stu-id="8f23c-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f23c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f23c-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="8f23c-106">[out] 이 함수가 정의 된 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f23c-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f23c-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f23c-107">Requirements</span></span>  
 <span data-ttu-id="8f23c-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f23c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f23c-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f23c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f23c-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f23c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f23c-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f23c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
