---
title: "ICorDebugBlockingObjectEnum 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBlockingObjectEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBlockingObjectEnum
helpviewer_keywords: ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d35d4ee2ce3c1b7b0f54d78dba8b8639c522d509
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="6efc7-102">ICorDebugBlockingObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6efc7-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="6efc7-103">목록에 대 한 열거자를 제공 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="6efc7-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="6efc7-104">이 인터페이스는 ICorDebugEnum 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6efc7-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6efc7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6efc7-105">Methods</span></span>  
  
|<span data-ttu-id="6efc7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6efc7-106">Method</span></span>|<span data-ttu-id="6efc7-107">설명</span><span class="sxs-lookup"><span data-stu-id="6efc7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6efc7-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="6efc7-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="6efc7-109">목록을 열거 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="6efc7-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6efc7-110">설명</span><span class="sxs-lookup"><span data-stu-id="6efc7-110">Remarks</span></span>  
 <span data-ttu-id="6efc7-111">각 `CorDebugBlockingObject` 구조체는 스레드를 차단하는 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6efc7-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6efc7-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6efc7-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6efc7-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6efc7-113">Requirements</span></span>  
 <span data-ttu-id="6efc7-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6efc7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6efc7-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6efc7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6efc7-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6efc7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6efc7-117">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6efc7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6efc7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6efc7-118">See Also</span></span>  
 [<span data-ttu-id="6efc7-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6efc7-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6efc7-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="6efc7-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
