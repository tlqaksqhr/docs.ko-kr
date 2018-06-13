---
title: IMetaDataEmit::SetPropertyProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 024ab8254f566e5386198fa1735af4c6b1972ca1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448038"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="2a72c-102">IMetaDataEmit::SetPropertyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="2a72c-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="2a72c-103">이전 호출에서 정의한 속성에 대 한 메타 데이터에 저장 하는 기능을 설정 [DefineProperty 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a72c-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a72c-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a72c-104">Syntax</span></span>  
  
```  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a72c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a72c-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="2a72c-106">[in] 변경할 속성에 대 한 토큰</span><span class="sxs-lookup"><span data-stu-id="2a72c-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="2a72c-107">[in] 속성 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="2a72c-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="2a72c-108">[in] 형식 속성의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a72c-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2a72c-109">[in] 속성에 대 한 기본 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a72c-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="2a72c-110">[in] \(유니코드) 수의 문자 `pValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="2a72c-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="2a72c-111">[in] 속성 값을 설정 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="2a72c-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="2a72c-112">[in] 속성 값을 가져오는 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="2a72c-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="2a72c-113">[in] 배열 속성에 연결 된 다른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2a72c-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="2a72c-114">이 배열의 종료는 `mdTokenNil` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2a72c-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a72c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a72c-115">Requirements</span></span>  
 <span data-ttu-id="2a72c-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a72c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a72c-117">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2a72c-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a72c-118">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="2a72c-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a72c-119">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a72c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a72c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a72c-120">See Also</span></span>  
 [<span data-ttu-id="2a72c-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a72c-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="2a72c-122">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a72c-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
