---
title: "IHostAssemblyStore::ProvideModule 메서드"
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
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8b29f19933ae985d15627d1eba2622f350a52e72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="7b62e-102">IHostAssemblyStore::ProvideModule 메서드</span><span class="sxs-lookup"><span data-stu-id="7b62e-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="7b62e-103">어셈블리 또는 연결 된 (그러나 포함이 아님) 내의 모듈 리소스 파일을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b62e-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b62e-104">Syntax</span></span>  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b62e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b62e-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="7b62e-106">[in] 에 대 한 포인터는 [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) 요청된 된 모듈을 나타내는 인스턴스 <xref:System.AppDomain>, 어셈블리 및 모듈 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="7b62e-107">[out] 에 대 한 고유 식별자에 대 한 포인터는 `IStream` 로드 된 모듈을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="7b62e-108">[out] 주소에 대 한 포인터는 `IStream` 이식 가능한 실행 (PE) 이미지를 로드할 수를 포함 된 개체 또는 모듈을 찾을 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="7b62e-109">[out] 주소에 대 한 포인터는 `IStream` 또는 개체 요청된 된 모듈에 대 한 프로그램 (PDB) 디버그 정보를 포함 하는.pdb 파일을 찾을 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b62e-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="7b62e-110">Return Value</span></span>  
  
|<span data-ttu-id="7b62e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7b62e-111">HRESULT</span></span>|<span data-ttu-id="7b62e-112">설명</span><span class="sxs-lookup"><span data-stu-id="7b62e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b62e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b62e-113">S_OK</span></span>|<span data-ttu-id="7b62e-114">`ProvideModule`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="7b62e-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7b62e-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7b62e-116">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7b62e-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7b62e-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7b62e-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-118">The call timed out.</span></span>|  
|<span data-ttu-id="7b62e-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7b62e-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7b62e-120">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7b62e-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7b62e-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7b62e-122">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7b62e-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7b62e-123">E_FAIL</span></span>|<span data-ttu-id="7b62e-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7b62e-125">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7b62e-126">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7b62e-127">COR_E_FILENOTFOUND (0X80070002)</span><span class="sxs-lookup"><span data-stu-id="7b62e-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="7b62e-128">요청한 어셈블리 또는 링크 된 리소스를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="7b62e-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="7b62e-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="7b62e-130">`pdwModuleId`호스트를 반환 하는 식별자를 포함할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="7b62e-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b62e-131">설명</span><span class="sxs-lookup"><span data-stu-id="7b62e-131">Remarks</span></span>  
 <span data-ttu-id="7b62e-132">Id 값에 대해 반환 `pdwModuleId` 호스트에 의해 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="7b62e-133">식별자는 프로세스의 수명 동안 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="7b62e-134">CLR에서이 값을 연결 된 스트림 고유 식별자로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="7b62e-135">각 값에 대 한 값에 대해 확인 `pAssemblyId` 에 대 한 호출에서 반환 된 [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 및에 대 한 값과 대조 `pdwModuleId` 에 대 한 다른 호출에서 반환 된 `ProvideModule`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="7b62e-136">호스트가 다른 같은 식별자 값을 반환 하는 경우 `IStream`, CLR 해당 스트림의 내용을 이미 매핑 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="7b62e-137">이 경우 CLR 새 매핑하는 대신 이미지의 기존 복사본을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="7b62e-138">따라서 식별자도 겹치지 않아야에서 반환 된 어셈블리 식별자와 `ProvideAssembly`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b62e-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b62e-139">Requirements</span></span>  
 <span data-ttu-id="7b62e-140">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b62e-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b62e-141">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7b62e-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7b62e-142">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7b62e-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b62e-143">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b62e-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b62e-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b62e-144">See Also</span></span>  
 [<span data-ttu-id="7b62e-145">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b62e-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="7b62e-146">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b62e-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="7b62e-147">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b62e-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
