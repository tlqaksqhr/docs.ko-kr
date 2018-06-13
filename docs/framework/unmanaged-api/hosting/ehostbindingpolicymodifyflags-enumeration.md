---
title: EHostBindingPolicyModifyFlags 열거형
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fa8cc15f77ff59e3d3c570341d9bba70cf1e953
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431716"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="3d7f0-102">EHostBindingPolicyModifyFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="3d7f0-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="3d7f0-103">호스트를 정책 수정 내용을 소스 어셈블리의 대상 어셈블리에 적용할 때 공용 언어 런타임 (CLR) 수행할 리디렉션 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d7f0-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d7f0-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d7f0-104">Syntax</span></span>  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3d7f0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3d7f0-105">Members</span></span>  
  
|<span data-ttu-id="3d7f0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="3d7f0-106">Member</span></span>|<span data-ttu-id="3d7f0-107">설명</span><span class="sxs-lookup"><span data-stu-id="3d7f0-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="3d7f0-108">CLR에서 대상 어셈블리의 소스 어셈블리의 정책 값을 연결할 됩니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d7f0-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="3d7f0-109">CLR 기본 작업을 수행할 것을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d7f0-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="3d7f0-110">CLR 설정 한다는 대상 어셈블리의 정책 값을 최대값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d7f0-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="3d7f0-111">CLR에서 대상 어셈블리의 정책 값 소스 어셈블리의 사용을 바꿉니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d7f0-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d7f0-112">설명</span><span class="sxs-lookup"><span data-stu-id="3d7f0-112">Remarks</span></span>  
 <span data-ttu-id="3d7f0-113">[iclrhostbindingpolicymanager:: Modifyapplicationpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) 형식의 매개 변수를 사용 하는 메서드 `EHostBindingPolicyModifyFlags`합니다.</span><span class="sxs-lookup"><span data-stu-id="3d7f0-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d7f0-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d7f0-114">Requirements</span></span>  
 <span data-ttu-id="3d7f0-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d7f0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d7f0-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3d7f0-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d7f0-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d7f0-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d7f0-118">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d7f0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d7f0-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d7f0-119">See Also</span></span>  
 [<span data-ttu-id="3d7f0-120">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d7f0-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="3d7f0-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="3d7f0-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
