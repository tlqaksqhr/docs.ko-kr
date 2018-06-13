---
title: ICorDebugSymbolProvider::GetObjectSize 메서드
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1da526ac133604fa43081f86988459c4238517c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421505"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="067cb-102">ICorDebugSymbolProvider::GetObjectSize 메서드</span><span class="sxs-lookup"><span data-stu-id="067cb-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="067cb-103">typespec 서명을 기준으로 개체의 개체 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="067cb-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="067cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="067cb-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="067cb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="067cb-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="067cb-106">[in] typespec 서명의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="067cb-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="067cb-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="067cb-107">typeSig</span></span>  
 <span data-ttu-id="067cb-108">[in] typespec 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="067cb-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="067cb-109">[out] 개체 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="067cb-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="067cb-110">설명</span><span class="sxs-lookup"><span data-stu-id="067cb-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="067cb-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067cb-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="067cb-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="067cb-112">Requirements</span></span>  
 <span data-ttu-id="067cb-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="067cb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="067cb-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="067cb-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="067cb-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="067cb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="067cb-116">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="067cb-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="067cb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="067cb-117">See Also</span></span>  
 [<span data-ttu-id="067cb-118">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="067cb-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="067cb-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="067cb-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
