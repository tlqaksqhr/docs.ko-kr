---
title: "ICorDebugSymbolProvider::GetTypeProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ba736caf8d8d823a4cb56c75aa2202ad616983fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="fac87-102">ICorDebugSymbolProvider::GetTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="fac87-102">ICorDebugSymbolProvider::GetTypeProps Method</span></span>
<span data-ttu-id="fac87-103">vtable에 RVA(상대 가상 주소)가 제공된 경우 해당 제네릭 매개 변수의 서명 수와 같은 형식의 속성 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fac87-103">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac87-104">구문</span><span class="sxs-lookup"><span data-stu-id="fac87-104">Syntax</span></span>  
  
```  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fac87-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fac87-105">Parameters</span></span>  
 `tableRva`  
 <span data-ttu-id="fac87-106">[in] vtable의 RVA(상대 가상 주소)입니다.</span><span class="sxs-lookup"><span data-stu-id="fac87-106">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="fac87-107">[in] `signature` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fac87-107">[in] The size of the `signature` array.</span></span> <span data-ttu-id="fac87-108">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fac87-108">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="fac87-109">[out] [out] 반환된 `signature` 배열의 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fac87-109">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="fac87-110">[out] 모든 제네릭 매개 변수의 typespec 서명을 보유하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="fac87-110">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fac87-111">설명</span><span class="sxs-lookup"><span data-stu-id="fac87-111">Remarks</span></span>  
 <span data-ttu-id="fac87-112">필요한 크기의 형식 `signature` 배열, 설정 된 `cbSignature` 인수를 0으로 및 `signature` 를 **null**합니다.</span><span class="sxs-lookup"><span data-stu-id="fac87-112">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="fac87-113">메서드가 반환되면 `signature` 배열에 필요한 바이트 수가 `pcbSignature`에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fac87-113">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fac87-114">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac87-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fac87-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fac87-115">Requirements</span></span>  
 <span data-ttu-id="fac87-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fac87-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fac87-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fac87-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fac87-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fac87-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fac87-119">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac87-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac87-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fac87-120">See Also</span></span>  
 [<span data-ttu-id="fac87-121">GetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="fac87-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)  
 [<span data-ttu-id="fac87-122">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fac87-122">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="fac87-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fac87-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)