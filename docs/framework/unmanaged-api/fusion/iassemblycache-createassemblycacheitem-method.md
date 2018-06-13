---
title: IAssemblyCache::CreateAssemblyCacheItem 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c45257a76127adf2bcf9ab356639d4754d151bf6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430686"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="2b2ae-102">IAssemblyCache::CreateAssemblyCacheItem 메서드</span><span class="sxs-lookup"><span data-stu-id="2b2ae-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="2b2ae-103">새에 대 한 참조 [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2ae-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b2ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b2ae-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b2ae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b2ae-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="2b2ae-106">[in] 값에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2ae-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="2b2ae-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b2ae-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="2b2ae-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="2b2ae-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="2b2ae-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="2b2ae-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="2b2ae-110">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2ae-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="2b2ae-111">`pvReserved` null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2ae-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="2b2ae-112">[out] 반환 된 `IAssemblyCacheItem` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2ae-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="2b2ae-113">[in, 선택 사항] Uncanonicalized, 쉼표로 구분 된 `name=value` 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2ae-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b2ae-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b2ae-114">Requirements</span></span>  
 <span data-ttu-id="2b2ae-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2ae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b2ae-116">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="2b2ae-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2b2ae-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b2ae-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b2ae-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b2ae-118">See Also</span></span>  
 [<span data-ttu-id="2b2ae-119">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b2ae-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="2b2ae-120">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b2ae-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
