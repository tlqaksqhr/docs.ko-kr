---
title: "ICorDebugInternalFrame2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame2
helpviewer_keywords: ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d87303fbe95804b458a42ed43b65f29233814977
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="4369e-102">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4369e-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="4369e-103">스택 주소 및 ICorDebugFrame 개체와 관련 위치를 비롯 하 여 내부 프레임에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4369e-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4369e-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4369e-104">Methods</span></span>  
  
|<span data-ttu-id="4369e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4369e-105">Method</span></span>|<span data-ttu-id="4369e-106">설명</span><span class="sxs-lookup"><span data-stu-id="4369e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4369e-107">GetFrameAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="4369e-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="4369e-108">내부 프레임의 스택 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4369e-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="4369e-109">IsCloserToLeaf 메서드</span><span class="sxs-lookup"><span data-stu-id="4369e-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="4369e-110">확인 여부는 `this` 내부 프레임 보다 더 가까운 리프에 지정된 된 ICorDebugFrame 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4369e-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4369e-111">설명</span><span class="sxs-lookup"><span data-stu-id="4369e-111">Remarks</span></span>  
 <span data-ttu-id="4369e-112">이 인터페이스는 ICorDebugInternalFrame 인터페이스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="4369e-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4369e-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4369e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4369e-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4369e-114">Requirements</span></span>  
 <span data-ttu-id="4369e-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4369e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4369e-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4369e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4369e-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4369e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4369e-118">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4369e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4369e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4369e-119">See Also</span></span>  
 [<span data-ttu-id="4369e-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4369e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4369e-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="4369e-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
