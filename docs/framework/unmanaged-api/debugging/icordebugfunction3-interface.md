---
title: "ICorDebugFunction3 인터페이스"
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
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 28d2d0d1058dae69bc17e370cc42ed56dc35b0e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="fc33d-102">ICorDebugFunction3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc33d-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="fc33d-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="fc33d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="fc33d-104">ReJIT 요청의 코드에 액세스 권한을 제공 ICorDebugFunction 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc33d-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc33d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fc33d-105">Methods</span></span>  
  
|<span data-ttu-id="fc33d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="fc33d-106">Method</span></span>|<span data-ttu-id="fc33d-107">설명</span><span class="sxs-lookup"><span data-stu-id="fc33d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc33d-108">GetActiveReJitRequestILCode 메서드</span><span class="sxs-lookup"><span data-stu-id="fc33d-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="fc33d-109">한 인터페이스 포인터를 가져옵니다는 [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) 활성 ReJIT 요청의 IL을 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc33d-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc33d-110">설명</span><span class="sxs-lookup"><span data-stu-id="fc33d-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc33d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc33d-111">Requirements</span></span>  
 <span data-ttu-id="fc33d-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc33d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc33d-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc33d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc33d-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc33d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc33d-115">**.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc33d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc33d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc33d-116">See Also</span></span>  
 [<span data-ttu-id="fc33d-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc33d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="fc33d-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="fc33d-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 [<span data-ttu-id="fc33d-119">방법 가이드는 ReJIT:</span><span class="sxs-lookup"><span data-stu-id="fc33d-119">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
