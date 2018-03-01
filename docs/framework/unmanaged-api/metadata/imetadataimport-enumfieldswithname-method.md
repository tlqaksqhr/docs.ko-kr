---
title: "IMetaDataImport::EnumFieldsWithName 메서드"
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
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77b5ba7e191d9aa0f1587e4ac1ec25e655c27b14
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="8396c-102">IMetaDataImport::EnumFieldsWithName 메서드</span><span class="sxs-lookup"><span data-stu-id="8396c-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="8396c-103">지정한 이름을 가진 지정한 형식의 FieldDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8396c-104">구문</span><span class="sxs-lookup"><span data-stu-id="8396c-104">Syntax</span></span>  
  
```  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]  mdTypeDef       cl,   
   [in]  LPCWSTR         szName,   
   [out] mdFieldDef      rFields[],   
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTokens   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8396c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8396c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8396c-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="8396c-107">[in] 열거할 수는 필드가 포함 된 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="8396c-108">[in] 열거형의 범위를 제한 하는 필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="8396c-109">[out] FieldDef 토큰을 저장 하는 데 사용 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8396c-110">[in] `rFields` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8396c-111">[out] 반환 된 FieldDef 토큰의 실제 수 `rFields`합니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8396c-112">설명</span><span class="sxs-lookup"><span data-stu-id="8396c-112">Remarks</span></span>  
 <span data-ttu-id="8396c-113">와 달리 [imetadataimport:: Enumfields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` 지정된 된 이름을 갖지 않는 모든 필드 토큰을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8396c-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="8396c-114">Return Value</span></span>  
  
|<span data-ttu-id="8396c-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8396c-115">HRESULT</span></span>|<span data-ttu-id="8396c-116">설명</span><span class="sxs-lookup"><span data-stu-id="8396c-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8396c-117">`EnumFieldsWithName`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8396c-118">열거 하는 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-118">There are no fields to enumerate.</span></span> <span data-ttu-id="8396c-119">이 경우 `pcTokens` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8396c-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8396c-120">Requirements</span></span>  
 <span data-ttu-id="8396c-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8396c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8396c-122">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8396c-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8396c-123">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8396c-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8396c-124">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8396c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8396c-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8396c-125">See Also</span></span>  
 [<span data-ttu-id="8396c-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8396c-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="8396c-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8396c-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
