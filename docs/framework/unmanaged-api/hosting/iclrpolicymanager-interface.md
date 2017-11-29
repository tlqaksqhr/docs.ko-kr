---
title: "ICLRPolicyManager 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager
helpviewer_keywords: ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f3dd904184b730a5b0f5b2dfcac4197e708544d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="81c64-102">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81c64-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="81c64-103">정책 오류 및 시간 초과가 발생할 경우 수행할 작업을 지정 하려면 호스트를 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c64-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81c64-104">메서드</span><span class="sxs-lookup"><span data-stu-id="81c64-104">Methods</span></span>  
  
|<span data-ttu-id="81c64-105">메서드</span><span class="sxs-lookup"><span data-stu-id="81c64-105">Method</span></span>|<span data-ttu-id="81c64-106">설명</span><span class="sxs-lookup"><span data-stu-id="81c64-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81c64-107">SetActionOnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="81c64-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="81c64-108">공용 언어 런타임 (CLR)의 오류가 발생할 경우 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c64-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="81c64-109">SetActionOnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="81c64-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="81c64-110">정책 CLR에서 수행할 작업을 지정된 된 작업 시간 초과 될 때를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c64-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="81c64-111">SetDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="81c64-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="81c64-112">지정 된 작업이 수행 될 때 CLR 수행할 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c64-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="81c64-113">SetTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="81c64-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="81c64-114">지정된 된 작업에 대 한 제한 시간 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81c64-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="81c64-115">SetTimeoutAndAction 메서드</span><span class="sxs-lookup"><span data-stu-id="81c64-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="81c64-116">지정된 된 작업에 대 한 제한 시간 값을 설정 하 고 CLR에서 작업이 수행 될 때 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c64-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="81c64-117">SetUnhandledExceptionPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="81c64-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="81c64-118">처리 되지 않은 예외가 발생 하면 CLR의 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c64-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81c64-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81c64-119">Requirements</span></span>  
 <span data-ttu-id="81c64-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="81c64-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81c64-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="81c64-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81c64-122">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="81c64-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81c64-123">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81c64-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c64-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81c64-124">See Also</span></span>  
 [<span data-ttu-id="81c64-125">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="81c64-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="81c64-126">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="81c64-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="81c64-127">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="81c64-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="81c64-128">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81c64-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
