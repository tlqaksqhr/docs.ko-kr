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
ms.openlocfilehash: 07f76d8add6c8b0e44eba241b7787b8e8a2de570
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="c3df7-102">ICorDebugManagedCallback::ExitAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="c3df7-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="c3df7-103">응용 프로그램 도메인이 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c3df7-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3df7-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3df7-104">Syntax</span></span>  
  
```  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3df7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3df7-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="c3df7-106">[in] 특정된 응용 프로그램 도메인을 포함 하는 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3df7-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="c3df7-107">[in] 종료 될 때 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3df7-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3df7-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3df7-108">Requirements</span></span>  
 <span data-ttu-id="c3df7-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3df7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3df7-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3df7-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3df7-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3df7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3df7-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3df7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3df7-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3df7-113">See Also</span></span>  
 [<span data-ttu-id="c3df7-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3df7-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
