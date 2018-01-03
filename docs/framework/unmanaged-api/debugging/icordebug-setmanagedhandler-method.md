---
title: "ICorDebug::SetManagedHandler 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.SetManagedHandler
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dde32b6a8251474c4254e35a3a1ba3ba3bafcb8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="b3ef1-102">ICorDebug::SetManagedHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="b3ef1-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="b3ef1-103">관리 되는 이벤트에 대 한 이벤트 처리기 개체를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3ef1-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3ef1-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3ef1-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3ef1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3ef1-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="b3ef1-106">[in] 에 대 한 포인터는 [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) 개체의 이벤트 처리기 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b3ef1-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3ef1-107">설명</span><span class="sxs-lookup"><span data-stu-id="b3ef1-107">Remarks</span></span>  
 <span data-ttu-id="b3ef1-108">`SetManagedHandler`생성 시 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3ef1-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="b3ef1-109">경우는 `ICorDebugManagedCallback` 구현에는 디버깅 중인 응용 프로그램에 대 한 디버깅 이벤트를 처리 하기 위해 충분 한 인터페이스 `SetManagedHandler` 는 E_NOINTERFACE HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3ef1-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3ef1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3ef1-110">Requirements</span></span>  
 <span data-ttu-id="b3ef1-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3ef1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3ef1-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3ef1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3ef1-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3ef1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3ef1-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3ef1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ef1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3ef1-115">See Also</span></span>  
 [<span data-ttu-id="b3ef1-116">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3ef1-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
