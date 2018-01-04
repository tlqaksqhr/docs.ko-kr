---
title: "IMetaDataImport::GetCustomAttributeProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetCustomAttributeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1e6ef9443b99b3e6b36154558ce226d421dbc0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetcustomattributeprops-method"></a><span data-ttu-id="76992-102">IMetaDataImport::GetCustomAttributeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="76992-102">IMetaDataImport::GetCustomAttributeProps Method</span></span>
<span data-ttu-id="76992-103">해당 메타데이터 토큰이 지정된 경우 사용자 지정 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76992-103">Gets the value of the custom attribute, given its metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76992-104">구문</span><span class="sxs-lookup"><span data-stu-id="76992-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76992-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76992-105">Parameters</span></span>  
 `cv`  
 <span data-ttu-id="76992-106">[in] 검색할 사용자 지정 특성을 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="76992-106">[in] A metadata token that represents the custom attribute to be retrieved.</span></span>  
  
 `ptkObj`  
 <span data-ttu-id="76992-107">[out, optional] 사용자 지정 특성이 수정하는 개체를 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="76992-107">[out, optional] A metadata token representing the object that the custom attribute modifies.</span></span> <span data-ttu-id="76992-108">이 값은 `mdCustomAttribute`를 제외한 모든 메타데이터 토큰 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76992-108">This value can be any type of metadata token except `mdCustomAttribute`.</span></span>  
  
 `ptkType`  
 <span data-ttu-id="76992-109">[out, optional] 반환된 사용자 지정 특성의 <xref:System.Type>을 나타내는 `mdMethodDef` 또는 `mdMemberRef` 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="76992-109">[out, optional] An `mdMethodDef` or `mdMemberRef` metadata token representing the <xref:System.Type> of the returned custom attribute.</span></span>  
  
 `ppBlob`  
 <span data-ttu-id="76992-110">[out, optional] 사용자 지정 특성의 값인 데이터 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="76992-110">[out, optional] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="76992-111">[out, optional] *`ppBlob`에 반환된 데이터의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="76992-111">[out, optional] The size in bytes of the data returned in *`ppBlob`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76992-112">설명</span><span class="sxs-lookup"><span data-stu-id="76992-112">Remarks</span></span>  
 <span data-ttu-id="76992-113">사용자 지정 특성은 메타데이터 엔진에서 인식할 수 있는 형식인 데이터 배열로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="76992-113">A custom attribute is stored as an array of data, the format which is understood by the metadata engine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76992-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76992-114">Requirements</span></span>  
 <span data-ttu-id="76992-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="76992-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76992-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="76992-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76992-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="76992-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="76992-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76992-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76992-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76992-119">See Also</span></span>  
 [<span data-ttu-id="76992-120">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76992-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="76992-121">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76992-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
