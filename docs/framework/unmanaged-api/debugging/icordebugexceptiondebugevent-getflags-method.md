---
title: "ICorDebugExceptionDebugEvent::GetFlags 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c6e7767ca5467f69dc7f53728bda9daf5f08331c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="6850a-102">ICorDebugExceptionDebugEvent::GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="6850a-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="6850a-103">예외를 가로챌 수 있는지 여부를 나타내는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6850a-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6850a-104">구문</span><span class="sxs-lookup"><span data-stu-id="6850a-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6850a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6850a-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="6850a-106">[out] 에 대 한 포인터는 [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) 예외를 가로챌 수 있는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6850a-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6850a-107">설명</span><span class="sxs-lookup"><span data-stu-id="6850a-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6850a-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6850a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6850a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6850a-109">Requirements</span></span>  
 <span data-ttu-id="6850a-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6850a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6850a-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6850a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6850a-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6850a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6850a-113">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6850a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6850a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6850a-114">See Also</span></span>  
 [<span data-ttu-id="6850a-115">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6850a-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="6850a-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6850a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
