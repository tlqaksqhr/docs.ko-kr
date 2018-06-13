---
title: ICorDebugManagedCallback::NameChange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a7ef478fed697f4152a6348931ddf3b4b4b2885
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415011"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="2748f-102">ICorDebugManagedCallback::NameChange 메서드</span><span class="sxs-lookup"><span data-stu-id="2748f-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="2748f-103">응용 프로그램 도메인 또는 스레드의 이름을 변경 된 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2748f-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2748f-104">구문</span><span class="sxs-lookup"><span data-stu-id="2748f-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2748f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2748f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2748f-106">[in] 중 하나에 이름이 변경 되었거나 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터 이름을 변경 하는 스레드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2748f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="2748f-107">[in] 이름을 변경 하는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2748f-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2748f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2748f-108">Requirements</span></span>  
 <span data-ttu-id="2748f-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2748f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2748f-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2748f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2748f-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2748f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2748f-112">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2748f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2748f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2748f-113">See Also</span></span>  
 [<span data-ttu-id="2748f-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2748f-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
