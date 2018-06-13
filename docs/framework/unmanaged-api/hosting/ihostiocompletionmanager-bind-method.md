---
title: IHostIoCompletionManager::Bind 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89a30cf4fa95df85e3650459e356a6a82b19bcd6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439829"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="2184c-102">IHostIoCompletionManager::Bind 메서드</span><span class="sxs-lookup"><span data-stu-id="2184c-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="2184c-103">지정된 된 핸들에 대 한 이전 호출에서 생성 된 I/O 완료 포트에 바인딩합니다 [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2184c-104">구문</span><span class="sxs-lookup"><span data-stu-id="2184c-104">Syntax</span></span>  
  
```  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2184c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2184c-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="2184c-106">[in] I/O 완료 포트를 바인딩할 `hHandle`합니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="2184c-107">하는 경우의 값 `hPort` 매개 변수가 null 이면 `hHandle` 기본 I/O 완료 포트에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="2184c-108">[in] 운영 체제 핸들을 바인딩할 `hPort`합니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2184c-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="2184c-109">Return Value</span></span>  
  
|<span data-ttu-id="2184c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2184c-110">HRESULT</span></span>|<span data-ttu-id="2184c-111">설명</span><span class="sxs-lookup"><span data-stu-id="2184c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2184c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2184c-112">S_OK</span></span>|<span data-ttu-id="2184c-113">`Bind` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="2184c-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2184c-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2184c-115">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2184c-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2184c-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2184c-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-117">The call timed out.</span></span>|  
|<span data-ttu-id="2184c-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2184c-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2184c-119">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2184c-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2184c-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2184c-121">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2184c-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2184c-122">E_FAIL</span></span>|<span data-ttu-id="2184c-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2184c-124">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2184c-125">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2184c-126">설명</span><span class="sxs-lookup"><span data-stu-id="2184c-126">Remarks</span></span>  
 <span data-ttu-id="2184c-127">I/O 완료 포트에 대 한 호출을 사용 하 여 만들어집니다 `CreateIoCompletionPort`합니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="2184c-128">CLR에서는 `Bind` 에 해당 포트에 대 한 핸들을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2184c-129">호스트에서는 I/O 요청이 완료 되 면 호출 하 여 [iclriocompletionmanager:: Oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="2184c-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2184c-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2184c-130">Requirements</span></span>  
 <span data-ttu-id="2184c-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2184c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2184c-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2184c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2184c-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2184c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2184c-134">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2184c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2184c-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2184c-135">See Also</span></span>  
 [<span data-ttu-id="2184c-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2184c-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
