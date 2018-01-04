---
title: "ICorRuntimeHost::GetConfiguration 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.GetConfiguration
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 446142d8bd61d384c3b8a58d5469e27a7a512c60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="c174f-102">ICorRuntimeHost::GetConfiguration 메서드</span><span class="sxs-lookup"><span data-stu-id="c174f-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="c174f-103">호스트에서 공용 언어 런타임 (CLR)의 콜백 구성을 지정할 수 있는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c174f-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c174f-104">구문</span><span class="sxs-lookup"><span data-stu-id="c174f-104">Syntax</span></span>  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c174f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c174f-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="c174f-106">[out] 주소에 대 한 포인터는 [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) CLR을 구성 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c174f-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c174f-107">설명</span><span class="sxs-lookup"><span data-stu-id="c174f-107">Remarks</span></span>  
 <span data-ttu-id="c174f-108">CLR은 초기화; 하기 전에 구성 해야 합니다. 그렇지 않은 경우는 `GetConfiguration` 메서드 오류를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c174f-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c174f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c174f-109">Requirements</span></span>  
 <span data-ttu-id="c174f-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c174f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c174f-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c174f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c174f-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c174f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c174f-113">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="c174f-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c174f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c174f-114">See Also</span></span>  
 [<span data-ttu-id="c174f-115">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c174f-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
