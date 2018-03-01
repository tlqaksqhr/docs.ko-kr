---
title: "ICorDebugThread::GetObject 메서드"
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
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7c7802b51a8012b46b1d0bd9de5fbe9d3c6ff0da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="7f3e6-102">ICorDebugThread::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="7f3e6-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="7f3e6-103">공용 언어 런타임 (CLR) 스레드에서에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f3e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f3e6-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f3e6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f3e6-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="7f3e6-106">[out] CLR 스레드를 나타내는 ICorDebugValue 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f3e6-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f3e6-107">Requirements</span></span>  
 <span data-ttu-id="7f3e6-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3e6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f3e6-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f3e6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f3e6-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f3e6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f3e6-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f3e6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f3e6-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f3e6-112">See Also</span></span>  
 <xref:System.Threading.Thread>
