---
title: "IMetaDataEmit::SetFieldMarshal 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetFieldMarshal
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 20186870510e67e518414d2bd5e9a00fd5164dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="db850-102">IMetaDataEmit::SetFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="db850-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="db850-103">지정한 토큰이 참조 하는 필드, return, 메서드 또는 메서드 매개 변수의 대 한 마샬링 정보 PInvoke를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="db850-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db850-104">구문</span><span class="sxs-lookup"><span data-stu-id="db850-104">Syntax</span></span>  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db850-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="db850-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="db850-106">[in] 대상 데이터 항목에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="db850-106">[in] The token for target data item.</span></span> <span data-ttu-id="db850-107">이 역할은 한 `mdFieldDef` 또는 `mdParamDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="db850-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="db850-108">[in] 관리 되지 않는 형식에 대 한 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="db850-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="db850-109">[in] 바이트 수 `pvNativeType`합니다.</span><span class="sxs-lookup"><span data-stu-id="db850-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db850-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db850-110">Requirements</span></span>  
 <span data-ttu-id="db850-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db850-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db850-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="db850-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="db850-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="db850-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db850-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db850-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db850-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db850-115">See Also</span></span>  
 [<span data-ttu-id="db850-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db850-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="db850-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db850-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
