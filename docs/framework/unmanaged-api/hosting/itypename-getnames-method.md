---
title: ITypeName::GetNames 메서드
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d718564f4ed106956aadd2f54212f28e8cfc3de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440699"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="f3b97-102">ITypeName::GetNames 메서드</span><span class="sxs-lookup"><span data-stu-id="f3b97-102">ITypeName::GetNames Method</span></span>
<span data-ttu-id="f3b97-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3b97-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b97-104">구문</span><span class="sxs-lookup"><span data-stu-id="f3b97-104">Syntax</span></span>  
  
```  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f3b97-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3b97-105">Requirements</span></span>  
 <span data-ttu-id="f3b97-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b97-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3b97-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f3b97-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3b97-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f3b97-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3b97-109">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3b97-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b97-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3b97-110">See Also</span></span>  
 [<span data-ttu-id="f3b97-111">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3b97-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
