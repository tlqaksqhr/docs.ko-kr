---
title: "IHostIoCompletionManager::InitializeHostOverlapped 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6b558d638e598ba6e3d0055e3a842976896e99d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="3c187-102">IHostIoCompletionManager::InitializeHostOverlapped 메서드</span><span class="sxs-lookup"><span data-stu-id="3c187-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="3c187-103">호스트에는 Win32에 추가할 사용자 지정 데이터를 초기화할 수 있도록 제공 `OVERLAPPED` 비동기 I/O 요청에 사용 되는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c187-104">구문</span><span class="sxs-lookup"><span data-stu-id="3c187-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c187-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c187-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="3c187-106">[in] Win32에 대 한 포인터 `OVERLAPPED` I/O 요청에 포함 될 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c187-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="3c187-107">Return Value</span></span>  
  
|<span data-ttu-id="3c187-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c187-108">HRESULT</span></span>|<span data-ttu-id="3c187-109">설명</span><span class="sxs-lookup"><span data-stu-id="3c187-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c187-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c187-110">S_OK</span></span>|<span data-ttu-id="3c187-111">`InitializeHostOverlapped`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="3c187-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c187-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c187-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3c187-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3c187-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3c187-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-115">The call timed out.</span></span>|  
|<span data-ttu-id="3c187-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c187-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3c187-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3c187-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3c187-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3c187-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3c187-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c187-120">E_FAIL</span></span>|<span data-ttu-id="3c187-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3c187-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3c187-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3c187-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3c187-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3c187-125">요청 된 리소스를 할당할 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c187-126">설명</span><span class="sxs-lookup"><span data-stu-id="3c187-126">Remarks</span></span>  
 <span data-ttu-id="3c187-127">Windows 플랫폼에 사용 하 여 함수는 `OVERLAPPED` 비동기 I/O 요청에 대 한 상태를 저장 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="3c187-128">CLR에서는 `InitializeHostOverlapped` 호스트는 사용자 지정 데이터를 추가할 수 있도록 지정 합니다. 메서드는 `OVERLAPPED` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3c187-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c187-129">해당 사용자 지정 데이터 블록의 시작 부분을 가져오려면 호스트 설정 해야 오프셋의 크기는 `OVERLAPPED` 구조 (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="3c187-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="3c187-130">반환 값 E_OUTOFMEMORY 호스트에 사용자 지정 데이터 초기화 되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="3c187-131">이 경우 CLR에서 오류를 보고 하 고 호출에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c187-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c187-132">Requirements</span></span>  
 <span data-ttu-id="3c187-133">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c187-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c187-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3c187-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c187-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3c187-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c187-136">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c187-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c187-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c187-137">See Also</span></span>  
 [<span data-ttu-id="3c187-138">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c187-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="3c187-139">GetHostOverlappedSize 메서드</span><span class="sxs-lookup"><span data-stu-id="3c187-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)  
 [<span data-ttu-id="3c187-140">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c187-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
