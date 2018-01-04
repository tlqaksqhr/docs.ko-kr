---
title: "IAssemblyName::GetName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.GetName
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 681df0b4d6b3d7206954264355afb3ef2628243d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="57ded-102">IAssemblyName::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="57ded-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="57ded-103">이 참조 하는 어셈블리의 단순 하 고 암호화 되지 않은 이름을 가져옵니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="57ded-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57ded-104">구문</span><span class="sxs-lookup"><span data-stu-id="57ded-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57ded-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="57ded-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="57ded-106">[out에서] 크기 `pwzName` 와이드에서 null 종결자 문자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="57ded-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="57ded-107">[out] 참조 된 어셈블리의 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="57ded-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57ded-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="57ded-108">Requirements</span></span>  
 <span data-ttu-id="57ded-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="57ded-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57ded-110">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="57ded-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="57ded-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57ded-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57ded-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57ded-112">See Also</span></span>  
 [<span data-ttu-id="57ded-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="57ded-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
