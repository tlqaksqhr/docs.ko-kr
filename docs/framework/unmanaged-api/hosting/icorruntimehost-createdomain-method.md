---
title: ICorRuntimeHost::CreateDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea2353f1375667619db47ac5e1f037ce68dbded5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438144"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="15504-102">ICorRuntimeHost::CreateDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="15504-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="15504-103">응용 프로그램 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="15504-103">Creates an application domain.</span></span> <span data-ttu-id="15504-104">호출자가 형식의 인터페이스 포인터를 받을 <xref:System._AppDomain> 형식의 인스턴스로 <xref:System.AppDomain?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="15504-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15504-105">구문</span><span class="sxs-lookup"><span data-stu-id="15504-105">Syntax</span></span>  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15504-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15504-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="15504-107">[in] 도메인에 친숙 한 이름을 지정 하는 데 사용 되는 선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="15504-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="15504-108">이 이름은 도메인을 식별 하는 디버거 같은 사용자 인터페이스에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15504-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="15504-109">[in] 에 대 한 포인터의 선택적 배열 `IIdentity` 사용 권한 집합을 설정 하기 위해 보안 정책을 통해 매핑된 증명 정보를 나타내는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="15504-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="15504-110">`IIdentity` 호출 하 여 개체를 가져올 수는 [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="15504-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="15504-111">[out] 형식의 인터페이스 포인터 <xref:System._AppDomain> 인스턴스에 <xref:System.AppDomain?displayProperty=nameWithType> 도메인 추가 제어를 위해 사용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="15504-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15504-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="15504-112">Return Value</span></span>  
  
|<span data-ttu-id="15504-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15504-113">HRESULT</span></span>|<span data-ttu-id="15504-114">설명</span><span class="sxs-lookup"><span data-stu-id="15504-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15504-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="15504-115">S_OK</span></span>|<span data-ttu-id="15504-116">작업이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="15504-116">The operation was successful.</span></span>|  
|<span data-ttu-id="15504-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="15504-117">S_FALSE</span></span>|<span data-ttu-id="15504-118">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="15504-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="15504-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15504-119">E_FAIL</span></span>|<span data-ttu-id="15504-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="15504-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="15504-121">메서드가 E_FAIL을 반환 하는 경우 공용 언어 런타임 (CLR)을 하는 프로세스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15504-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="15504-122">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="15504-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="15504-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15504-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15504-124">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15504-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15504-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15504-125">Requirements</span></span>  
 <span data-ttu-id="15504-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15504-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15504-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15504-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15504-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="15504-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15504-129">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="15504-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15504-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15504-130">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="15504-131">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15504-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
