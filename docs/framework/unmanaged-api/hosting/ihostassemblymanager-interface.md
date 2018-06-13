---
title: IHostAssemblyManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8c8d17723481fc5b41fe5f3006fe8db2c53d1ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438482"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="4993b-102">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4993b-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="4993b-103">공용 언어 런타임 (CLR)에서 또는 호스트에 의해 로드 하는 어셈블리 집합을 지정 하는 데 사용 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4993b-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4993b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4993b-104">Methods</span></span>  
  
|<span data-ttu-id="4993b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4993b-105">Method</span></span>|<span data-ttu-id="4993b-106">설명</span><span class="sxs-lookup"><span data-stu-id="4993b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4993b-107">GetAssemblyStore 메서드</span><span class="sxs-lookup"><span data-stu-id="4993b-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="4993b-108">한 인터페이스 포인터를 가져옵니다는 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) 호스트에 의해 로드 된 어셈블리 목록을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="4993b-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="4993b-109">GetNonHostStoreAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="4993b-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="4993b-110">한 인터페이스 포인터를 가져옵니다는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 호스트에서는 로드 하기 위해 CLR 어셈블리 목록이 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="4993b-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4993b-111">설명</span><span class="sxs-lookup"><span data-stu-id="4993b-111">Remarks</span></span>  
 <span data-ttu-id="4993b-112">호스트 구현할 필요가 없습니다 `IHostAssemblyManager` 또는 `IHostAssemblyStore`합니다.</span><span class="sxs-lookup"><span data-stu-id="4993b-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="4993b-113">호스트에서 구현 하는 경우 `IHostAssemblyManager`를 구현 해야 `IHostAssemblyStore`합니다.</span><span class="sxs-lookup"><span data-stu-id="4993b-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="4993b-114">런타임에서 대 한 쿼리는 `IHostAssemblyManager` 호출 하 여 [ihostcontrol:: Gethostmanager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) 사용 하 여 초기화 시 한 `IID` IID_IHostAssemblyManager의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4993b-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4993b-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4993b-115">Requirements</span></span>  
 <span data-ttu-id="4993b-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4993b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4993b-117">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4993b-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4993b-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4993b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4993b-119">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4993b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4993b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4993b-120">See Also</span></span>  
 [<span data-ttu-id="4993b-121">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4993b-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="4993b-122">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4993b-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="4993b-123">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4993b-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="4993b-124">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4993b-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
