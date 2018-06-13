---
title: ICorDebugSymbolProvider::GetInstanceFieldSymbols 메서드
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a0b5bb29ffa313df8b2ec3de9d1dca7ddbc99c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422618"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="36d9e-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="36d9e-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="36d9e-103">typespec 서명에 해당하는 인스턴스 필드 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="36d9e-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d9e-104">구문</span><span class="sxs-lookup"><span data-stu-id="36d9e-104">Syntax</span></span>  
  
```  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36d9e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="36d9e-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="36d9e-106">[in] `typeSig` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="36d9e-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="36d9e-107">[in] `typespec` 서명이 들어 있는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="36d9e-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="36d9e-108">[in] 요청된 기호 수입니다.</span><span class="sxs-lookup"><span data-stu-id="36d9e-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="36d9e-109">[out] 메서드에 의해 검색되는 기호 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="36d9e-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="36d9e-110">[out] 에 대 한 포인터는 [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) 요청한 인스턴스 필드 기호를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="36d9e-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36d9e-111">설명</span><span class="sxs-lookup"><span data-stu-id="36d9e-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36d9e-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d9e-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36d9e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36d9e-113">Requirements</span></span>  
 <span data-ttu-id="36d9e-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36d9e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36d9e-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36d9e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36d9e-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36d9e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36d9e-117">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36d9e-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d9e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36d9e-118">See Also</span></span>  
 [<span data-ttu-id="36d9e-119">GetStaticFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="36d9e-119">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)  
 [<span data-ttu-id="36d9e-120">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36d9e-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="36d9e-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36d9e-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
