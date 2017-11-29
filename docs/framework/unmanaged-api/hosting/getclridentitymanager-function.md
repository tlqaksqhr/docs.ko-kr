---
title: "GetCLRIdentityManager 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCLRIdentityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: GetCLRIdentityManager
helpviewer_keywords: GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ddc0395b6fd659ecd6a26a3132fccc65bbb961fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="c4b5c-102">GetCLRIdentityManager 함수</span><span class="sxs-lookup"><span data-stu-id="c4b5c-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="c4b5c-103">공용 언어 런타임 (CLR) id를 관리할 수 있는 인터페이스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c4b5c-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="c4b5c-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b5c-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b5c-105">구문</span><span class="sxs-lookup"><span data-stu-id="c4b5c-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4b5c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c4b5c-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="c4b5c-107">[in] A `REFIID` 얻으려고 하는 인터페이스를 지정 하는 (인터페이스 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="c4b5c-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="c4b5c-108">이 값은 IID_ICLRAssemblyIdentityManager 또는 IID_ICLRHostBindingPolicyManager 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b5c-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="c4b5c-109">[out] 주소에 대 한 포인터는 [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) 또는 [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c4b5c-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4b5c-110">설명</span><span class="sxs-lookup"><span data-stu-id="c4b5c-110">Remarks</span></span>  
 <span data-ttu-id="c4b5c-111">호출 된 [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) 함수에 대 한 포인터를는 `GetCLRIdentityManager` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c4b5c-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4b5c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4b5c-112">Requirements</span></span>  
 <span data-ttu-id="c4b5c-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b5c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4b5c-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c4b5c-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4b5c-115">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="c4b5c-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="c4b5c-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4b5c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b5c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4b5c-117">See Also</span></span>  
 [<span data-ttu-id="c4b5c-118">사용 되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="c4b5c-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
