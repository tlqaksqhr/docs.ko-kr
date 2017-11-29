---
title: "IMetaDataImport::GetMemberRefProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMemberRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0b4b0399c22890226ad49ca0f3a5c709fb251653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="b2bb0-102">IMetaDataImport::GetMemberRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="b2bb0-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="b2bb0-103">지정한 토큰이 참조하는 멤버와 연결된 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2bb0-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2bb0-104">Syntax</span></span>  
  
```  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,   
   [out] mdToken           *ptk,   
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pbSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2bb0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2bb0-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="b2bb0-106">[in] 반환할 연결 된 메타 데이터에 대 한 MemberRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="b2bb0-107">[out] TypeDef 또는 TypeRef, 또는 TypeSpec 토큰은 멤버 또는 멤버 또는 멤버를 나타내는 MethodDef 선언 하는 모듈 클래스를 나타내는 ModuleRef 토큰을 선언 하는 클래스를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="b2bb0-108">[out] 멤버의 이름에 대 한 문자열 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="b2bb0-109">[in] 요청된 된 크기의 와이드 문자에서 `szMember`합니다.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="b2bb0-110">[out] 반환 되는 크기의 와이드 문자에서 `szMember`합니다.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="b2bb0-111">[out] 멤버에 대 한 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="b2bb0-112">[out] 바이트 크기 `ppvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2bb0-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2bb0-113">Requirements</span></span>  
 <span data-ttu-id="b2bb0-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2bb0-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b2bb0-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2bb0-116">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b2bb0-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2bb0-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2bb0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bb0-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2bb0-118">See Also</span></span>  
 [<span data-ttu-id="b2bb0-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2bb0-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b2bb0-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2bb0-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
