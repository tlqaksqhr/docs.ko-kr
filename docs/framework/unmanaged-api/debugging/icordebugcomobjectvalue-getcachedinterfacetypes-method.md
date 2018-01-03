---
title: "ICorDebugComObjectValue::GetCachedInterfaceTypes 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location: mscordbi.dll
f1_keywords: ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e99054b32deb6b2e4b621ea4c193e416220f8f6f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="90c53-102">ICorDebugComObjectValue::GetCachedInterfaceTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="90c53-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="90c53-103">현재 개체 캐스팅 되거나으로 사용 된는 인터페이스 형식에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90c53-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c53-104">구문</span><span class="sxs-lookup"><span data-stu-id="90c53-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90c53-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90c53-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="90c53-106">[in] 메서드가 반환 하는지 여부를 나타내는 값 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 인터페이스 (`IInspectable` 인터페이스) 또는 런타임 호출 가능 래퍼 (RCW)에 의해 캐시 되는 모든 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="90c53-106">[in] A value that indicates whether the method returns only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="90c53-107">[out] 캐시 된 인터페이스 형식을 나타내는 ICorDebugType 개체에 대 한 액세스를 제공 하는 ICorDebugTypeEnum 열거자의 주소에 대 한 포인터에 따라 필터링 `bIInspectableOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="90c53-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90c53-108">설명</span><span class="sxs-lookup"><span data-stu-id="90c53-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90c53-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90c53-109">Requirements</span></span>  
 <span data-ttu-id="90c53-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90c53-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90c53-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90c53-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90c53-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90c53-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90c53-113">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90c53-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c53-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90c53-114">See Also</span></span>  
 [<span data-ttu-id="90c53-115">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90c53-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [<span data-ttu-id="90c53-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90c53-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
