---
title: IMetaDataEmit::SaveToStream 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 656f5ee20e50ea9ac5c03711adfd0b8264fbcca0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444960"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="fe73d-102">IMetaDataEmit::SaveToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="fe73d-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="fe73d-103">지정 된 현재 범위에서 모든 메타 데이터를 저장 `IStream`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe73d-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe73d-104">구문</span><span class="sxs-lookup"><span data-stu-id="fe73d-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe73d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fe73d-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="fe73d-106">[in] 에 저장 하는 쓰기 가능한 스트림.</span><span class="sxs-lookup"><span data-stu-id="fe73d-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="fe73d-107">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe73d-107">[in] Reserved.</span></span> <span data-ttu-id="fe73d-108">0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe73d-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe73d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe73d-109">Requirements</span></span>  
 <span data-ttu-id="fe73d-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe73d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe73d-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fe73d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe73d-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="fe73d-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe73d-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe73d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe73d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe73d-114">See Also</span></span>  
 [<span data-ttu-id="fe73d-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe73d-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="fe73d-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe73d-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
