---
title: "IMetaDataImport2::GetGenericParamConstraintProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport2.GetGenericParamConstraintProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2c860c4f2bf1991ca929d82ef3dec61f5d20a57d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="cf458-102">IMetaDataImport2::GetGenericParamConstraintProps 메서드</span><span class="sxs-lookup"><span data-stu-id="cf458-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>
<span data-ttu-id="cf458-103">지정 된 제약 조건 토큰이 나타내는 제네릭 매개 변수 제약 조건과 연관 된 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf458-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf458-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf458-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf458-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf458-105">Parameters</span></span>  
 `gpc`  
 <span data-ttu-id="cf458-106">[in] 제네릭 매개 변수 제약 조건에 반환할 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="cf458-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="cf458-107">[out] 제한 된 제네릭 매개 변수를 나타내는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cf458-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="cf458-108">[out] 에 제약 조건을 나타내는 TypeDef, TypeRef, 또는 TypeSpec 토큰에 대 한 포인터 `ptGenericParam`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf458-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf458-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf458-109">Requirements</span></span>  
 <span data-ttu-id="cf458-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf458-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf458-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cf458-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf458-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="cf458-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf458-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf458-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf458-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf458-114">See Also</span></span>  
 [<span data-ttu-id="cf458-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf458-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="cf458-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf458-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
