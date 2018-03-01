---
title: "ICLRMetaHostPolicy 인터페이스"
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
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd9b8d6aef2289833a0bd192b838e6f70ea8c0ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="1705c-102">ICLRMetaHostPolicy 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1705c-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="1705c-103">제공 된 [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) 메서드, 정책 조건에 따라 공용 언어 런타임 (CLR) 인터페이스에 대 한 포인터를 반환 하는 어셈블리, 버전 및 구성 파일을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1705c-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1705c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1705c-104">Methods</span></span>  
  
|<span data-ttu-id="1705c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1705c-105">Method</span></span>|<span data-ttu-id="1705c-106">설명</span><span class="sxs-lookup"><span data-stu-id="1705c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1705c-107">GetRequestedRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="1705c-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="1705c-108">기본 CLR 인터페이스 정책 조건에 따라, 어셈블리, 버전 및 구성 파일을 관리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1705c-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1705c-109">설명</span><span class="sxs-lookup"><span data-stu-id="1705c-109">Remarks</span></span>  
 <span data-ttu-id="1705c-110">호출 하 여이 인터페이스에 대 한 참조를 가져올 수 있습니다는 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 다음 코드에 나와 있는 것 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1705c-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="1705c-111">이 인터페이스를 로드 하거나 CLR, 하지만 기본 CLR 버전 설치 되거나 로드 된 사용 가능한 버전에 따라 반환 활성화 실제로 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1705c-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="1705c-112">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] API를 호스팅하는 특정 요구 사항이 있는 호스트가 헤드 의도 하지 않은 저하 없이 기본 기능을 사용할 수 있도록 정책을 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1705c-112">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="1705c-113">예를 들어 다양 한 방법으로 MSCorEE.dll 내보내기에 바인딩됩니다 특정 CLR 메서드 수 필요 하지 않지만 논리적으로 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1705c-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="1705c-114">[METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) 열거형은 대부분의 호스트에 공통적으로 적용 하는 바인딩 정책을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1705c-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1705c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1705c-115">Requirements</span></span>  
 <span data-ttu-id="1705c-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1705c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1705c-117">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1705c-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1705c-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1705c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1705c-119">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1705c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1705c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1705c-120">See Also</span></span>  
 [<span data-ttu-id="1705c-121">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1705c-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="1705c-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1705c-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="1705c-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="1705c-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
