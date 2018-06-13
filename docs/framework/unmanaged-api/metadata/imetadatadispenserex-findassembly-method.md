---
title: IMetaDataDispenserEx::FindAssembly 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b4caf27fe45ce0a85b7e1800827a1e5cd0893ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445240"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="20215-102">IMetaDataDispenserEx::FindAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="20215-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="20215-103">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="20215-103">This method is not implemented.</span></span> <span data-ttu-id="20215-104">를 호출 하는 경우 E_NOTIMPL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="20215-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20215-105">구문</span><span class="sxs-lookup"><span data-stu-id="20215-105">Syntax</span></span>  
  
```  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20215-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20215-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="20215-107">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20215-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="20215-108">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20215-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="20215-109">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20215-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="20215-110">[in] 어셈블리를 찾을 수입니다.</span><span class="sxs-lookup"><span data-stu-id="20215-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="20215-111">[out] 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="20215-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="20215-112">[in] 를 바이트 단위로 크기의 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="20215-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="20215-113">[out] 에 실제로 반환 된 문자 수가 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="20215-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20215-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20215-114">Requirements</span></span>  
 <span data-ttu-id="20215-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20215-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20215-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="20215-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20215-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="20215-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="20215-118">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20215-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20215-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20215-119">See Also</span></span>  
 [<span data-ttu-id="20215-120">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20215-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="20215-121">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20215-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
