---
title: IMetaDataAssemblyImport::EnumExportedTypes 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9aef8c40be2456532bd6df6feb8d286cdaeefa7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445633"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="eee66-102">IMetaDataAssemblyImport::EnumExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="eee66-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="eee66-103">현재 메타 데이터 범위에 있는 어셈블리 매니페스트에에서 참조 된 내보낸된 형식을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee66-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eee66-104">구문</span><span class="sxs-lookup"><span data-stu-id="eee66-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eee66-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eee66-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="eee66-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eee66-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="eee66-107">null 이어야 합니다 경우이 값은 `EnumExportedTypes` 메서드를 처음으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee66-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="eee66-108">[out] 열거 `mdExportedType` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="eee66-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="eee66-109">[in] 최대 `mdExportedType` 에 배치할 수 있는 토큰의 `rExportedTypes` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="eee66-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="eee66-110">[out] 수가 `mdExportedType` 토큰에 실제로 배치 `rExportedTypes`합니다.</span><span class="sxs-lookup"><span data-stu-id="eee66-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eee66-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="eee66-111">Return Value</span></span>  
  
|<span data-ttu-id="eee66-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eee66-112">HRESULT</span></span>|<span data-ttu-id="eee66-113">설명</span><span class="sxs-lookup"><span data-stu-id="eee66-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="eee66-114">`EnumExportedTypes` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee66-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="eee66-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee66-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="eee66-116">이 경우 `pcTokens` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee66-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eee66-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eee66-117">Requirements</span></span>  
 <span data-ttu-id="eee66-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eee66-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eee66-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eee66-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eee66-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="eee66-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eee66-121">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eee66-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee66-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eee66-122">See Also</span></span>  
 [<span data-ttu-id="eee66-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eee66-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
