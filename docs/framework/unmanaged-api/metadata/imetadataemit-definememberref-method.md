---
title: "IMetaDataEmit::DefineMemberRef 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMemberRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4dc4cd317e0e540aaa774cbf9c4c7a2a2ffa40be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="0f537-102">IMetaDataEmit::DefineMemberRef 메서드</span><span class="sxs-lookup"><span data-stu-id="0f537-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="0f537-103">현재 범위를 벗어난 모듈의 멤버에 대 한 참조를 정의 하 고 해당 참조 정의 하는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f537-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f537-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f537-104">Syntax</span></span>  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f537-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f537-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="0f537-106">[in] 멤버가 전역; 경우 대상 멤버의 클래스 또는 인터페이스에 대 한 토큰 멤버가 전역,이 경우에 `mdModuleRef` 해당 다른 파일에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0f537-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="0f537-107">[in] 대상 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0f537-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="0f537-108">[in] 대상 멤버의 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="0f537-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="0f537-109">[in] 바이트 수 `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f537-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="0f537-110">[out] `mdMemberRef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0f537-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f537-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f537-111">Requirements</span></span>  
 <span data-ttu-id="0f537-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f537-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f537-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0f537-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f537-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0f537-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f537-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f537-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f537-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f537-116">See Also</span></span>  
 [<span data-ttu-id="0f537-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f537-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0f537-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f537-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
