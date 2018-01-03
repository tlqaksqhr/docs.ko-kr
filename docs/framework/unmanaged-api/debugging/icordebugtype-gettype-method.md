---
title: "ICorDebugType::GetType 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c07f9974d0178a1a7502a97d54d7103ee795425f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="97d39-102">ICorDebugType::GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="97d39-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="97d39-103">공용 언어 런타임 (CLR)의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다 <xref:System.Type> 이 ICorDebugType로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d39-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97d39-104">구문</span><span class="sxs-lookup"><span data-stu-id="97d39-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97d39-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97d39-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="97d39-106">[out] 값에 대 한 포인터는 `CorElementType` CLR를 나타내는 열거형 <xref:System.Type> 이 `ICorDebugType` 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="97d39-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97d39-107">설명</span><span class="sxs-lookup"><span data-stu-id="97d39-107">Remarks</span></span>  
 <span data-ttu-id="97d39-108">하는 경우의 값 `ty` ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE는 [icordebugtype:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) 방법으로 인스턴스화되지 않은 형식을 제네릭 형식에 대 한 가져오기 위해 호출할 수 있습니다; 그리고 그렇지 않으면 호출 하지 않으면 `ICorDebugType::GetClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="97d39-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97d39-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97d39-109">Requirements</span></span>  
 <span data-ttu-id="97d39-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="97d39-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97d39-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97d39-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97d39-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97d39-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97d39-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97d39-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
