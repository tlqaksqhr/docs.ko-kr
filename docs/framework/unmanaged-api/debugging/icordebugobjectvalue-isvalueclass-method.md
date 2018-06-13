---
title: ICorDebugObjectValue::IsValueClass 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7deab95db2e7ccfd167f3158f0f008c6b077a012
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416441"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="e0e61-102">ICorDebugObjectValue::IsValueClass 메서드</span><span class="sxs-lookup"><span data-stu-id="e0e61-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="e0e61-103">이 개체 값에는 값 형식 인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0e61-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0e61-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0e61-104">Syntax</span></span>  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0e61-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0e61-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="e0e61-106">[out] 부울 값이에 대 한 포인터 `true` 이 "ICorDebugObjectValue"으로 표시 된 개체 값을이; 참조 형식이 아닌 값 형식, `pbIsValueClass` 은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e61-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0e61-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0e61-107">Requirements</span></span>  
 <span data-ttu-id="e0e61-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e61-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0e61-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0e61-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0e61-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0e61-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0e61-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0e61-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e61-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0e61-112">See Also</span></span>  
    
 
