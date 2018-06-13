---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28e97289eda5949e6d124426eb58105e2e3ad33e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435044"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="e7e2d-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e2d-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="e7e2d-103">지정 된 파일 경로에 있는 어셈블리에 대 한 데이터 바인딩 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e2d-104">구문</span><span class="sxs-lookup"><span data-stu-id="e7e2d-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7e2d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e7e2d-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="e7e2d-106">[in] 평가할 파일에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e7e2d-107">[in] 값은 [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) 어셈블리의 id 유형을 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="e7e2d-108">다음 버전의 확장을 위해 제공.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-108">Provided for future extensibility.</span></span> <span data-ttu-id="e7e2d-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT은 공용 언어 런타임 (CLR) 버전 2.0에서 지원 되는 유일한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="e7e2d-110">[out] 불투명 한 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="e7e2d-111">[out에서] 크기에 대 한 포인터 `pwzBuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7e2d-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="e7e2d-112">Return Value</span></span>  
  
|<span data-ttu-id="e7e2d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7e2d-113">HRESULT</span></span>|<span data-ttu-id="e7e2d-114">설명</span><span class="sxs-lookup"><span data-stu-id="e7e2d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7e2d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7e2d-115">S_OK</span></span>|<span data-ttu-id="e7e2d-116">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="e7e2d-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e7e2d-117">E_INVALIDARG</span></span>|<span data-ttu-id="e7e2d-118">제공 된 `pwzFilePath` null입니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="e7e2d-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e7e2d-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e7e2d-120">크기 `pwzBuffer` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="e7e2d-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e7e2d-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e7e2d-122">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e7e2d-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e7e2d-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e7e2d-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-124">The call timed out.</span></span>|  
|<span data-ttu-id="e7e2d-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e7e2d-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e7e2d-126">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e7e2d-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e7e2d-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e7e2d-128">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e7e2d-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e7e2d-129">E_FAIL</span></span>|<span data-ttu-id="e7e2d-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e7e2d-131">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e7e2d-132">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7e2d-133">설명</span><span class="sxs-lookup"><span data-stu-id="e7e2d-133">Remarks</span></span>  
 <span data-ttu-id="e7e2d-134">`GetBindingIdentityFromFile` 두 번 호출 일반적으로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="e7e2d-135">첫 번째 호출에 대 한 null 값이 제공 `pwzBuffer`, 메서드가 반환에 적절 한 크기 및 `pcchBufferSize`합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="e7e2d-136">두 번째 호출을 적절 하 게 할당 된 버퍼를 제공 하 고 완료 되 면 실제 버퍼 데이터와 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7e2d-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7e2d-137">Requirements</span></span>  
 <span data-ttu-id="e7e2d-138">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e2d-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7e2d-139">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7e2d-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7e2d-140">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e7e2d-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7e2d-141">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7e2d-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e2d-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7e2d-142">See Also</span></span>  
 [<span data-ttu-id="e7e2d-143">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7e2d-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="e7e2d-144">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7e2d-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="e7e2d-145">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7e2d-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
