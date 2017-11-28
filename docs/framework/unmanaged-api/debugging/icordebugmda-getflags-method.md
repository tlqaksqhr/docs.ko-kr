---
title: "ICorDebugMDA::GetFlags 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1388356cb3c67c1a4b292931710dc72323ed6da8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="ecb6d-102">ICorDebugMDA::GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="ecb6d-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="ecb6d-103">관리 디버깅 도우미 (MDA) 표시와 관련 된 플래그를 가져옵니다 [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6d-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecb6d-104">구문</span><span class="sxs-lookup"><span data-stu-id="ecb6d-104">Syntax</span></span>  
  
```  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecb6d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ecb6d-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="ecb6d-106">[in] 비트 조합 된 [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) 이 MDA에 대 한 플래그의 설정을 지정 하는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6d-106">[in] A bitwise combination of the [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecb6d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ecb6d-107">Requirements</span></span>  
 <span data-ttu-id="ecb6d-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecb6d-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecb6d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecb6d-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecb6d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecb6d-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecb6d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecb6d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecb6d-112">See Also</span></span>  
 [<span data-ttu-id="ecb6d-113">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ecb6d-113">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="ecb6d-114">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="ecb6d-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
