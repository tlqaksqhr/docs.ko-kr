---
title: "ValidatorFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ValidatorFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ValidatorFlags
helpviewer_keywords: ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f283beb79ec47454185800bd772904c3c696c7c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="4efc2-102">ValidatorFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="4efc2-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="4efc2-103">에 대 한 호출에서 수행 해야 하는 유효성 검사의 유형을 나타내는 값이 포함 되어는 [iclrvalidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="4efc2-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4efc2-104">구문</span><span class="sxs-lookup"><span data-stu-id="4efc2-104">Syntax</span></span>  
  
```  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="4efc2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4efc2-105">Members</span></span>  
  
|<span data-ttu-id="4efc2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4efc2-106">Member</span></span>|<span data-ttu-id="4efc2-107">설명</span><span class="sxs-lookup"><span data-stu-id="4efc2-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="4efc2-108">만 Microsoft intermediate language (MSIL)에서 실행 파일을 검사 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4efc2-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="4efc2-109">실행 파일의 형식에만 검사 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4efc2-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="4efc2-110">모든 유형의 유효성 검사 수행 및 보고를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4efc2-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="4efc2-111">실행 파일의 형식을 확인 하지 않음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4efc2-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="4efc2-112">유효성 검사 오류 메시지 유효성 검사 오류가 발생 하는 소스 코드의 줄에 포함 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4efc2-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="4efc2-113">필드 값이.NET Framework 버전 2.0에서에서 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4efc2-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4efc2-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4efc2-114">Requirements</span></span>  
 <span data-ttu-id="4efc2-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4efc2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4efc2-116">**헤더:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="4efc2-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="4efc2-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4efc2-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4efc2-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4efc2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4efc2-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4efc2-119">See Also</span></span>  
 [<span data-ttu-id="4efc2-120">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4efc2-120">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="4efc2-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="4efc2-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
