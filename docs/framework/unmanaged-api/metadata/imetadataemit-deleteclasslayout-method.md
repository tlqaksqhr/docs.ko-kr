---
title: "IMetaDataEmit::DeleteClassLayout 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DeleteClassLayout
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a35606f85e134886addd8b30c240442800a9109e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="6871e-102">IMetaDataEmit::DeleteClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="6871e-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="6871e-103">지정한 토큰이 나타내는 형식에 대 한 클래스 레이아웃 메타 데이터 서명을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="6871e-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6871e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6871e-104">Syntax</span></span>  
  
```  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6871e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6871e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="6871e-106">[in] `mdTypeDef` 클래스 레이아웃 삭제할 수 형식을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6871e-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6871e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6871e-107">Requirements</span></span>  
 <span data-ttu-id="6871e-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6871e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6871e-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6871e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6871e-110">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="6871e-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6871e-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6871e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6871e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6871e-112">See Also</span></span>  
 [<span data-ttu-id="6871e-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6871e-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="6871e-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6871e-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
