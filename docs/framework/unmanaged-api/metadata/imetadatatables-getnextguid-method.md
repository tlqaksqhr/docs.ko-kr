---
title: "IMetaDataTables::GetNextGuid 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNextGuid
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 015bf62bdca1c7437afb26a5d08d21bd276cd3db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="8a05e-102">IMetaDataTables::GetNextGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="8a05e-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="8a05e-103">현재 테이블 열에 다음 GUID 값의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8a05e-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a05e-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a05e-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a05e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a05e-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="8a05e-106">[in] GUID 테이블 열에서 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8a05e-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="8a05e-107">[out] 다음 GUID 값의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8a05e-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a05e-108">설명</span><span class="sxs-lookup"><span data-stu-id="8a05e-108">Remarks</span></span>  
 <span data-ttu-id="8a05e-109">권장 하지는 않습니다이 메서드를 사용 하 여 일관 된 결과 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a05e-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="8a05e-110">GUID 테이블에 대 한 내용은 "II: 메타 데이터 정의 및 의미" 인프라 CLI (공용 언어) 설명서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a05e-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="8a05e-111">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](http://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](http://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a05e-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a05e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a05e-112">Requirements</span></span>  
 <span data-ttu-id="8a05e-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a05e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a05e-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8a05e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a05e-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="8a05e-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a05e-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a05e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a05e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a05e-117">See Also</span></span>  
 [<span data-ttu-id="8a05e-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a05e-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="8a05e-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a05e-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
