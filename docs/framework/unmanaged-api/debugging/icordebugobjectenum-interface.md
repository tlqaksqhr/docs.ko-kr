---
title: ICorDebugObjectEnum Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3674643d5590c320bddd5a0e6f1f95814e07ecf1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420206"
---
# <a name="icordebugobjectenum-interface1"></a><span data-ttu-id="ae46f-102">ICorDebugObjectEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="ae46f-102">ICorDebugObjectEnum Interface1</span></span>
<span data-ttu-id="ae46f-103">ICorDebugEnum 메서드를 구현 하 고 상대 가상 주소 (Rva) 개체의 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae46f-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae46f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ae46f-104">Methods</span></span>  
  
|<span data-ttu-id="ae46f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ae46f-105">Method</span></span>|<span data-ttu-id="ae46f-106">설명</span><span class="sxs-lookup"><span data-stu-id="ae46f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae46f-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="ae46f-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="ae46f-108">개체의 지정된 된 숫자의 rva가 현재 위치부터 시작 하는 열거형에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae46f-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae46f-109">설명</span><span class="sxs-lookup"><span data-stu-id="ae46f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae46f-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae46f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae46f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae46f-111">Requirements</span></span>  
 <span data-ttu-id="ae46f-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae46f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae46f-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae46f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae46f-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae46f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae46f-115">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae46f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae46f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae46f-116">See Also</span></span>  
 [<span data-ttu-id="ae46f-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae46f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
