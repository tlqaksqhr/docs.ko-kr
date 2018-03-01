---
title: "EApiCategories 열거형"
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
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 630a3048072ed7b19b3250e75aca3b31e4dd7df7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="94026-102">EApiCategories 열거형</span><span class="sxs-lookup"><span data-stu-id="94026-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="94026-103">부분적으로 신뢰할 수 있는 코드에서 실행 되는 호스트를 차단할 수 있는 기능의 범주를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94026-104">구문</span><span class="sxs-lookup"><span data-stu-id="94026-104">Syntax</span></span>  
  
```  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a><span data-ttu-id="94026-105">멤버</span><span class="sxs-lookup"><span data-stu-id="94026-105">Members</span></span>  
  
|<span data-ttu-id="94026-106">멤버</span><span class="sxs-lookup"><span data-stu-id="94026-106">Member</span></span>|<span data-ttu-id="94026-107">설명</span><span class="sxs-lookup"><span data-stu-id="94026-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="94026-108">모든 다른 검사는 클래스와 멤버 관리 지정 `EApiCategories` 필드 부분적으로 신뢰할 수 있는 코드에서 실행 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="94026-109">관리 되는 클래스 및 멤버 만들기, 조작, 외부 프로세스의 소멸을 수행할 수 있는 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="94026-110">관리 되는 클래스 및 멤버 만들기, 조작, 외부 스레드의 소멸을 수행할 수 있는 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="94026-111">부분적으로 신뢰할 수 있는 코드에서 실행 중단 시 메모리 누수가 발생할 수 있는 관리 되는 형식 및 멤버 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="94026-112">관리 코드 범주가 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="94026-113">공용 언어 런타임 (CLR) 보안 인프라에서 부분적으로 신뢰할 수 있는 코드에서 사용 하 고 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="94026-114">관리 되는 클래스 및 멤버 호스팅된 프로세스 영향을 줄 수 있는 기능이 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="94026-115">관리 되는 클래스 및 멤버 호스팅된 프로세스의 스레드가 영향을 줄 수 있는 기능이 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="94026-116">공유 상태를 노출 하는 관리 되는 클래스와 멤버 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="94026-117">공용 언어 런타임 클래스 및 멤버를 잠금을 유지 하는 사용자 코드를 사용 하면 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="94026-118">부분적으로 신뢰할 수 있는 코드에서 실행을 허용 하거나 사용자 상호 작용을 요청 하는 관리 되는 클래스와 멤버 차단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94026-119">설명</span><span class="sxs-lookup"><span data-stu-id="94026-119">Remarks</span></span>  
 <span data-ttu-id="94026-120">[iclrhostprotectionmanager:: Setprotectedcategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) 형식의 매개 변수를 사용 하는 메서드 `EApiCategories`합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="94026-121">`EApiCategories` 열거형 및 `SetProtectedCategories` 메서드 직접 관련 된 관리 되는 <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="94026-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="94026-122">관리 되는 클래스와 함께 사용 되는 <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> 해당 값에 직접 해당 열거형의 `EApiCategories` 관리 되는 형식 및 해당 범주에서 설명 하는 기능을 노출 하는 멤버를 표시 하려면 값 `EApiCategories`합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94026-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94026-123">Requirements</span></span>  
 <span data-ttu-id="94026-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94026-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94026-125">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="94026-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94026-126">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94026-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94026-127">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94026-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94026-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94026-128">See Also</span></span>  
 [<span data-ttu-id="94026-129">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94026-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="94026-130">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="94026-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
