---
title: "IMetaDataEmit2::DefineGenericParam 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.DefineGenericParam
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 737e57b86e74cc7e4668589d16c2e2cb351162bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="58620-102">IMetaDataEmit2::DefineGenericParam 메서드</span><span class="sxs-lookup"><span data-stu-id="58620-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="58620-103">제네릭 형식 매개 변수에 대 한 정의 만들고 해당 제네릭 형식 매개 변수에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="58620-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58620-104">구문</span><span class="sxs-lookup"><span data-stu-id="58620-104">Syntax</span></span>  
  
```  
HRESULT DefineGenericParam (   
    [in]  mdToken         tk,   
    [in]  ULONG           ulParamSeq,   
    [in]  DWORD           dwParamFlags,   
    [in]  LPCWSTR         szname,   
    [in]  DWORD           reserved,   
    [in]  mdToken         rtkConstraints[],   
    [out] mdGenericParam  *pgp  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58620-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="58620-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="58620-106">[in] `mdTypeDef` 또는 `mdMethodDef` 메서드 또는 제네릭 매개 변수를 정의 하는 생성자를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="58620-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="58620-107">[in] 제네릭 매개 변수의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="58620-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="58620-108">[in] 값은 [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 제네릭 매개 변수 형식을 설명 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="58620-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="58620-109">[in] 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="58620-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="58620-110">[in] 이 매개 변수는 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58620-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="58620-111">[in] 형식 제약 조건과 0으로 끝나는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="58620-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="58620-112">배열 멤버 이어야 합니다는 `mdTypeDef`, `mdTypeRef`, 또는 `mdTypeSpec` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="58620-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="58620-113">[out] 제네릭 매개 변수를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="58620-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58620-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58620-114">Requirements</span></span>  
 <span data-ttu-id="58620-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58620-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58620-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="58620-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58620-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="58620-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58620-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58620-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58620-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58620-119">See Also</span></span>  
 [<span data-ttu-id="58620-120">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58620-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="58620-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58620-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
