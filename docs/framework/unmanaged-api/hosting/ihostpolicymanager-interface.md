---
title: "IHostPolicyManager 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager
helpviewer_keywords: IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8f49474f1a75af91ac5296be866914e05732e755
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="61645-102">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61645-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="61645-103">공용 언어 런타임 (CLR)의 경우 수행 하는 동작의 호스트 중단, 제한 시간, 또는 실패를 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61645-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61645-104">메서드</span><span class="sxs-lookup"><span data-stu-id="61645-104">Methods</span></span>  
  
|<span data-ttu-id="61645-105">메서드</span><span class="sxs-lookup"><span data-stu-id="61645-105">Method</span></span>|<span data-ttu-id="61645-106">설명</span><span class="sxs-lookup"><span data-stu-id="61645-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61645-107">OnDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="61645-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="61645-108">CLR에 대 한 호출으로 지정 된 기본 작업을 수행 하려고 하는 호스트에 알립니다 [iclrpolicymanager:: Setdefaultaction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) 대 한 응답으로 스레드 중단 또는 <xref:System.AppDomain> 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="61645-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="61645-109">OnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="61645-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="61645-110">CLR에 대 한 호출으로 지정 된 작업을 수행 하려고 하는 호스트에 알립니다 [iclrpolicymanager:: Setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) 리소스 할당 또는 재사용에 따른 오류에 대 한 응답에서입니다.</span><span class="sxs-lookup"><span data-stu-id="61645-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="61645-111">OnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="61645-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="61645-112">CLR에 대 한 호출으로 지정 된 작업을 수행 하려고 하는 호스트에 알립니다 [iclrpolicymanager:: Setactionontimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) 시간 초과에 대 한 응답입니다.</span><span class="sxs-lookup"><span data-stu-id="61645-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61645-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61645-113">Requirements</span></span>  
 <span data-ttu-id="61645-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61645-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61645-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="61645-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61645-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="61645-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61645-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61645-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61645-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61645-118">See Also</span></span>  
 [<span data-ttu-id="61645-119">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="61645-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="61645-120">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="61645-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="61645-121">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="61645-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="61645-122">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61645-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="61645-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61645-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
