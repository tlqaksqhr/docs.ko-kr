---
title: "IMetaDataImport::GetRVA 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetRVA
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f64cc5b0aa6043c5408868a5a6bf23e24278ea26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="f02da-102">IMetaDataImport::GetRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="f02da-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="f02da-103">상대 가상 주소 (RVA)와 메서드 또는 지정한 토큰이 나타내는 필드의 구현 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f02da-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f02da-104">구문</span><span class="sxs-lookup"><span data-stu-id="f02da-104">Syntax</span></span>  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f02da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f02da-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f02da-106">[in] MethodDef 또는 FieldDef 메타 데이터를 나타내는 토큰에 대 한 RVA를 반환할 코드 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f02da-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="f02da-107">한 FieldDef 토큰을 사용 하는 경우 필드에는 전역 변수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f02da-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="f02da-108">[out] 토큰이 나타내는 코드 개체의 상대 가상 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f02da-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="f02da-109">[out] 메서드에 대 한 구현 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f02da-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="f02da-110">이 값은의 비트 마스크는 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f02da-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="f02da-111">값 `pdwImplFlags` 유효한 경우에만 `tk` MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f02da-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f02da-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f02da-112">Requirements</span></span>  
 <span data-ttu-id="f02da-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f02da-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f02da-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f02da-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f02da-115">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f02da-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f02da-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f02da-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02da-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f02da-117">See Also</span></span>  
 [<span data-ttu-id="f02da-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f02da-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f02da-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f02da-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
