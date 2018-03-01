---
title: "ICorDebugProcess3 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 894d3295b83a1971792e6da845f276be486a4ea5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="9ab2c-102">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ab2c-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="9ab2c-103">사용자 지정 디버거 알림을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab2c-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ab2c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="9ab2c-104">Methods</span></span>  
  
|<span data-ttu-id="9ab2c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9ab2c-105">Method</span></span>|<span data-ttu-id="9ab2c-106">설명</span><span class="sxs-lookup"><span data-stu-id="9ab2c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ab2c-107">SetEnableCustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="9ab2c-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="9ab2c-108">사용 하도록 설정 하 고 지정 된 형식의 사용자 지정 디버거 알림을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab2c-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ab2c-109">설명</span><span class="sxs-lookup"><span data-stu-id="9ab2c-109">Remarks</span></span>  
 <span data-ttu-id="9ab2c-110">이 인터페이스는 ICorDebugProcess 및 ICorDebugProcess2 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab2c-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ab2c-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ab2c-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ab2c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ab2c-112">Requirements</span></span>  
 <span data-ttu-id="9ab2c-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab2c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ab2c-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ab2c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ab2c-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ab2c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ab2c-116">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ab2c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab2c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ab2c-117">See Also</span></span>  
 [<span data-ttu-id="9ab2c-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ab2c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="9ab2c-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="9ab2c-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
