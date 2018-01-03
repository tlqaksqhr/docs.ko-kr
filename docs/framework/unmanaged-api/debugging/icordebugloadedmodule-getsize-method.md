---
title: "ICorDebugLoadedModule::GetSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fb340845afac0f5a13f7c4646d11ac057ebd054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="aa1be-102">ICorDebugLoadedModule::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="aa1be-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="aa1be-103">로드된 모듈의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aa1be-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa1be-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa1be-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa1be-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa1be-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="aa1be-106">[out] 로드된 모듈의 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa1be-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa1be-107">설명</span><span class="sxs-lookup"><span data-stu-id="aa1be-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa1be-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa1be-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa1be-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa1be-109">Requirements</span></span>  
 <span data-ttu-id="aa1be-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aa1be-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa1be-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa1be-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa1be-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa1be-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa1be-113">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa1be-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa1be-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa1be-114">See Also</span></span>  
 [<span data-ttu-id="aa1be-115">ICorDebugLoadedModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa1be-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="aa1be-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa1be-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
