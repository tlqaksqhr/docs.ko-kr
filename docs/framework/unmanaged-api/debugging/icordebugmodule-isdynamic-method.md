---
title: "ICorDebugModule::IsDynamic 메서드"
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
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b9d7ae1a8619e3d259b6dd44c6b7b0a1c7c057c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="3e853-102">ICorDebugModule::IsDynamic 메서드</span><span class="sxs-lookup"><span data-stu-id="3e853-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="3e853-103">이 모듈에 동적 인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3e853-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e853-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e853-104">Syntax</span></span>  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e853-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e853-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="3e853-106">[out] `true` 이 모듈이 고, 그렇지 않으면 동적 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="3e853-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e853-107">설명</span><span class="sxs-lookup"><span data-stu-id="3e853-107">Remarks</span></span>  
 <span data-ttu-id="3e853-108">동적 모듈 새 클래스를 추가할 수 있습니다 및 모듈을 로드 한 후에 기존 클래스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e853-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="3e853-109">[icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 및 [icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) 콜백을 클래스 때 추가 또는 삭제 되었음을 디버거에 알리기.</span><span class="sxs-lookup"><span data-stu-id="3e853-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e853-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e853-110">Requirements</span></span>  
 <span data-ttu-id="3e853-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e853-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e853-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e853-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e853-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e853-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e853-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e853-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
