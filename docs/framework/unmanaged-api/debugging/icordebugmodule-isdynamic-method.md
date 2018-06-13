---
title: ICorDebugModule::IsDynamic 메서드
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5157c62f2719a9d62608750cd122561807197494
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418302"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="5bc7d-102">ICorDebugModule::IsDynamic 메서드</span><span class="sxs-lookup"><span data-stu-id="5bc7d-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="5bc7d-103">이 모듈에 동적 인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bc7d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5bc7d-104">Syntax</span></span>  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bc7d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5bc7d-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="5bc7d-106">[out] `true` 이 모듈이 고, 그렇지 않으면 동적 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bc7d-107">설명</span><span class="sxs-lookup"><span data-stu-id="5bc7d-107">Remarks</span></span>  
 <span data-ttu-id="5bc7d-108">동적 모듈 새 클래스를 추가할 수 있습니다 및 모듈을 로드 한 후에 기존 클래스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="5bc7d-109">[icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 및 [icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) 콜백을 클래스 때 추가 또는 삭제 되었음을 디버거에 알리기.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bc7d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bc7d-110">Requirements</span></span>  
 <span data-ttu-id="5bc7d-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bc7d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bc7d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bc7d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bc7d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bc7d-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bc7d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
