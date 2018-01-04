---
title: "ICorDebugInstanceFieldSymbol::GetOffset 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ab38a19d2bd2d06f2a04d7efafcdad6956ad7c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="bc375-102">ICorDebugInstanceFieldSymbol::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="bc375-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="bc375-103">부모 클래스에서 이 인스턴스 필드의 오프셋(바이트)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bc375-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc375-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc375-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc375-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc375-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="bc375-106">부모 클래스에서 이 인스턴스 필드가 오프셋되는 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bc375-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc375-107">설명</span><span class="sxs-lookup"><span data-stu-id="bc375-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc375-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc375-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc375-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc375-109">Requirements</span></span>  
 <span data-ttu-id="bc375-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc375-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc375-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc375-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc375-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc375-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc375-113">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc375-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc375-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc375-114">See Also</span></span>  
 [<span data-ttu-id="bc375-115">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc375-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="bc375-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc375-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
