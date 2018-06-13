---
title: IMetaDataTables::GetNextString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eea43e5eaa037a3b70f482b0602d8d8d3d594f75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449851"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="1c3cf-102">IMetaDataTables::GetNextString 메서드</span><span class="sxs-lookup"><span data-stu-id="1c3cf-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="1c3cf-103">현재 테이블 열에 다음 문자열의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c3cf-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c3cf-104">구문</span><span class="sxs-lookup"><span data-stu-id="1c3cf-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c3cf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c3cf-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="1c3cf-106">[in] 문자열 테이블 열에서 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3cf-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="1c3cf-107">[out] 열에 다음 문자열의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3cf-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c3cf-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c3cf-108">Requirements</span></span>  
 <span data-ttu-id="1c3cf-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3cf-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c3cf-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1c3cf-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c3cf-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="1c3cf-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c3cf-112">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c3cf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c3cf-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c3cf-113">See Also</span></span>  
 [<span data-ttu-id="1c3cf-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c3cf-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="1c3cf-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c3cf-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
