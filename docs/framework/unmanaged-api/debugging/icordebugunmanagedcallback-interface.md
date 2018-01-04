---
title: "ICorDebugUnmanagedCallback 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnmanagedCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnmanagedCallback
helpviewer_keywords: ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2a0dc561010ead94f1b2ffcd306a6067a04d7e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="5a134-102">ICorDebugUnmanagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a134-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="5a134-103">공용 언어 런타임 (CLR)와 직접 관련 되지 않는 네이티브 이벤트에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a134-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a134-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5a134-104">Methods</span></span>  
  
|<span data-ttu-id="5a134-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5a134-105">Method</span></span>|<span data-ttu-id="5a134-106">설명</span><span class="sxs-lookup"><span data-stu-id="5a134-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a134-107">DebugEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="5a134-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="5a134-108">네이티브 이벤트가 발생 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5a134-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a134-109">설명</span><span class="sxs-lookup"><span data-stu-id="5a134-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a134-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a134-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a134-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a134-111">Requirements</span></span>  
 <span data-ttu-id="5a134-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a134-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a134-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a134-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a134-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a134-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a134-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a134-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a134-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a134-116">See Also</span></span>  
 [<span data-ttu-id="5a134-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a134-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
