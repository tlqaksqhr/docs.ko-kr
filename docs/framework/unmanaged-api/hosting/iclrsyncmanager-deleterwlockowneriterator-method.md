---
title: ICLRSyncManager::DeleteRWLockOwnerIterator 메서드
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.DeleteRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ee4a09902be093bdbfe0b367f4add35bdda571c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434069"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="46971-102">ICLRSyncManager::DeleteRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="46971-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="46971-103">공용 언어 런타임 (CLR)를 호출 하 여 생성 된 반복기로 손상 요청 [iclrsyncmanager:: Createrwlockowneriterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="46971-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46971-104">구문</span><span class="sxs-lookup"><span data-stu-id="46971-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46971-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46971-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="46971-106">[in] 반복기에 대 한 호출을 사용 하 여 만든 `CreateRWLockOwnerIterator`합니다.</span><span class="sxs-lookup"><span data-stu-id="46971-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46971-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="46971-107">Return Value</span></span>  
  
|<span data-ttu-id="46971-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46971-108">HRESULT</span></span>|<span data-ttu-id="46971-109">설명</span><span class="sxs-lookup"><span data-stu-id="46971-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46971-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="46971-110">S_OK</span></span>|<span data-ttu-id="46971-111">`DeleteRWLockOwnerIterator` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="46971-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="46971-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="46971-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="46971-113">CLR은 프로세스에 로드 되지 않은 또는 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46971-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="46971-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="46971-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="46971-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="46971-115">The call timed out.</span></span>|  
|<span data-ttu-id="46971-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="46971-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="46971-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46971-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="46971-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="46971-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="46971-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="46971-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="46971-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="46971-120">E_FAIL</span></span>|<span data-ttu-id="46971-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="46971-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="46971-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46971-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="46971-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="46971-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46971-124">설명</span><span class="sxs-lookup"><span data-stu-id="46971-124">Remarks</span></span>  
 <span data-ttu-id="46971-125">호스트는이 메서드를 호출할 수 및 `CreateRWLockOwnerIterator` 스레딩 구현 동기화 유지 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="46971-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46971-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46971-126">Requirements</span></span>  
 <span data-ttu-id="46971-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="46971-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46971-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="46971-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46971-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="46971-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46971-130">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46971-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46971-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46971-131">See Also</span></span>  
 [<span data-ttu-id="46971-132">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46971-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="46971-133">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46971-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
