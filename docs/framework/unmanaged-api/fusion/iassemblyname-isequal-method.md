---
title: "IAssemblyName::IsEqual 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.IsEqual
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 51a4fbe005a8e270b9fe6767ae5173bd027a191b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="d39b4-102">IAssemblyName::IsEqual 메서드</span><span class="sxs-lookup"><span data-stu-id="d39b4-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="d39b4-103">지정 된 있는지 여부를 결정 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체가 같은지를이 `IAssemblyName`지정된 된 비교 플래그에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39b4-103">Determines whether a specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d39b4-104">구문</span><span class="sxs-lookup"><span data-stu-id="d39b4-104">Syntax</span></span>  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d39b4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d39b4-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="d39b4-106">[in] `IAssemblyName` 비교 하는 개체 `IAssemblyName`합니다.</span><span class="sxs-lookup"><span data-stu-id="d39b4-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="d39b4-107">[in] 비트 조합 [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) 비교 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d39b4-107">[in] A bitwise combination of [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d39b4-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d39b4-108">Requirements</span></span>  
 <span data-ttu-id="d39b4-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d39b4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d39b4-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d39b4-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d39b4-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d39b4-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d39b4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d39b4-112">See Also</span></span>  
 [<span data-ttu-id="d39b4-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d39b4-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="d39b4-114">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="d39b4-114">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
