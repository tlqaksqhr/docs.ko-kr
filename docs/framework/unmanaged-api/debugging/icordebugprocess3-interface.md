---
title: "ICorDebugProcess3 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess3
helpviewer_keywords: ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8483c53ed8b35fd3948ec42b14859146afa8ce42
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="dd245-102">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd245-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="dd245-103">사용자 지정 디버거 알림을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dd245-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd245-104">메서드</span><span class="sxs-lookup"><span data-stu-id="dd245-104">Methods</span></span>  
  
|<span data-ttu-id="dd245-105">메서드</span><span class="sxs-lookup"><span data-stu-id="dd245-105">Method</span></span>|<span data-ttu-id="dd245-106">설명</span><span class="sxs-lookup"><span data-stu-id="dd245-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd245-107">SetEnableCustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="dd245-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="dd245-108">사용 하도록 설정 하 고 지정 된 형식의 사용자 지정 디버거 알림을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd245-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd245-109">설명</span><span class="sxs-lookup"><span data-stu-id="dd245-109">Remarks</span></span>  
 <span data-ttu-id="dd245-110">이 인터페이스는 ICorDebugProcess 및 ICorDebugProcess2 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd245-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd245-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd245-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd245-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd245-112">Requirements</span></span>  
 <span data-ttu-id="dd245-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd245-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd245-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd245-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd245-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd245-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd245-116">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd245-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd245-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd245-117">See Also</span></span>  
 [<span data-ttu-id="dd245-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd245-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="dd245-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="dd245-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
