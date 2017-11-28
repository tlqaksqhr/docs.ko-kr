---
title: "IMetaDataEmit::DefineParam 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineParam
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5abe9cf0385a42645468bf58c2f81223ac4eeead
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="9be3d-102">IMetaDataEmit::DefineParam 메서드</span><span class="sxs-lookup"><span data-stu-id="9be3d-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="9be3d-103">지정된 된 토큰에서 참조 하는 메서드에 대 한 지정한 서명을 가진 매개 변수 정의 만들고 해당 매개 변수 정의 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9be3d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9be3d-104">Syntax</span></span>  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9be3d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9be3d-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="9be3d-106">[in] 매개 변수를 정의 하는 방법에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="9be3d-107">[in] 매개 변수 시퀀스 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="9be3d-108">[in] 유니코드에 대 한 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="9be3d-109">[in] 매개 변수에 대 한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="9be3d-110">이 비트 마스크의 `CorParamAttr` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="9be3d-111">[in] `ELEMENT_TYPE_`  *\**  상수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="9be3d-112">[in] 매개 변수에 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="9be3d-113">[in] 유니코드 문자에서 크기의 `pValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="9be3d-114">[out] `mdParamDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9be3d-115">설명</span><span class="sxs-lookup"><span data-stu-id="9be3d-115">Remarks</span></span>  
 <span data-ttu-id="9be3d-116">시퀀스 값 `ulParamSeq` 매개 변수에 대 한 1부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="9be3d-117">반환 값 0의 시퀀스 번호가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9be3d-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9be3d-118">Requirements</span></span>  
 <span data-ttu-id="9be3d-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9be3d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9be3d-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9be3d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9be3d-121">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="9be3d-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9be3d-122">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9be3d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be3d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9be3d-123">See Also</span></span>  
 [<span data-ttu-id="9be3d-124">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9be3d-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9be3d-125">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9be3d-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
