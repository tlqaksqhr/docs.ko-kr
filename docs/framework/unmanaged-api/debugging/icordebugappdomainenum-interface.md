---
title: ICorDebugAppDomainEnum Interface1
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
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e5d3d11e3897ff56ffcd475eb363405651578c1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainenum-interface1"></a><span data-ttu-id="e7485-102">ICorDebugAppDomainEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="e7485-102">ICorDebugAppDomainEnum Interface1</span></span>
<span data-ttu-id="e7485-103">제공 된 `Next` 지정된 된 수를 반환 하는 메서드 `ICorDebugAppDomainEnum` 열거형의 다음 위치에서 시작 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e7485-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="e7485-104">이 인터페이스는 "ICorDebugEnum"의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e7485-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7485-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e7485-105">Methods</span></span>  
  
|<span data-ttu-id="e7485-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e7485-106">Method</span></span>|<span data-ttu-id="e7485-107">설명</span><span class="sxs-lookup"><span data-stu-id="e7485-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7485-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="e7485-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="e7485-109">현재 커서 위치부터 시작 하 고 컬렉션에서 지정된 된 응용 프로그램 도메인 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e7485-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7485-110">설명</span><span class="sxs-lookup"><span data-stu-id="e7485-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7485-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7485-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7485-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7485-112">Requirements</span></span>  
 <span data-ttu-id="e7485-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7485-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7485-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7485-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7485-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7485-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7485-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7485-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7485-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7485-117">See Also</span></span>  
 [<span data-ttu-id="e7485-118">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7485-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="e7485-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7485-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
