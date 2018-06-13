---
title: ICorDebugBreakpointEnum Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8299be7189522c1b508e647ae227de5d5dd68c73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403320"
---
# <a name="icordebugbreakpointenum-interface1"></a><span data-ttu-id="eaeff-102">ICorDebugBreakpointEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="eaeff-102">ICorDebugBreakpointEnum Interface1</span></span>
<span data-ttu-id="eaeff-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugBreakpoint 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeff-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eaeff-104">메서드</span><span class="sxs-lookup"><span data-stu-id="eaeff-104">Methods</span></span>  
  
|<span data-ttu-id="eaeff-105">메서드</span><span class="sxs-lookup"><span data-stu-id="eaeff-105">Method</span></span>|<span data-ttu-id="eaeff-106">설명</span><span class="sxs-lookup"><span data-stu-id="eaeff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eaeff-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="eaeff-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="eaeff-108">지정된 된 수의 가져옵니다 `ICorDebugBreakpoint` 인스턴스 현재 위치부터 시작 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="eaeff-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaeff-109">설명</span><span class="sxs-lookup"><span data-stu-id="eaeff-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eaeff-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eaeff-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaeff-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eaeff-111">Requirements</span></span>  
 <span data-ttu-id="eaeff-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaeff-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eaeff-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eaeff-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eaeff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eaeff-115">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaeff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaeff-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eaeff-116">See Also</span></span>  
 [<span data-ttu-id="eaeff-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eaeff-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
