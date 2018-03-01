---
title: "ICorDebug::EnumerateProcesses 메서드"
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
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4ffabcc97a4af33fc859cd096e671f98d52e89e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="160f6-102">ICorDebug::EnumerateProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="160f6-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="160f6-103">디버깅 중인 프로세스에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="160f6-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="160f6-104">구문</span><span class="sxs-lookup"><span data-stu-id="160f6-104">Syntax</span></span>  
  
```  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="160f6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="160f6-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="160f6-106">디버깅 중인 프로세스에 대 한 열거자를 ICorDebugProcessEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="160f6-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="160f6-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="160f6-107">Requirements</span></span>  
 <span data-ttu-id="160f6-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="160f6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="160f6-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="160f6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="160f6-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="160f6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="160f6-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="160f6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="160f6-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="160f6-112">See Also</span></span>  
 [<span data-ttu-id="160f6-113">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="160f6-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
