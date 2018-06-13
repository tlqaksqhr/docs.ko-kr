---
title: IMetaDataTables::GetUserStringHeapSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a217a835e258052ace5b59a70cbc0fa31691d78e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452848"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="a2f05-102">IMetaDataTables::GetUserStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="a2f05-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="a2f05-103">사용자 문자열 힙을 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a2f05-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2f05-104">구문</span><span class="sxs-lookup"><span data-stu-id="a2f05-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2f05-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2f05-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="a2f05-106">[out] 사용자 문자열 힙을 바이트 단위로 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a2f05-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2f05-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2f05-107">Requirements</span></span>  
 <span data-ttu-id="a2f05-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2f05-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2f05-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a2f05-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2f05-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a2f05-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a2f05-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2f05-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f05-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2f05-112">See Also</span></span>  
 [<span data-ttu-id="a2f05-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2f05-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="a2f05-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2f05-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
