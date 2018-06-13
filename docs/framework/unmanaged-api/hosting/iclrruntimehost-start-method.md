---
title: ICLRRuntimeHost::Start 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df2747b7cce112e61c6fb99cdb91dc0d56047b9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432562"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="7c391-102">ICLRRuntimeHost::Start 메서드</span><span class="sxs-lookup"><span data-stu-id="7c391-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="7c391-103">공용 언어 런타임 (CLR) 프로세스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c391-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c391-104">Syntax</span></span>  
  
```  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7c391-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="7c391-105">Return Value</span></span>  
  
|<span data-ttu-id="7c391-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c391-106">HRESULT</span></span>|<span data-ttu-id="7c391-107">설명</span><span class="sxs-lookup"><span data-stu-id="7c391-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c391-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c391-108">S_OK</span></span>|<span data-ttu-id="7c391-109">`Start` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="7c391-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c391-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c391-111">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c391-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c391-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c391-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-113">The call timed out.</span></span>|  
|<span data-ttu-id="7c391-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c391-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c391-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c391-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c391-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c391-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c391-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c391-118">E_FAIL</span></span>|<span data-ttu-id="7c391-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c391-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c391-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c391-122">설명</span><span class="sxs-lookup"><span data-stu-id="7c391-122">Remarks</span></span>  
 <span data-ttu-id="7c391-123">대부분의 시나리오에서 필요 없는 호출할 `Start`첫 번째 요청을 관리 코드를 실행할 때 런타임에서 자체 자동으로 초기화 되므로, 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="7c391-124">그러나 사용할 수 있습니다 `Start` 정확 하 게 런타임이 초기화 시기를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c391-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c391-125">Requirements</span></span>  
 <span data-ttu-id="7c391-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c391-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c391-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c391-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7c391-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c391-129">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c391-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c391-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c391-130">See Also</span></span>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="7c391-131">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c391-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
