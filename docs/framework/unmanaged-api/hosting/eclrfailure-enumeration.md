---
title: "EClrFailure 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrFailure
helpviewer_keywords: EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e25a5378349dd476321765bb085db958e29670e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="3135a-102">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="3135a-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="3135a-103">호스트 정책 작업 설정할 수 있는 오류를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3135a-104">구문</span><span class="sxs-lookup"><span data-stu-id="3135a-104">Syntax</span></span>  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a><span data-ttu-id="3135a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3135a-105">Members</span></span>  
  
|<span data-ttu-id="3135a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="3135a-106">Member</span></span>|<span data-ttu-id="3135a-107">설명</span><span class="sxs-lookup"><span data-stu-id="3135a-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="3135a-108">코드는 중요 하지 않은 영역에서 리소스 (예: 스레드, 메모리의 블록 또는 잠금)를 할당 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="3135a-109">코드의 중요 한 영역에서 리소스 (예: 스레드, 메모리의 블록 또는 잠금)를 할당 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="3135a-110">공용 언어 런타임 (CLR)을 프로세스의 관리 되는 코드를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="3135a-111">예측이 호스팅 모든 함수에 대 한 호출 HOST_E_CLRNOTAVAILABLE HRESULT 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="3135a-112">반환 하면 잠금을 해제 하는 스레드 못한는 <xref:System.AppDomain> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="3135a-113">호스트는이 오류는 스레드가 중단 되도록를 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="3135a-114">스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="3135a-115">보호 된 메모리를 읽거나 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="3135a-116">지원 되지 않습니다는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-116">Not supported in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="3135a-117">코드 계약 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-117">A code contract failure occurred.</span></span> <span data-ttu-id="3135a-118">참조 [계약 코드](../../../../docs/framework/debug-trace-profile/code-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3135a-119">설명</span><span class="sxs-lookup"><span data-stu-id="3135a-119">Remarks</span></span>  
 <span data-ttu-id="3135a-120">참조는 [iclrpolicymanager:: Setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) 목록은 메서드 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값 오류 상태에 대 한 정책 동작을 지정 하는 호스트가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="3135a-121">코드의 중요 하 고 중요 하지 않은 영역에 대 한 자세한 내용은 참조 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3135a-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3135a-122">Requirements</span></span>  
 <span data-ttu-id="3135a-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3135a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3135a-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3135a-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3135a-125">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3135a-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3135a-126">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3135a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3135a-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3135a-127">See Also</span></span>  
 [<span data-ttu-id="3135a-128">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3135a-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="3135a-129">SetActionOnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="3135a-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [<span data-ttu-id="3135a-130">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3135a-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="3135a-131">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="3135a-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
