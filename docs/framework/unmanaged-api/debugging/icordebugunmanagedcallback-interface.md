---
title: ICorDebugUnmanagedCallback 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b55b27d45ef3efea10215c8a4163b5981f9d145
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422862"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="4af05-102">ICorDebugUnmanagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4af05-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="4af05-103">공용 언어 런타임 (CLR)와 직접 관련 되지 않는 네이티브 이벤트에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4af05-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4af05-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4af05-104">Methods</span></span>  
  
|<span data-ttu-id="4af05-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4af05-105">Method</span></span>|<span data-ttu-id="4af05-106">설명</span><span class="sxs-lookup"><span data-stu-id="4af05-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4af05-107">DebugEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="4af05-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="4af05-108">네이티브 이벤트가 발생 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4af05-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4af05-109">설명</span><span class="sxs-lookup"><span data-stu-id="4af05-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4af05-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4af05-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4af05-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4af05-111">Requirements</span></span>  
 <span data-ttu-id="4af05-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4af05-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4af05-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4af05-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4af05-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4af05-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4af05-115">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4af05-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af05-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4af05-116">See Also</span></span>  
 [<span data-ttu-id="4af05-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4af05-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
