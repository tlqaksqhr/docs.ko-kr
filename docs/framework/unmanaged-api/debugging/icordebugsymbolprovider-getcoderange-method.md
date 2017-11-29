---
title: "ICorDebugSymbolProvider::GetCodeRange 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c46fb62e5f1867e2b527404bd3d003ba884ebfbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="ef1f4-102">ICorDebugSymbolProvider::GetCodeRange 메서드</span><span class="sxs-lookup"><span data-stu-id="ef1f4-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="ef1f4-103">메서드의 RVA(상대 가상 주소)가 지정된 경우 메서드 시작 주소와 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f4-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef1f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="ef1f4-104">Syntax</span></span>  
  
```  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef1f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef1f4-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="ef1f4-106">[in] 메서드의 RVA(상대 가상 주소)입니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f4-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="ef1f4-107">[out] 메서드의 시작 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f4-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="ef1f4-108">메서드 코드 크기(메서드 코드의 바이트 수)에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f4-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef1f4-109">설명</span><span class="sxs-lookup"><span data-stu-id="ef1f4-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef1f4-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f4-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef1f4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef1f4-111">Requirements</span></span>  
 <span data-ttu-id="ef1f4-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef1f4-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef1f4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef1f4-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef1f4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef1f4-115">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef1f4-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef1f4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef1f4-116">See Also</span></span>  
 [<span data-ttu-id="ef1f4-117">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef1f4-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="ef1f4-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef1f4-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
