---
title: "ModuleBindInfo 구조체"
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
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 399ba2471b4dc7c5e372a56a9dcab8117068a693
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="73155-102">ModuleBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="73155-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="73155-103">참조 된 모듈 및 포함 된 어셈블리에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73155-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73155-104">구문</span><span class="sxs-lookup"><span data-stu-id="73155-104">Syntax</span></span>  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="73155-105">멤버</span><span class="sxs-lookup"><span data-stu-id="73155-105">Members</span></span>  
  
|<span data-ttu-id="73155-106">멤버</span><span class="sxs-lookup"><span data-stu-id="73155-106">Member</span></span>|<span data-ttu-id="73155-107">설명</span><span class="sxs-lookup"><span data-stu-id="73155-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="73155-108">에 대 한 고유 식별자는 `IStream` 에 대 한 호출에서 반환 하는 [ihostassemblystore:: Providemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) 메서드 로드 되도록은 참조 된 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="73155-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="73155-109">참조 된 모듈을 포함 하는 어셈블리에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="73155-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="73155-110">참조 된 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="73155-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73155-111">설명</span><span class="sxs-lookup"><span data-stu-id="73155-111">Remarks</span></span>  
 <span data-ttu-id="73155-112">`ModuleBindInfo`에 대 한 매개 변수로 전달 됩니다 `IHostAssemblyStore::ProvideModule`합니다.</span><span class="sxs-lookup"><span data-stu-id="73155-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="73155-113">고유 식별자를 제공 하는 호스트 `dwAppDomainId` 공용 언어 런타임 (CLR).</span><span class="sxs-lookup"><span data-stu-id="73155-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="73155-114">호출한 후에 [ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 런타임 식별자를 사용 하 여 결정 메서드가 반환 하는지 여부를의 내용을 `IStream` 매핑 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73155-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="73155-115">이 경우 런타임에서 스트림을 다시 매핑하는 것이 아니라 기존 복사본을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="73155-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="73155-116">또한 공용 언어 런타임은이 식별자에 대 한 호출에서 반환 되는 스트림에 대 한 조회 키로는 `IHostAssemblyStore::ProvideAssembly` 메서드.</span><span class="sxs-lookup"><span data-stu-id="73155-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="73155-117">따라서 식별자 어셈블리 요청에 대 한 모듈 요청 및 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73155-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73155-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73155-118">Requirements</span></span>  
 <span data-ttu-id="73155-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73155-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73155-120">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="73155-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="73155-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="73155-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73155-122">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73155-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73155-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73155-123">See Also</span></span>  
 [<span data-ttu-id="73155-124">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="73155-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="73155-125">AssemblyBindInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="73155-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 [<span data-ttu-id="73155-126">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73155-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="73155-127">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73155-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="73155-128">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73155-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
