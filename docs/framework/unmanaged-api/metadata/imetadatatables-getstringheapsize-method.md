---
title: IMetaDataTables::GetStringHeapSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d814a741bc88bb50bfe9ddc3db57635a7266a82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449922"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="b8db3-102">IMetaDataTables::GetStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="b8db3-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="b8db3-103">문자열 힙을 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b8db3-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8db3-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8db3-104">Syntax</span></span>  
  
```  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8db3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8db3-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="b8db3-106">[out] 문자열 힙을 바이트 단위로 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b8db3-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8db3-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8db3-107">Requirements</span></span>  
 <span data-ttu-id="b8db3-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b8db3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8db3-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b8db3-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8db3-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b8db3-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b8db3-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8db3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8db3-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8db3-112">See Also</span></span>  
 [<span data-ttu-id="b8db3-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8db3-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="b8db3-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8db3-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
