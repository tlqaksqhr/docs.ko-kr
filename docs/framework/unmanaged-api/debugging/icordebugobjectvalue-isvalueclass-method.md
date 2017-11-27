---
title: "ICorDebugObjectValue::IsValueClass 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue.IsValueClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b504a9fe28ee72ae8a394359f1f1ef51e7d9d3af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="9ceeb-102">ICorDebugObjectValue::IsValueClass 메서드</span><span class="sxs-lookup"><span data-stu-id="9ceeb-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="9ceeb-103">이 개체 값에는 값 형식 인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9ceeb-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ceeb-104">구문</span><span class="sxs-lookup"><span data-stu-id="9ceeb-104">Syntax</span></span>  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ceeb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ceeb-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="9ceeb-106">[out] 부울 값이에 대 한 포인터 `true` 이 "ICorDebugObjectValue"으로 표시 된 개체 값을이; 참조 형식이 아닌 값 형식, `pbIsValueClass` 은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ceeb-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ceeb-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ceeb-107">Requirements</span></span>  
 <span data-ttu-id="9ceeb-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ceeb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ceeb-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ceeb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ceeb-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ceeb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ceeb-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ceeb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ceeb-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ceeb-112">See Also</span></span>  
    
 
