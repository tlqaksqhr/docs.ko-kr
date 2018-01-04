---
title: "IMetaDataAssemblyImport::GetAssemblyFromScope 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyFromScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 725e442180da16ae8165cbea2f625178eb943354
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="35515-102">IMetaDataAssemblyImport::GetAssemblyFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="35515-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="35515-103">현재 범위에서 어셈블리에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35515-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35515-104">구문</span><span class="sxs-lookup"><span data-stu-id="35515-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35515-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35515-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="35515-106">[out] 검색에 대 한 포인터 `mdAssembly` 어셈블리를 식별 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="35515-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35515-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35515-107">Requirements</span></span>  
 <span data-ttu-id="35515-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="35515-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35515-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35515-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35515-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="35515-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35515-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35515-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35515-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35515-112">See Also</span></span>  
 [<span data-ttu-id="35515-113">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35515-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
