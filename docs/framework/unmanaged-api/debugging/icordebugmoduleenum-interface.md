---
title: ICorDebugModuleEnum Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd6391c06900d5cafc1bfde23bd12c22ee0c77a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422428"
---
# <a name="icordebugmoduleenum-interface1"></a><span data-ttu-id="0bbf5-102">ICorDebugModuleEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="0bbf5-102">ICorDebugModuleEnum Interface1</span></span>
<span data-ttu-id="0bbf5-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugModule 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf5-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0bbf5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="0bbf5-104">Methods</span></span>  
  
|<span data-ttu-id="0bbf5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0bbf5-105">Method</span></span>|<span data-ttu-id="0bbf5-106">설명</span><span class="sxs-lookup"><span data-stu-id="0bbf5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0bbf5-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="0bbf5-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="0bbf5-108">지정된 된 수의 가져옵니다 `ICorDebugModule` 인스턴스 현재 위치부터 시작 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf5-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bbf5-109">설명</span><span class="sxs-lookup"><span data-stu-id="0bbf5-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bbf5-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf5-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bbf5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0bbf5-111">Requirements</span></span>  
 <span data-ttu-id="0bbf5-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bbf5-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bbf5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bbf5-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bbf5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bbf5-115">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bbf5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bbf5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bbf5-116">See Also</span></span>  
 [<span data-ttu-id="0bbf5-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0bbf5-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
