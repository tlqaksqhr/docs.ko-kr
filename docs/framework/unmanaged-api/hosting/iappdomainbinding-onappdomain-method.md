---
title: "IAppDomainBinding::OnAppDomain 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppDomainBinding.OnAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f5350b9c44c04a4faee3b5026bc2b97ff549d4b4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="b35ba-102">IAppDomainBinding::OnAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="b35ba-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="b35ba-103">공용 언어 런타임 (CLR)는 응용 프로그램 도메인이 생성 된 호스트에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b35ba-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b35ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="b35ba-104">Syntax</span></span>  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b35ba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b35ba-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="b35ba-106">[in] 에 대 한 포인터는 [IUnknown](https://msdn.microsoft.com/library/94as6ehy(v=vs.110).aspx) 새 응용 프로그램 도메인을 나타내는 인터페이스 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b35ba-106">[in] A pointer to an [IUnknown](https://msdn.microsoft.com/library/94as6ehy(v=vs.110).aspx) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b35ba-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b35ba-107">Requirements</span></span>  
 <span data-ttu-id="b35ba-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b35ba-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b35ba-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b35ba-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b35ba-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b35ba-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b35ba-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b35ba-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b35ba-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b35ba-112">See Also</span></span>  
 [<span data-ttu-id="b35ba-113">IAppDomainBinding 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b35ba-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
