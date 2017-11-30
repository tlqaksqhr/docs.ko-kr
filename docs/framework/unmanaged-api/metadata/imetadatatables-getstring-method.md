---
title: "IMetaDataTables::GetString 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 687380d3a09a80db216aafbf1ee84c76e31bbf36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="2e1a6-102">IMetaDataTables::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="2e1a6-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="2e1a6-103">현재 참조 범위에서 테이블 열에서 지정된 된 인덱스에 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2e1a6-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e1a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="2e1a6-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e1a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e1a6-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="2e1a6-106">[in] 다음 값을 검색할 시작 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="2e1a6-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="2e1a6-107">[out] 반환 된 문자열 값에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2e1a6-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e1a6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e1a6-108">Requirements</span></span>  
 <span data-ttu-id="2e1a6-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e1a6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e1a6-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2e1a6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e1a6-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="2e1a6-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2e1a6-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e1a6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e1a6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e1a6-113">See Also</span></span>  
 [<span data-ttu-id="2e1a6-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e1a6-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="2e1a6-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e1a6-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
