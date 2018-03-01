---
title: "IMetaDataTables::GetRow 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 760bee2c4a6a6efb16a32579578ab4953492c48e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="6bab5-102">IMetaDataTables::GetRow 메서드</span><span class="sxs-lookup"><span data-stu-id="6bab5-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="6bab5-103">지정 된 행 인덱스에 지정된 된 테이블 인덱스에 있는 테이블에 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6bab5-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bab5-104">구문</span><span class="sxs-lookup"><span data-stu-id="6bab5-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bab5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6bab5-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="6bab5-106">[in] 행을 검색할 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="6bab5-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="6bab5-107">[in] 가져올 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="6bab5-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="6bab5-108">[out] 행에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6bab5-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bab5-109">설명</span><span class="sxs-lookup"><span data-stu-id="6bab5-109">Remarks</span></span>  
 <span data-ttu-id="6bab5-110">권장 하지는 않습니다이 메서드를 사용 하 여 일관 된 결과 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bab5-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="6bab5-111">GUID 테이블에 대 한 내용은 "II: 메타 데이터 정의 및 의미" 인프라 CLI (공용 언어) 설명서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bab5-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="6bab5-112">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](http://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](http://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bab5-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bab5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6bab5-113">Requirements</span></span>  
 <span data-ttu-id="6bab5-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bab5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bab5-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6bab5-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6bab5-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="6bab5-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6bab5-117">**.NET framework 버전**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bab5-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bab5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bab5-118">See Also</span></span>  
 [<span data-ttu-id="6bab5-119">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bab5-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="6bab5-120">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bab5-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
