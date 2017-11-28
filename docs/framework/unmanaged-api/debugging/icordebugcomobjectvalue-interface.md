---
title: "ICorDebugComObjectValue 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugComObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugComObjectValue
helpviewer_keywords: ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d339d3146a8a9214c3518eac6c31ed5222f9b31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="1244d-102">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1244d-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="1244d-103">런타임 호출 가능 래퍼 (RCW)와 관련 된 정보를 검색 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1244d-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1244d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1244d-104">Methods</span></span>  
  
|<span data-ttu-id="1244d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1244d-105">Method</span></span>|<span data-ttu-id="1244d-106">설명</span><span class="sxs-lookup"><span data-stu-id="1244d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1244d-107">GetCachedInterfacePointers 메서드</span><span class="sxs-lookup"><span data-stu-id="1244d-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="1244d-108">현재 RCW에서 캐시 된 원시 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1244d-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="1244d-109">GetCachedInterfaceTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="1244d-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="1244d-110">현재 개체를 대/소문자 되거나으로 사용 된는 인터페이스 형식에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1244d-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1244d-111">설명</span><span class="sxs-lookup"><span data-stu-id="1244d-111">Remarks</span></span>  
 <span data-ttu-id="1244d-112">디버거를 "ICorDebugValue" 인터페이스의 인스턴스는 RCW를 나타내는지 여부를 확인 하려면 호출 `QueryInterface` "ICorDebugValue"와 `IID_ICorDebugComObjectValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="1244d-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1244d-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1244d-113">Requirements</span></span>  
 <span data-ttu-id="1244d-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1244d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1244d-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1244d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1244d-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1244d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1244d-117">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1244d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1244d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1244d-118">See Also</span></span>  
 [<span data-ttu-id="1244d-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1244d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1244d-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="1244d-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
