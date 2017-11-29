---
title: "ICorDebugModule::EnableClassLoadCallbacks 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.EnableClassLoadCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9045cceda54e6fe89c8c1baa8d4b9fa63105607
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="48df4-102">ICorDebugModule::EnableClassLoadCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="48df4-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="48df4-103">컨트롤 여부는 [icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 및 [icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) 이 모듈에 대 한 콜백을 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48df4-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48df4-104">구문</span><span class="sxs-lookup"><span data-stu-id="48df4-104">Syntax</span></span>  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48df4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48df4-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="48df4-106">[in] 이 값을 설정 `true` 공용 언어 런타임 (CLR) 호출을 사용 하 여 `ICorDebugManagedCallback::LoadClass` 및 `ICorDebugManagedCallback::UnloadClass` 관련된 이벤트가 발생할 때 메서드.</span><span class="sxs-lookup"><span data-stu-id="48df4-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="48df4-107">기본값은 `false` 동적이 지 않은 모듈에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="48df4-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="48df4-108">값은 항상 `true` 동적 모듈에 대 한 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48df4-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48df4-109">설명</span><span class="sxs-lookup"><span data-stu-id="48df4-109">Remarks</span></span>  
 <span data-ttu-id="48df4-110">`ICorDebugManagedCallback::LoadClass` 및 `ICorDebugManagedCallback::UnloadClass` 콜백을 동적 모듈의 항상 사용 하도록 설정 하 고 비활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48df4-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48df4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48df4-111">Requirements</span></span>  
 <span data-ttu-id="48df4-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48df4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48df4-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48df4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48df4-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48df4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48df4-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48df4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48df4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48df4-116">See Also</span></span>  
    
 
