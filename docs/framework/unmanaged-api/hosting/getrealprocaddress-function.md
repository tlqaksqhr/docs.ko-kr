---
title: "GetRealProcAddress 함수"
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
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ade1c902d00e991612406041ef0a0b2c1bb884e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="a3aa6-102">GetRealProcAddress 함수</span><span class="sxs-lookup"><span data-stu-id="a3aa6-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="a3aa6-103">공용 언어 런타임 (CLR)의 최신 설치 버전에서 내보낸 지정 된 함수의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa6-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="a3aa6-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa6-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3aa6-105">구문</span><span class="sxs-lookup"><span data-stu-id="a3aa6-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3aa6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3aa6-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="a3aa6-107">[in] 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa6-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="a3aa6-108">[out] 포인터는 함수의 주소를 받는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa6-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3aa6-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="a3aa6-109">Return Value</span></span>  
 <span data-ttu-id="a3aa6-110">이 메서드는 CorError.h에 정의 된 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa6-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="a3aa6-111">반환 코드</span><span class="sxs-lookup"><span data-stu-id="a3aa6-111">Return code</span></span>|<span data-ttu-id="a3aa6-112">설명</span><span class="sxs-lookup"><span data-stu-id="a3aa6-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a3aa6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3aa6-113">S_OK</span></span>|<span data-ttu-id="a3aa6-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa6-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="a3aa6-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a3aa6-115">E_POINTER</span></span>|<span data-ttu-id="a3aa6-116">`ppv`가 잘못된 경우</span><span class="sxs-lookup"><span data-stu-id="a3aa6-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="a3aa6-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="a3aa6-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="a3aa6-118">런타임에 함수를 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa6-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3aa6-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3aa6-119">Requirements</span></span>  
 <span data-ttu-id="a3aa6-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3aa6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3aa6-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a3aa6-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3aa6-122">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3aa6-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3aa6-123">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3aa6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3aa6-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3aa6-124">See Also</span></span>  
 [<span data-ttu-id="a3aa6-125">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="a3aa6-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
