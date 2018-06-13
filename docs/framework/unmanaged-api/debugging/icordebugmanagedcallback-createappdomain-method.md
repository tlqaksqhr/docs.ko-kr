---
title: ICorDebugManagedCallback::CreateAppDomain 메서드
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdac4b5b7a4a64a5fc939a7d35718ef276717fe7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415430"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="dc232-102">ICorDebugManagedCallback::CreateAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="dc232-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="dc232-103">응용 프로그램 도메인을 이미 만들었다고 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="dc232-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc232-104">구문</span><span class="sxs-lookup"><span data-stu-id="dc232-104">Syntax</span></span>  
  
```  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dc232-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc232-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="dc232-106">[in] 응용 프로그램 도메인 생성 된 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc232-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="dc232-107">[in] 생성 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc232-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc232-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc232-108">Requirements</span></span>  
 <span data-ttu-id="dc232-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc232-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc232-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc232-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc232-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc232-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc232-112">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc232-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc232-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc232-113">See Also</span></span>  
 [<span data-ttu-id="dc232-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc232-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
