---
title: "EClrUnhandledException 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrUnhandledException
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrUnhandledException
helpviewer_keywords: EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 67787072779e0cb22a339c2d13c972ba36f3ed61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="2dff7-102">EClrUnhandledException 열거형</span><span class="sxs-lookup"><span data-stu-id="2dff7-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="2dff7-103">사용자 코드에서 처리 되지 않은 예외를 관리 하기 위한 사용 가능한 옵션에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dff7-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dff7-104">구문</span><span class="sxs-lookup"><span data-stu-id="2dff7-104">Syntax</span></span>  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="2dff7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="2dff7-105">Members</span></span>  
  
|<span data-ttu-id="2dff7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2dff7-106">Member</span></span>|<span data-ttu-id="2dff7-107">설명</span><span class="sxs-lookup"><span data-stu-id="2dff7-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="2dff7-108">기본 동작이 발생 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dff7-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="2dff7-109">프로세스 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dff7-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="2dff7-110">공용 언어 런타임 (CLR) 처리 되지 않은 예외를 무시 하 고 이후 작업을 결정 하 고 호스트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dff7-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dff7-111">설명</span><span class="sxs-lookup"><span data-stu-id="2dff7-111">Remarks</span></span>  
 <span data-ttu-id="2dff7-112">이전 버전 동일 CLR을 지정 하려면 사용 된 `eHostDeterminedPolicy` 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="2dff7-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dff7-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dff7-113">Requirements</span></span>  
 <span data-ttu-id="2dff7-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2dff7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dff7-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2dff7-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2dff7-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2dff7-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2dff7-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dff7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dff7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2dff7-118">See Also</span></span>  
 [<span data-ttu-id="2dff7-119">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="2dff7-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="2dff7-120">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="2dff7-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="2dff7-121">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dff7-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="2dff7-122">SetUnhandledExceptionPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="2dff7-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)  
 [<span data-ttu-id="2dff7-123">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dff7-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="2dff7-124">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="2dff7-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
