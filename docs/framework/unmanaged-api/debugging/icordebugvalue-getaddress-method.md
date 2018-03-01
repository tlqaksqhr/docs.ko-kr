---
title: "ICorDebugValue::GetAddress 메서드"
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
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8aa5a0c3740b6cf97d2a5d855343a36b90fd538
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="45022-102">ICorDebugValue::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="45022-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="45022-103">디버깅 중인 프로세스에 있는이 "ICorDebugValue" 개체의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45022-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45022-104">구문</span><span class="sxs-lookup"><span data-stu-id="45022-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45022-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="45022-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="45022-106">[out] 에 대 한 포인터는 `CORDB_ADDRESS` 이 값 개체의 주소를 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="45022-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45022-107">설명</span><span class="sxs-lookup"><span data-stu-id="45022-107">Remarks</span></span>  
 <span data-ttu-id="45022-108">값에 사용할 수 없는 경우 0 (영)이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45022-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="45022-109">이 가비지 수집기 핸들에 저장 된 나 레지스터에 부분적으로 이상 값이 발생할 수 없습니다 (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="45022-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45022-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45022-110">Requirements</span></span>  
 <span data-ttu-id="45022-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45022-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45022-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45022-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45022-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45022-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45022-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45022-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45022-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45022-115">See Also</span></span>  
 
