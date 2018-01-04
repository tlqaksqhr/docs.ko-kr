---
title: "ICorDebugProcess5::GetTypeLayout 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeLayout
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4317fd374646dd5187a94f3e91cc88df939ed762
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="26d41-102">ICorDebugProcess5::GetTypeLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="26d41-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="26d41-103">유형 식별자를 기반으로 메모리에 개체의 레이아웃에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="26d41-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26d41-104">구문</span><span class="sxs-lookup"><span data-stu-id="26d41-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26d41-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="26d41-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="26d41-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 레이아웃이 필요한 형식을 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="26d41-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="26d41-107">[out] 에 대 한 포인터는 [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) 메모리에 있는 개체의 레이아웃에 대 한 정보가 포함 된 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="26d41-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26d41-108">설명</span><span class="sxs-lookup"><span data-stu-id="26d41-108">Remarks</span></span>  
 <span data-ttu-id="26d41-109">`ICorDebugProcess5::GetTypeLayout` 기준으로 개체에 대 한 정보를 제공 하는 메서드는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), 여러 개의 다른에서 반환 된 [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="26d41-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="26d41-110">정보는 [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) 메서드에 의해 채워지는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="26d41-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26d41-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26d41-111">Requirements</span></span>  
 <span data-ttu-id="26d41-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26d41-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26d41-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26d41-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26d41-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26d41-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26d41-115">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26d41-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d41-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26d41-116">See Also</span></span>  
 [<span data-ttu-id="26d41-117">COR_TYPE_LAYOUT 구조체</span><span class="sxs-lookup"><span data-stu-id="26d41-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 [<span data-ttu-id="26d41-118">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26d41-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="26d41-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26d41-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
