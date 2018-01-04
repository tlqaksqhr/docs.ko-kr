---
title: "ICorRuntimeHost::CurrentDomain 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CurrentDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ac437d924b6f5b290db117260701b554e29b6e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="fb153-102">ICorRuntimeHost::CurrentDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="fb153-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="fb153-103">형식의 인터페이스 포인터를 가져옵니다 <xref:System.AppDomain?displayProperty=nameWithType> 현재 스레드에서 로드 도메인을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="fb153-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb153-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb153-104">Syntax</span></span>  
  
```  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb153-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb153-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fb153-106">[out] 형식의 포인터 <xref:System.AppDomain?displayProperty=nameWithType> 스레드의 현재 응용 프로그램 도메인을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="fb153-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="fb153-107">이 포인터 형식이 `IUnknown`호출자에 게 일반적으로 호출 해야 하므로 `QueryInterface` 형식의 포인터를 가져올 수 <xref:System._AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="fb153-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb153-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="fb153-108">Return Value</span></span>  
  
|<span data-ttu-id="fb153-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb153-109">HRESULT</span></span>|<span data-ttu-id="fb153-110">설명</span><span class="sxs-lookup"><span data-stu-id="fb153-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb153-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb153-111">S_OK</span></span>|<span data-ttu-id="fb153-112">작업이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb153-112">The operation was successful.</span></span>|  
|<span data-ttu-id="fb153-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fb153-113">S_FALSE</span></span>|<span data-ttu-id="fb153-114">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb153-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="fb153-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fb153-115">E_FAIL</span></span>|<span data-ttu-id="fb153-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb153-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="fb153-117">메서드가 E_FAIL을 반환 하는 경우 공용 언어 런타임 (CLR)을 하는 프로세스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb153-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="fb153-118">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb153-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fb153-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fb153-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fb153-120">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb153-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb153-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb153-121">Requirements</span></span>  
 <span data-ttu-id="fb153-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb153-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb153-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb153-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb153-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fb153-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb153-125">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="fb153-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb153-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb153-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="fb153-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb153-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
