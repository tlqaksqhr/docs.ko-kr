---
title: IMetaDataTables::GetNextBlob 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: caf7faeea4bcec9b73f3c43f0923d308baebf6d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447622"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="08f97-102">IMetaDataTables::GetNextBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="08f97-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="08f97-103">테이블에 다음 이진 대형 개체 (BLOB)의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="08f97-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08f97-104">구문</span><span class="sxs-lookup"><span data-stu-id="08f97-104">Syntax</span></span>  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08f97-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08f97-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="08f97-106">[in] Blob의 열에서 반환 된 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="08f97-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="08f97-107">[out] 추가 BLOB의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="08f97-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08f97-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08f97-108">Requirements</span></span>  
 <span data-ttu-id="08f97-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="08f97-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08f97-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="08f97-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08f97-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="08f97-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08f97-112">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08f97-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f97-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08f97-113">See Also</span></span>  
 [<span data-ttu-id="08f97-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08f97-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="08f97-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08f97-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
