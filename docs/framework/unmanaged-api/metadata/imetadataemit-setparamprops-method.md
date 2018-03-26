---
title: IMetaDataEmit::SetParamProps 메서드
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
caps.latest.revision: ''
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e8ada9deddf8528321797c1f9bd06b5b775ac4bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="25ae8-102">IMetaDataEmit::SetParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="25ae8-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="25ae8-103">변경 된 기능에 대 한 이전 호출에서 정의 된 메서드의 매개 변수를 설정 하거나 [imetadataemit:: Defineparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25ae8-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25ae8-104">구문</span><span class="sxs-lookup"><span data-stu-id="25ae8-104">Syntax</span></span>  
  
```  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25ae8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25ae8-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="25ae8-106">[in] 대상 매개 변수에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="25ae8-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="25ae8-107">[in] 유니코드에 대 한 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="25ae8-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="25ae8-108">[in] 매개 변수에 대 한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="25ae8-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="25ae8-109">[in] ELEMENT_TYPE_ \* 상수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ae8-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="25ae8-110">[in] 매개 변수에 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="25ae8-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="25ae8-111">[in] \(유니코드) 문자의 크기 `pValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="25ae8-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25ae8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25ae8-112">Requirements</span></span>  
 <span data-ttu-id="25ae8-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25ae8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25ae8-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="25ae8-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25ae8-115">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="25ae8-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25ae8-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25ae8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ae8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25ae8-117">See Also</span></span>  
 [<span data-ttu-id="25ae8-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25ae8-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="25ae8-119">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25ae8-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
