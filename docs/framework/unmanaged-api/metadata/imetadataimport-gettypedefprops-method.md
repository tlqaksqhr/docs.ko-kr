---
title: "IMetaDataImport::GetTypeDefProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetTypeDefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1025ffde2bd066c81c4c562c0dd86e829fc2aef3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="bc76b-102">IMetaDataImport::GetTypeDefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="bc76b-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="bc76b-103">에 대 한 메타 데이터 정보를 반환 된 <xref:System.Type> 지정한 TypeDef 토큰이 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="bc76b-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc76b-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc76b-104">Syntax</span></span>  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc76b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc76b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bc76b-106">[in] 에 대 한 메타 데이터를 반환할 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="bc76b-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="bc76b-107">[out] 형식 이름을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="bc76b-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="bc76b-108">[in] 와이드 문자에서 크기 `szTypeDef`합니다.</span><span class="sxs-lookup"><span data-stu-id="bc76b-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="bc76b-109">[out] 반환 된 와이드 문자의 수가 `szTypeDef`합니다.</span><span class="sxs-lookup"><span data-stu-id="bc76b-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="bc76b-110">[out] 형식 정의 수정 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bc76b-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="bc76b-111">이 값은의 비트 마스크는 [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc76b-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="bc76b-112">[out] TypeDef 또는 TypeRef 메타 데이터 토큰 요청 된 형식의 기본 형식을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="bc76b-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc76b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc76b-113">Requirements</span></span>  
 <span data-ttu-id="bc76b-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc76b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc76b-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bc76b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc76b-116">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="bc76b-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc76b-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc76b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc76b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc76b-118">See Also</span></span>  
 [<span data-ttu-id="bc76b-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc76b-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="bc76b-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc76b-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
