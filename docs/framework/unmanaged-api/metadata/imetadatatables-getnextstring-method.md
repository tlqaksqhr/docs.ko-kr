---
title: "IMetaDataTables::GetNextString 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNextString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b9d9062ef164c5a50652ed78786725967fda999d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="9b533-102">IMetaDataTables::GetNextString 메서드</span><span class="sxs-lookup"><span data-stu-id="9b533-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="9b533-103">현재 테이블 열에 다음 문자열의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9b533-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b533-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b533-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b533-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b533-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="9b533-106">[in] 문자열 테이블 열에서 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b533-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="9b533-107">[out] 열에 다음 문자열의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9b533-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b533-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b533-108">Requirements</span></span>  
 <span data-ttu-id="9b533-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b533-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b533-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b533-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b533-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="9b533-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b533-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b533-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b533-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b533-113">See Also</span></span>  
 [<span data-ttu-id="9b533-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b533-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="9b533-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b533-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
