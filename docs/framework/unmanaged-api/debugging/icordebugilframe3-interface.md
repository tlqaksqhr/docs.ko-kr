---
title: ICorDebugILFrame3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be45022701f72e15e83b7ca28cd110ef58c809b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415599"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="d1218-102">ICorDebugILFrame3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1218-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="d1218-103">함수의 반환 값을 캡슐화하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1218-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="d1218-104">`ICorDebugILFrame3` ICorDebugILFrame 및 ICorDebugILFrame2 인터페이스를 논리적으로 확장이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1218-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1218-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d1218-105">Methods</span></span>  
  
|<span data-ttu-id="d1218-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d1218-106">Method</span></span>|<span data-ttu-id="d1218-107">설명</span><span class="sxs-lookup"><span data-stu-id="d1218-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1218-108">GetReturnValueForILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="d1218-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="d1218-109">함수의 반환 값을 캡슐화 하는 ICorDebugValue 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d1218-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1218-110">설명</span><span class="sxs-lookup"><span data-stu-id="d1218-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1218-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1218-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1218-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1218-112">Requirements</span></span>  
 <span data-ttu-id="d1218-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1218-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1218-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1218-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1218-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1218-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1218-116">**.NET framework 버전:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1218-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1218-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1218-117">See Also</span></span>  
 [<span data-ttu-id="d1218-118">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1218-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="d1218-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1218-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
