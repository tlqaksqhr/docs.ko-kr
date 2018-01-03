---
title: "ICorDebugSymbolProvider::GetObjectSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8817eb79c825a02ec5654ec340dedd6c77889a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="0f6a0-102">ICorDebugSymbolProvider::GetObjectSize 메서드</span><span class="sxs-lookup"><span data-stu-id="0f6a0-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="0f6a0-103">typespec 서명을 기준으로 개체의 개체 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f6a0-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f6a0-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f6a0-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f6a0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f6a0-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="0f6a0-106">[in] typespec 서명의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0f6a0-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="0f6a0-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="0f6a0-107">typeSig</span></span>  
 <span data-ttu-id="0f6a0-108">[in] typespec 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="0f6a0-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="0f6a0-109">[out] 개체 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0f6a0-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f6a0-110">설명</span><span class="sxs-lookup"><span data-stu-id="0f6a0-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f6a0-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f6a0-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f6a0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f6a0-112">Requirements</span></span>  
 <span data-ttu-id="0f6a0-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f6a0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f6a0-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f6a0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f6a0-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f6a0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f6a0-116">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f6a0-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f6a0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f6a0-117">See Also</span></span>  
 [<span data-ttu-id="0f6a0-118">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f6a0-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="0f6a0-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f6a0-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
