---
title: "ITypeName::GetModifiers 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ITypeName.GetModifiers
api_location: mscoree.dll
api_type: COM
f1_keywords: GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a7a6bfb8a8520d390844442665e4ba5feb4dcffb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="76f0c-102">ITypeName::GetModifiers 메서드</span><span class="sxs-lookup"><span data-stu-id="76f0c-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="76f0c-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76f0c-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f0c-104">구문</span><span class="sxs-lookup"><span data-stu-id="76f0c-104">Syntax</span></span>  
  
```  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="76f0c-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76f0c-105">Requirements</span></span>  
 <span data-ttu-id="76f0c-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="76f0c-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76f0c-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="76f0c-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76f0c-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="76f0c-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76f0c-109">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76f0c-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f0c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76f0c-110">See Also</span></span>  
 [<span data-ttu-id="76f0c-111">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76f0c-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
