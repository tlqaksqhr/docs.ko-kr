---
title: ICorDebugThreadEnum Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca683e5925325fae2470aca3cd67be39c12a055d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423275"
---
# <a name="icordebugthreadenum-interface1"></a><span data-ttu-id="0aa3e-102">ICorDebugThreadEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="0aa3e-102">ICorDebugThreadEnum Interface1</span></span>
<span data-ttu-id="0aa3e-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugThread 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0aa3e-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0aa3e-104">메서드</span><span class="sxs-lookup"><span data-stu-id="0aa3e-104">Methods</span></span>  
  
|<span data-ttu-id="0aa3e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0aa3e-105">Method</span></span>|<span data-ttu-id="0aa3e-106">설명</span><span class="sxs-lookup"><span data-stu-id="0aa3e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0aa3e-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="0aa3e-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="0aa3e-108">지정된 된 수의 가져옵니다 `ICorDebugThread` 인스턴스 현재 위치부터 시작 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0aa3e-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0aa3e-109">설명</span><span class="sxs-lookup"><span data-stu-id="0aa3e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0aa3e-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aa3e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aa3e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0aa3e-111">Requirements</span></span>  
 <span data-ttu-id="0aa3e-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0aa3e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aa3e-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0aa3e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0aa3e-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0aa3e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0aa3e-115">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aa3e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa3e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0aa3e-116">See Also</span></span>  
 [<span data-ttu-id="0aa3e-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0aa3e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
