---
title: "ICorRuntimeHost 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost
helpviewer_keywords: ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b115b8d52f904fef41a2e85c1192a18e5c3d3e08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehost-interface"></a><span data-ttu-id="8955b-102">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8955b-102">ICorRuntimeHost Interface</span></span>
<span data-ttu-id="8955b-103">시작 하 고를 만들고 기본 도메인에 액세스 하 고 프로세스에서 실행 중인 모든 도메인을 열거 하는 응용 프로그램 도메인을 구성 하려면 공용 언어 런타임 (CLR)를 명시적으로 중지할 호스트를 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-103">Provides methods that enable the host to start and stop the common language runtime (CLR) explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>  
  
 <span data-ttu-id="8955b-104">.NET Framework 버전 2.0에서에서이 인터페이스는 의해 대체 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-104">In the .NET Framework version 2.0, this interface is superceded by [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8955b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-105">Methods</span></span>  
  
|<span data-ttu-id="8955b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-106">Method</span></span>|<span data-ttu-id="8955b-107">설명</span><span class="sxs-lookup"><span data-stu-id="8955b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8955b-108">CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-108">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|<span data-ttu-id="8955b-109">도메인 목록의 시작 부분으로 다시 도메인 열거자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-109">Resets a domain enumerator back to the beginning of the domain list.</span></span>|  
|[<span data-ttu-id="8955b-110">CreateDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-110">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|<span data-ttu-id="8955b-111">응용 프로그램 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-111">Creates an application domain.</span></span> <span data-ttu-id="8955b-112">호출자가 형식의 인터페이스 포인터를 받을 <xref:System._AppDomain> 형식의 인스턴스로 <xref:System.AppDomain?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-112">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>|  
|[<span data-ttu-id="8955b-113">CreateDomainEx 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-113">CreateDomainEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|<span data-ttu-id="8955b-114">응용 프로그램 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-114">Creates an application domain.</span></span> <span data-ttu-id="8955b-115">이 메서드를 사용 하면 호출자가 반환 된 추가 기능을 구성을 IAppDomainSetup 인스턴스를 전달 하 여 <xref:System._AppDomain> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8955b-115">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>|  
|[<span data-ttu-id="8955b-116">CreateDomainSetup 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-116">CreateDomainSetup Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|<span data-ttu-id="8955b-117">형식의 인터페이스 포인터를 가져옵니다 `IAppDomainSetup` 에 <xref:System.AppDomainSetup> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8955b-117">Gets an interface pointer of type `IAppDomainSetup` to an <xref:System.AppDomainSetup> instance.</span></span> <span data-ttu-id="8955b-118">`IAppDomainSetup`만들기 전에 응용 프로그램 도메인의 측면을 구성 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-118">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>|  
|[<span data-ttu-id="8955b-119">CreateEvidence 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-119">CreateEvidence Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|<span data-ttu-id="8955b-120">형식의 인터페이스 포인터를 가져옵니다 <xref:System.Security.Principal.IIdentity>, 보안 증명 정보에 전달할를 만들 호스트를 허용 하는 [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) 또는 [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-120">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity>, which allows the host to create security evidence to pass to [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).</span></span>|  
|[<span data-ttu-id="8955b-121">CreateLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-121">CreateLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|<span data-ttu-id="8955b-122">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8955b-122">Do not use.</span></span>|  
|[<span data-ttu-id="8955b-123">CurrentDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-123">CurrentDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|<span data-ttu-id="8955b-124">형식의 인터페이스 포인터를 가져옵니다 <xref:System._AppDomain> 현재 스레드에서 로드 도메인을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-124">Gets an interface pointer of type <xref:System._AppDomain> that represents the domain loaded on the current thread.</span></span>|  
|[<span data-ttu-id="8955b-125">DeleteLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-125">DeleteLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|<span data-ttu-id="8955b-126">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8955b-126">Do not use.</span></span>|  
|[<span data-ttu-id="8955b-127">EnumDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-127">EnumDomains Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|<span data-ttu-id="8955b-128">현재 프로세스에서 도메인에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-128">Gets an enumerator for the domains in the current process.</span></span>|  
|[<span data-ttu-id="8955b-129">GetConfiguration 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-129">GetConfiguration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|<span data-ttu-id="8955b-130">호스트가 CLR의 콜백 구성을 지정할 수 있도록 하는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-130">Gets an object that allows the host to specify the callback configuration of the CLR.</span></span>|  
|[<span data-ttu-id="8955b-131">GetDefaultDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-131">GetDefaultDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|<span data-ttu-id="8955b-132">형식의 인터페이스 포인터를 가져옵니다 <xref:System._AppDomain> 현재 프로세스에 대 한 기본 도메인을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-132">Gets an interface pointer of type <xref:System._AppDomain> that represents the default domain for the current process.</span></span>|  
|[<span data-ttu-id="8955b-133">LocksHeldByLogicalThread 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-133">LocksHeldByLogicalThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|<span data-ttu-id="8955b-134">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8955b-134">Do not use.</span></span>|  
|[<span data-ttu-id="8955b-135">MapFile 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-135">MapFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|<span data-ttu-id="8955b-136">지정된 된 파일을 메모리에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-136">Maps the specified file into memory.</span></span> <span data-ttu-id="8955b-137">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-137">This method is obsolete.</span></span>|  
|[<span data-ttu-id="8955b-138">NextDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-138">NextDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|<span data-ttu-id="8955b-139">다음 도메인으로 열거형에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-139">Gets an interface pointer to the next domain in the enumeration.</span></span>|  
|[<span data-ttu-id="8955b-140">Start 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-140">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|<span data-ttu-id="8955b-141">CLR을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-141">Starts the CLR.</span></span>|  
|[<span data-ttu-id="8955b-142">Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-142">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|<span data-ttu-id="8955b-143">현재 프로세스에 대해 런타임에서 코드의 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-143">Stops the execution of code in the runtime for the current process.</span></span>|  
|[<span data-ttu-id="8955b-144">SwitchInLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-144">SwitchInLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|<span data-ttu-id="8955b-145">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8955b-145">Do not use.</span></span>|  
|[<span data-ttu-id="8955b-146">SwitchOutLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-146">SwitchOutLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|<span data-ttu-id="8955b-147">사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8955b-147">Do not use.</span></span>|  
|[<span data-ttu-id="8955b-148">UnloadDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="8955b-148">UnloadDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|<span data-ttu-id="8955b-149">현재 프로세스에서 지정 된 응용 프로그램 도메인을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-149">Unloads the specified application domain from the current process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8955b-150">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8955b-150">Requirements</span></span>  
 <span data-ttu-id="8955b-151">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8955b-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8955b-152">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8955b-152">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8955b-153">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8955b-153">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8955b-154">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="8955b-154">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8955b-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8955b-155">See Also</span></span>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="8955b-156">호스팅</span><span class="sxs-lookup"><span data-stu-id="8955b-156">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="8955b-157">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8955b-157">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="8955b-158">런타임 호스트</span><span class="sxs-lookup"><span data-stu-id="8955b-158">Runtime Hosts</span></span>](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [<span data-ttu-id="8955b-159">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8955b-159">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="8955b-160">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="8955b-160">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
