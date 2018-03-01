---
title: "ICorDebugModule::GetAssembly 메서드"
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
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7b359b68c1bff91e1077afe8ccf52befe22c246b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="d45a0-102">ICorDebugModule::GetAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="d45a0-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="d45a0-103">이 모듈에 대 한 포함 하는 어셈블리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d45a0-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d45a0-104">구문</span><span class="sxs-lookup"><span data-stu-id="d45a0-104">Syntax</span></span>  
  
```  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d45a0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d45a0-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="d45a0-106">[out] 이 모듈을 포함 하는 어셈블리를 나타내는 ICorDebugAssembly 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d45a0-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d45a0-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d45a0-107">Requirements</span></span>  
 <span data-ttu-id="d45a0-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d45a0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d45a0-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d45a0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d45a0-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d45a0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d45a0-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d45a0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
