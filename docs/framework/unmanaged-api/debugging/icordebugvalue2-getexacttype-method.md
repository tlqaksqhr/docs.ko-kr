---
title: ICorDebugValue2::GetExactType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1f8292a6964a6b25e228fcd07ab21a7ee5f5a04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423334"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="9bc60-102">ICorDebugValue2::GetExactType 메서드</span><span class="sxs-lookup"><span data-stu-id="9bc60-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="9bc60-103">나타내는 "ICorDebugType" 개체에 대 한 인터페이스 포인터를 가져옵니다는 <xref:System.Type> 이 값의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bc60-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bc60-104">구문</span><span class="sxs-lookup"><span data-stu-id="9bc60-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bc60-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9bc60-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="9bc60-106">[out] 주소에 대 한 포인터는 `ICorDebugType` 을 나타내는 개체는 <xref:System.Type> 값이 "ICorDebugValue2" 개체로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bc60-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bc60-107">설명</span><span class="sxs-lookup"><span data-stu-id="9bc60-107">Remarks</span></span>  
 <span data-ttu-id="9bc60-108">제네릭 인식 `GetExactType` 메서드 둘 다 대체는 [icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) 및 [icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) 메서드, 각 값의 형식에 대 한 정보 반환 .</span><span class="sxs-lookup"><span data-stu-id="9bc60-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bc60-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bc60-109">Requirements</span></span>  
 <span data-ttu-id="9bc60-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9bc60-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bc60-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bc60-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bc60-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bc60-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bc60-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bc60-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc60-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bc60-114">See Also</span></span>  
 
