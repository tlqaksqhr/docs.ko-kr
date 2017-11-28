---
title: "ICLRAssemblyIdentityManager::IsStronglyNamed 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.IsStronglyNamed
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d0cb0bcaf5d19ec088511e64baffff9031911b32
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="88e95-102">ICLRAssemblyIdentityManager::IsStronglyNamed 메서드</span><span class="sxs-lookup"><span data-stu-id="88e95-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="88e95-103">지정된 된 어셈블리 강력한 이름을 지정 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88e95-104">구문</span><span class="sxs-lookup"><span data-stu-id="88e95-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88e95-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88e95-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="88e95-106">[in] 불투명 정식 어셈블리 id 평가할 어셈블리의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="88e95-107">[out] `true`어셈블리에서 참조 하는 경우는 `pwzAssemblyIdentity` 하 고, 그렇지 않으면 명명 된 매개 변수는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88e95-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="88e95-108">Return Value</span></span>  
  
|<span data-ttu-id="88e95-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88e95-109">HRESULT</span></span>|<span data-ttu-id="88e95-110">설명</span><span class="sxs-lookup"><span data-stu-id="88e95-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88e95-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="88e95-111">S_OK</span></span>|<span data-ttu-id="88e95-112">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="88e95-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="88e95-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="88e95-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="88e95-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="88e95-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="88e95-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-116">The call timed out.</span></span>|  
|<span data-ttu-id="88e95-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="88e95-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="88e95-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="88e95-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="88e95-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="88e95-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="88e95-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="88e95-121">E_FAIL</span></span>|<span data-ttu-id="88e95-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="88e95-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="88e95-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88e95-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88e95-125">Requirements</span></span>  
 <span data-ttu-id="88e95-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88e95-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88e95-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="88e95-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88e95-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="88e95-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88e95-129">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88e95-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88e95-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88e95-130">See Also</span></span>  
 [<span data-ttu-id="88e95-131">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88e95-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
