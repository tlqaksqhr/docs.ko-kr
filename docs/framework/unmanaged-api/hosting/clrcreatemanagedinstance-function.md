---
title: "ClrCreateManagedInstance 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: ClrCreateManagedInstance
helpviewer_keywords: ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 64a1bc6bbd89e3a36ac53b322bb246a7e61baa67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="3e9c6-102">ClrCreateManagedInstance 함수</span><span class="sxs-lookup"><span data-stu-id="3e9c6-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="3e9c6-103">지정 된 관리 되는 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e9c6-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="3e9c6-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3e9c6-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="3e9c6-105">관리 되는 형식의 인스턴스를 만드는 COM 정품 인증을 사용 하거나 호스팅을 사용 (참조 [CLR 호스팅 인터페이스에 추가 된.NET Framework 4 및 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="3e9c6-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e9c6-106">구문</span><span class="sxs-lookup"><span data-stu-id="3e9c6-106">Syntax</span></span>  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e9c6-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e9c6-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="3e9c6-108">[in] 요청 되는 인스턴스 형식 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3e9c6-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="3e9c6-109">[in] `IID` 요청 되는 인스턴스 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3e9c6-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="3e9c6-110">[out] 호출자에 의해 요청 된 관리 되는 형식의 인스턴스로에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3e9c6-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e9c6-111">설명</span><span class="sxs-lookup"><span data-stu-id="3e9c6-111">Remarks</span></span>  
 <span data-ttu-id="3e9c6-112">공용 언어 런타임 프로세스에 이미 로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e9c6-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="3e9c6-113">예를 들어에 대 한 호출을 사용 하 여 로드할 수 있습니다는 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 하기 전에 함수는 `ClrCreateManagedInstance` 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e9c6-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="3e9c6-114">런타임이 로드 되지 않은 경우 `ClrCreateManagedInstance` 먼저 런타임 v 1.0.3705를 로드 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e9c6-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="3e9c6-115">실패할 경우 최신 버전의 런타임 로드를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e9c6-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e9c6-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e9c6-116">Requirements</span></span>  
 <span data-ttu-id="3e9c6-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e9c6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e9c6-118">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3e9c6-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e9c6-119">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e9c6-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e9c6-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e9c6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e9c6-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e9c6-121">See Also</span></span>  
 [<span data-ttu-id="3e9c6-122">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="3e9c6-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [<span data-ttu-id="3e9c6-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="3e9c6-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
