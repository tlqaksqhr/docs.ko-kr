---
title: "ICLRTaskManager 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager
helpviewer_keywords: ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 342d7b82802fcfbe9e179d85d6d692205f19e382
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="e28a7-102">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e28a7-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="e28a7-103">공용 언어 런타임 (CLR) 명시적으로 요청 하는 호스트를 사용할 수 있는 메서드는 새 작업 만들기, 현재 실행 중인 작업을 가져오고 설정 언어와 문화권을 작업에 대 한 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28a7-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e28a7-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e28a7-104">Methods</span></span>  
  
|<span data-ttu-id="e28a7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e28a7-105">Method</span></span>|<span data-ttu-id="e28a7-106">설명</span><span class="sxs-lookup"><span data-stu-id="e28a7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e28a7-107">CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="e28a7-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="e28a7-108">CLR을 새로 만들 명시적 요청 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e28a7-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="e28a7-109">GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="e28a7-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="e28a7-110">가져옵니다는 `ICLRTask` 현재 실행 중인 작업을 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="e28a7-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="e28a7-111">GetCurrentTaskType 메서드</span><span class="sxs-lookup"><span data-stu-id="e28a7-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="e28a7-112">현재 실행 중인 작업의 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e28a7-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="e28a7-113">SetLocale 메서드</span><span class="sxs-lookup"><span data-stu-id="e28a7-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="e28a7-114">호스트가 현재 실행 중인 작업에 대 한 로캘 식별자를 수정 하는 CLR에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e28a7-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="e28a7-115">SetUILocale 메서드</span><span class="sxs-lookup"><span data-stu-id="e28a7-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="e28a7-116">호스트가 현재 실행 중인 작업에서 사용자 인터페이스 로캘 식별자를 수정 하는 공용 언어 런타임 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e28a7-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e28a7-117">설명</span><span class="sxs-lookup"><span data-stu-id="e28a7-117">Remarks</span></span>  
 <span data-ttu-id="e28a7-118">호스트 된 환경에서 실행 되는 각 작업이 호스트 측에 대 한 표현을 두 (인스턴스의 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) CLR 쪽에 (인스턴스의 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="e28a7-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="e28a7-119">호스트 또는 CLR, 작업의 만들기를 시작할 수 있지만 호스트 측 표현을 호스트와 작업에 대 한 CLR 간의 성공적으로 통신을 위해 해당 CLR 측 표현과와 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28a7-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="e28a7-120">두 개체가 만들고 인스턴스화하기 전에 운영 체제 스레드에 대해 관리 코드를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28a7-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e28a7-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e28a7-121">Requirements</span></span>  
 <span data-ttu-id="e28a7-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e28a7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e28a7-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e28a7-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e28a7-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e28a7-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e28a7-125">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e28a7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e28a7-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e28a7-126">See Also</span></span>  
 [<span data-ttu-id="e28a7-127">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e28a7-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="e28a7-128">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e28a7-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="e28a7-129">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e28a7-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="e28a7-130">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e28a7-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
