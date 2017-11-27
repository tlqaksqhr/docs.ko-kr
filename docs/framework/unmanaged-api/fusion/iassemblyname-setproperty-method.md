---
title: "IAssemblyName::SetProperty 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.SetProperty
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b99b9c01d014f7b6c02eedde157fa6fdd4e142a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="cff88-102">IAssemblyName::SetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="cff88-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="cff88-103">지정 된 속성 식별자가 참조 하는 속성의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff88-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff88-104">구문</span><span class="sxs-lookup"><span data-stu-id="cff88-104">Syntax</span></span>  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cff88-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cff88-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="cff88-106">[in] 해당 값을 설정할 속성의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="cff88-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="cff88-107">[in] 참조 하는 속성을 설정 하는 값 `PropertyId`합니다.</span><span class="sxs-lookup"><span data-stu-id="cff88-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="cff88-108">[in] 를 바이트 단위로 크기의 `pvProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="cff88-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cff88-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cff88-109">Requirements</span></span>  
 <span data-ttu-id="cff88-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cff88-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cff88-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="cff88-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cff88-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cff88-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff88-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cff88-113">See Also</span></span>  
 [<span data-ttu-id="cff88-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cff88-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
