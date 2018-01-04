---
title: "CallFunctionShim 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CallFunctionShim
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CallFunctionShim
helpviewer_keywords: CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12c399c876a244d0c27e34b41e08c284d7429bac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="fed0d-102">CallFunctionShim 함수</span><span class="sxs-lookup"><span data-stu-id="fed0d-102">CallFunctionShim Function</span></span>
<span data-ttu-id="fed0d-103">지정된 된 라이브러리에 지정 된 이름 및 매개 변수를 가진 함수를 호출 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="fed0d-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="fed0d-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="fed0d-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed0d-105">구문</span><span class="sxs-lookup"><span data-stu-id="fed0d-105">Syntax</span></span>  
  
```  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fed0d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fed0d-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="fed0d-107">[in] 함수를 포함 하는 라이브러리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fed0d-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="fed0d-108">[in] 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fed0d-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="fed0d-109">[in] 첫 번째 인수는 함수에 전달할입니다.</span><span class="sxs-lookup"><span data-stu-id="fed0d-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="fed0d-110">[in] 두 번째 인수는 함수에 전달할입니다.</span><span class="sxs-lookup"><span data-stu-id="fed0d-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="fed0d-111">[in] 함수가 포함 된 라이브러리의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="fed0d-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="fed0d-112">[in] 나중에 사용할 수는 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed0d-112">[in] Reserved for future use.</span></span> <span data-ttu-id="fed0d-113">이 매개 변수에서 0을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="fed0d-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed0d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fed0d-114">Requirements</span></span>  
 <span data-ttu-id="fed0d-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fed0d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fed0d-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fed0d-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fed0d-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fed0d-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fed0d-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fed0d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed0d-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fed0d-119">See Also</span></span>  
 [<span data-ttu-id="fed0d-120">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="fed0d-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
