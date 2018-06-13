---
title: ICLRRuntimeHost::ExecuteApplication 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56a49b3d08b58da109924267e6c23c188efefe29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436074"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="9c4dc-102">ICLRRuntimeHost::ExecuteApplication 메서드</span><span class="sxs-lookup"><span data-stu-id="9c4dc-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="9c4dc-103">ClickOnce 배포 매니페스트 기반 시나리오에서 새 도메인의 활성화 될 응용 프로그램을 지정 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="9c4dc-104">이러한 시나리오에 대 한 자세한 내용은 참조 [ClickOnce 보안 및 배포](/visualstudio/deployment/clickonce-security-and-deployment)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c4dc-105">구문</span><span class="sxs-lookup"><span data-stu-id="9c4dc-105">Syntax</span></span>  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c4dc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c4dc-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="9c4dc-107">[in] 에 대해 정의 된 대로 응용 프로그램의 전체 이름을 <xref:System.ApplicationIdentity>합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="9c4dc-108">[in] 에 포함 된 문자열의 수는 `ppwzManifestPaths` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="9c4dc-109">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="9c4dc-109">[in] Optional.</span></span> <span data-ttu-id="9c4dc-110">응용 프로그램에 대 한 매니페스트 경로 포함 하는 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="9c4dc-111">[in] 에 포함 된 문자열의 수는 `ppwzActivationData` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="9c4dc-112">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="9c4dc-112">[in] Optional.</span></span> <span data-ttu-id="9c4dc-113">웹을 통해 배포 된 응용 프로그램에 대 한 URL의 쿼리 문자열 부분 같은 응용 프로그램의 정품 인증 데이터를 포함 하는 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="9c4dc-114">[out] 응용 프로그램의 진입점에서 반환한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c4dc-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="9c4dc-115">Return Value</span></span>  
  
|<span data-ttu-id="9c4dc-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c4dc-116">HRESULT</span></span>|<span data-ttu-id="9c4dc-117">설명</span><span class="sxs-lookup"><span data-stu-id="9c4dc-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c4dc-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c4dc-118">S_OK</span></span>|<span data-ttu-id="9c4dc-119">`ExecuteApplication` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="9c4dc-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9c4dc-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9c4dc-121">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9c4dc-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9c4dc-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9c4dc-123">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-123">The call timed out.</span></span>|  
|<span data-ttu-id="9c4dc-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9c4dc-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9c4dc-125">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9c4dc-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9c4dc-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9c4dc-127">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9c4dc-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9c4dc-128">E_FAIL</span></span>|<span data-ttu-id="9c4dc-129">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9c4dc-130">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9c4dc-131">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c4dc-132">설명</span><span class="sxs-lookup"><span data-stu-id="9c4dc-132">Remarks</span></span>  
 <span data-ttu-id="9c4dc-133">`ExecuteApplication` 새로 만든된 응용 프로그램 도메인에서 ClickOnce 응용 프로그램을 활성화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="9c4dc-134">`pReturnValue` 출력 매개 변수는 응용 프로그램에 의해 반환 되는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="9c4dc-135">에 대 한 null 값을 제공 하는 경우 `pReturnValue`, `ExecuteApplication` 실패 하지 하지만 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9c4dc-136">호출 하지 마십시오는 [Start 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 메서드 호출 하기 전에 `ExecuteApplication` 메서드 매니페스트 기반 응용 프로그램을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="9c4dc-137">경우는 `Start` 메서드는 먼저는 `ExecuteApplication` 메서드 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c4dc-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c4dc-138">Requirements</span></span>  
 <span data-ttu-id="9c4dc-139">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4dc-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c4dc-140">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9c4dc-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9c4dc-141">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9c4dc-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c4dc-142">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c4dc-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4dc-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c4dc-143">See Also</span></span>  
 <xref:System.ActivationContext>  
 <xref:System.AppDomainManager>  
 <xref:System.ApplicationIdentity>  
 [<span data-ttu-id="9c4dc-144">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c4dc-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="9c4dc-145">SetAppDomainManager 메서드</span><span class="sxs-lookup"><span data-stu-id="9c4dc-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)  
 [<span data-ttu-id="9c4dc-146">연습: 디자이너를 사용하여 ClickOnce 배포 API에서 요청 시 어셈블리 다운로드</span><span class="sxs-lookup"><span data-stu-id="9c4dc-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
