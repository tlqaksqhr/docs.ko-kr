---
title: "IMetaDataImport::EnumMemberRefs 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMemberRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ea308db566e37d10cccdc2777b5a2374408a8ea6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="2a936-102">IMetaDataImport::EnumMemberRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="2a936-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="2a936-103">지정한 형식의 멤버를 나타내는 MemberRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="2a936-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a936-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a936-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a936-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a936-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2a936-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2a936-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="2a936-107">[in] 구성원을 열거할 수 인 형식에 대 한 형식 정의 TypeRef, MethodDef, 또는 ModuleRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2a936-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="2a936-108">[out] MemberRef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2a936-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2a936-109">[in] `rMemberRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2a936-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2a936-110">[out] MemberRef 토큰에 반환 된 실제 수가 `rMemberRefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="2a936-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a936-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="2a936-111">Return Value</span></span>  
  
|<span data-ttu-id="2a936-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a936-112">HRESULT</span></span>|<span data-ttu-id="2a936-113">설명</span><span class="sxs-lookup"><span data-stu-id="2a936-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2a936-114">`EnumMemberRefs`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a936-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2a936-115">열거할 MemberRef 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a936-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="2a936-116">이 경우 `pcTokens` 는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="2a936-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a936-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a936-117">Requirements</span></span>  
 <span data-ttu-id="2a936-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a936-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a936-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2a936-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a936-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2a936-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a936-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a936-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a936-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a936-122">See Also</span></span>  
 [<span data-ttu-id="2a936-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a936-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="2a936-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a936-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
