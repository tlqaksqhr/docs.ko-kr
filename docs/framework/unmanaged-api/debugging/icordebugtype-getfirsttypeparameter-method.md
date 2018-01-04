---
title: "ICorDebugType::GetFirstTypeParameter 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetFirstTypeParameter
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e963553bfeac2d659de8fc460a938d2d523b53e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="da64b-102">ICorDebugType::GetFirstTypeParameter 메서드</span><span class="sxs-lookup"><span data-stu-id="da64b-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="da64b-103">첫 번째 나타내는 ICorDebugType에 대 한 인터페이스 포인터를 가져옵니다 <xref:System.Type> 이 표시 되는 형식의 매개 변수 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="da64b-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da64b-104">구문</span><span class="sxs-lookup"><span data-stu-id="da64b-104">Syntax</span></span>  
  
```  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da64b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da64b-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="da64b-106">[out] 주소에 대 한 포인터는 `ICorDebugType` 첫 번째 매개 변수를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="da64b-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da64b-107">설명</span><span class="sxs-lookup"><span data-stu-id="da64b-107">Remarks</span></span>  
 <span data-ttu-id="da64b-108">`GetFirstTypeParameter`호출할 수 있습니다 유형에 대 한 추가 정보를 포함 되는 있는 경우에서 하나의 형식 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="da64b-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="da64b-109">특히, 사용할 수 있습니다 형식이 ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, 또는 ELEMENT_TYPE_PTR, 경우에 표시 된 대로 [icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="da64b-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da64b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da64b-110">Requirements</span></span>  
 <span data-ttu-id="da64b-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="da64b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da64b-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da64b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da64b-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da64b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da64b-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da64b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
