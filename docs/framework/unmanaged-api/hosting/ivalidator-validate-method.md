---
title: "IValidator::Validate 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IValidator.Validate
api_location: mscoree.dll
api_type: COM
f1_keywords: Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a74249cb806f332b3ae575223f237438da616972
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="ab5c6-102">IValidator::Validate 메서드</span><span class="sxs-lookup"><span data-stu-id="ab5c6-102">IValidator::Validate Method</span></span>
<span data-ttu-id="ab5c6-103">지정 된 pe (이식 가능) 또는 Microsoft MSIL (intermediate language) 파일의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5c6-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab5c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab5c6-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab5c6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab5c6-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="ab5c6-106">[in] 에 대 한 포인터는 `IVEHandler` 유효성 검사 오류를 처리 하는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5c6-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="ab5c6-107">[in] 파일이 로드 된 응용 프로그램 도메인에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5c6-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="ab5c6-108">[in] 비트 조합 [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) 수행 해야 하는 유효성 검사를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5c6-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="ab5c6-109">[in] 유효성 검사를 종료 하기 전까지 허용 오류의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5c6-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="ab5c6-110">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab5c6-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="ab5c6-111">[in] 유효성을 검사할 파일의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5c6-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="ab5c6-112">[in] 파일이 저장 된 메모리 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5c6-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="ab5c6-113">[in] 유효성을 검사할 파일의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ab5c6-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab5c6-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab5c6-114">Requirements</span></span>  
 <span data-ttu-id="ab5c6-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab5c6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab5c6-116">**헤더:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="ab5c6-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="ab5c6-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ab5c6-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab5c6-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab5c6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab5c6-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab5c6-119">See Also</span></span>  
 
