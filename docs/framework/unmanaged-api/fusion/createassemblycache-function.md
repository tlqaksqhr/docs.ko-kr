---
title: CreateAssemblyCache 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba4259ad9cdf4f56fd4c00b5c7e9ebfa8b7fe1ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429581"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="388c6-102">CreateAssemblyCache 함수</span><span class="sxs-lookup"><span data-stu-id="388c6-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="388c6-103">새에 대 한 포인터를 가져옵니다 [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) 전역 어셈블리 캐시를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="388c6-103">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="388c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="388c6-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="388c6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="388c6-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="388c6-106">[out] 반환 된 `IAssemblyCache` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="388c6-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="388c6-107">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388c6-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="388c6-108">`dwReserved` 0 (영) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="388c6-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="388c6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="388c6-109">Requirements</span></span>  
 <span data-ttu-id="388c6-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="388c6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="388c6-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="388c6-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="388c6-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="388c6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="388c6-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="388c6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388c6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="388c6-114">See Also</span></span>  
 [<span data-ttu-id="388c6-115">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="388c6-115">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="388c6-116">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="388c6-116">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="388c6-117">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="388c6-117">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
