---
title: IMetaDataTables::GetTableIndex 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d207eae5e9ac1b3020216226442321e72840c037
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450364"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="3e7f5-102">IMetaDataTables::GetTableIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="3e7f5-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="3e7f5-103">지정한 토큰이 참조 하는 테이블에 대 한 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3e7f5-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e7f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e7f5-104">Syntax</span></span>  
  
```  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e7f5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e7f5-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="3e7f5-106">[in] 테이블을 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3e7f5-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="3e7f5-107">[out] 참조 된 테이블에 대 한 반환 된 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3e7f5-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e7f5-108">설명</span><span class="sxs-lookup"><span data-stu-id="3e7f5-108">Remarks</span></span>  
 <span data-ttu-id="3e7f5-109">권장 하지는 않습니다이 메서드를 사용 하 여 일관 된 결과 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e7f5-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="3e7f5-110">GUID 테이블에 대 한 내용은 "II: 메타 데이터 정의 및 의미" 인프라 CLI (공용 언어) 설명서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7f5-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="3e7f5-111">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](http://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](http://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e7f5-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e7f5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e7f5-112">Requirements</span></span>  
 <span data-ttu-id="3e7f5-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7f5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e7f5-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3e7f5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e7f5-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="3e7f5-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e7f5-116">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e7f5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e7f5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e7f5-117">See Also</span></span>  
 [<span data-ttu-id="3e7f5-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e7f5-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="3e7f5-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e7f5-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
