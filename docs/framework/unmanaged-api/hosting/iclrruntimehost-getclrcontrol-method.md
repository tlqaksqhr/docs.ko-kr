---
title: ICLRRuntimeHost::GetCLRControl 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86858d5fe5bf9ac07a91e810599c27a479141f4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435057"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="1f842-102">ICLRRuntimeHost::GetCLRControl 메서드</span><span class="sxs-lookup"><span data-stu-id="1f842-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="1f842-103">형식의 인터페이스 포인터를 가져옵니다 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) 호스트 공용 언어 런타임 (CLR)의 측면을 사용자 지정 하는 데 사용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f842-104">구문</span><span class="sxs-lookup"><span data-stu-id="1f842-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f842-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f842-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="1f842-106">[out] 형식의 인터페이스 포인터 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) CLR의 추가 측면을 구성 하는 호스트 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f842-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1f842-107">Return Value</span></span>  
  
|<span data-ttu-id="1f842-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1f842-108">HRESULT</span></span>|<span data-ttu-id="1f842-109">설명</span><span class="sxs-lookup"><span data-stu-id="1f842-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1f842-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f842-110">S_OK</span></span>|<span data-ttu-id="1f842-111">`GetCLRControl` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="1f842-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1f842-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1f842-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1f842-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1f842-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1f842-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-115">The call timed out.</span></span>|  
|<span data-ttu-id="1f842-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1f842-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1f842-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1f842-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1f842-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1f842-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1f842-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1f842-120">E_FAIL</span></span>|<span data-ttu-id="1f842-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1f842-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1f842-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1f842-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="1f842-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="1f842-125">CLR가 이미 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f842-126">설명</span><span class="sxs-lookup"><span data-stu-id="1f842-126">Remarks</span></span>  
 <span data-ttu-id="1f842-127">`ICLRControl` 제공 된 [GetCLRManager 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드를 통해 호스트는 관리자 유형 중 하나에 대 한 인터페이스 포인터를 얻으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f842-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f842-128">Requirements</span></span>  
 <span data-ttu-id="1f842-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f842-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f842-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1f842-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f842-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1f842-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f842-132">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f842-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f842-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f842-133">See Also</span></span>  
 [<span data-ttu-id="1f842-134">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f842-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="1f842-135">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f842-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
