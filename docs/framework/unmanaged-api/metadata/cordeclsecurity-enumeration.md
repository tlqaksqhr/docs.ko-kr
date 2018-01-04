---
title: "CorDeclSecurity 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDeclSecurity
api_location: mscoree.dll
api_type: COM
f1_keywords: CorDeclSecurity
helpviewer_keywords: CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30fd7ca2cf7962c6cadb43d4d8e3031b59292463
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="91a04-102">CorDeclSecurity 열거형</span><span class="sxs-lookup"><span data-stu-id="91a04-102">CorDeclSecurity Enumeration</span></span>
<span data-ttu-id="91a04-103">선언적 보안을 사용하여 수행할 수 있는 보안 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a04-104">구문</span><span class="sxs-lookup"><span data-stu-id="91a04-104">Syntax</span></span>  
  
```  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="91a04-105">멤버</span><span class="sxs-lookup"><span data-stu-id="91a04-105">Members</span></span>  
  
|<span data-ttu-id="91a04-106">멤버</span><span class="sxs-lookup"><span data-stu-id="91a04-106">Member</span></span>|<span data-ttu-id="91a04-107">설명</span><span class="sxs-lookup"><span data-stu-id="91a04-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="91a04-108">예약됨.</span><span class="sxs-lookup"><span data-stu-id="91a04-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="91a04-109">예약됨.</span><span class="sxs-lookup"><span data-stu-id="91a04-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="91a04-110">예약됨.</span><span class="sxs-lookup"><span data-stu-id="91a04-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="91a04-111">호출 스택의 상위에 있는 모든 호출자에게 현재 사용 권한 개체가 지정한 사용 권한이 부여되었어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="91a04-112">스택의 상위 호출자가 리소스에 액세스할 수 있는 권한이 부여 되지 않았습니다 않더라도 호출 코드에서 현재 사용 권한 개체로 식별 되는 리소스를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="91a04-113">현재 사용 권한 개체가 지정한 리소스에 액세스 하는 기능에 액세스할 권한이 하는 경우에 호출자에 게 액세스가 거부 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="91a04-114">코드에 다른 리소스에 액세스할 수 있는 권한이 부여되더라도 이 권한 개체가 지정한 리소스에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="91a04-115">직접 실행 호출자는 지정된 된 기간 동안에 대해 지정한 사용 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="91a04-116">다른 클래스를 상속 하거나 메서드를 재정의 하는 파생된 클래스는 지정 된 권한이 부여 된 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="91a04-117">호출자에 게 코드를 실행 하는 데 필요한 최소 사용 권한을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="91a04-118">이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="91a04-119">호출자에 게는 선택 사항 (실행 하려면 필요 없음) 하는 추가 권한을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="91a04-120">이 요청은 특별히 요청되지 않은 다른 모든 사용 권한을 암시적으로 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="91a04-121">이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="91a04-122">잘못 사용 될 수 있는 사용 권한에 대 한 호출자의 요청을 부여 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="91a04-123">이 작업은 어셈블리 범위 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="91a04-124">예약됨.</span><span class="sxs-lookup"><span data-stu-id="91a04-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="91a04-125">예약됨.</span><span class="sxs-lookup"><span data-stu-id="91a04-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="91a04-126">예약됨.</span><span class="sxs-lookup"><span data-stu-id="91a04-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="91a04-127">직접 실행 호출자에게 지정된 사용 권한이 부여되었어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="91a04-128">예약됨.</span><span class="sxs-lookup"><span data-stu-id="91a04-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="91a04-129">예약됨.</span><span class="sxs-lookup"><span data-stu-id="91a04-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="91a04-130">예약됨.</span><span class="sxs-lookup"><span data-stu-id="91a04-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="91a04-131">예약됨.</span><span class="sxs-lookup"><span data-stu-id="91a04-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="91a04-132">예약됨.</span><span class="sxs-lookup"><span data-stu-id="91a04-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91a04-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="91a04-133">Requirements</span></span>  
 <span data-ttu-id="91a04-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="91a04-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a04-135">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="91a04-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="91a04-136">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a04-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a04-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91a04-137">See Also</span></span>  
 [<span data-ttu-id="91a04-138">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="91a04-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
