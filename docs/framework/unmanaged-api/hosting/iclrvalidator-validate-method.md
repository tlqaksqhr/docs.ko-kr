---
title: "ICLRValidator::Validate 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRValidator.Validate
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7328fe62276de6c33464ab8cfc6d6a5f39ee710e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="9b965-102">ICLRValidator::Validate 메서드</span><span class="sxs-lookup"><span data-stu-id="9b965-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="9b965-103">Pe (이식 가능) 또는 Microsoft MSIL (intermediate language)에 지정된 된 파일의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b965-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b965-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);      
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b965-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b965-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="9b965-106">[in] 에 대 한 포인터는 `IVEHandler` 유효성 검사 오류를 처리 하는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="9b965-107">[in] 현재 식별자 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="9b965-108">[in] 조합을 [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) 수행 해야 하는 유효성 검사의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="9b965-109">[in] 유효성 검사를 종료 하기 전까지 허용 오류의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="9b965-110">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="9b965-111">[in] 유효성을 검사할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="9b965-112">[in] 파일 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="9b965-113">[in] 유효성을 검사할 파일의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b965-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="9b965-114">Return Value</span></span>  
  
|<span data-ttu-id="9b965-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b965-115">HRESULT</span></span>|<span data-ttu-id="9b965-116">설명</span><span class="sxs-lookup"><span data-stu-id="9b965-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b965-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b965-117">S_OK</span></span>|<span data-ttu-id="9b965-118">`Validate`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="9b965-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b965-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b965-120">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b965-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b965-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b965-122">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-122">The call timed out.</span></span>|  
|<span data-ttu-id="9b965-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b965-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b965-124">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b965-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b965-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b965-126">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b965-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b965-127">E_FAIL</span></span>|<span data-ttu-id="9b965-128">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b965-129">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b965-130">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b965-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b965-131">Requirements</span></span>  
 <span data-ttu-id="9b965-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b965-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b965-133">**헤더:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="9b965-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="9b965-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9b965-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b965-135">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b965-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b965-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b965-136">See Also</span></span>  
 [<span data-ttu-id="9b965-137">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b965-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
