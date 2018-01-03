---
title: "ICorDebugManagedCallback::CreateProcess 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.CreateProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 14c2219f1a328b3e48380c7c31f705b79da3b1ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="96a4f-102">ICorDebugManagedCallback::CreateProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="96a4f-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="96a4f-103">프로세스 연결 되거나 처음으로 시작 하는 경우 디버거를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96a4f-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96a4f-104">구문</span><span class="sxs-lookup"><span data-stu-id="96a4f-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96a4f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96a4f-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="96a4f-106">[in] 연결 되거나 시작 된 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="96a4f-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96a4f-107">설명</span><span class="sxs-lookup"><span data-stu-id="96a4f-107">Remarks</span></span>  
 <span data-ttu-id="96a4f-108">공용 언어 런타임 초기화 될 때까지이 메서드가 호출 되지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96a4f-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="96a4f-109">대부분의 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 메서드 전에 CORDBG_E_NOTREADY 돌아갑니다는 `CreateProcess` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="96a4f-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96a4f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96a4f-110">Requirements</span></span>  
 <span data-ttu-id="96a4f-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96a4f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96a4f-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96a4f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96a4f-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96a4f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96a4f-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96a4f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a4f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96a4f-115">See Also</span></span>  
 [<span data-ttu-id="96a4f-116">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="96a4f-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
