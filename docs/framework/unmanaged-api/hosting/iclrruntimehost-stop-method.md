---
title: ICLRRuntimeHost::Stop 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8d479e271c2cc4ebf9ea6ff349fd28bff37c3857
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436100"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="ea2c6-102">ICLRRuntimeHost::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="ea2c6-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="ea2c6-103">공용 언어 런타임 (CLR) 하 여 코드의 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ea2c6-104">이 메서드는 없는 호스트에 리소스를 해제, 응용 프로그램 도메인, 언로드 또는 스레드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="ea2c6-105">이러한 리소스를 해제 하는 프로세스를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea2c6-106">구문</span><span class="sxs-lookup"><span data-stu-id="ea2c6-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ea2c6-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ea2c6-107">Return Value</span></span>  
  
|<span data-ttu-id="ea2c6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea2c6-108">HRESULT</span></span>|<span data-ttu-id="ea2c6-109">설명</span><span class="sxs-lookup"><span data-stu-id="ea2c6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea2c6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea2c6-110">S_OK</span></span>|<span data-ttu-id="ea2c6-111">`Stop` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="ea2c6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ea2c6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ea2c6-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ea2c6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ea2c6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ea2c6-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-115">The call timed out.</span></span>|  
|<span data-ttu-id="ea2c6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ea2c6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ea2c6-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ea2c6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ea2c6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ea2c6-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ea2c6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ea2c6-120">E_FAIL</span></span>|<span data-ttu-id="ea2c6-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ea2c6-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ea2c6-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea2c6-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea2c6-124">Requirements</span></span>  
 <span data-ttu-id="ea2c6-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2c6-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea2c6-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ea2c6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea2c6-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ea2c6-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea2c6-128">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea2c6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea2c6-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea2c6-129">See Also</span></span>  
 [<span data-ttu-id="ea2c6-130">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea2c6-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
