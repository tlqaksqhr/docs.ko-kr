---
title: IMetaDataTables::GetColumn 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 850a97240e0a6450b4dec759a8786e0df5bffac8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448962"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="a8fe5-102">IMetaDataTables::GetColumn 메서드</span><span class="sxs-lookup"><span data-stu-id="a8fe5-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="a8fe5-103">지정 된 열과 지정된 된 테이블의 행의 셀에 포함 된 값에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8fe5-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8fe5-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8fe5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8fe5-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="a8fe5-106">[in] 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="a8fe5-107">[in] 테이블에 있는 열의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="a8fe5-108">[in] 테이블의 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="a8fe5-109">[out] 셀의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8fe5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8fe5-110">Requirements</span></span>  
 <span data-ttu-id="a8fe5-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8fe5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8fe5-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a8fe5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8fe5-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a8fe5-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8fe5-114">**.NET framework 버전** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8fe5-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8fe5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8fe5-115">See Also</span></span>  
 [<span data-ttu-id="a8fe5-116">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8fe5-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="a8fe5-117">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8fe5-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
