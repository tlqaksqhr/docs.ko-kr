---
title: ICorDebugProcess3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95c2218aadd62902ff9bc7f2e6a190aa2ce241ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418849"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="92ee4-102">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92ee4-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="92ee4-103">사용자 지정 디버거 알림을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee4-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92ee4-104">메서드</span><span class="sxs-lookup"><span data-stu-id="92ee4-104">Methods</span></span>  
  
|<span data-ttu-id="92ee4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="92ee4-105">Method</span></span>|<span data-ttu-id="92ee4-106">설명</span><span class="sxs-lookup"><span data-stu-id="92ee4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92ee4-107">SetEnableCustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="92ee4-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="92ee4-108">사용 하도록 설정 하 고 지정 된 형식의 사용자 지정 디버거 알림을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee4-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92ee4-109">설명</span><span class="sxs-lookup"><span data-stu-id="92ee4-109">Remarks</span></span>  
 <span data-ttu-id="92ee4-110">이 인터페이스는 ICorDebugProcess 및 ICorDebugProcess2 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee4-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92ee4-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee4-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ee4-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92ee4-112">Requirements</span></span>  
 <span data-ttu-id="92ee4-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ee4-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92ee4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92ee4-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92ee4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92ee4-116">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92ee4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ee4-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92ee4-117">See Also</span></span>  
 [<span data-ttu-id="92ee4-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92ee4-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="92ee4-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="92ee4-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
