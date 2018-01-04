---
title: "ICorDebugProcess5::GetObject 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetObject
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 285554502271f0e93ff5de08ba593a08ab95eb6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="5535d-102">ICorDebugProcess5::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="5535d-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="5535d-103">개체 주소를 "ICorDebugObjectValue" 개체로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5535d-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5535d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5535d-104">Syntax</span></span>  
  
```  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5535d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5535d-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="5535d-106">[in] 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5535d-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="5535d-107">[out] "ICorDebugObjectValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5535d-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5535d-108">설명</span><span class="sxs-lookup"><span data-stu-id="5535d-108">Remarks</span></span>  
 <span data-ttu-id="5535d-109">경우 `addr` 유효한 관리 되는 개체를 가리키지 않습니다는 `GetObject` 메서드 반환 `E_FAIL`합니다.</span><span class="sxs-lookup"><span data-stu-id="5535d-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5535d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5535d-110">Requirements</span></span>  
 <span data-ttu-id="5535d-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5535d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5535d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5535d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5535d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5535d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5535d-114">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5535d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5535d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5535d-115">See Also</span></span>  
 [<span data-ttu-id="5535d-116">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5535d-116">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="5535d-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5535d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
