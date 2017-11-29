---
title: CLRRuntimeHost Coclass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CLRRuntimeHost
helpviewer_keywords: CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 372b2466baaa76ba47a6710447d93f9fa6bb967f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="5fe42-102">CLRRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="5fe42-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="5fe42-103">런타임에 의해 코드 실행을 관리 하기 위한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe42-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe42-104">구문</span><span class="sxs-lookup"><span data-stu-id="5fe42-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="5fe42-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fe42-105">Interfaces</span></span>  
  
|<span data-ttu-id="5fe42-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fe42-106">Interface</span></span>|<span data-ttu-id="5fe42-107">설명</span><span class="sxs-lookup"><span data-stu-id="5fe42-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="5fe42-108">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fe42-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="5fe42-109">런타임에서 응용 프로그램의 실행을 제어 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe42-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="5fe42-110">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fe42-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="5fe42-111">유효성 검사 오류를 자세히 보고에 대 한 메서드 이식 가능한 실행 이미지의 유효성 검사에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe42-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5fe42-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5fe42-112">Requirements</span></span>  
 <span data-ttu-id="5fe42-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe42-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fe42-114">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="5fe42-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="5fe42-115">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5fe42-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5fe42-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fe42-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fe42-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5fe42-117">See Also</span></span>  
 [<span data-ttu-id="5fe42-118">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="5fe42-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
