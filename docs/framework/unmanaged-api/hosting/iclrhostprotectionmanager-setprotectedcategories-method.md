---
title: ICLRHostProtectionManager::SetProtectedCategories 메서드
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6c93566d0909f1dbef46862760d47ede478d51a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434540"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="04db6-102">ICLRHostProtectionManager::SetProtectedCategories 메서드</span><span class="sxs-lookup"><span data-stu-id="04db6-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="04db6-103">관리 되는 형식과 멤버의 범주는 부분적으로 신뢰할 수 있는 코드에서 실행에서 차단 해야 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04db6-104">구문</span><span class="sxs-lookup"><span data-stu-id="04db6-104">Syntax</span></span>  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04db6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04db6-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="04db6-106">[in] 조합을 [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) 값을 나타내는 관리 되는 형식과 멤버의 범주는 부분적으로 신뢰할 수 있는 코드에서 실행에서 차단 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04db6-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="04db6-107">Return Value</span></span>  
  
|<span data-ttu-id="04db6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04db6-108">HRESULT</span></span>|<span data-ttu-id="04db6-109">설명</span><span class="sxs-lookup"><span data-stu-id="04db6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04db6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="04db6-110">S_OK</span></span>|<span data-ttu-id="04db6-111">`SetProtectedCategories` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="04db6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="04db6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04db6-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="04db6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="04db6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="04db6-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-115">The call timed out.</span></span>|  
|<span data-ttu-id="04db6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="04db6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="04db6-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="04db6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="04db6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="04db6-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="04db6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04db6-120">E_FAIL</span></span>|<span data-ttu-id="04db6-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="04db6-122">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="04db6-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04db6-124">설명</span><span class="sxs-lookup"><span data-stu-id="04db6-124">Remarks</span></span>  
 <span data-ttu-id="04db6-125">각 `EApiCategories` 값은 관리 되는 형식과 멤버의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="04db6-126">`EApiCategories` 열거형 및 `SetProtectedCategories` 메서드 직접 관련 된 관리 되는 <xref:System.Security.Permissions.HostProtectionAttribute> 관리 되는 형식 및 해당 범주에서 설명 하는 기능을 노출 하는 멤버를 표시 하는 데 사용 되는 클래스 `EApiCategories`합니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="04db6-127">자세한 내용은 참조 <xref:System.Security.Permissions.HostProtectionAttribute> 및 <xref:System.Security.Permissions.HostProtectionResource> 에 해당 하는 열거형 `EApiCategories`합니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04db6-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04db6-128">Requirements</span></span>  
 <span data-ttu-id="04db6-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04db6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04db6-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="04db6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04db6-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="04db6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04db6-132">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04db6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04db6-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04db6-133">See Also</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
 <xref:System.Security.Permissions.HostProtectionResource>  
 [<span data-ttu-id="04db6-134">EApiCategories 열거형</span><span class="sxs-lookup"><span data-stu-id="04db6-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="04db6-135">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="04db6-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="04db6-136">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="04db6-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
