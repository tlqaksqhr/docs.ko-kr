---
title: "EBindPolicyLevels 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EBindPolicyLevels
api_location: mscoree.dll
api_type: COM
f1_keywords: EBindPolicyLevels
helpviewer_keywords: EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e55fdb58129cd530bb63f26fab0be471b133d62f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="200ba-102">EBindPolicyLevels 열거형</span><span class="sxs-lookup"><span data-stu-id="200ba-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="200ba-103">어셈블리 정책 적용 또는 수정 하는 수준을 지정 하는 플래그를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="200ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="200ba-104">Syntax</span></span>  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="200ba-105">멤버</span><span class="sxs-lookup"><span data-stu-id="200ba-105">Members</span></span>  
  
|<span data-ttu-id="200ba-106">멤버</span><span class="sxs-lookup"><span data-stu-id="200ba-106">Member</span></span>|<span data-ttu-id="200ba-107">설명</span><span class="sxs-lookup"><span data-stu-id="200ba-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="200ba-108">관리자 수준에서 정책이 적용 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="200ba-109">응용 프로그램 수준에서 정책이 적용 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="200ba-110">호스트 수준에서 정책이 적용 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="200ba-111">없는 정책 수준 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="200ba-112">게시자 수준의 정책이 적용 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="200ba-113">변수 수준에서 정책을 적용할 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="200ba-114">정책이.NET Framework 어셈블리의 구현 간의 이식성을 지원 해야 한다고 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="200ba-115">참조는 [ \<되어 supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) 구성 파일 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="200ba-116">정책에 통합 공용 언어 런타임 (CLR) 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="200ba-117">설명</span><span class="sxs-lookup"><span data-stu-id="200ba-117">Remarks</span></span>  
 <span data-ttu-id="200ba-118">이 열거형의 메서드에 전달 되는 [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) 응용 프로그램 정책에서 변경 내용을 지정 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="200ba-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="200ba-119">Requirements</span></span>  
 <span data-ttu-id="200ba-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="200ba-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="200ba-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="200ba-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="200ba-122">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="200ba-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="200ba-123">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="200ba-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200ba-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="200ba-124">See Also</span></span>  
 [<span data-ttu-id="200ba-125">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="200ba-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="200ba-126">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="200ba-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
