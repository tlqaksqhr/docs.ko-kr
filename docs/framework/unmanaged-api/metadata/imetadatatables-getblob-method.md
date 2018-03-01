---
title: "IMetaDataTables::GetBlob 메서드"
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
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 173d854548391acdc9f1896a07eb993cdf1ce4d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="cb39f-102">IMetaDataTables::GetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="cb39f-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="cb39f-103">이진 대형 개체 (BLOB)에 지정 된 열 인덱스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb39f-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb39f-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb39f-104">Syntax</span></span>  
  
```  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb39f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb39f-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="cb39f-106">[in] 메모리 주소를 가져올 `ppData`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb39f-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="cb39f-107">[out] 를 바이트 단위로 크기에 대 한 포인터의 `ppData`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb39f-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="cb39f-108">[out] 이진 데이터에 대 한 포인터에 대 한 포인터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb39f-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb39f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb39f-109">Requirements</span></span>  
 <span data-ttu-id="cb39f-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb39f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb39f-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cb39f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb39f-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="cb39f-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb39f-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb39f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb39f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb39f-114">See Also</span></span>  
 [<span data-ttu-id="cb39f-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb39f-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="cb39f-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb39f-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
