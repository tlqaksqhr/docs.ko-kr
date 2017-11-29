---
title: "IMetaDataEmit2::SetGenericParamProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5de54b3d113c8d43bd004b18e0a6cb22b1051dc6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="473f0-102">IMetaDataEmit2::SetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="473f0-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="473f0-103">지정 된 토큰에서 참조 하는 제네릭 매개 변수 정의 대 한 속성 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="473f0-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="473f0-104">구문</span><span class="sxs-lookup"><span data-stu-id="473f0-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="473f0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="473f0-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="473f0-106">[in] 값을 설정 하는 작업에 대 한 제네릭 매개 변수 정의 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="473f0-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="473f0-107">[in] 값은 [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 제네릭 매개 변수 형식을 설명 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="473f0-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="473f0-108">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="473f0-108">[in] Optional.</span></span> <span data-ttu-id="473f0-109">값을 설정 하려는 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="473f0-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="473f0-110">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="473f0-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="473f0-111">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="473f0-111">[in] Optional.</span></span> <span data-ttu-id="473f0-112">형식 제약 조건과 0으로 끝나는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="473f0-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="473f0-113">배열 멤버 이어야 합니다는 `mdTypeDef`, `mdTypeRef`, 또는 `mdTypeSpec` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="473f0-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="473f0-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="473f0-114">Requirements</span></span>  
 <span data-ttu-id="473f0-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="473f0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="473f0-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="473f0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="473f0-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="473f0-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="473f0-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="473f0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="473f0-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="473f0-119">See Also</span></span>  
 [<span data-ttu-id="473f0-120">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="473f0-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="473f0-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="473f0-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
