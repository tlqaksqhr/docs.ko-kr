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
ms.openlocfilehash: 8966b113e331488a27664de8d42eca4c2db5e51e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="d6a22-102">ICorDebugProcess5::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="d6a22-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="d6a22-103">개체 주소를 "ICorDebugObjectValue" 개체로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a22-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6a22-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6a22-104">Syntax</span></span>  
  
```  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6a22-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d6a22-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="d6a22-106">[in] 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a22-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="d6a22-107">[out] "ICorDebugObjectValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d6a22-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6a22-108">설명</span><span class="sxs-lookup"><span data-stu-id="d6a22-108">Remarks</span></span>  
 <span data-ttu-id="d6a22-109">경우 `addr` 유효한 관리 되는 개체를 가리키지 않습니다는 `GetObject` 메서드 반환 `E_FAIL`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a22-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6a22-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6a22-110">Requirements</span></span>  
 <span data-ttu-id="d6a22-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6a22-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6a22-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6a22-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6a22-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6a22-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6a22-114">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6a22-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6a22-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6a22-115">See Also</span></span>  
 [<span data-ttu-id="d6a22-116">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6a22-116">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="d6a22-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6a22-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
