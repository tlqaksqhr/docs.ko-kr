---
title: "ICorDebugManagedCallback::ExitAppDomain 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ExitAppDomain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 352ea9b93059237526edad41ec56f200d399a60f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="302ba-102">ICorDebugManagedCallback::ExitAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="302ba-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="302ba-103">응용 프로그램 도메인이 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="302ba-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="302ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="302ba-104">Syntax</span></span>  
  
```  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="302ba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="302ba-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="302ba-106">[in] 특정된 응용 프로그램 도메인을 포함 하는 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="302ba-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="302ba-107">[in] 종료 될 때 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="302ba-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="302ba-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="302ba-108">Requirements</span></span>  
 <span data-ttu-id="302ba-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="302ba-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="302ba-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="302ba-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="302ba-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="302ba-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="302ba-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="302ba-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="302ba-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="302ba-113">See Also</span></span>  
 [<span data-ttu-id="302ba-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="302ba-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
