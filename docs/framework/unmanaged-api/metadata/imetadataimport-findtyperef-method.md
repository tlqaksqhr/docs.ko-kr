---
title: "IMetaDataImport::FindTypeRef 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindTypeRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d742033788e270f01ee0cea70569ca65e7f35697
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="012ff-102">IMetaDataImport::FindTypeRef 메서드</span><span class="sxs-lookup"><span data-stu-id="012ff-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="012ff-103">에 대 한 토큰은 TypeRef에 대 한 포인터를 가져옵니다는 <xref:System.Type> 참조에 지정된 된 범위 및 지정된 된 이름을 가진입니다.</span><span class="sxs-lookup"><span data-stu-id="012ff-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="012ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="012ff-104">Syntax</span></span>  
  
```  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="012ff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="012ff-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="012ff-106">[in] 모듈, 어셈블리 또는 형식을 지정 하는 ModuleRef, AssemblyRef, 또는 TypeRef 토큰 각각 형식이 참조를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="012ff-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="012ff-107">[in] 검색할 형식 참조의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="012ff-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="012ff-108">[out] 일치 하는 TypeRef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="012ff-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="012ff-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="012ff-109">Requirements</span></span>  
 <span data-ttu-id="012ff-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="012ff-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="012ff-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="012ff-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="012ff-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="012ff-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="012ff-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="012ff-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="012ff-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="012ff-114">See Also</span></span>  
 [<span data-ttu-id="012ff-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="012ff-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="012ff-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="012ff-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
