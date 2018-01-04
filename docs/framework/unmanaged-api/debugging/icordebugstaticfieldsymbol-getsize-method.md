---
title: "ICorDebugStaticFieldSymbol::GetSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b67cbe6858e91e089c36047d6ed83743e45e1d1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="859bb-102">ICorDebugStaticFieldSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="859bb-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="859bb-103">정적 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="859bb-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="859bb-104">구문</span><span class="sxs-lookup"><span data-stu-id="859bb-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="859bb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="859bb-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="859bb-106">[out] 필드 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="859bb-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="859bb-107">설명</span><span class="sxs-lookup"><span data-stu-id="859bb-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="859bb-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="859bb-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="859bb-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="859bb-109">Requirements</span></span>  
 <span data-ttu-id="859bb-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="859bb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="859bb-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="859bb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="859bb-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="859bb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="859bb-113">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="859bb-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859bb-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="859bb-114">See Also</span></span>  
 [<span data-ttu-id="859bb-115">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="859bb-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="859bb-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="859bb-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
