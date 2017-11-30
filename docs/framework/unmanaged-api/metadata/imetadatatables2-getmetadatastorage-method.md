---
title: "IMetaDataTables2::GetMetaDataStorage 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables2.GetMetaDataStorage
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b86542a55c0b4e778dfd956961f5a14a1c9d6f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="a7a74-102">IMetaDataTables2::GetMetaDataStorage 메서드</span><span class="sxs-lookup"><span data-stu-id="a7a74-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="a7a74-103">크기와 지정된 된 섹션에 저장 된 메타 데이터의 내용을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a7a74-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7a74-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7a74-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7a74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7a74-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="a7a74-106">[out에서] 메타 데이터 섹션에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a74-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="a7a74-107">[out] 메타 데이터 스트림의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a74-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7a74-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7a74-108">Requirements</span></span>  
 <span data-ttu-id="a7a74-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a74-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7a74-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7a74-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7a74-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a7a74-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7a74-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7a74-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a74-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7a74-113">See Also</span></span>  
 [<span data-ttu-id="a7a74-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7a74-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 [<span data-ttu-id="a7a74-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7a74-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
