---
title: "ICorDebug::GetProcess 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3acdcb15f22c130601394ee1bb259207e5e3df23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="20f76-102">ICorDebug::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="20f76-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="20f76-103">지정된 된 프로세스에 대 한 "ICorDebugProcess" 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="20f76-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20f76-104">구문</span><span class="sxs-lookup"><span data-stu-id="20f76-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20f76-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20f76-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="20f76-106">[in] 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="20f76-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="20f76-107">[out] 주소에 대 한 포인터는 `ICorDebugProcess` 지정된 된 프로세스에 대 한 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="20f76-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20f76-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20f76-108">Requirements</span></span>  
 <span data-ttu-id="20f76-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20f76-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20f76-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20f76-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20f76-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20f76-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20f76-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20f76-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f76-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20f76-113">See Also</span></span>  
 [<span data-ttu-id="20f76-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20f76-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
