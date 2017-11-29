---
title: "IMetaDataImport::ResetEnum 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.ResetEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2cdb4c00185d152be856a99e1fec9392fd2a4029
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="378ff-102">IMetaDataImport::ResetEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="378ff-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="378ff-103">지정한 열거자를 지정한 위치로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="378ff-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="378ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="378ff-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="378ff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="378ff-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="378ff-106">[in] 다시 설정 하는 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="378ff-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="378ff-107">[in] 열거자를 배치할 새 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="378ff-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="378ff-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="378ff-108">Requirements</span></span>  
 <span data-ttu-id="378ff-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="378ff-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="378ff-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="378ff-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="378ff-111">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="378ff-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="378ff-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="378ff-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="378ff-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="378ff-113">See Also</span></span>  
 [<span data-ttu-id="378ff-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="378ff-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="378ff-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="378ff-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
