---
title: "ICorDebugProcess5::GetArrayLayout 메서드"
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
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 608cf003d71599a141b1009ef16c7b7bf89161aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="d60dc-102">ICorDebugProcess5::GetArrayLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="d60dc-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="d60dc-103">배열 형식의 레이아웃에 대 한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d60dc-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="d60dc-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d60dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d60dc-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="d60dc-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 레이아웃이 필요한 배열을 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d60dc-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="d60dc-107">[out] 에 대 한 포인터는 [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) 메모리에 배열 레이아웃에 대 한 정보가 포함 된 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="d60dc-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d60dc-108">설명</span><span class="sxs-lookup"><span data-stu-id="d60dc-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d60dc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d60dc-109">Requirements</span></span>  
 <span data-ttu-id="d60dc-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d60dc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d60dc-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d60dc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d60dc-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d60dc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d60dc-113">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d60dc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60dc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d60dc-114">See Also</span></span>  
 [<span data-ttu-id="d60dc-115">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d60dc-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="d60dc-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d60dc-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
