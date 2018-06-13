---
title: ICLRAssemblyIdentityManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3a58a9ec4ed9514e748ed6c8c21a404feed9560
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435669"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="33095-102">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33095-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="33095-103">호스트와 어셈블리에 대 한 공용 언어 런타임 (CLR) 간의 통신을 지 원하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="33095-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33095-104">메서드</span><span class="sxs-lookup"><span data-stu-id="33095-104">Methods</span></span>  
  
|<span data-ttu-id="33095-105">메서드</span><span class="sxs-lookup"><span data-stu-id="33095-105">Method</span></span>|<span data-ttu-id="33095-106">설명</span><span class="sxs-lookup"><span data-stu-id="33095-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33095-107">GetBindingIdentityFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="33095-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="33095-108">지정 된 파일 경로에 있는 어셈블리에 대 한 데이터 바인딩 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="33095-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="33095-109">GetBindingIdentityFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="33095-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="33095-110">지정한 스트림에 어셈블리에 대 한 정식 어셈블리 id 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="33095-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="33095-111">GetCLRAssemblyReferenceList 메서드</span><span class="sxs-lookup"><span data-stu-id="33095-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="33095-112">가져옵니다는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 부분 어셈블리 id의 지정된 된 목록에서 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="33095-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="33095-113">GetProbingAssembliesFromReference 메서드</span><span class="sxs-lookup"><span data-stu-id="33095-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="33095-114">가져옵니다는 [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) 지정된 된 id 사용 하 여 어셈블리에서 참조 한 어셈블리 id에 대 한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="33095-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="33095-115">GetReferencedAssembliesFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="33095-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="33095-116">가져옵니다는 [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) 지정 된 파일 경로에 있는 어셈블리에서 참조 어셈블리의 목록을 포함 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="33095-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="33095-117">GetReferencedAssembliesFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="33095-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="33095-118">에 대 한 포인터를 가져옵니다는 `ICLRReferenceAssemblyEnum` 에 지정된 된 스트림에 있는 어셈블리에서 참조 하는 어셈블리에 대 한 어셈블리 id 데이터를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="33095-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="33095-119">IsStronglyNamed 메서드</span><span class="sxs-lookup"><span data-stu-id="33095-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="33095-120">지정된 된 어셈블리 강력한 이름을 지정 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="33095-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33095-121">설명</span><span class="sxs-lookup"><span data-stu-id="33095-121">Remarks</span></span>  
 <span data-ttu-id="33095-122">사용 하 여 `ICLRAssemblyIdentityManager` 인스턴스를 가져옵니다 `ICLRAssemblyReferenceList` 및 어셈블리 id를 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33095-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33095-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33095-123">Requirements</span></span>  
 <span data-ttu-id="33095-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="33095-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33095-125">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33095-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33095-126">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="33095-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33095-127">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33095-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33095-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33095-128">See Also</span></span>  
 [<span data-ttu-id="33095-129">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33095-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="33095-130">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33095-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [<span data-ttu-id="33095-131">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33095-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
