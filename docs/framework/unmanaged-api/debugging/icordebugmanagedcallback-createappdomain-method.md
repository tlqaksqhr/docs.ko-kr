---
title: "ICorDebugManagedCallback::CreateAppDomain 메서드"
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
- ICorDebugManagedCallback.CreateAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateAppDomain
helpviewer_keywords:
- CreateAppDomain method [.NET Framework debugging]
- ICorDebugManagedCallback::CreateAppDomain method [.NET Framework debugging]
ms.assetid: 48d410d7-6749-4125-a8fd-f9562c7088e9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f0f9b6322ee391edaba73e0c222b75aa86eee7e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="349e6-102">ICorDebugManagedCallback::CreateAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="349e6-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="349e6-103">응용 프로그램 도메인을 이미 만들었다고 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="349e6-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="349e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="349e6-104">Syntax</span></span>  
  
```  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="349e6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="349e6-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="349e6-106">[in] 응용 프로그램 도메인 생성 된 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="349e6-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="349e6-107">[in] 생성 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="349e6-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="349e6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="349e6-108">Requirements</span></span>  
 <span data-ttu-id="349e6-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="349e6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="349e6-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="349e6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="349e6-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="349e6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="349e6-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="349e6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="349e6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="349e6-113">See Also</span></span>  
 [<span data-ttu-id="349e6-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="349e6-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
