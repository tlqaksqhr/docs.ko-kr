---
title: "EHostBindingPolicyModifyFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EHostBindingPolicyModifyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: EHostBindingPolicyModifyFlags
helpviewer_keywords: EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ff7ec7487be649e353b48e537cf1d8d45f6962
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="85c5b-102">EHostBindingPolicyModifyFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="85c5b-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="85c5b-103">호스트를 정책 수정 내용을 소스 어셈블리의 대상 어셈블리에 적용할 때 공용 언어 런타임 (CLR) 수행할 리디렉션 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85c5b-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c5b-104">구문</span><span class="sxs-lookup"><span data-stu-id="85c5b-104">Syntax</span></span>  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="85c5b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="85c5b-105">Members</span></span>  
  
|<span data-ttu-id="85c5b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="85c5b-106">Member</span></span>|<span data-ttu-id="85c5b-107">설명</span><span class="sxs-lookup"><span data-stu-id="85c5b-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="85c5b-108">CLR에서 대상 어셈블리의 소스 어셈블리의 정책 값을 연결할 됩니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c5b-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="85c5b-109">CLR 기본 작업을 수행할 것을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c5b-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="85c5b-110">CLR 설정 한다는 대상 어셈블리의 정책 값을 최대값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c5b-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="85c5b-111">CLR에서 대상 어셈블리의 정책 값 소스 어셈블리의 사용을 바꿉니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c5b-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85c5b-112">설명</span><span class="sxs-lookup"><span data-stu-id="85c5b-112">Remarks</span></span>  
 <span data-ttu-id="85c5b-113">[iclrhostbindingpolicymanager:: Modifyapplicationpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) 형식의 매개 변수를 사용 하는 메서드 `EHostBindingPolicyModifyFlags`합니다.</span><span class="sxs-lookup"><span data-stu-id="85c5b-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85c5b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85c5b-114">Requirements</span></span>  
 <span data-ttu-id="85c5b-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="85c5b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85c5b-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85c5b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85c5b-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85c5b-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85c5b-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85c5b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c5b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85c5b-119">See Also</span></span>  
 [<span data-ttu-id="85c5b-120">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85c5b-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="85c5b-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="85c5b-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
