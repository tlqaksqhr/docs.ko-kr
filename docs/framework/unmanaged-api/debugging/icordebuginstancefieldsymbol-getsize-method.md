---
title: "ICorDebugInstanceFieldSymbol::GetSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 364144dcef21e7e9c058cb0317970a273aa8ecac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="a8675-102">ICorDebugInstanceFieldSymbol::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="a8675-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="a8675-103">인스턴스 필드의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a8675-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8675-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8675-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8675-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8675-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="a8675-106">[out] 필드 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8675-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8675-107">설명</span><span class="sxs-lookup"><span data-stu-id="a8675-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8675-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8675-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8675-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8675-109">Requirements</span></span>  
 <span data-ttu-id="a8675-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8675-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8675-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8675-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8675-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8675-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8675-113">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8675-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8675-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8675-114">See Also</span></span>  
 [<span data-ttu-id="a8675-115">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8675-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="a8675-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8675-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
