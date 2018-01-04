---
title: "ICorRuntimeHost::CreateEvidence 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateEvidence
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 754b254fb9a41ab8bb900fdb5d0c10a126b804c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="b8304-102">ICorRuntimeHost::CreateEvidence 메서드</span><span class="sxs-lookup"><span data-stu-id="b8304-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="b8304-103">형식의 인터페이스 포인터를 가져옵니다 <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>를 허용 하는 호스트를 만드는 보안 증명 정보를 전달 하는 [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) 또는 [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b8304-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8304-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8304-104">Syntax</span></span>  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8304-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8304-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="b8304-106">[out] 에 대 한 인터페이스 포인터는 <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> 인스턴스를 보안 증명을 만드는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8304-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="b8304-107">이 포인터 형식이 `IUnknown`호출자에 게 일반적으로 호출 해야 하므로 `QueryInterface` 이 인터페이스에 대 한 포인터를 가져올 수에 <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="b8304-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8304-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="b8304-108">Return Value</span></span>  
  
|<span data-ttu-id="b8304-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8304-109">HRESULT</span></span>|<span data-ttu-id="b8304-110">설명</span><span class="sxs-lookup"><span data-stu-id="b8304-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8304-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8304-111">S_OK</span></span>|<span data-ttu-id="b8304-112">작업이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b8304-112">The operation was successful.</span></span>|  
|<span data-ttu-id="b8304-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b8304-113">S_FALSE</span></span>|<span data-ttu-id="b8304-114">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="b8304-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="b8304-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b8304-115">E_FAIL</span></span>|<span data-ttu-id="b8304-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b8304-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b8304-117">메서드가 E_FAIL을 반환 하는 경우 공용 언어 런타임 (CLR)을 하는 프로세스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8304-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b8304-118">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b8304-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b8304-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b8304-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b8304-120">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8304-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8304-121">설명</span><span class="sxs-lookup"><span data-stu-id="b8304-121">Remarks</span></span>  
 <span data-ttu-id="b8304-122">이 메서드는 네이티브 코드에서 채울 수 있는 빈 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8304-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="b8304-123">사용 해야는 <xref:System.Security.Policy.Evidence> 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8304-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8304-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8304-124">Requirements</span></span>  
 <span data-ttu-id="b8304-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b8304-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8304-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b8304-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8304-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b8304-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8304-128">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="b8304-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8304-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8304-129">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="b8304-130">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8304-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
