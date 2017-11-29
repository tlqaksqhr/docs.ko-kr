---
title: "IMetaDataEmit2::DefineMethodSpec 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.DefineMethodSpec
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 036654c733dc73d40c526bf5cad4dd3750e2e9d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="7df4d-102">IMetaDataEmit2::DefineMethodSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="7df4d-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="7df4d-103">메서드의 제네릭 인스턴스를 만들고 정의에 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7df4d-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7df4d-104">구문</span><span class="sxs-lookup"><span data-stu-id="7df4d-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7df4d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7df4d-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="7df4d-106">[in] 제네릭 인스턴스를 만들려고 하는 방법에는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7df4d-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="7df4d-107">토큰 형식 이어야 합니다 `mdMethodDef` 또는 `mdMemberRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="7df4d-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="7df4d-108">[in] 이진 COM + 메서드의 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7df4d-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="7df4d-109">[in] 를 바이트 단위로 크기의 `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="7df4d-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="7df4d-110">[out] 메서드의 메타 데이터 서명 정의에 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7df4d-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7df4d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7df4d-111">Requirements</span></span>  
 <span data-ttu-id="7df4d-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7df4d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7df4d-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7df4d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7df4d-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="7df4d-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7df4d-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7df4d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df4d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7df4d-116">See Also</span></span>  
 [<span data-ttu-id="7df4d-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7df4d-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="7df4d-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7df4d-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
