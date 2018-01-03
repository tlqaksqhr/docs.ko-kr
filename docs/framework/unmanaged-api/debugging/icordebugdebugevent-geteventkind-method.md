---
title: "ICorDebugDebugEvent::GetEventKind 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25bb63f1b1fa759cd6d61a71682b803e3320f22d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="bf174-102">ICorDebugDebugEvent::GetEventKind 메서드</span><span class="sxs-lookup"><span data-stu-id="bf174-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="bf174-103">이 `ICorDebugDebugEvent` 개체가 나타내는 이벤트의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bf174-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf174-104">구문</span><span class="sxs-lookup"><span data-stu-id="bf174-104">Syntax</span></span>  
  
```  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf174-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bf174-105">Parameters</span></span>  
 <span data-ttu-id="bf174-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="bf174-106">pDebugEventKind</span></span>  
 <span data-ttu-id="bf174-107">에 대 한 포인터는 [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) 이벤트의 형식을 나타내는 열거형 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="bf174-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf174-108">설명</span><span class="sxs-lookup"><span data-stu-id="bf174-108">Remarks</span></span>  
 <span data-ttu-id="bf174-109">`pDebugEventKind`의 값에 따라 `QueryInterface`를 호출하여 추가 데이터를 포함하는 보다 정확한 디버그 이벤트 인터페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf174-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf174-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf174-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf174-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf174-111">Requirements</span></span>  
 <span data-ttu-id="bf174-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf174-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf174-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf174-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf174-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf174-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf174-115">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf174-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf174-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf174-116">See Also</span></span>  
 [<span data-ttu-id="bf174-117">ICorDebugDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bf174-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="bf174-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bf174-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
