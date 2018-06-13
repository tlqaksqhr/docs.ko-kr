---
title: IMetaDataImport2::EnumGenericParams 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ecd1c714f41c76833ef6a0a4b7be87e338ca1a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448832"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="a50b3-102">IMetaDataImport2::EnumGenericParams 메서드</span><span class="sxs-lookup"><span data-stu-id="a50b3-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="a50b3-103">지정한 TypeDef 또는 MethodDef와 연결 된 제네릭 매개 변수 토큰의 배열을 토큰 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a50b3-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a50b3-104">구문</span><span class="sxs-lookup"><span data-stu-id="a50b3-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a50b3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a50b3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a50b3-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a50b3-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="a50b3-107">[in] 제네릭 매개 변수를 가진을 열거할 수는 TypeDef 또는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a50b3-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="a50b3-108">[out] 열거 하는 제네릭 매개 변수의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a50b3-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a50b3-109">[in] 요청 된 최대 수에 배치 하는 토큰의 `rGenericParams`합니다.</span><span class="sxs-lookup"><span data-stu-id="a50b3-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="a50b3-110">[out] 반환 된 토큰 수에 배치 `rGenericParams`합니다.</span><span class="sxs-lookup"><span data-stu-id="a50b3-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a50b3-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="a50b3-111">Return Value</span></span>  
  
|<span data-ttu-id="a50b3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a50b3-112">HRESULT</span></span>|<span data-ttu-id="a50b3-113">설명</span><span class="sxs-lookup"><span data-stu-id="a50b3-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a50b3-114">`EnumGenericParams` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50b3-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a50b3-115">`phEnum` 에 멤버가 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a50b3-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="a50b3-116">이 경우 `pcGenericParams` 0 (영)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a50b3-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a50b3-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a50b3-117">Requirements</span></span>  
 <span data-ttu-id="a50b3-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a50b3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a50b3-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a50b3-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a50b3-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a50b3-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a50b3-121">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a50b3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a50b3-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a50b3-122">See Also</span></span>  
 [<span data-ttu-id="a50b3-123">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50b3-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="a50b3-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50b3-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
