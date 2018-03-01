---
title: "IMetaDataEmit::SetFieldRVA 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 260d5458af9fb8fbc8161018c438346fd58af06f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="532f5-102">IMetaDataEmit::SetFieldRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="532f5-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="532f5-103">지정한 토큰이 참조 하는 필드의 상대 가상 주소에 대 한 전역 변수 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="532f5-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="532f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="532f5-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="532f5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="532f5-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="532f5-106">[in] 대상 필드에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="532f5-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="532f5-107">[in] 주소는 코드 또는 데이터 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="532f5-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="532f5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="532f5-108">Requirements</span></span>  
 <span data-ttu-id="532f5-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="532f5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="532f5-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="532f5-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="532f5-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="532f5-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="532f5-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="532f5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="532f5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="532f5-113">See Also</span></span>  
 [<span data-ttu-id="532f5-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="532f5-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="532f5-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="532f5-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
