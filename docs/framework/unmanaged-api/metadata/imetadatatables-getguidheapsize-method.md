---
title: IMetaDataTables::GetGuidHeapSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97d196769b549022ce498958fc34cf08df442d0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447092"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="b3f24-102">IMetaDataTables::GetGuidHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="b3f24-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="b3f24-103">GUID 힙을 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b3f24-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f24-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3f24-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3f24-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3f24-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="b3f24-106">[out] GUID 힙을 바이트 단위로 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f24-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3f24-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3f24-107">Requirements</span></span>  
 <span data-ttu-id="b3f24-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f24-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3f24-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b3f24-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3f24-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b3f24-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3f24-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3f24-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f24-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3f24-112">See Also</span></span>  
 [<span data-ttu-id="b3f24-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3f24-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="b3f24-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3f24-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
