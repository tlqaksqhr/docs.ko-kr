---
title: "IMetaDataEmit::DefineField 메서드"
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
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e2c4b5604c3daec78744eb8902a30750571b9f82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="c1077-102">IMetaDataEmit::DefineField 메서드</span><span class="sxs-lookup"><span data-stu-id="c1077-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="c1077-103">지정한 메타 데이터 서명을 사용 하 여 필드에 대 한 정의 만들고 해당 필드 정의 하는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1077-104">구문</span><span class="sxs-lookup"><span data-stu-id="c1077-104">Syntax</span></span>  
  
```  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1077-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c1077-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c1077-106">[in] `mdTypeDef` 바깥쪽 클래스 또는 인터페이스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="c1077-107">[in] 유니코드에 대 한 필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="c1077-108">[in] 필드 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-108">[in] The field attributes.</span></span> <span data-ttu-id="c1077-109">이 비트 마스크의 `CorFieldAttr` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c1077-110">[in] BLOB로 필드 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c1077-111">[in] 바이트 수 `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlage`  
 <span data-ttu-id="c1077-112">[in] `ELEMENT_TYPE_`  *\**  상수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="c1077-113">이 한 `CorElementType` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="c1077-114">필드에 대 한 상수 값을 정의 하지 않는 사용 하 여 `ELEMENT_TYPE_END`합니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="c1077-115">[in] 필드에 대 한 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="c1077-116">[in] (유니코드) 문자의 크기 `pValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="c1077-117">[out] `mdFieldDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1077-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1077-118">Requirements</span></span>  
 <span data-ttu-id="c1077-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1077-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1077-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1077-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1077-121">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="c1077-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1077-122">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1077-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1077-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1077-123">See Also</span></span>  
 [<span data-ttu-id="c1077-124">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1077-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c1077-125">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1077-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
