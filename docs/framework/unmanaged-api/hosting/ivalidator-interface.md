---
title: "IValidator 인터페이스"
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
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1afa255fa0b1baec35dbd8aa6e0beef62d240c31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ivalidator-interface"></a><span data-ttu-id="480e8-102">IValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="480e8-102">IValidator Interface</span></span>
<span data-ttu-id="480e8-103">이식 가능한 실행 (PE) 이미지 유효성 검사 및 유효성 검사 오류를 보고에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="480e8-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="480e8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="480e8-104">Methods</span></span>  
  
|<span data-ttu-id="480e8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="480e8-105">Method</span></span>|<span data-ttu-id="480e8-106">설명</span><span class="sxs-lookup"><span data-stu-id="480e8-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="480e8-107">Validate</span><span class="sxs-lookup"><span data-stu-id="480e8-107">Validate</span></span>|<span data-ttu-id="480e8-108">지정된 된 PE 또는 Microsoft MSIL (intermediate language) 파일의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="480e8-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="480e8-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="480e8-109">FormatEventInfo</span></span>|<span data-ttu-id="480e8-110">지정 된 유효성 검사 오류에 해당 하는 오류 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="480e8-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="480e8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="480e8-111">Requirements</span></span>  
 <span data-ttu-id="480e8-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="480e8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="480e8-113">**헤더:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="480e8-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="480e8-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="480e8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="480e8-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="480e8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="480e8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="480e8-116">See Also</span></span>  
 [<span data-ttu-id="480e8-117">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="480e8-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="480e8-118">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="480e8-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
