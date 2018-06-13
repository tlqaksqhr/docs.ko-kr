---
title: IMetaDataTables2::GetMetaDataStorage 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33064fe8292eb7a8079d2f68bcdea767d306be6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452321"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="d3f88-102">IMetaDataTables2::GetMetaDataStorage 메서드</span><span class="sxs-lookup"><span data-stu-id="d3f88-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="d3f88-103">크기와 지정된 된 섹션에 저장 된 메타 데이터의 내용을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3f88-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3f88-104">구문</span><span class="sxs-lookup"><span data-stu-id="d3f88-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3f88-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3f88-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="d3f88-106">[out에서] 메타 데이터 섹션에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f88-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="d3f88-107">[out] 메타 데이터 스트림의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f88-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3f88-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3f88-108">Requirements</span></span>  
 <span data-ttu-id="d3f88-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f88-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3f88-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d3f88-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3f88-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="d3f88-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3f88-112">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3f88-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3f88-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3f88-113">See Also</span></span>  
 [<span data-ttu-id="d3f88-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3f88-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 [<span data-ttu-id="d3f88-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3f88-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
