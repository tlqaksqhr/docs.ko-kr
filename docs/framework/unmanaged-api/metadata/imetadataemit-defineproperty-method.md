---
title: "IMetaDataEmit::DefineProperty 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineProperty
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: accc6503cc9fb87d39a429331dc82ff5717f6989
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="ca103-102">IMetaDataEmit::DefineProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="ca103-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="ca103-103">지정 된 지정된 된 형식에 대 한 속성 정의 만들고 `get` 및 `set` 메서드 접근자를 토큰 정의 속성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca103-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca103-104">Syntax</span></span>  
  
```  
HRESULT DefineProperty (   
    [in]  mdTypeDef          td,   
    [in]  LPCWSTR            szProperty,   
    [in]  DWORD              dwPropFlags,   
    [in]  PCCOR_SIGNATURE    pvSig,   
    [in]  ULONG              cbSig,   
    [in]  DWORD              dwCPlusTypeFlag,   
    [in]  void const         *pValue,   
    [in]  ULONG              cchValue,   
    [in]  mdMethodDef        mdSetter,   
    [in]  mdMethodDef        mdGetter,   
    [in]  mdMethodDef        rmdOtherMethods[],   
    [out] mdProperty         *pmdProp   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca103-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca103-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ca103-106">[in] 클래스 또는 속성이 정의 되는 인터페이스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="ca103-107">[in] 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="ca103-108">[in] 속성 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="ca103-109">[in] 속성 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="ca103-110">[in] 바이트 수 `pvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="ca103-111">[in] 형식 속성의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="ca103-112">[in] 속성에 대 한 기본 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="ca103-113">[in] (유니코드) 수의 문자 `pValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="ca103-114">[in] 속성 값을 설정 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="ca103-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="ca103-115">[in] 속성 값을 가져오는 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="ca103-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="ca103-116">[in] 배열 속성에 연결 된 다른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="ca103-117">사용 하 여 배열을 종료는 `mdTokenNil`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="ca103-118">[out] `mdProperty` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca103-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca103-119">Requirements</span></span>  
 <span data-ttu-id="ca103-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca103-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca103-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ca103-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca103-122">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="ca103-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca103-123">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca103-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca103-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca103-124">See Also</span></span>  
 [<span data-ttu-id="ca103-125">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca103-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="ca103-126">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca103-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
