---
title: "ICorRuntimeHost::NextDomain 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.NextDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: de7d90ed55cf27aa0b1679b5e55d9f28902b6aeb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="e58da-102">ICorRuntimeHost::NextDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="e58da-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="e58da-103">다음 도메인으로 열거형에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e58da-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e58da-104">구문</span><span class="sxs-lookup"><span data-stu-id="e58da-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e58da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e58da-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="e58da-106">[in] 열거자에 대 한 호출을 통해 가져온 [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e58da-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="e58da-107">[out] 에 대 한 인터페이스 포인터의 <xref:System._AppDomain?displayProperty=nameWithType> 도메인이 더 있는 경우 열거형 또는 null에서 다음 도메인을 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e58da-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e58da-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="e58da-108">Return Value</span></span>  
  
|<span data-ttu-id="e58da-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e58da-109">HRESULT</span></span>|<span data-ttu-id="e58da-110">설명</span><span class="sxs-lookup"><span data-stu-id="e58da-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e58da-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e58da-111">S_OK</span></span>|<span data-ttu-id="e58da-112">작업이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e58da-112">The operation was successful.</span></span>|  
|<span data-ttu-id="e58da-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e58da-113">S_FALSE</span></span>|<span data-ttu-id="e58da-114">도메인이 더 열거에 없는 또는 작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="e58da-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="e58da-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e58da-115">E_FAIL</span></span>|<span data-ttu-id="e58da-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e58da-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e58da-117">메서드가 E_FAIL을 반환 하는 경우 공용 언어 런타임 (CLR)을 하는 프로세스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e58da-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e58da-118">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e58da-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e58da-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e58da-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e58da-120">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e58da-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e58da-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e58da-121">Requirements</span></span>  
 <span data-ttu-id="e58da-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e58da-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e58da-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e58da-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e58da-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e58da-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e58da-125">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="e58da-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e58da-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e58da-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="e58da-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e58da-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
