---
title: "ICorDebugMergedAssemblyRecord::GetIndex 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54ff8d6935f5507ab02d9d566921cb7f8a890bb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="9e2a8-102">ICorDebugMergedAssemblyRecord::GetIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="9e2a8-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="9e2a8-103">어셈블리의 접두사 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9e2a8-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e2a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e2a8-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e2a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e2a8-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="9e2a8-106">[out] 접두사 인덱스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e2a8-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e2a8-107">설명</span><span class="sxs-lookup"><span data-stu-id="9e2a8-107">Remarks</span></span>  
 <span data-ttu-id="9e2a8-108">접두사 인덱스는 병합된 메타데이터 형식 이름에서 이름 충돌을 방지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e2a8-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e2a8-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e2a8-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e2a8-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e2a8-110">Requirements</span></span>  
 <span data-ttu-id="9e2a8-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e2a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e2a8-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e2a8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e2a8-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e2a8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e2a8-114">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e2a8-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e2a8-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e2a8-115">See Also</span></span>  
 [<span data-ttu-id="9e2a8-116">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e2a8-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="9e2a8-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e2a8-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
