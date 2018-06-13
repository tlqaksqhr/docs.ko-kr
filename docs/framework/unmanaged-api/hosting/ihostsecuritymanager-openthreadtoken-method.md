---
title: IHostSecurityManager::OpenThreadToken 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35a41badd7ade016619d940880a3ace80ccf5693
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439516"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="a7b7d-102">IHostSecurityManager::OpenThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="a7b7d-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="a7b7d-103">현재 실행 중인 스레드와 연결 된 임의 액세스 토큰을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7b7d-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7b7d-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7b7d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7b7d-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="a7b7d-106">[in] 요청 된 유형의 스레드 토큰에 대 한 액세스를 지정 하는 액세스 값의 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="a7b7d-107">이러한 값은 win32에서 정의 `OpenThreadToken` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="a7b7d-108">요청 된 액세스 형식은 토큰의 임의 액세스 제어 목록 (DACL)의 액세스를 허용 하거나 거부할 유형을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="a7b7d-109">[in] `true` 호출 스레드가;에 대 한 프로세스의 보안 컨텍스트를 사용 하 여 액세스 검사 수행 수를 지정 하려면 `false` 액세스 확인을 수행 하는 호출 스레드 자체에 대 한 보안 컨텍스트를 사용 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="a7b7d-110">스레드는 클라이언트를 가장 하는 경우 클라이언트 프로세스의 보안 컨텍스트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="a7b7d-111">[out] 새로 열린된 액세스 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7b7d-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="a7b7d-112">Return Value</span></span>  
  
|<span data-ttu-id="a7b7d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7b7d-113">HRESULT</span></span>|<span data-ttu-id="a7b7d-114">설명</span><span class="sxs-lookup"><span data-stu-id="a7b7d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7b7d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7b7d-115">S_OK</span></span>|<span data-ttu-id="a7b7d-116">`OpenThreadToken` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="a7b7d-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a7b7d-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a7b7d-118">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a7b7d-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a7b7d-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a7b7d-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-120">The call timed out.</span></span>|  
|<span data-ttu-id="a7b7d-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a7b7d-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a7b7d-122">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a7b7d-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a7b7d-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a7b7d-124">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a7b7d-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a7b7d-125">E_FAIL</span></span>|<span data-ttu-id="a7b7d-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a7b7d-127">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a7b7d-128">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7b7d-129">설명</span><span class="sxs-lookup"><span data-stu-id="a7b7d-129">Remarks</span></span>  
 <span data-ttu-id="a7b7d-130">`IHostSecurityManager::OpenThreadToken` 동작 마찬가지로 동일한 이름 가진 해당 Win32 함수에 Win32 함수에서는 임의의 스레드에 대 한 핸들에 전달할 호출자를 허용 한다는 점을 제외 하는 동안 `IHostSecurityManager::OpenThreadToken` 만 호출 스레드에 연결 된 토큰을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="a7b7d-131">`HANDLE` 형식이 COM 호환, 즉, 해당 크기는 운영 체제에 적용 하 고 사용자 지정 마샬링 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="a7b7d-132">따라서이 토큰은 CLR과 호스트 간에 프로세스 에서만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7b7d-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7b7d-133">Requirements</span></span>  
 <span data-ttu-id="a7b7d-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7d-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7b7d-135">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7b7d-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7b7d-136">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a7b7d-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7b7d-137">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7b7d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b7d-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7b7d-138">See Also</span></span>  
 [<span data-ttu-id="a7b7d-139">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7b7d-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="a7b7d-140">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7b7d-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
