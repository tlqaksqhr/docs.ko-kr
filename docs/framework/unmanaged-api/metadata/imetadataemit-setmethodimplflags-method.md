---
title: "IMetaDataEmit::SetMethodImplFlags 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetMethodImplFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d69940d5cffe397d009b7364a20a09dbbd95db4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="18857-102">IMetaDataEmit::SetMethodImplFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="18857-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="18857-103">설정 하거나 상속 된 메서드 구현 지정한 토큰이 참조 되는 메타 데이터 서명을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="18857-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18857-104">구문</span><span class="sxs-lookup"><span data-stu-id="18857-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18857-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18857-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="18857-106">[in] 변경 하려는 방법에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="18857-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="18857-107">[in] 값의 조합 된 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 메서드 구현 함수를 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="18857-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18857-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18857-108">Requirements</span></span>  
 <span data-ttu-id="18857-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="18857-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18857-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="18857-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18857-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="18857-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18857-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18857-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18857-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18857-113">See Also</span></span>  
 [<span data-ttu-id="18857-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18857-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="18857-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18857-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
