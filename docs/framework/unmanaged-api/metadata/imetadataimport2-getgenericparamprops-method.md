---
title: "IMetaDataImport2::GetGenericParamProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70a9669e2f47c3b56f7b50dc96ed2d3ba8314c4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="a5d7c-102">IMetaDataImport2::GetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="a5d7c-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="a5d7c-103">지정한 토큰이 나타내는 제네릭 매개 변수와 연관 된 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5d7c-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5d7c-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5d7c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5d7c-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="a5d7c-106">[in] 반환할 메타 데이터에 대 한 제네릭 매개 변수를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="a5d7c-107">[out] 서 수 위치는 `Type` 부모 생성자 또는 메서드 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="a5d7c-108">[out] 값은 [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 설명 하는 열거형의 `Type` 제네릭 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-108">[out] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="a5d7c-109">[out] 형식 정의 또는 MethodDef 토큰 매개 변수의 소유자를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="a5d7c-110">[out] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="a5d7c-111">[out] 제네릭 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="a5d7c-112">[in] 크기는 `wzName` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="a5d7c-113">[out] 와이드 문자에서는 이름의 반환 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5d7c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5d7c-114">Requirements</span></span>  
 <span data-ttu-id="a5d7c-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d7c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5d7c-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5d7c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5d7c-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a5d7c-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a5d7c-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5d7c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d7c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5d7c-119">See Also</span></span>  
 [<span data-ttu-id="a5d7c-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5d7c-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="a5d7c-121">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5d7c-121">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
