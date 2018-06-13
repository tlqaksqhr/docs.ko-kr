---
title: IMetaDataEmit::DefineMethodImpl 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ab66fecfaa66b5c56690950f6b19ecfd7e85e33
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443991"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="0790e-102">IMetaDataEmit::DefineMethodImpl 메서드</span><span class="sxs-lookup"><span data-stu-id="0790e-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="0790e-103">인터페이스에서 상속 된 메서드의 구현에 대 한 정의 만들고 해당 메서드 구현 정의에 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0790e-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0790e-104">구문</span><span class="sxs-lookup"><span data-stu-id="0790e-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0790e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0790e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="0790e-106">[in] `mdTypedef` 토큰 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0790e-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="0790e-107">[in] `mdMethodDef` 또는 `mdMethodRef` 코드 본문의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0790e-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="0790e-108">[in] `mdMethodDef` 또는 `mdMethodRef` 구현 되는 인터페이스 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0790e-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0790e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0790e-109">Requirements</span></span>  
 <span data-ttu-id="0790e-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0790e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0790e-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0790e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0790e-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0790e-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0790e-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0790e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0790e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0790e-114">See Also</span></span>  
 [<span data-ttu-id="0790e-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0790e-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0790e-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0790e-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
