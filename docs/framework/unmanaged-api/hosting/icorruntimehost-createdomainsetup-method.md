---
title: ICorRuntimeHost::CreateDomainSetup 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf3aff2c3c4d10c4ee805a6110561d6fdcd63a55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437988"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="be623-102">ICorRuntimeHost::CreateDomainSetup 메서드</span><span class="sxs-lookup"><span data-stu-id="be623-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="be623-103">인터페이스 포인터의 형식에 IAppDomainSetup 가져옵니다는 <xref:System.AppDomainSetup?displayProperty=nameWithType> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="be623-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="be623-104">`IAppDomainSetup` 만들기 전에 응용 프로그램 도메인의 측면을 구성 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be623-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be623-105">구문</span><span class="sxs-lookup"><span data-stu-id="be623-105">Syntax</span></span>  
  
```  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be623-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="be623-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="be623-107">[out] 에 대 한 인터페이스 포인터는 <xref:System.AppDomainSetup?displayProperty=nameWithType> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="be623-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="be623-108">형식의이 매개 변수를 `IUnknown`호출자에 게 일반적으로 호출 해야 하므로 `QueryInterface` 가져올 형식의 인터페이스 포인터에 대 한 포인터이 `IAppDomainSetup`합니다.</span><span class="sxs-lookup"><span data-stu-id="be623-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be623-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="be623-109">Return Value</span></span>  
  
|<span data-ttu-id="be623-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be623-110">HRESULT</span></span>|<span data-ttu-id="be623-111">설명</span><span class="sxs-lookup"><span data-stu-id="be623-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be623-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="be623-112">S_OK</span></span>|<span data-ttu-id="be623-113">작업이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="be623-113">The operation was successful.</span></span>|  
|<span data-ttu-id="be623-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="be623-114">S_FALSE</span></span>|<span data-ttu-id="be623-115">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="be623-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="be623-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="be623-116">E_FAIL</span></span>|<span data-ttu-id="be623-117">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="be623-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="be623-118">메서드가 E_FAIL을 반환 하는 경우 공용 언어 런타임 (CLR)을 하는 프로세스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be623-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="be623-119">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="be623-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="be623-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="be623-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="be623-121">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be623-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be623-122">설명</span><span class="sxs-lookup"><span data-stu-id="be623-122">Remarks</span></span>  
 <span data-ttu-id="be623-123">이 메서드에서 반환 된 포인터는 일반적으로 매개 변수로 전달 되는 [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="be623-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be623-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be623-124">Requirements</span></span>  
 <span data-ttu-id="be623-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="be623-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be623-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="be623-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be623-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="be623-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be623-128">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="be623-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be623-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be623-129">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup?displayProperty=nameWithType>  
 [<span data-ttu-id="be623-130">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be623-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
