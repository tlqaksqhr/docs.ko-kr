---
title: ICorDebugProcess8 인터페이스
ms.date: 03/30/2017
ms.assetid: 7ab1a70f-ec11-46ff-8869-cd8ca679cc51
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbedff96abe525a1fe39d7255379c0e1612d5893
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422261"
---
# <a name="icordebugprocess8-interface"></a><span data-ttu-id="febd5-102">ICorDebugProcess8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="febd5-102">ICorDebugProcess8 Interface</span></span>
<span data-ttu-id="febd5-103">[[!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="febd5-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="febd5-104">특정 유형의 사용할지 여부를 ICorDebugProcess 인터페이스를 논리적으로 확장 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 합니다.</span><span class="sxs-lookup"><span data-stu-id="febd5-104">Logically extends the ICorDebugProcess interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="febd5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="febd5-105">Methods</span></span>  
  
|<span data-ttu-id="febd5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="febd5-106">Method</span></span>|<span data-ttu-id="febd5-107">설명</span><span class="sxs-lookup"><span data-stu-id="febd5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="febd5-108">EnableExceptionCallbacksOutsideOfMyCode 메서드</span><span class="sxs-lookup"><span data-stu-id="febd5-108">EnableExceptionCallbacksOutsideOfMyCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-enableexceptioncallbacksoutsideofmycode-method.md)|<span data-ttu-id="febd5-109">특정 유형의 사용할지 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 합니다.</span><span class="sxs-lookup"><span data-stu-id="febd5-109">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="febd5-110">설명</span><span class="sxs-lookup"><span data-stu-id="febd5-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="febd5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="febd5-111">Requirements</span></span>  
 <span data-ttu-id="febd5-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="febd5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="febd5-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="febd5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="febd5-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="febd5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="febd5-115">**.NET framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="febd5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="febd5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="febd5-116">See Also</span></span>  
 [<span data-ttu-id="febd5-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="febd5-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="febd5-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="febd5-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
