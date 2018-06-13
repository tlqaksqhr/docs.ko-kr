---
title: ICorDebugDataTarget2::GetSymbolProviderForImage 메서드
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cdd2d0b6f6fbc8d3c2b1a14ca05a84d13c56331
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411105"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="61909-102">ICorDebugDataTarget2::GetSymbolProviderForImage 메서드</span><span class="sxs-lookup"><span data-stu-id="61909-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="61909-103">모듈의 시스템 공급자를 해당 모듈의 기본 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61909-104">구문</span><span class="sxs-lookup"><span data-stu-id="61909-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61909-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="61909-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="61909-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) 모듈의 기준 주소를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="61909-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="61909-107">[out] 주소에 대 한 포인터는 [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="61909-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61909-108">설명</span><span class="sxs-lookup"><span data-stu-id="61909-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61909-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61909-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61909-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61909-110">Requirements</span></span>  
 <span data-ttu-id="61909-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61909-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61909-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61909-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61909-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61909-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61909-114">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61909-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61909-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61909-115">See Also</span></span>  
 [<span data-ttu-id="61909-116">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61909-116">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="61909-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61909-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
