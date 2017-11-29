---
title: "IMetaDataImport::GetMethodSemantics 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMethodSemantics
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f15aedb74fd7322031d213c5229f65d70f7cb771
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="b62ad-102">IMetaDataImport::GetMethodSemantics 메서드</span><span class="sxs-lookup"><span data-stu-id="b62ad-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="b62ad-103">토큰 쌍으로 연결 된 속성 및 지정한 MethodDef 토큰이 참조 메서드와 지정한 eventprop 참조 이벤트 간의 관계를 나타내는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b62ad-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b62ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="b62ad-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b62ad-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b62ad-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="b62ad-106">[in] 에 대 한 의미 체계 역할 정보를 가져오는 메서드를 나타내는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b62ad-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="b62ad-107">[in] 쌍으로 연결 된 속성 및 메서드의 역할을 얻을 수 있는 작업에 대 한 이벤트를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b62ad-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="b62ad-108">[out] 관련된 의미 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b62ad-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="b62ad-109">이 값은의 비트 마스크는 [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b62ad-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b62ad-110">설명</span><span class="sxs-lookup"><span data-stu-id="b62ad-110">Remarks</span></span>  
 <span data-ttu-id="b62ad-111">[imetadataemit:: Defineproperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) 메서드는 메서드의 의미 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b62ad-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b62ad-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b62ad-112">Requirements</span></span>  
 <span data-ttu-id="b62ad-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b62ad-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b62ad-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b62ad-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b62ad-115">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b62ad-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b62ad-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b62ad-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b62ad-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b62ad-117">See Also</span></span>  
 [<span data-ttu-id="b62ad-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b62ad-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b62ad-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b62ad-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
