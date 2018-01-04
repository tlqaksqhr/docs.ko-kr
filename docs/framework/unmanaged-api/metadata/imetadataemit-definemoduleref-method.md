---
title: "IMetaDataEmit::DefineModuleRef 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineModuleRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b745e216ca49ed5d226d6d531281880b43e4939
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="dd92c-102">IMetaDataEmit::DefineModuleRef 메서드</span><span class="sxs-lookup"><span data-stu-id="dd92c-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="dd92c-103">지정 된 이름의 모듈에 대 한 메타 데이터 서명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd92c-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd92c-104">구문</span><span class="sxs-lookup"><span data-stu-id="dd92c-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd92c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dd92c-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="dd92c-106">[in] 다른 메타 데이터 파일 일반적으로 DLL의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dd92c-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="dd92c-107">이 파일 이름만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd92c-107">This is the file name only.</span></span> <span data-ttu-id="dd92c-108">전체 경로 이름을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="dd92c-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="dd92c-109">[out] 할당 된 `mdModuleRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="dd92c-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd92c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd92c-110">Requirements</span></span>  
 <span data-ttu-id="dd92c-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd92c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd92c-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dd92c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd92c-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="dd92c-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd92c-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd92c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd92c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd92c-115">See Also</span></span>  
 [<span data-ttu-id="dd92c-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd92c-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="dd92c-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd92c-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
