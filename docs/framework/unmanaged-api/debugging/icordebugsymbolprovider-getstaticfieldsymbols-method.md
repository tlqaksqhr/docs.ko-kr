---
title: ICorDebugSymbolProvider::GetStaticFieldSymbols 메서드
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7d5195215762c25b2d7dc2b71fcd53959656303
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420897"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="645e9-102">ICorDebugSymbolProvider::GetStaticFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="645e9-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="645e9-103">typespec 서명에 해당하는 정적 필드 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="645e9-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="645e9-104">구문</span><span class="sxs-lookup"><span data-stu-id="645e9-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="645e9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="645e9-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="645e9-106">[in] `typeSig` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="645e9-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="645e9-107">[in] `typespec` 서명이 들어 있는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="645e9-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="645e9-108">[in] 요청된 기호 수입니다.</span><span class="sxs-lookup"><span data-stu-id="645e9-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="645e9-109">[out] 메서드에 의해 검색되는 기호 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="645e9-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="645e9-110">[out] 에 대 한 포인터는 [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) 요청 된 정적 필드 기호를 포함 된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="645e9-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="645e9-111">설명</span><span class="sxs-lookup"><span data-stu-id="645e9-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="645e9-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="645e9-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="645e9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="645e9-113">Requirements</span></span>  
 <span data-ttu-id="645e9-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="645e9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="645e9-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="645e9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="645e9-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="645e9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="645e9-117">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="645e9-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645e9-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="645e9-118">See Also</span></span>  
 [<span data-ttu-id="645e9-119">GetInstanceFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="645e9-119">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)  
 [<span data-ttu-id="645e9-120">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="645e9-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="645e9-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="645e9-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
