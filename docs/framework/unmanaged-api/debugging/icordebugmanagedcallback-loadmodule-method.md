---
title: ICorDebugManagedCallback::LoadModule 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbf538f066058b4f80d8cfd6cdf1a79683c79be9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413419"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="9ae09-102">ICorDebugManagedCallback::LoadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="9ae09-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="9ae09-103">공용 언어 런타임 (CLR) 모듈 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9ae09-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ae09-104">구문</span><span class="sxs-lookup"><span data-stu-id="9ae09-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ae09-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ae09-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9ae09-106">[in] 모듈 로드 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae09-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="9ae09-107">[in] CLR 모듈을 나타내는 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9ae09-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ae09-108">설명</span><span class="sxs-lookup"><span data-stu-id="9ae09-108">Remarks</span></span>  
 <span data-ttu-id="9ae09-109">`LoadModule` 콜백 모듈에 대 한 메타 데이터를 검사 또는, 적시에 (JIT) 컴파일러 플래그를 설정 하거나 사용 모듈에 대 한 콜백을 로드 하는 클래스를 사용 하지 않도록 설정 하려면 적절 한 시간을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae09-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ae09-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ae09-110">Requirements</span></span>  
 <span data-ttu-id="9ae09-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ae09-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ae09-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ae09-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ae09-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ae09-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ae09-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ae09-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae09-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ae09-115">See Also</span></span>  
 [<span data-ttu-id="9ae09-116">UnloadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="9ae09-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)  
 [<span data-ttu-id="9ae09-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ae09-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
