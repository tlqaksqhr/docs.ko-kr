---
title: "IMetaDataImport::GetPropertyProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fc3a1ce1d07bda50b2b578e7d20870324d60edc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="a1d6f-102">IMetaDataImport::GetPropertyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="a1d6f-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="a1d6f-103">지정한 토큰이 나타내는 속성에 대 한 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1d6f-104">구문</span><span class="sxs-lookup"><span data-stu-id="a1d6f-104">Syntax</span></span>  
  
```  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1d6f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a1d6f-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="a1d6f-106">[in] 에 대 한 메타 데이터를 반환할 속성을 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="a1d6f-107">[out] 속성을 구현 하는 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="a1d6f-108">[out] 속성 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="a1d6f-109">[in] 와이드 문자에서 크기 `szProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="a1d6f-110">[out] 반환 된 와이드 문자의 수가 `szProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="a1d6f-111">[out] 이 속성에 적용 하는 모든 특성 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="a1d6f-112">이 값은의 비트 마스크는 [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="a1d6f-113">[out] 속성의 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="a1d6f-114">[out] 반환 된 바이트 수가 `ppvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="a1d6f-115">[out] 속성의 기본값은 상수 종류를 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="a1d6f-116">CorElementType 열거형에서이 값은입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="a1d6f-117">[out] 이 속성에 대 한 기본값을 저장 하는 바이트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="a1d6f-118">[out] 와이드 문자에서 크기 `ppDefaultValue`경우 `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING;는 그렇지 않은 경우이 값은와 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="a1d6f-119">길이 경우 `ppDefaultValue` 변수로 지정 된 형식에서 유추 `pdwCPlusTypeFlag`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="a1d6f-120">[out] 속성에 대 한 set 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="a1d6f-121">[out] 속성 get 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="a1d6f-122">[out] 배열 속성에 연결 된 다른 메서드를 나타내는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a1d6f-123">[in] `rmdOtherMethod` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="a1d6f-124">배열을 모든 메서드를 포함할 수 있는 크기를 제공 하지 않는 경우 경고 없이 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="a1d6f-125">[out] 반환 된 MethodDef 토큰 수 `rmdOtherMethod`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1d6f-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1d6f-126">Requirements</span></span>  
 <span data-ttu-id="a1d6f-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d6f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1d6f-128">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a1d6f-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1d6f-129">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a1d6f-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1d6f-130">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1d6f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d6f-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1d6f-131">See Also</span></span>  
 [<span data-ttu-id="a1d6f-132">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d6f-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a1d6f-133">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1d6f-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
