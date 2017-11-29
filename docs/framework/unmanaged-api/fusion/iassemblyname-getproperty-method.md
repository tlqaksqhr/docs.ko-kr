---
title: "IAssemblyName::GetProperty 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.GetProperty
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6eae7cf2d6dabe9bad4912d6a97249f52464fe65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="ad773-102">IAssemblyName::GetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="ad773-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="ad773-103">지정 된 속성 식별자가 참조 하는 속성에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ad773-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad773-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad773-104">Syntax</span></span>  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad773-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad773-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="ad773-106">[in] 요청된 된 속성에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ad773-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="ad773-107">[out] 반환 된 속성 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="ad773-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="ad773-108">[out에서] 를 바이트 단위로 크기의 `pvProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad773-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad773-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad773-109">Requirements</span></span>  
 <span data-ttu-id="ad773-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad773-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad773-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ad773-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ad773-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad773-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad773-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad773-113">See Also</span></span>  
 [<span data-ttu-id="ad773-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad773-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
